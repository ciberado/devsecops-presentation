```
cat create-vpc.sh | grep -n "0.0.0.0/0"

LOCAL_IP=$(curl -s https://httpbin.org/ip | jq .origin -r)
echo Your local IP is $LOCAL_IP

sed -i "s/0.0.0.0\/0/$LOCAL_IP\/32/g" create-vpc.sh
cat create-vpc.sh | grep -n "0.0.0.0/0"

bash create-vpc.sh $USER
```