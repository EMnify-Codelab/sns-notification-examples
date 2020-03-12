# SNS-Notification-Examples

A repository with Python and Node.js examples for SNS notifications

![alt text](https://emnify-public-docs.s3.eu-central-1.amazonaws.com/assets/images/kb/stack.png "Example Setup")

## Tutorial

An article which has step-by-step instructions for these code examples can be found at the [EMnify Knowledgebase](https://support.emnify.com/hc/en-us/articles/360010536679-Webinar-Email-Slack-notifications-from-the-EMnify-Data-Streamer)

## Cloudformation Template

A cloudformation template is provided to bootstrap the AWS components used in this repository and get started with the Slack integration.
To get started, copy the [template](https://github.com/EMnify-Codelab/sns-notification-examples/blob/master/s3-sns-slack-cloudformation.template) into the cloudformation service, or launch the stack directly here:

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=emnify-datastreamer-notifications&templateURL=https://cd-templates-example.s3.eu-west-3.amazonaws.com/s3-sns-slack.template)

The parameters that have to be set suring launch are as follows:

* `DatastreamBucketName` - The name of an S3 Bucket. Will be created during launch and used as a destination for EMnify Datastreamer events.
* `SlackBotName` - The name of the bot that will deliver notifications to your slack workspace
* `SlackChannel` - The name of the Slack channel to receive notifications
* `SlackMatchPattern` - A regular expression match pattern for triggering slack notifications. This is passed to the Lambda function as an environment variable and can easily be edited later.
* `SlackWebhookURL` - The full Webhook URL for the Slack notifications. This is passed to the Lambda function as an environment variable and can easily be edited later.

__Note:__ This stack does not include the email notification lambda or SNS topic. 
To add this to the stack, add an email SNS topic and copy the SES lambda in this repository to this stack.

## Repository contents

```
├── S3toSNS
│   └── s3tosns.py                   <- Reads incoming Data Stream events, trigger SNS messages
├── SNStoSlack
│   └── SNStoSlack.js                <- A Node.js lambda which sends Slack notifications to a configurable workspace
├── SNStoSES
│   ├── SNStoSES.py                  <- Send SES emails using a basic HTML template, lexx flexible, but quick to start
│   └── template.html                <- An example HTML template for use with SES
└── SESwithTemplate
    ├── email_template.json          <- A more complex HTML template for use with SES
    └── sendSESMailWithTemplate.py   <- Send SES emails using the templating utility privided by AWS
```
