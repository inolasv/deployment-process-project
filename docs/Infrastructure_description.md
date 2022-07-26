

# Infrastucture

### RDS - Database
This holds the postgres SQL database in the cloud in order to store the data for the udagram application.
- PostgresSQL
- db instance: udagram-db
- db name: postgres
- allows inbound config from anywhere (0.0.0.0/0)
- port: 5432

### ElasticBeanstalk - Backend API
This deploys the backaend api (udagram-api) as an application on the cloud so that it can be accessed from places other than local machines
- environment: udagram-api-dev
- application: udagram-api
- port: 8080

### S3 - Frontend
This stores the frontend static web page in a bucket on the cloud, allowing to also be able to be accessed from places other than local machines.
- ACLs enabled, public s3 bucket
- Bucket policy:
```
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "Stmt1625306057759",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:*",
            "Resource": "arn:aws:s3:::udagramprojectbucket138483414154/*"
        }
    ]
}
```
- CORS config:
```
[
 {
     "AllowedHeaders": [
         "*",
         "Content-Type",
         "Authorization",
         "Access-Control-Allow-Origin",
         "Access-Control-Allow-Headers",
         "Access-Control-Allow-Methods"
     ],
     "AllowedMethods": [
         "POST",
         "GET",
         "PUT",
         "DELETE",
         "HEAD"
     ],
     "AllowedOrigins": [
         "*"
     ],
     "ExposeHeaders": []
 }
]
```