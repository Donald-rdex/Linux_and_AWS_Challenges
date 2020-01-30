**Category: Linux/AWS**

**Difficulty: Intermediate**

Today's challenge involves both a Linux piece and an AWS piece. Several pieces to get working in 
this one with a lot of things most of you have not touched before.

* Part 1
  * Launch a free tier instance (a t2.micro currently) instance, Setup the squid proxy server on it. Verify you can access it
 via the default port 3128 locally.  The 'curl' command with the proxy server flag will work here.
    * NOTE: it may not work from a laptop on the amazon network, so either run curl from the instance,
   or when connected to another network if you want to connect remotely.
* Part 2
  * Setup AWS Cloudwatch Logs to receive the log files in /var/log/squid/access.log and cache.log
     * Note: you will need to the setup and IAM role and attach it to the instance to allow the 
     instance to send logs to the log group.
* Part 3 - Verification
  * provide the output from:
  
    `curl -x <proxyip> https://www.calpoly.edu/ -o - 2>&1  | head -15`
 
  * provide the corresponding log group, and log stream message from cloudwatch logs showing the
  access.log connection statement. Use the AWS CLI commands starting with:
  
  `aws logs describe-log-groups`, 
  
  then `aws logs describe-log-streams --log-group-name <yourLogGroupName>`
  
  then `aws logs get-log-events --log-group-name <yourLogGroupName> --log-stream-name <LogStreamName>`
  
  Use the '--start-time' and '--end-time' flags to isolate the specific log entry from Cloudwatch logs.
  

