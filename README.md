# Stony Bend Barn – Static Site Starter

This is a minimal, single-page static site you can deploy for free.

## Replace the placeholders
- Put your real photos in `/images` and update captions in `index.html`.
- Update the email and Instagram link in the Contact section.

## Deploy Options

### GitHub Pages (free, HTTPS)
1. Create a repo named `<your-username>.github.io` **or** any repo and enable Pages.
2. Upload `index.html`, `style.css`, and the `images` folder.
3. In repo Settings → Pages, set Source to the `main` branch (or `docs` folder if you prefer).
4. For a custom domain (recommended `www.stonybendbarn.com`):
   - Create a `CNAME` file at repo root with: `www.stonybendbarn.com`
   - In GoDaddy DNS, create a CNAME:
     - Host: `www`
     - Points to: `<your-username>.github.io`
   - (Optional) Forward the apex `stonybendbarn.com` → `https://www.stonybendbarn.com` in GoDaddy.

### AWS S3 (+ optional CloudFront)
1. Create S3 bucket: `www.stonybendbarn.com` (Block public access OFF for website hosting).
2. Enable **Static website hosting** and set index document to `index.html`.
3. Upload site files. Make them publicly readable (via bucket policy or ACLs as needed).
4. (Recommended) Put CloudFront in front of S3 for HTTPS and better performance.
   - Create a distribution with the S3 bucket as origin.
   - Add an **Alternate Domain Name (CNAME)** for `www.stonybendbarn.com` and attach an ACM cert for that domain.
   - In GoDaddy DNS, CNAME `www` → your CloudFront distribution domain.
5. Use GoDaddy forwarding for the apex `stonybendbarn.com` → `https://www.stonybendbarn.com`.

## Local preview
Just open `index.html` in your browser.
