﻿# Static-WebPage
## Hosting a simple webpage on AWS 

The goal of this project is the deployment of a simple static webpage on Amazon Web Services (AWS). The project includes the design of the cloud architecture and deploying it. 
The web page itself is a  static 'Hello World' file for demonstration purposes only.

## Cloud Architecture:
1. User Access
Global visitors access the website via the CloudFront distribution URL
https://d2pftt2xeh25n7.cloudfront.net

2. Traffic Routing: 
CloudFront acts as the CDN, routing user requests to the nearest edge location to reduce latency. 

3.  Content delivery
The S3 bucket hosts the static HTML page. CloudFront fetches the static content (HTML file) from the S3 bucket. 
Origin Access Identity ensures that only CloudFront can access the S3 bucket, preventing direct access by users.

## Installation instructions

1. Clone the repository:

   ```bash
   git clone https://github.com/your-username/your-repository.git

2.  Navigate to the project directory:

cd your-repository

4. Wait until the stack creation is complete. You can check the status using:

   aws cloudformation describe-stacks --stack-name my-secure-static-website

5. Access the website using the CloudFront distribution URL:

 https://d2pftt2xeh25n7.cloudfront.net
