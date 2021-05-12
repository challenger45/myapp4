# AWS CloudFormation Template Example

### 1. Node Application on EC2 Instance

### 2. MySQL Engine of RDS Instance

### 3. Object Store on S3 

### 4. AWS::CloudFormation::Init Metadata Configuration on aws-cfn-bootstrap
#### 1. packages: yum install
#### 2. sources: tarball download from github's repository
#### 3. files
1. redhat SysV init scripts
2. db.env of mysql connection credential & Sequelize ORM Configuration
3. store.env of S3 Configuration
#### 4. commands: npm install
#### 5. services: sysvinit enable and start

### 5. Deployment: Creating Stack
```bash
$ aws cloudformation create-stack --stack-name myapp /
--template-body https://raw.githubusercontent.com/aws-bitacademy/aws-practices/master/ch06/02/ex01.json /
--parameters ParameterKey=KeyName,ParameterValue={yourSSHkeyName} /
ParameterKey=VPC,ParameterValue={yourVPCId} /
ParameterKey=InstanceType,ParameterValue=t2.micro /
ParameterKey=DBName,ParameterValue=myapp / 
ParameterKey=DBUserName,ParameterValue=myapp /
ParameterKey=DBUserPassword,ParameterValue={password}
```