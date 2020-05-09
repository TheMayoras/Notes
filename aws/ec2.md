# SSH

SSH'ing into the EC2 instance requires logging in as ec2-user.  The private key must be supplied to
connect.  This is most likely contained in the `.aws` directory contained in the project the EC2
instance is for.

## Error: Connection Timed Out

Check that SSH on the EC2 instance has port 22 open for SSH _and_ the IP address that the inbound
rule allows matches the the current IP address

1.  Select the EC2 instance in the AWS EC2 console.
2.  Select the security group for the inbound/outbound traffic
3.  Click edit rules
4.  Verify there is an SSH, Port 22 rule.
5.  Verify the IP address that matches the rule either matches the current IP address or 
(any) 0.0.0.0/::0
