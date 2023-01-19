```
export AWS_DEFAULT_REGION=eu-west-1

aws ec2 describe-security-groups | jq

aws ec2 describe-security-groups | jq -C | less -R

aws ec2 describe-security-groups \
    --filters Name=ip-permission.from-port,Values=22 Name=ip-permission.to-port,Values=22 Name=ip-permission.cidr,Values='0.0.0.0/0' \
    | jq -C | less -R

aws ec2 describe-security-groups \
    --filters Name=ip-permission.from-port,Values=22 Name=ip-permission.to-port,Values=22 Name=ip-permission.cidr,Values='0.0.0.0/0' \
    --query "SecurityGroups[*].[GroupName]" \
    --output text

aws ec2 describe-vpcs

aws ec2 describe-vpcs --filters "Name=is-default,Values=true"

ec2 describe-vpcs --filters "Name=is-default,Values=true" --query Vpcs[0].VpcId

aws ec2 describe-vpcs --filters "Name=is-default,Values=true" --query Vpcs[0].VpcId --output text

DEFAULT_VPC=$(aws ec2 describe-vpcs --filters "Name=is-default,Values=true" --query Vpcs[0].VpcId --output text)
echo The default VPC is $DEFAULT_VPC


aws ec2 describe-security-groups \
  --filter Name=vpc-id,Values=$DEFAULT_VPC \
  Name=group-name,Values=web \
  --query 'SecurityGroups[*].[GroupId]' \
  --output text

WEB_SG_ID=$(aws ec2 describe-security-groups \
  --filter Name=vpc-id,Values=$DEFAULT_VPC \
  Name=group-name,Values=web \
  --query 'SecurityGroups[*].[GroupId]' \
  --output text)
echo The ID of the security group Web is $WEB_SG_ID.


SELECTED_SUBNET=$(aws ec2 describe-subnets \
  --filters "Name=vpc-id,Values=$DEFAULT_VPC" \
  --query Subnets[0].SubnetId --output text)
echo The selected subnet is $SELECTED_SUBNET

```
