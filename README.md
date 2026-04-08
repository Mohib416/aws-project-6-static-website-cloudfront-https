# 🚀 AWS Project 6 — S3 Static Website + CloudFront + Custom Domain + HTTPS

## 📌 Project Overview

In this project, I built a professional static website hosting architecture using AWS and a custom domain.
The goal was to understand how real cloud websites are delivered globally with low latency, HTTPS security, and a custom domain.

Instead of serving the website directly from Amazon S3, I placed Amazon CloudFront in front of the bucket to improve performance, security, and global availability.

This project includes:

* Amazon S3 Static Website Hosting
* Amazon CloudFront CDN
* AWS Certificate Manager (ACM)
* Custom Domain with Namecheap DNS
* HTTPS / SSL Certificate
* Troubleshooting and real-world issue fixing

---

## ⚙️ Step 1: Creating the S3 Bucket

First, I created an Amazon S3 bucket to host the static website files.

Configuration used:

* **Bucket name:** `mohib-project6-static-site-2026`
* **Object Ownership:** Bucket owner enforced
* **ACLs:** Disabled (recommended)
* **Tags:**

  * Project = AWS-Project-6
  * Environment = Lab
  * Owner = Mohib

This follows modern AWS best practices for security and governance.

---

## 📂 Step 2: Uploading Website Files

Then I created the website source files:

* `index.html`
* `style.css`

These files contain the homepage structure and the CSS styling for the website.

After that, I uploaded both files into the S3 bucket.

---

## 🌐 Step 3: Enabling Static Website Hosting

After uploading the files, I enabled **Static Website Hosting** in the S3 bucket.

Configuration:

* **Hosting type:** Static website hosting
* **Index document:** `index.html`

This allows the S3 bucket to serve the website as a static web application.

---

## ☁️ Step 4: Creating CloudFront Distribution

Next, I created an Amazon CloudFront distribution in front of the S3 bucket.

Configuration:

* **Origin type:** Amazon S3
* **Viewer protocol policy:** Redirect HTTP to HTTPS
* **Allowed methods:** GET, HEAD
* **Cache policy:** CachingOptimized

CloudFront was added to:

* improve performance globally
* reduce latency through edge locations
* increase security
* enable HTTPS support

This is how real production websites are commonly delivered.

---

## 🔧 Step 5: Troubleshooting & Fix

At first, the website returned:

`AccessDenied`

After investigating the issue, I found that the files had been uploaded incorrectly as:

* `index.html.txt`
* `style.css.txt`

This caused CloudFront and S3 not to detect the correct index file.

### ✅ Fix

I recreated the files properly using Visual Studio Code:

* `index.html`
* `style.css`

Then I reuploaded them to S3.

After the fix, the website started working successfully through CloudFront.

This was an important real-world troubleshooting step.

---

## 🌍 Step 6: Custom Domain + HTTPS

To make the project more professional, I purchased a custom domain:

`mohibcloud.com`

using Namecheap.

Then I configured:

* DNS records in Namecheap
* AWS Certificate Manager (ACM)
* SSL certificate validation using CNAME records
* CloudFront custom domain settings

Final result:

`https://mohibcloud.com`

with valid HTTPS and secure SSL connection.

---

## 🧠 What I Learned

* How static websites are hosted in Amazon S3
* How CloudFront CDN works
* How caching improves website performance
* How HTTPS works with ACM
* How DNS resolution works
* How to connect a custom domain to CloudFront
* Real-world troubleshooting and debugging

---

## 🔧 Problems Solved

* Fixed `AccessDenied` issue
* Fixed wrong file extension issue (`.txt`)
* Fixed ACM DNS validation issue for subdomain
* Successfully connected custom domain with HTTPS

---

## 🏗️ Architecture Summary

* **Client** → sends HTTPS request
* **Namecheap DNS** → resolves domain
* **CloudFront** → handles CDN + cache + HTTPS
* **ACM** → provides SSL certificate
* **S3** → stores static website files

---

## 🏗️ Architecture Diagram

![Architecture Diagram](./diagram/23-final-project-6-architecture-diagram.png)

---

## 📸 Screenshots

### Project Steps

* [01 - S3 Bucket Created](./screenshots/01-s3-bucket-created.png)
* [02 - S3 Bucket Properties](./screenshots/02-s3-bucket-properties.png)
* [03 - Upload Files](./screenshots/03-s3-upload-files.png)
* [04 - Files Uploaded](./screenshots/04-s3-files-uploaded.png)
* [05 - Static Website Enabled](./screenshots/05-static-website-enabled.png)
* [06 - CloudFront Settings Before Create](./screenshots/06-cloudfront-settings-before-create.png)
* [07 - CloudFront Created Overview](./screenshots/07-cloudfront-created-overview.png)
* [08 - Access Denied Error](./screenshots/08-cloudfront-access-denied-error.png)
* [09 - File Extension Troubleshooting](./screenshots/09-s3-file-extension-troubleshooting.png)
* [10 - Correct HTML CSS Files](./screenshots/10-vscode-correct-html-css-files.png)
* [11 - CloudFront Live Website Success](./screenshots/11-cloudfront-live-website-success.png)
* [12 - Namecheap Domain Checkout](./screenshots/12-namecheap-domain-checkout.png)
* [13 - ACM Dashboard](./screenshots/13-ACM_Dashboard_us-east-1.png)
* [14 - Request Public Certificate](./screenshots/14-Request_Public_Certificate.png)
* [15 - Certificate Validation Settings](./screenshots/15-Certificate_Domain_Validation_Settings.png)
* [16 - Certificate Pending Validation](./screenshots/16-Certificate_Pending_Validation.png)
* [17 - ACM CNAME Records Added](./screenshots/17-Namecheap_ACM_CNAME_Records_Added.png)
* [18 - Certificate Validation Success](./screenshots/18-acm-certificate-validation-success.png)
* [19 - CloudFront Custom Domain Settings](./screenshots/19-cloudfront-custom-domain-settings.png)
* [20 - Namecheap CNAME to CloudFront](./screenshots/20-namecheap-www-cname-cloudfront.png)
* [22 - Final HTTPS Secure Live Site](./screenshots/22-custom-domain-live-https-secure-final.png)

---

## 🌐 Live Demo

🔗 https://mohibcloud.com

---

## 👨‍💻 Author

Muhammad Mohib

