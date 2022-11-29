```
wget https://gist.githubusercontent.com/ciberado/2069aa77a0d8d51af426b29b60cb842a/raw/9f8d9cf44e41f9c8f90aa8e6f55c0b3c274ff8b9/create-vpc.yaml

aws cloudformation validate-template --template-body file://create-vpc.yaml

sudo apt install ruby-full
sudo gem install cfn-nag

cfn_nag_scan --version
cfn_nag_scan --input-path create-vpc.yaml | less -R

cfn_nag_scan \
  --output-format json \
  --input-path create-vpc.yaml \
  | jq ".[].file_results.violations[].message"

  
LOCAL_IP=$(curl -s https://httpbin.org/ip | jq .origin -r)
echo Your local IP is $LOCAL_IP

sed -i "0,/CidrIp: 0.0.0.0/{s/CidrIp: 0.0.0.0\/0/CidrIp: $LOCAL_IP\/32/}" create-vpc.yaml

cfn_nag_scan \
  --output-format json \
  --input-path create-vpc.yaml \
  | jq ".[].file_results.violations[].message"
  


# https://serverlessrepo.aws.amazon.com/applications/us-east-1/275155842945/cfn-nag-pipeline

# https://stelligent.com/2018/07/23/screencast-continuous-delivery-for-machine-learning-with-aws-codepipeline-and-amazon-sagemaker/

```