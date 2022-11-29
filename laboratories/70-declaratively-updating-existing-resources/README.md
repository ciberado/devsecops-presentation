```
sed -i "s/80/443/g" create-vpc.yaml

CHANGE_SET_ID=$(aws cloudformation create-change-set \
    --stack-name $STACK_ID \
    --change-set-name ${vpc-$USER}-cs-1 \
    --template-body file://create-vpc.yaml \
    --parameters \
      ParameterKey=Owner,ParameterValue=$USER \
      ParameterKey=ClassB,ParameterValue=0 \
    --query Id \
    --output text)
echo The changeset is $CHANGE_SET_ID.

aws cloudformation describe-change-set \
    --change-set-name ${vpc-$USER}-cs-1 \
    --stack-name $STACK_ID

aws cloudformation describe-change-set \
  --change-set-name ${vpc-$USER}-cs-1 \
  --stack-name $STACK_ID \
  --query "Changes[].ResourceChange.{Id: LogicalResourceId, Action: Action}" \
  --output table

aws cloudformation execute-change-set \
    --change-set-name ${vpc-$USER}-cs-1 \
    --stack-name $STACK_ID


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