## CloudFormation Option

### DeletionPolicy
**DeletionPolicy란?**
Stack 삭제 시 Policy가 삭제되는 것을 막을 수 있습니다.

ex)
```yaml
AWSTemplateFormatVersion: '2010-09-09'
Resources:
  myS3Bucket:
    Type: AWS::S3::Bucket
    DeletionPolicy: Retain
```
S3 Bucket에 대한 Stack이 삭제되어도 S3 Bucket에대한 Policy 및 Role이 그대로 유지됩니다.

---

<br>

### DependsOn
**DependsOnf란?**
리소스 생성의 우선권을 부여할 수 있습니다.

Ex)
```yaml
AWSTemplateFormatVersion: '2010-09-09'
Mappings:
  RegionMap:
    us-east-1:
      AMI: ami-0ff8a91507f77f867
    us-west-1:
      AMI: ami-0bdb828fd58c52235
    eu-west-1:
      AMI: ami-047bb4163c506cd98
    ap-northeast-1:
      AMI: ami-06cd52961ce9f0d85
    ap-southeast-1:
      AMI: ami-08569b978cc4dfa10
Resources:
  EC2Instance:
    Type: AWS::EC2::Instance
    Properties:
      ImageId:
        Fn::FindInMap:
        - RegionMap
        - Ref: AWS::Region
        - AMI
    DependsOn: DataBase
  DataBase:
    Type: AWS::RDS::DBInstance
    Properties:
      AllocatedStorage: '5'
      DBInstanceClass: db.t2.small
      Engine: MySQL
      EngineVersion: '5.5'
      MasterUsername: MyName
      MasterUserPassword: MyPassword
```
EC2Instance와 DataBase Secsion 중 DataBase Secstion을 먼저 생성합니다.
