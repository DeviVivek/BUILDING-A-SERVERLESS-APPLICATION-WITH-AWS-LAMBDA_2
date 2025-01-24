# Internship Details

**Name:** CH DEVI VIVEK  
**Company:** CODTECH IT SOLUTIONS  
**ID:** CT4MECQ  
**Domain:** Cloud Computing  
**Duration:** 17 Dec 2024 to 17 Apr 2025  
**Mentor:** Neela Santhosh Kumar


# Building a Serverless Application with AWS Lambda

This project demonstrates how to create and deploy a basic serverless application using **AWS Lambda** and **Amazon API Gateway**. The application processes HTTP requests and returns a simple JSON response. Monitoring and troubleshooting are performed using **Amazon CloudWatch**.

---

## Steps to Build the Application

### 1. Create a Lambda Function
1. Navigate to the [AWS Lambda Console](https://aws.amazon.com/lambda/).
![Screenshot 2025-01-24 164630](https://github.com/user-attachments/assets/2fac5d2b-7067-4617-99df-664865ed88fb)
2. Click **Create Function** and choose:
![Screenshot 2025-01-24 164708](https://github.com/user-attachments/assets/c3b71bef-fd62-4a1a-a56a-e2734f1146a2)
   - **Author from scratch**
   - Function name: `MyBasicLambda`
   - Runtime: `Node.js 18.x`
![Screenshot 2025-01-24 164739](https://github.com/user-attachments/assets/d5a54227-c6db-444f-877b-2d0c137c07a4)
3. Select **Create a new role with basic Lambda permissions**. 
4. Write the following code in the inline editor:
   ```javascript
   exports.handler = async (event) => {
       const response = {
           statusCode: 200,
           body: JSON.stringify({
               message: "Hello, World! Your serverless app is live.",
           }),
       };
       return response;
   };
   ```
   ![Screenshot 2025-01-24 164950](https://github.com/user-attachments/assets/d0cc74c7-1f68-48f0-bc6a-5efd584986ca)
5. Save and deploy the function.


### 2. Create an API Gateway Trigger
1. Navigate to the **Configuration** tab of your Lambda function.
![Screenshot 2025-01-24 165121](https://github.com/user-attachments/assets/fda0817c-0368-4491-bb38-2393a3bd4206)
2. Click **Add trigger** and select **API Gateway**.
![Screenshot 2025-01-24 165139](https://github.com/user-attachments/assets/aaf1b9ae-3261-4d14-b79a-7495646b41ca)
3. Configure the trigger:
   - **API type**: HTTP API
   - **Security**: Open (for public access)
![Screenshot 2025-01-24 165218](https://github.com/user-attachments/assets/2f0bcc4a-c200-4480-8e36-434d7184ef38)
4. Deploy the API and note the endpoint URL.

---

### 3. Test the Lambda Function
1. Access the **API Gateway endpoint** in a browser or with a tool like Postman:
   ```
   https://<your-api-endpoint>.amazonaws.com/
   ```
2. You should see the following JSON response:
   ```json
   {
       "message": "Hello, World! Your serverless app is live."
   }
   ```
![Screenshot 2025-01-24 165315](https://github.com/user-attachments/assets/e7387244-0f48-4314-86b5-f4735f34e11c)

---

## Monitoring and Logs

Use **Amazon CloudWatch** to view logs and monitor your Lambda function:
1. Navigate to the **CloudWatch Console** > **Logs**.
2. Select your Lambda function's log group.
3. Review the logs for insights into execution details and errors.

---

## Benefits of Using AWS Lambda
- **Cost-Effective**: Pay only for the compute time used.
- **Scalable**: Automatically handles thousands of concurrent requests.
- **Fully Managed**: No need to manage or provision servers.

---

## Troubleshooting

### Common Issues
1. **403 Forbidden on API Gateway**:
   - Ensure the API Gateway is deployed and the URL is correct.
2. **Lambda Execution Role Issues**:
   - Verify that your IAM role has permissions for CloudWatch logs and API Gateway execution.

---

## Resources
- [AWS Lambda Documentation](https://docs.aws.amazon.com/lambda/latest/dg/welcome.html)
- [Amazon API Gateway Documentation](https://docs.aws.amazon.com/apigateway/latest/developerguide/welcome.html)
- [AWS Free Tier](https://aws.amazon.com/free/)

---

## Project Goals
- Learn how to create and deploy a basic serverless application with AWS Lambda.
- Set up **Amazon API Gateway** to trigger Lambda functions.
- Monitor and troubleshoot Lambda functions with **Amazon CloudWatch**.

---

## License
This project is open-source and available under the [MIT License](LICENSE).
