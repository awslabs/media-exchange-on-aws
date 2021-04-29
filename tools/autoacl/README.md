# AutoACL

This is a utility to automatically set permissions on the objects in the mediaexchange bucket. This allows the publishers to not have to set the explicit read permissions on the objects. This allows them do direct get and put to the bucket without having to be concerned about permissions or tooling.


### Sharing assets

```
$ aws s3 cp <filename> s3://<bucket name>/
```

## Getting Started
It is deployed on publisher's account.

## Prerequisites
* GNU make
* Install docker desktop
* Install and configure [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-install.html)
* Install [AWS SAM CLI](https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-sam-cli-install.html)


### Install
* Initialize a shell with the necessary credentials to deploy to target (publisher / subscriber) account. You can do this by adding AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY and AWS_SESSION_TOKEN as environment variables or by selecting the appropriate profile by adding AWS_PROFILE environment variable.
* Deploy AutoIngest
  * At the command prompt type `make install`.
  * follow the on-screen instructions for configuration parameters.
    * Specify the SNS topic Arn, Subscriber Canonical Id, Media Exchange Bucket Name, and EventBus from publisher on boarding summary.


### Pricing

1. S3 API pricing for GET / PUT. See [here](https://aws.amazon.com/s3/pricing/).
1. There is no cost for egress in the same region.
1. AWS Lambda pricing. See [here](https://aws.amazon.com/lambda/pricing/)

### Cleanup

* Initialize a shell with the necessary credentials to the account where you have deployed this. You can do this by adding AWS_ACCESS_KEY_ID, AWS_SECRET_ACCESS_KEY and AWS_SESSION_TOKEN as environment variables or by selecting the appropriate profile by adding AWS_PROFILE environment variable.
* Navigate to MediaExchnageOnAWS/tools/autoacl directory.
* At the command prompt type `make clean`.