# ShopSimple Delight — AWS re/Start Group Project

A static bag boutique website built with HTML5, CSS3 and Vanilla JavaScript.
Designed for hosting on **Amazon S3 Static Website Hosting**.

---

## Project Structure

```
aws-static-website/
├── index.html                  Home page
├── catalogue.html              Product catalogue (12 bags)
├── about.html                  About page
├── booking.html                Store visit booking form
├── booking-confirmation.html   Booking confirmation page
├── cart.html                   Shopping cart
├── checkout.html               Order / checkout form
├── order-confirmation.html     Order confirmation page
├── contact.html                Contact page + form
├── css/
│   └── style.css               All styles (single file)
├── js/
│   ├── products.js             Product data array
│   ├── cart.js                 Cart logic (localStorage)
│   ├── main.js                 Shared nav / animation logic
│   ├── booking.js              Booking form validation
│   └── checkout.js             Checkout form + order summary
└── images/
    └── (add your bag images here)
```

---

## How to Run Locally

1. Open `index.html` directly in any modern browser.
2. No server, no npm, no installation required.

---

## Adding Real Images

Each product in `js/products.js` has an `image` field set to `null`.

To add a real image:
1. Add the image file to the `images/` folder (e.g. `images/classic-tote.jpg`).
2. Open `js/products.js` and change `image: null` to `image: "images/classic-tote.jpg"` for that product.

---

## Deploying to Amazon S3

### Step 1 — Create an S3 Bucket
1. Sign in to the AWS Management Console.
2. Go to **S3** → **Create bucket**.
3. Enter a unique bucket name (e.g. `shopsimple-delight-website`).
4. Choose your AWS Region.
5. **Uncheck** "Block all public access" and confirm.
6. Click **Create bucket**.

### Step 2 — Enable Static Website Hosting
1. Open your bucket → **Properties** tab.
2. Scroll to **Static website hosting** → click **Edit**.
3. Select **Enable**.
4. Set **Index document** to `index.html`.
5. Set **Error document** to `index.html` (optional).
6. Click **Save changes**.

### Step 3 — Set a Bucket Policy (Public Read)
1. Go to the **Permissions** tab → **Bucket policy** → **Edit**.
2. Paste the following (replace `YOUR-BUCKET-NAME`):

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

3. Click **Save changes**.

### Step 4 — Upload Files
1. Go to the **Objects** tab → **Upload**.
2. Upload all files and folders:
   - `index.html`, `catalogue.html`, `about.html`, `booking.html`
   - `booking-confirmation.html`, `cart.html`, `checkout.html`
   - `order-confirmation.html`, `contact.html`
   - `css/` folder
   - `js/` folder
   - `images/` folder
3. Click **Upload**.

### Step 5 — Access Your Website
1. Go to **Properties** → **Static website hosting**.
2. Copy the **Bucket website endpoint** URL.
3. Open it in a browser — your website is live!

---

## Features

| Feature | Implementation |
|---|---|
| Product catalogue (12 bags) | `products.js` data array rendered to DOM |
| Shopping cart | `localStorage` via `cart.js` |
| Cart badge (item count) | Updates on every page |
| Checkout form | Validation + order reference `SSD-YYYY-XXXXX` |
| Order confirmation | Reads from `sessionStorage` |
| Booking form | Validation + booking reference `BOOK-YYYY-XXXXX` |
| Booking confirmation | Reads from `sessionStorage` |
| Contact form | Client-side success message |
| Responsive design | CSS Grid + media queries |
| Mobile navigation | Hamburger menu toggle |

---

## No Backend Required

- No server-side code
- No Node.js
- No database
- No API calls
- Works entirely in the browser
- 100% compatible with Amazon S3 Static Website Hosting
