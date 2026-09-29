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
