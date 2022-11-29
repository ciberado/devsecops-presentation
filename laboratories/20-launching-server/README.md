```
wget https://gist.githubusercontent.com/ciberado/3196cbcf568001dd0e8fedc6214a18d0/raw/a7581270061f9a234a339ce00fc8250388aa0dfc/pokemon.sh

# See https://cloud-images.ubuntu.com/locator/

aws ec2 run-instances \
    --subnet-id $SELECTED_SUBNET \
    --image-id ami-020fc399c31009b50 \
    --security-group-ids $WEB_SG_ID  \
    --instance-type t3.micro \
    --block-device-mapping DeviceName=/dev/sda1,Ebs={VolumeSize=8} \
    --tag-specifications \
       "ResourceType=instance,Tags=[{Key=Name,Value=pokemon},{Key=Owner,Value=$USER}]" \
    --user-data file://pokemon.sh 

INSTANCE_IP=$(aws ec2 describe-instances \
    --filters "Name=tag:Owner,Values=$USER" \
    --query "Reservations[*].Instances[*].PublicIpAddress" \
    --output text)
echo Visit http://$INSTANCE_IP:8080 to meet your pokemon

```
