# AWS-S3

Configure CLI autoprompt (Cloudshell as well):
export AWS_CLI_AUTO_PROMPT=on-partial
Grep (for checking if it's updated)
env | grep AWS_CLI

S3 -> Object Storage (Unlimited storage)
- Serverless
- S3 console provides an interface and access your data
- You can store objects from 0 B - 5 TB
- S3 Object contains of:
    - Key (name)
    - Value (Data itself made up of bytes)
    - Version ID (Version of Object)
    - Metadata (Additional info)
- S3 Bucket -> Holds objects. Buckets can also have folders (Prefixes to the buckets / No real folders). S3 buckets much have unique names
Default encryption - (SSE-S3)

CLI Interactions with S3:
S3 Command - aws s3 ls (All existing buckets)
- Point to a bucket - s3://
- cp : Copy local file or S3 object to another location locally or S3. Ex. aws s3 cp test.txt s3://mybucket/test.txt
- rm : 
Remove bucket: aws s3 rb s3:// (Can't unless bucket is empty)
Remove all objects: aws s3 rm s3:// if we add --recursive
S3 API (More robust since you get JSON) - aws s3api 
- Create bucket: aws s3api create-bucket --bucket my-example-bucket --region us-east-1
- Filter by name: aws s3api list-buckets --query "Buckets[?Name == 'my-example-bucket'].Name" --output text/json/yaml(optional format)

Create _ for examples purposes (Linux):
touch hello.txt
nano hello.txt (To edit)
mkdir images (Make folder)
mv logo.png images/
mv hello.txt images/
ls images/

- aws s3 get-object --bucket aws-saa-sebastian123 --key hello.txt world.txt