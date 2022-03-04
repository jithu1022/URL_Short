**STEPS TO CREATE URL SHORTENER**

1. Create database using dynamoDB with Primary key as shortid
2. Create a Lambda function with dynamoDB WRITE permission(PutItem) and connect the database using the ARN of the database. 
3. Add the function which accepts longURL as the event and which also puts the longURL into the database and returns the shortURL(Shortener.js).
4. Create an API Gateway and connect it to the Lambda function just created and also to accept the longURL as the input paramater.
5. Create another Lambda function with dynamoDB READ permission(GetItem) and connect the database using the ARN of the database.
6. Add the function which accepts shortid as the event and which also gets the longURL from the database using the shortid. And also add the redirection code. (getLongUrl.js).
7. Create an API Gateway and connect it to the Lambda function just created and also to accept the shortid as the input paramater.
8. Configure the API Gateway to perform a redirect(code: 302).
    Reference: https://aws.amazon.com/blogs/compute/redirection-in-a-serverless-api-with-aws-lambda-and-amazon-api-gateway/ 
    
    
    
