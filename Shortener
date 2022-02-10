const AWS = require("aws-sdk");
const dynamodb = new AWS.DynamoDB();


exports.handler = async (event, context, callback) => {
  const longURL = event.longURL;
  const shortURL =Math.random().toString(16).substr(2, 6);
  if (longURL){
  return dynamodb
    .putItem({
      TableName: "URL_Shortener",
      Item: {
        shortid: { S: shortURL },
        longURL: { S: longURL },
        owner: { S: "owner" }
      }
    })
    .promise()
    .then(data => {
      console.log("response post create", data);
      return 'domain.com/'+ shortURL
    })
    .catch(err => {
      console.error("error", err);
      return err;
    });
}};
