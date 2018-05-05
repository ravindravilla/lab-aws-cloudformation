# SAM Local - How To Guide

### Documentation: https://github.com/awslabs/aws-sam-local

### To Test Lambda Function Locally

##### Prerequisites 
    - Install SAM Local (follow the installation instructions from above github link)
    - Install Docker in your machine

##### Commands:
- To validate SAM template

    `sam validate`
    
- To invoke Lambda function with a sample event
 
    `sam local invoke -e event.json HelloWorld`

- To Package Lambda function

    `sam package --template-file template.yaml --s3-bucket [BUCKET-NAME] --output-template-file packaged-template.yaml`
    
- To Deploy Lambda function

    `sam deploy --template-file packaged-template.yaml --stack-name [STACK-NAME] --profile [PROFILE] --region [REGION] --capabilities CAPABILITY_IAM`
    
    Ex:
    `sam deploy --template-file packaged-template.yaml --stack-name lambda-sam-stack --profile aws-qa --region us-west-1 --capabilities CAPABILITY_IAM`