```
wget https://gist.githubusercontent.com/ciberado/7966a80fb7e5ad53648a6e03b741581d/raw/3546624bcc846c02838fcc6bd0d26d6ea843564e/create-vpc.sh

bash create-vpc.sh $USER

aws ec2 describe-vpcs \
    --filters "Name=tag:Name,Values=pokemon-$USER" \
    --query "Vpcs[*].VpcId" \
    --output table
```