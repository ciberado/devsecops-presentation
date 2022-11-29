```
cat << EOF > pokemon.sh
#!/bin/sh
 
sudo apt update
sudo apt install openjdk-8-jre-headless -y
wget https://github.com/ciberado/pokemon/releases/download/stress/pokemon-0.0.4-SNAPSHOT.jar
java -jar pokemon-0.0.4-SNAPSHOT.jar
EOF

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