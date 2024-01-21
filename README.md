# EC2 Instance Scheduler Lambda Function

This Lambda function is designed to automatically start and stop EC2 instances based on a predefined schedule. The schedule, in this case, is set to start instances at 5 AM and stop them at 11 PM.


## Usage

### Deploying the Lambda Function

1. **Create an AWS Lambda function:**
   - [Follow the AWS Lambda documentation](https://docs.aws.amazon.com/lambda/latest/dg/getting-started.html)

2. **Enter your code directly or Upload the ZIP file containing your Lambda function code.**

3. **Set up an IAM role for your Lambda function:**
   - Ensure the IAM role has the necessary permissions to interact with EC2 instances.

### CloudWatch Events

To trigger the Lambda function at specific intervals, set up a CloudWatch Events rule.

1. Open the AWS Management Console and navigate to the CloudWatch service.

2. In the left sidebar, choose "Rules" under "Events."

3. Create a new rule with the following settings:
    - **Event Source:** `Event Source Type > Event Source`
    - **Service Name:** `Event Source Type > Event Type`
    - **Targets:** Add the Lambda function you created earlier.

4. Configure the schedule expression based on your requirements. For example, to trigger the function every hour:

    ```plaintext
    cron(0 * * * ? *)
    ```

### Monitoring

You can monitor the execution of your Lambda function through CloudWatch Logs. Check the Lambda function's logs for any errors or unexpected behavior.

## Acknowledgments

- [Boto3 Documentation](https://boto3.amazonaws.com/v1/documentation/api/latest/index.html)
