ansible-cloudwatch-metrics
==========================

This script uses Amazon's CloudWatch script to send metrics via systemd's service/timer.
It requires AWS keys.

Official guide: http://docs.aws.amazon.com/AmazonCloudWatch/latest/DeveloperGuide/mon-scripts-perl.html

Variables required:  
`cloudwatch_dir`: directory to install CLI tools (http://aws.amazon.com/code/8720044071969977)  
`aws_credential_file_src`: location of AWS credential file on ansible server  
`aws_credential_file_dest`: location to install the AWS credential file on target instance  
`alarm_recipients`: array of alarm actions  

Example group_vars/all file:  
```
cloudwatch_dir: /usr/local
aws_credential_file_src: /usr/local/cloudwatch/awscreds
aws_credential_file_dest: "{{cloudwatch_dir}}/aws-scripts-mon/awscreds.template"
alarm_recipients: ["arn:aws:sns:us-west-1:1234567890:Peter"]
```
