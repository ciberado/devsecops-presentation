```
STACK_ID=$(aws cloudformation create-stack \
  --stack-name vpc-$USER \
  --template-body file://create-vpc.yaml \
  --parameters \
    ParameterKey=Owner,ParameterValue=$USER \
    ParameterKey=ClassB,ParameterValue=0 \
  --query StackId \
  --output text)

echo Your Stack ID is $STACK_ID.

wget https://raw.githubusercontent.com/alestic/aws-cloudformation-stack-status/master/aws-cloudformation-stack-status
chmod +x aws-cloudformation-stack-status
sudo mv aws-cloudformation-stack-status /usr/local/bin/


aws-cloudformation-stack-status --watch --stack-name $STACK_ID

aws cloudformation describe-stacks \
  --stack-name $STACK_ID \
  --query "Stacks[0].Outputs" \
  --output table

aws ec2 describe-vpcs \
  --output text \
  --query 'Vpcs[*].{VpcId:VpcId,Name:Tags[?Key==`Name`].Value|[0],CidrBlock:CidrBlock}' \
  --output table
```
