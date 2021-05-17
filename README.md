# Root Account Console Login / API Activity Monitor

This template can be used to add an SNS topic and a lambda to your AWS accounts.

When the root account is accessed via the console, an event fires and triggers SNS
notification. 

This idea and template is based on this useful AWS blog:

https://aws.amazon.com/blogs/mt/monitor-and-notify-on-aws-account-root-user-activity/

I made a few small changes:

* Converted to YAML
* Removed the SNS subscriptions to avoid add/remove of subscriptions and sending confirmation emails repeatedly
* Changed the lambda to output text suitable for email rather than JSON
* Inlined the lambda code

## Pre-requisites
All-region CloudTrail setup - see: 

* https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-tutorial.html
* https://docs.aws.amazon.com/awscloudtrail/latest/userguide/receive-cloudtrail-log-files-from-multiple-regions.html

## How to use
Deploy the template to your AWS account - I put it in us-east-1

Once in a completed state, find the SNS topic and add some subscriptions. This code is designed for email so outputs text.