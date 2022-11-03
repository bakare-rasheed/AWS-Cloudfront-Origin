## CLOUDFRONT ORIGIN GROUPS

In this project I created a cloudfront distribution(A content delivery Network) using S3 bucket and Amazon EC2 as Origins

Amazon CloudFront is a web service that speeds up distribution of your static and dynamic web content, such as .html, .css, .js, and image files, to your users. 
CloudFront delivers your content through a worldwide network of data centers called edge locations. When a user requests content that you're serving with CloudFront,
the request is routed to the edge location that provides the lowest latency (time delay), so that content is delivered with the best possible performance.

An origin is the location where content is stored, and from which CloudFront gets content to serve to viewers
When you create a distribution, you specify the origin where CloudFront sends requests for the files.
You can use several different kinds of origins with CloudFront.
-Amazon S3 bucket
-MediaStore container
-MediaPackage channel
-Application Load Balancer, or an 
-AWS Lambda function URL.

![bucket](https://user-images.githubusercontent.com/114327344/199685484-36cf26f3-3420-4857-ab32-47a716df12f4.PNG)

*Step one
CREATING S3 BUCKET
- Name : rasheed-bucket
- ACLs disabled
- Uncheck 'block all public access'

![s3](https://user-images.githubusercontent.com/114327344/199685324-1badf23f-1139-462b-a952-6b44715799ef.png)
![policy](https://user-images.githubusercontent.com/114327344/199686981-bd0d5fc2-0c37-4c28-9a9e-92e587428406.PNG)

*Step two
Upload an index.html file to S3 and make the object publicly accessible by changing the bucket policy

![index-upload](https://user-images.githubusercontent.com/114327344/199686066-6b703a94-8221-4b2d-a207-125084df4d85.PNG)

*Step three
Creating CloudFront Distribution

![cloudfront](https://user-images.githubusercontent.com/114327344/199685884-9c95c154-b6d4-4811-a707-e41e2ea7dfba.PNG)

-My S3 bucket was Chosen as the origin domain name
-Copied and pasted the domain of CloudFront distribution in the new tab of my browser and added /index.html in the URL.
 
*Step four
An ec2 instance was launched with an inbound rule of HTTP port 80 from anywhere

![bakare-instance](https://user-images.githubusercontent.com/114327344/199686408-de361994-df36-4e2a-9769-e4bb079af1f1.PNG)

*Step Five
Added EC2 as the Origin and created Origin Group

![last2](https://user-images.githubusercontent.com/114327344/199686952-92c4d848-820b-4874-8796-621810845dfa.PNG)

*Step Six
Testing the Origin group
Copied the Distribution domain name and pasted it into the new tab of my browser.

![ec2-s3](https://user-images.githubusercontent.com/114327344/199686663-b28c38f3-d014-49bb-9d9a-edace80cb281.PNG)

![indexbakare](https://user-images.githubusercontent.com/114327344/199686759-01de05d1-c6d2-4eab-bf5d-bf7842a56fec.PNG)

![index-bakare](https://user-images.githubusercontent.com/114327344/199686789-e2fa7b6a-747e-42b7-ad8a-cff6a5eef82f.PNG)

![indexrasheed](https://user-images.githubusercontent.com/114327344/199686813-f801aaf4-4afc-4b3c-9095-28b3125f7bb4.PNG)
![last1](https://user-images.githubusercontent.com/114327344/199686916-a6754178-1a5d-42d0-911d-0905a9d78acd.PNG)
