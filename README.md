---

# Deploying a Static Website on AWS via S3

This guide will walk you through the process of deploying a static website on Amazon Web Services (AWS) using Amazon S3 (Simple Storage Service).

## Prerequisites

- An AWS account
- Basic knowledge of AWS services
- Static website files (HTML, CSS, JavaScript, images, etc.)

## Steps

### 1. Create an S3 Bucket

1. Log in to the AWS Management Console.
2. Navigate to the S3 service.
3. Click on "Create bucket".
4. Enter a unique bucket name and select the region.
5. Keep the default settings and click "Create bucket".

### 2. Upload Website Content

1. Select the newly created bucket.
2. Click on the "Upload" button.
3. Upload your static website files.
4. Ensure that the uploaded files have public read permissions.

### 3. Enable Static Website Hosting

1. Select the bucket you created for your website.
2. Go to the "Properties" tab.
3. Click on "Static website hosting".
4. Choose "Use this bucket to host a website".
5. Enter the index document (e.g., index.html) and optionally, the error document.
6. Click "Save".

### 4. Set Bucket Policy for Public Access

1. Still in the bucket properties, navigate to the "Permissions" tab.
2. Click on "Bucket Policy".
3. Add a bucket policy to allow public access to your website content.
4. Use the sample policy provided below.
5. Replace "your-bucket-name" with your actual bucket name.
6. Click "Save".

Sample Bucket Policy:
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "PublicReadGetObject",
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
```

### 5. Access Your Website

1. After setting up static website hosting and configuring the bucket policy, AWS provides a website endpoint URL.
2. Access your website using the provided endpoint URL (e.g., http://your-bucket-name.s3-website.region.amazonaws.com).
3. Optionally, configure a custom domain using Route 53 or another DNS service for a more user-friendly URL.

---

