# This is a project to test an S3 bucket 
and it has these other services:
    
1. dynamodb, 
2. lambda, 
3. logs, 
4. cloudformation, 
5. iam and
6. ssm

## In order to run it follow the instructions:
Localstack


1. docker run -d -p 4566:4566 -v /Users/federicofailla/Downloads:/data/localstack -e SERVICES=s3 localstack/localstack:latest 
    
    or

    a. docker run -d —name localstack p 4566:4566 -v /Users/federicofailla/Downloads:/data/localstack -e SERVICES=s3 localstack/localstack:latest 

1.  export AWS_ACCESS_KEY_ID=foo &&

    export AWS_SECRET_ACCESS_KEY=bar &&

    export AWS_DEFAULT_REGION=sa-east-1

1. aws --endpoint-url=http://localhost:4566 s3api create-bucket --bucket sample-bucket

    or

    a. aws --endpoint-url=http://localhost:4566 s3api create-bucket --bucket sample-bucket --create-bucket-configuration LocationConstraint=sa-east-1

        {
            "Location": "http://sample-bucket.s3.localhost.localstack.cloud:4566/"
        }
	b. aws --endpoint-url=http://localhost:4566 s3api create-bucket --bucket sample-bucket --create-bucket-configuration LocationConstraint=us-east-1

1. aws --endpoint-url=http://localhost:4566 s3api list-buckets

1. aws s3 cp /data/localstack/Vehicle.csv s3://sample-bucket/Vehicle.csv --endpoint-url=http://localhost:4566
    
    a. aws s3 cp /data/localstack/vehiclesss.csv s3://sample-bucket/vehiclesss.csv --endpoint-url=http://localhost:4566
    b. aws s3 cp /data/localstack/fail.csv s3://sample-bucket/fail.csv --endpoint-url=http://localhost:4566

	c. aws --endpoint-url=http://localhost:4566 s3 cp /data/localstack/Vehicle.csv s3://sample-bucket/Vehicle.csv

    	aws s3 cp /data/localstack/pm-csv-processor s3://sample-bucket/pm-csv-processor --endpoint-url=http://localhost:4566

1. aws --endpoint-url=http://localhost:4566 s3 ls s3://sample-bucket --recursive
	aws --endpoint-url=http://localhost:4566 s3 ls s3://sample-bucket
