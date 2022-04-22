# GitHub Actions Deep Dive

A simple Lambda function that can be deployed via a GitHub Actions Workflow.

# A Cloud Guru AWS Playground Setup
Some of the lab content needs corresponding AWS contstructs to work and since the playgrounds are ephemeral you may need to set them up after a playground environment expiration:

1. Create an AWS Playground.
2. Create an S3 bucket and store the name in secrets as `AWS_S3_BUCKET`.
3. Create a `User` name `github-actions-user` with `Programmatic access` and attach these policies directly: `AWSLambda_FullAccess` and `AmazonS3FullAccess`. (No tags necessary). Store the value from `Access Key ID` in github secrets as `AWS_ACCESS_KEY_ID`. Store the value from `Secret access key` in github secrets as `AWS_SECRET_ACCESS_KEY`.
3. Create a Lambda `Role` of `my-lambda-role`. No permission policies are needed. It just needs to exist.
4. Create a Lambdda `Function`, authored from scratch, named `my-function`. Use `Python 3.8` and use the existing `my-lambda-role`.