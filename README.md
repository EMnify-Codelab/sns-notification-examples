# SNS-Notification-Examples

A repository with Python and Node.js examples for SNS notifications

![alt text](https://emnify-public-docs.s3.eu-central-1.amazonaws.com/assets/images/kb/stack.png "Example Setup")

## Tutorial

An article which has step-by-step instructions for these code examples can be found at the [EMnify Knowledgebase](https://support.emnify.com/hc/en-us/articles/360010536679-Webinar-Email-Slack-notifications-from-the-EMnify-Data-Streamer)

## Cloudformation Template

A cloudformation template is provided to bootstrap the AWS components used in this repository.
To get started, copy the [template](https://github.com/EMnify-Codelab/sns-notification-examples/blob/master/s3-sns-slack-cloudformation.template) into the cloudformation service, or launch the stack directly here:

[![Launch Stack](https://cdn.rawgit.com/buildkite/cloudformation-launch-stack-button-svg/master/launch-stack.svg)](https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=emnify-datastreamer-notifications&templateURL=https://cd-templates-example.s3.eu-west-3.amazonaws.com/s3-sns-slack.template)

## Repository contents

```
├── README.md
├── S3toSNS
│   └── s3tosns.py
├── SESwithTemplate
│   ├── email_template.json
│   └── sendSESMailWithTemplate.py
├── SNStoSES
│   ├── SNStoSES.py
│   └── template.html
└── SNStoSlack
    └── SNStoSlack.js
```
