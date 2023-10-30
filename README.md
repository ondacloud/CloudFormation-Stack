# CloudFormation-Stack

## Create Stack
```
aws cloudformation create-stack --stack-name <stack name> --region <region> --template-body file://<path>
```

## Create Stack on IAM Role
```
aws cloudformation create-stack --stack-name <stack name> --region <region> --template-body file://<path> --capabilities CAPABILITY_NAMED_IAM
```

## Deploy Stack
```
aws cloudformation deploy --stack-name <stack name> --region <region> --template-file <path>
```

## Delete Stack
```
aws cloudformation delete-stack --stack-name <stack name> --region <region>
```

## Validate template
```
aws cloudformation validate-template --region <region> --template-body file://<path>
```

## Update Stack
```
aws cloudformation update-template --region <region> --template-body file://<path>
```

## Sample Code Templates Link
```
https://docs.aws.amazon.com/ko_kr/AWSCloudFormation/latest/UserGuide/CHAP_TemplateQuickRef.html
```