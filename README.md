# Portfolio Website

Personal portfolio website for Rakesh Yemineni - Full Stack Developer

## Deployment

This portfolio is automatically deployed to AWS S3 using GitHub Actions.

### Setup Instructions

1. **Create S3 Bucket**
   - Go to AWS S3 Console
   - Create bucket (e.g., `rakesh-portfolio`)
   - Enable static website hosting
   - Set index document to `index.html`

2. **Set Bucket Policy**
   ```json
   {
       "Version": "2012-10-17",
       "Statement": [
           {
               "Sid": "PublicReadGetObject",
               "Effect": "Allow",
               "Principal": "*",
               "Action": "s3:GetObject",
               "Resource": "arn:aws:s3:::YOUR-BUCKET-NAME/*"
           }
       ]
   }
   ```

3. **Create IAM User**
   - Go to IAM Console
   - Create user with programmatic access
   - Attach policy: `AmazonS3FullAccess`
   - Save Access Key ID and Secret Access Key

4. **Add GitHub Secrets**
   - Go to your GitHub repository
   - Settings → Secrets and variables → Actions
   - Add these secrets:
     - `AWS_ACCESS_KEY_ID`: Your AWS access key
     - `AWS_SECRET_ACCESS_KEY`: Your AWS secret key
     - `S3_BUCKET_NAME`: Your S3 bucket name (e.g., `rakesh-portfolio`)
     - `CLOUDFRONT_DISTRIBUTION_ID`: (Optional) Your CloudFront distribution ID

5. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/portfolio.git
   git push -u origin main
   ```

### Website URL

After deployment, your website will be available at:
- S3: `http://YOUR-BUCKET-NAME.s3-website-REGION.amazonaws.com`
- CloudFront (if configured): `https://YOUR-DISTRIBUTION.cloudfront.net`

## Technologies Used

- HTML5
- CSS3
- JavaScript
- Google Fonts (Inter, JetBrains Mono, Orbitron)
- Devicons
- Simple Icons

## Features

- Responsive design
- Animated particle background
- Project slideshow
- Drag-to-scroll skills section
- Coding profiles integration
- Resume download

## License

© 2024 Rakesh Yemineni. All rights reserved.
