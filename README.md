AWS Static Website Hosting Project
This project demonstrates how to create and deploy a simple static website using Amazon S3 for hosting. The website includes a single HTML page with linked CSS for styling. This is ideal for beginners looking to understand the basics of cloud services and static website hosting on AWS. 

Features
Static Website: HTML and CSS files hosted on S3.
Public Access Configuration: Set up S3 bucket policies to make the website publicly accessible.
Scalable and Cost-Effective: Uses S3’s pay-as-you-go model, perfect for hosting small sites.

📁 Project Structure
csharp
Copy code
aws-static-website/
│
├── index.html           # Main HTML file
├── style.css            # CSS for basic styling
└── README.md            # Project documentation

 Step-by-Step Instructions:

Step 1: Create an S3 Bucket
Sign in to AWS Management Console and open the S3 service.
Click Create bucket.
Bucket name: Enter a globally unique name, like my-static-website-demo.
Region: Choose the closest region.
Uncheck Block all public access (since we need public access for a website).
Bucket Versioning: Leave it disabled for now.
Click Create bucket.

Step 2: Upload Files to S3
Go to your newly created bucket and click on Upload.
Add the index.html and style.css files.
Click Upload after confirming the files.

Step 3: Configure Bucket for Static Website Hosting
Open the Properties tab in the bucket.
Scroll down to Static website hosting and click Edit.
Select Enable for static website hosting.
Index document: Type index.html.
Leave Error document blank (or add a custom error page if needed).
Click Save changes.

Step 4: Set Bucket Policy for Public Access
Open the Permissions tab and scroll to Bucket policy.
Copy and paste the following JSON policy to make the files publicly accessible:

json
-------

{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::your-bucket-name/*"
    }
  ]
}
Replace your-bucket-name with your actual bucket name.
Click Save changes.

Step 5: Access Your Website
Go back to the Properties tab and scroll to Static website hosting.
You’ll see a Bucket website endpoint URL—click it to view your hosted website! 
