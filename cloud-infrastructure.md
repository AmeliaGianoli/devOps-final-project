# Cloud Infrastructure
## Amazon Linux
uname -a  shows name, OS version and other info  
uses yum instead of dnf or apt  
## S3 Storage
### Workflow:
create bucket  
set permissions- Json file  
Example:  
`
        { 
          "Version": "2012-10-17", 
          "Statement": [ 
            { 
              "Effect": "Allow", 
              "Principal": "*", 
              "Action": [ 
                "s3:GetObject" 
              ],
              "Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*" 
            } 
          ] 
        } 
`