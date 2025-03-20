Mock Lambda Test Tooll -> https://github.com/aws/aws-lambda-dotnet/blob/master/Tools/LambdaTestTool/README.md 
- 1.Install Or Update Lambda Test Tool.
    - Install -> dotnet tool install -g amazon.lambda.testtool
    - Update -> dotnet tool update -g amazon.lambda.testtool

- 2.Configure Path and Working Directory based on IDE 
  - Exe path
    - "C:\Users\giorgi\.dotnet\tools\.store\amazon.lambda.testtool-8.0\0.16.2\amazon.lambda.testtool-8.0\0.16.2\tools\net8.0\any\Amazon.Lambda.TestTool.BlazorTester.dll
  - in users folder find .dotnet and find Amazon.Lambda.TestTool.BlazorTester.dll
  - The working directory contains the Lambda functions.
- 3.Assume Role
  - For Team1 use:
     - aws sts assume-role --role-arn arn:aws:iam::761018851832:role/org/DeveloperAccessRoleTeam1 --role-session-name NewSession (Change Arn and RoleName based on team)
  - It will create :
      - AWS_ACCESS_KEY_ID = "yourAccesKey"
      - AWS_SECRET_ACCESS_KEY = "yourAccesKey"
      - AWS_SESSION_TOKEN = "yourSessionToken"
  - save given variables we will need later
  - with powershell set given Environment Variables :
    - $env:AWS_ACCESS_KEY_ID = "yourAccesKey"
    - $Env:AWS_SECRET_ACCESS_KEY = "yourSecretAccessKey"
    - $Env:AWS_SESSION_TOKEN = "yourSessionToken"
- 4.Configure Path and Working Directory based on IDE :
  - Based on your IDE set given variable paths :
    - Set ExePath
      - "C:\Users\giorgi\.dotnet\tools\.store\amazon.lambda.testtool-8.0\0.16.2\amazon.lambda.testtool-8.0\0.16.2\tools\net8.0\any\Amazon.Lambda.TestTool.BlazorTester.dll" 
    - in users folder find .dotnet and find Amazon.Lambda.TestTool.BlazorTester.dll
    - working directory -> directory that contains the Lambda functions.
    - also set Environment Variables That is needed for given lambda
      - Mandatory :
        - AWS_ACCESS_KEY_ID = "yourAccesKey"
        - AWS_SECRET_ACCESS_KEY = "yourSecretAccessKey"
        - AWS_SESSION_TOKEN = "yourSessionToken"
- 5.Syndicate.yml config
  - in Syndicate.yml file set variables from step-3
      - AWS_ACCESS_KEY_ID = "yourAccesKey"
      - AWS_SECRET_ACCESS_KEY = "yourSecretAccessKey"
      - AWS_SESSION_TOKEN = "yourSessionToken"
   
        
  ![image](https://github.com/user-attachments/assets/64ca545f-e698-4281-8f90-d40d09b1a5ba)

- 6.Use Local Variables + separate testRepository with implemented logic
   ![image](https://github.com/user-attachments/assets/add4ee41-4f01-4bed-bb60-f13cd0b08580)

- To use syndicate clean , build or deploy you must change yndicate.yml with new data from aws creds
