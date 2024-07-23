# Setup Instructions

## Follow these steps to configure your environment before running the code in the program.

[Setup Video]([https://youtu.be/153BboqWh-U](https://youtu.be/153BboqWh-U))

## Instructions

1. Fork the program's [GitHub Repository](https://github.com/svpino/ml.school) and clone it on your local computer.
2. Create and activate a virtual environment:
    
    $ python3 -m venv .venv 
    
    $ source .venv/bin/activate
    
3. Once the virtual environment is active, you can update `pip` and install the libraries in the `requirements.txt` file:
    
    $ python3 -m pip install --upgrade pip
    
    $ pip install -r requirements.txt
    
4. Install [Docker](https://docs.docker.com/). You'll find installation instructions on their site for your particular environment. After you install it, you can verify Docker is running using the following command:
    
    $ docker ps
    

At this point you can open the project using Visual Studio Code or your favorite IDE. Make sure you point the Jupyter kernel to the virtual environment that you created before.

## Setting up Comet

[Comet](https://www.comet.com/signup?utm_source=svpino_course&utm_medium=partner&utm_content=github) is a cloud-based machine learning platform that allows us to automatically track and version experiments.

1. Create a free [Comet account](https://www.comet.com/signup?utm_source=svpino_course&utm_medium=partner&utm_content=github) using either your email address or GitHub credentials.
2. Once inside Comet, create a new project of type "Experiment Tracking".
3. Get your Comet API Key. Check [Comet's quick start guide](https://www.comet.com/docs/v2/guides/getting-started/quickstart/) for information about where to find your API key.
4. Create an `.env` file in the root directory of your local repository and add the following environment variables to it. Make sure you replace the value of each variable with the correct value:
    
    COMET_API_KEY=[YOUR COMET API KEY]
    
    COMET_PROJECT_NAME=[YOUR COMET PROJECT NAME]
    

## Configuring AWS

1. Create a new AWS account. You can indicate the account is for personal use and you intend to use it for Machine Learning work.
2. Using the root user account, create a new user with the `AdministratorAccess` policy attached to it. Make sure this new user has access to the console and create an access key for it under the Security Credentials section.
3. [Install the AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) on your computer and [configure it](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html) with your Access Key and Secret Access Key.
4. After you finish configuring the AWS CLI, create a new S3 bucket where we will store the data and every resource we are going to create during the program. The name of the bucket must be unique:
    
    $ aws s3api create-bucket --bucket [YOUR-BUCKET-NAME]
    
    If you want to create a bucket in a region other than **us-east-1**, you need to use the`--create-bucket-configuration` argument to specify your `LocationConstraint`. See the example below:
    
    $ aws s3api create-bucket --bucket [YOUR-BUCKET-NAME] \
    
        --create-bucket-configuration LocationConstraint="eu-west-1"
    
5. Upload the dataset to the S3 bucket you just created by running the following command from the root directory of the project:
    
    $ aws s3 cp program/penguins.csv \
    
        s3://[YOUR-BUCKET-NAME]/penguins/data/data.csv
    
6. Add a new environment variable `BUCKET` to the `.env` file and set it to the name of the S3 bucket you just created:
    
    BUCKET=[YOUR BUCKET NAME]
    
7. We'll need access to `ml.m5.xlarge` instances to run some of the processes we'll implement. By default, the quota for most new accounts is zero, so you'll need to request a quota increase. You can do this in your AWS account under Service Quotas > AWS Services > Amazon SageMaker. Find `ml.m5.xlarge` and request a quota increase for processing jobs, training jobs, transform jobs, and endpoint usage. Ask for a minimum of 3 instances.

## Configuring SageMaker

1. Log into the [AWS console](https://aws.amazon.com/console/) using the user you created.
2. Open the SageMaker service and create a [SageMaker domain](https://docs.aws.amazon.com/sagemaker/latest/dg/gs-studio-onboard.html). It will take SageMaker a few minutes to set up the new domain.
3. After the domain comes online, run the following command to return the Domain Id and the User Profile Name of your SageMaker domain. You can also get these values directly from the console.
    
    $ aws sagemaker list-user-profiles \
    
        | grep -E '"DomainId"|"UserProfileName"' \
    
        | awk -F'[:,"]+' '{print $2":"$3 $4 $5}'
    
4. Use the `DomainId` and the `UserProfileName` from the response and replace them in the following command that we'll return the execution role attached to the domain:
    
    $ aws sagemaker describe-user-profile \
    
        --domain-id [YOUR-DOMAIN-ID] \
    
        --user-profile-name [YOUR-USER-PROFILE-NAME] \
    
        | grep -E "ExecutionRole" | awk -F'["]' '{print $2": "$4}'
    
5. Create a new environment variable in the the `.env` file and set its value to the Execution Role:
    
    ROLE=[YOUR EXECUTION ROLE]
    
6. Open the Amazon IAM service, go to the list of Roles, and find the `AmazonSageMaker-ExecutionRole`attached to the SageMaker domain. Under Permission Policies, click on the custom `AmazonSageMaker-ExecutionPolicy-` assigned to the role. Edit its permissions and replace them with the JSON below. These permissions will give the Execution Role access to the resources we'll use during the program:
    
    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Sid": "IAM0",
                "Effect": "Allow",
                "Action": [
                    "iam:CreateServiceLinkedRole"
                ],
                "Resource": "*",
                "Condition": {
                    "StringEquals": {
                        "iam:AWSServiceName": [
                            "autoscaling.amazonaws.com",
                            "ec2scheduled.amazonaws.com",
                            "elasticloadbalancing.amazonaws.com",
                            "spot.amazonaws.com",
                            "spotfleet.amazonaws.com",
                            "transitgateway.amazonaws.com"
                        ]
                    }
                }
            },
            {
                "Sid": "IAM1",
                "Effect": "Allow",
                "Action": [
                    "iam:CreateRole",
                    "iam:DeleteRole",
                    "iam:PassRole",
                    "iam:AttachRolePolicy",
                    "iam:DetachRolePolicy",
                    "iam:CreatePolicy"
                ],
                "Resource": "*"
            },
            {
                "Sid": "Lambda",
                "Effect": "Allow",
                "Action": [
                    "lambda:CreateFunction",
                    "lambda:DeleteFunction",
                    "lambda:InvokeFunctionUrl",
                    "lambda:InvokeFunction",
                    "lambda:UpdateFunctionCode",
                    "lambda:InvokeAsync",
                    "lambda:AddPermission",
                    "lambda:RemovePermission"
                ],
                "Resource": "*"
            },
            {
                "Sid": "SageMaker",
                "Effect": "Allow",
                "Action": [
                    "sagemaker:UpdateDomain",
                    "sagemaker:UpdateUserProfile"
                ],
                "Resource": "*"
            },
            {
                "Sid": "CloudWatch",
                "Effect": "Allow",
                "Action": [
                    "cloudwatch:PutMetricData",
                    "cloudwatch:GetMetricData",
                    "cloudwatch:DescribeAlarmsForMetric",
                    "logs:CreateLogStream",
                    "logs:PutLogEvents",
                    "logs:CreateLogGroup",
                    "logs:DescribeLogStreams"
                ],
                "Resource": "*"
            },
            {
                "Sid": "ECR",
                "Effect": "Allow",
                "Action": [
                    "ecr:GetAuthorizationToken",
                    "ecr:BatchCheckLayerAvailability",
                    "ecr:GetDownloadUrlForLayer",
                    "ecr:BatchGetImage"
                ],
                "Resource": "*"
            },
            {
                "Sid": "S3",
                "Effect": "Allow",
                "Action": [
                    "s3:CreateBucket",
                    "s3:ListBucket",
                    "s3:GetBucketLocation",
                    "s3:PutObject",
                    "s3:GetObject",
                    "s3:DeleteObject"
                ],
                "Resource": "arn:aws:s3:::*"
            },
            {
                "Sid": "EventBridge",
                "Effect": "Allow",
                "Action": [
                    "events:PutRule",
                    "events:PutTargets"
                ],
                "Resource": "*"
            }
        ]
    }
    
7. Finally, find the Trust relationships section under the same Execution Role, edit its configuration, and replace it with the JSON below:
    
    {
        "Version": "2012-10-17",
        "Statement": [
            {
                "Effect": "Allow",
                "Principal": {
                    "Service": [
                        "sagemaker.amazonaws.com",
                        "events.amazonaws.com"
                    ]
                },
                "Action": "sts:AssumeRole"
            }
        ]
    }
    

## Apple Silicon

If you are running the program on Apple Silicon, you'll need to build a TensorFlow Docker image to run some of the pipeline components on your local computer. SageMaker doesn't provide out-of-the-box TensorFlow images compatible with Apple Silicon, and that's why we need this custom Docker image.

You can build the image running the following command:

$ docker build -t sagemaker-tensorflow-toolkit-local container/.

After building this Docker image, the notebook will automatically use it when running the pipeline in Local Mode.

Copyright © 2024 Tideily LLC

All rights reserved.