# Dormant Lambda Checker

`dormant-lambda-checker.py` is a Python script designed to help identify AWS Lambda functions that have not been invoked within a specified time frame. This can assist in identifying potentially dormant, unused, or legacy Lambda functions, allowing you to clean up or manage your AWS resources efficiently.

---

## Use Case
The Dormant Lambda Checker is ideal for:
- **Identifying unused resources**: Find Lambda functions that haven't been invoked recently and may no longer be needed.
- **Cost optimization**: Detect dormant Lambda functions to reduce unnecessary costs.
- **Operational management**: Maintain visibility over function usage in multiple AWS regions.
- **Audit and compliance**: Ensure Lambda functions are actively used and maintained.

---

## How to Use
1. **Prerequisites**:
   - Install Python 3.x and the AWS SDK for Python (`boto3`).
   - Ensure AWS credentials are configured (e.g., using `aws configure`).

2. **Setup**:
   - Clone or download the script `dormant-lambda-checker.py`.
   - Open the script and update the `region_list` variable to include the AWS regions you want to check.

3. **Run the Script**:
   - Execute the script in your terminal:
     ```bash
     python dormant-lambda-checker.py
     ```
   - When prompted, enter the number of days to look back for Lambda invocations. Press Enter to use the default value (30 days).

4. **Output**:
   - The script displays a table with:
     - **FunctionName**: The name of each Lambda function.
     - **FirstInvocationTime**: The timestamp of the earliest invocation found within the lookback period, or a message if no invocations were found.
     - **Region**: The AWS region where the function is deployed.

---

## Permissions Required
To run the Dormant Lambda Checker, the following AWS permissions are required:
- **Lambda Permissions**:
  - `lambda:ListFunctions` (to list all Lambda functions in the region).
- **CloudWatch Logs Permissions**:
  - `logs:FilterLogEvents` (to search for invocation logs in CloudWatch Logs).
  - `logs:DescribeLogGroups` (to locate the log groups associated with Lambda functions).

Ensure these permissions are included in the IAM role or user account running the script.

---

## Feedback
I welcome feedback to improve the Dormant Lambda Checker! If you encounter issues or have feature requests, open an issue or submit a pull request on the repository.

