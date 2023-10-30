## CloudFormation Error
---
### 1. 같은 이름의 CF Stack이 존재할 경우
```
ex) test라는 stack이 존재하는 경우
Error message - An error occurred (AlreadyExistsException) when calling the CreateStack operation: Stack [test] already exists
```

### 2. CF yaml에 Resources Secsion이 정의가 되어있지 않은 경우
```
Error message - An error occurred (ValidationError) when calling the CreateStack operation: Invalid template parameter property 'Properties'
```

### 3. IAM을 생성 할 때 명령어에 "--capabilities CAPABILITY_NAMED_IAM"를 추가를 안해줬을 경우
```
Error message - An error occurred (InsufficientCapabilitiesException) when calling the CreateStack operation: Requires capabilities : [CAPABILITY_NAMED_IAM]
```

### 4. 주석이 있는 경우
```
Error parsing parameter '--template-body': Unable to load paramfile (C:\Users\user\Desktop\kinesis\kinesis-Provis.yaml), text contents could not be decoded.  If this is a binary file, please use the fileb:// prefix instead of the file:// prefix.
```

### 5. CloudFormation 형식이 잘못되었을 경우
```
Properties validation failed for resource LambdaFunction with message: #/Role: failed validation constraint for keyword [pattern]
```