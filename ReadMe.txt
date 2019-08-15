To deploy the project 

Step 1:

Create infrastructure stack

aws cloudformation create-stack  --stack-name infra --template-body file://infra-deployment.yaml --parameters file://infra-params.json --region us-west-2 --capabilities CAPABILITY_NAMED_IAM

Make sure the infrstructure is creation is completed

Step 2:

Create S3 bucket and upload index.zip file and note the name of the bucket you created 

Step 3:

Modify the server-deployment stack with your s3bucket address


Step 4: 

Create Server stack:


aws cloudformation create-stack  --stack-name servers --template-body file://servers-deployment.yaml --parameters file://servers-params.json --region us-west-2  --capabilities CAPABILITY_IAM


Step 5 go to EC2 dashboard and to loadbalancer menu and copy the DNS address and access index.html application on your browser.


