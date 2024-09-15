# Basic Amazon S3 Storage Solution

This project demonstrates how to create an Amazon S3 bucket, upload/download files, enable versioning, and configure the bucket for static website hosting.

## Features

- **Create S3 Bucket**: A simple, scalable storage solution for files and objects.
- **Upload and Download Files**: Upload a text file to S3 and make it publicly accessible for download.
- **Versioning**: Track changes to files by enabling versioning in the S3 bucket.
- **Static Website Hosting**: Host a basic static website using Amazon S3.

---

## Prerequisites

- An **AWS Account**.
- **AWS CLI** installed and configured. You can follow the setup guide [here](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html).
- **AWS Management Console** access.

---

## Step-by-Step Instructions

### 1. Create an S3 Bucket

1. **Login to AWS Management Console**:

   - Navigate to the **S3** service.
   - Click **Create bucket**.

2. **Configure Bucket Settings**:

   - **Bucket Name**: Provide a globally unique name (e.g., `azubi-s3-bucket-123`).
   - **Region**: Choose your preferred AWS region (e.g., `us-east-1`).
   - **Block Public Access**: For this example, uncheck the "Block all public access" option (if you want public access for your objects).
   - Click **Create Bucket**.

3. **Confirm the S3 Bucket Creation**:
   - Once the bucket is created, you should see it listed in the **S3 console**.

### 2. Upload and Download Files

1. **Upload a File**:
   - In the **S3 console**, click on your newly created bucket.
   - Click **Upload**, choose a text file (e.g., `azubi.txt`), and upload it.
2. **Make the File Public**:
   - After the upload is complete, select the file in the bucket.
   - Click on **Permissions** and then **Edit** under **Public access**.
   - Check **Grant public read access** to the object.
3. **Note the File URL**:

   - After granting public access, copy the **Object URL** from the file’s details. This will be the URL used to access the file.

4. **Download the File**:
   - Access the file using the Object URL in a browser to download it.

### 3. Enable Versioning

1. **Enable Versioning on the Bucket**:

   - In the **S3 console**, navigate to your bucket and click on **Properties**.
   - Scroll down to **Bucket Versioning** and click **Enable**.
   - Save the changes.

2. **Upload a New Version of the File**:
   - Upload the same file (with changes if desired) to the bucket using the **Upload** option.
   - This will create a new version of the file.
3. **Observe Version Changes**:
   - In the **Objects** tab of your bucket, click on **Show versions** to view the different versions of your file.
   - You can download or restore previous versions as needed.

### 4. Static Website Hosting

1. **Configure the Bucket for Static Website Hosting**:

   - In your S3 bucket, navigate to **Properties**.
   - Scroll down to **Static website hosting** and click **Edit**.
   - Choose **Enable** and enter the following:
     - **Index document**: `index.html`.
     - **Error document**: `error.html`.

2. **Upload an HTML File**:

   - Upload an `index.html` and file to the bucket (this will be your static website homepage).
   - Ensure that the file has public read access, as done with the text file earlier.

3. **Access the Static Website**:
   - After the `index.html` and `error.html` file is uploaded, go back to **Properties** and copy the **Static website hosting URL**.
   - Paste this URL in a browser to view your static website.

---

## Clean-Up

To avoid unnecessary charges, follow these steps to clean up resources:

1. **Delete S3 Objects**:

   - In the **S3 console**, navigate to your bucket.
   - Select all files and delete them.

2. **Delete the S3 Bucket**:
   - In the **S3 console**, select your bucket.
   - Click **Delete bucket**.

---

## Summary of Key Steps

1. **Create S3 Bucket**:

   - Created with a unique name and configured for public access.

2. **Upload and Download Files**:

   - Uploaded a text file and made it publicly accessible via a URL.

3. **Enable Versioning**:

   - Versioning was enabled to track changes to uploaded files.

4. **Static Website Hosting**:
   - The S3 bucket was configured to serve static HTML files as a website.
