# Document for DoorDash Processing Project

## Project Overview

This project involves creating an automated AWS-based solution for processing daily delivery data from DoorDash. JSON files containing delivery records will be uploaded to an Amazon S3 bucket (landing bucket). An AWS Lambda function, triggered by the file upload, will filter the records based on delivery status and save the filtered data to another S3 bucket (target bucket). Notifications regarding the processing outcome will be sent via Amazon SNS.

## Implementation Steps

1. **Lambda Function Development**: Created a `lambda_function.py` file to implement the filtering logic as per requirements.

2. **Requirements Specification**: Created a `requirements.txt` file listing the necessary libraries, such as pandas, required for the Lambda function.

3. **Build Specification**: Developed a `buildspec.yml` file outlining the commands to be executed by AWS CodeBuild for building and deploying the Lambda function.

4. **Version Control Management**: Push all project files to a test branch in a GitHub repository and merge them into the main branch after testing.

5. **AWS Services Setup**:
   - **AWS Account**: Ensure access to necessary AWS services.
   - **Amazon S3 Buckets**: Create `doordash-landing-zn` and `doordash-target-zn` buckets for storing incoming and processed data respectively.
   - **AWS Lambda**: Set up a Lambda function triggered by file uploads to the landing bucket.
   - **Amazon SNS**: Configure SNS for sending notifications.
   - **AWS IAM**: Define necessary permissions for Lambda function to access S3 buckets and SNS.

6. **Continuous Integration/Continuous Deployment (CI/CD)**:
   - Configure AWS CodeBuild to automate the build and deployment process.
   - Add the GitHub repository and the `buildspec.yml` file to the CodeBuild configuration.
   - Execute the CodeBuild process, ensuring successful deployment of the Lambda function.

7. **Testing**: Upload sample JSON files (daily delivery data) to the landing bucket to trigger the Lambda function. Verify that the filtered data is correctly saved to the target bucket.

8. **Notification Setup**: Subscribe to SNS notifications to receive email notifications about the processing outcome.

## AWS Tools Used

- **AWS Account**
- **Amazon S3 Buckets**: `doordash-landing-zn` and `doordash-target-zn`
- **AWS Lambda**
- **Amazon SNS**
- **AWS IAM**
- **AWS CodeBuild**
- **GitHub**
- **Python, pandas library**
- **Email Subscription for SNS Notifications**

By following these steps and utilizing the specified AWS tools, the DoorDash processing project can be successfully implemented, ensuring efficient handling of daily delivery data with automated filtering and notifications.
