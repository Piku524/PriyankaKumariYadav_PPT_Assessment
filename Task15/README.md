Task 15: CloudFront for S3 Website

Objective:
Deliver S3 static website globally via CloudFront and improve loading speed.

Steps:
Ensure S3 bucket has website files and Static Website Hosting enabled.

Go to CloudFront → Create Distribution → Web.

Origin Domain: select your S3 bucket.

Default Root Object: index.html.

Keep other settings default → Click Create Distribution.

Wait for Status = Deployed.

Open CloudFront Domain Name in browser → website loads.
