# Instructions 

## Create IAM key for AWS access

- create AWS IAM access key with programmatic access
- Provide permissions AmazonEC2FullAccess and AmazonVPCFULLACCESS

## Install aws cli, python3 and boto 3

- download and install aws cli on ansible controller
~~~bash
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
~~~

- install python3  - https://www.python.org/downloads/

- install boto3
~~~bash
sudo pip3 install boto3
~~~

## Setup IAM key on ansible controller

~~~bash
aws configure
AWS Access Key: ****************
AWS Secret Access Key: ***********
Default region name: ap-southeast-2
Default output format: json
~~~
This will set up the aws profile on ansible controller under default profile.


## Post Build

Run the following commands for execution
~~~bash
ansible-lint site.yml
ansible-galaxy collection install -r collections/requirements.yml
ansible-playbook -i inventory/aws_ec2.yml site.yml
~~~~

Launch URL 
- http://<publicip1>
- http://<publicip2>

Note: https URL may not work due to self-signed certificate
