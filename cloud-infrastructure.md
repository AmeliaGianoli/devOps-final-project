# Cloud Infrastructure
## Amazon Linux
uname -a  shows name, OS version and other info  
uses yum instead of dnf or apt  
## S3 Storage
### Workflow:
create bucket  
![creation and permissions](https://gianoli-devops-final-project.s3.us-east-1.amazonaws.com/BucketPermissions.png)
![Correct Bucket Policy](https://gianoli-devops-final-project.s3.us-east-1.amazonaws.com/BucketPolicyCorrect.png)
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
#### When updating "your bucket name" DO NOT FORGET the /* at the end; it will throw an error!
![screenshot of the error recieved when missing the '/*'](https://gianoli-devops-final-project.s3.us-east-1.amazonaws.com/Screenshot+2026-02-24+105224.png)

Upload objects as desired
![object upload](https://gianoli-devops-final-project.s3.us-east-1.amazonaws.com/objectUpload.png)

Using the GUI is pretty straightforward, just click the big orange buttons...
