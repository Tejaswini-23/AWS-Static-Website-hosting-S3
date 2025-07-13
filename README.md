
# 🌐 Static Website Hosting using Amazon S3

This project demonstrates how to host a fully static website (HTML, CSS, JS) using Amazon S3.

## ✅ Features

- Hosted using AWS S3 (Free Tier)
- Publicly accessible via static website endpoint
- Serves HTML, CSS, images, and other static assets
- No backend or server logic required

## 🏗️ Architecture

```
User Browser 
     ↓
 Amazon S3 (Static Website Hosting Enabled)
     ↓
 Public HTTP URL (Website Endpoint)
```

## 📁 Folder Structure

```
.
├── index.html
├── styles.css
└── assets/
    └── img/
```

## 🚀 Hosting Steps

1. **Create an S3 bucket**
   - Use a globally unique name (e.g., `tejaswini-portfolio`)
   - Disable "Block all public access"

2. **Upload files**
   - Add `index.html`, `assets/`, and other static files

3. **Set Bucket Policy**  
   (for public read access)

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

4. **Enable Static Website Hosting**
   - Go to **Properties > Static website hosting**
   - Enable and set `index.html` as the index document

5. **Access your site**
   - Use the given website endpoint like:  
     `http://your-bucket-name.s3-website.ap-south-1.amazonaws.com`

## 🔐 Notes

- Files are **publicly viewable**, but **cannot be modified or deleted** by others
- AWS Free Tier includes:
  - 5 GB S3 storage
  - 20,000 GET and 2,000 PUT requests/month
  - 1 GB outbound transfer/month

## ✍️ Author

Tejaswini Garaka  
[GitHub](https://github.com/Tejaswini-23) • [LinkedIn](https://www.linkedin.com/in/tejaswini-garaka-0638a234a/)
