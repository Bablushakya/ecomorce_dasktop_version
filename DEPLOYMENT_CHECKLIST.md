# 🚀 Deployment Checklist - GuiltFree Cravings

## Pre-Deployment Requirements

### ✅ Content & Assets

- [ ] **Hero Image**
  - Replace `assets/images/hero_image.png` with plain/unlabeled jar photo
  - Ensure jar is transparent/clear with laddoos visible
  - No printed labels or text on jar
  - Recommended size: 1200x900px minimum

- [ ] **Logo**
  - Extract gold circular flower emblem from Catalogue-New_Design_V2.jpg
  - Save as new file or update existing `assets/images/logo.jpg`
  - Circular crop with transparent or white background
  - Recommended size: 200x200px

- [ ] **Process Video**
  - Upload to YouTube or video host
  - Get embed code or direct video URL
  - Replace placeholder in Behind the Scenes section (line ~719 in index.html)
  - Recommended: 1-2 minute video showing hand-rolling process

- [ ] **Remaining Product Pages**
  - Complete `products/dates-delight-laddoo/index.html`
  - Complete `products/classic-sattu-laddoo/index.html`
  - Follow template guide in PRODUCT_PAGES_TEMPLATE_GUIDE.md

---

## 🧪 Testing Checklist

### Functionality Tests

- [ ] **Navigation**
  - [ ] All nav links work (Home, Products, About, Reviews, Contact)
  - [ ] Mobile menu opens and closes
  - [ ] Scroll-to-section anchors work smoothly

- [ ] **QR Code Landing**
  - [ ] Print/display QR code with URL: `https://guiltfree-dasktopversion.vercel.app/#products`
  - [ ] Scan with phone → Should land at Products section, not page top
  - [ ] Test from homepage → Click any #products link → Should scroll smoothly

- [ ] **Product Pages**
  - [ ] Open each product page directly via URL
  - [ ] All variant buttons work
  - [ ] "Order Now" opens WhatsApp with correct product name and price
  - [ ] "← All Laddoos" returns to main page
  - [ ] Images load correctly

- [ ] **Cart System**
  - [ ] Add Dry Fruit Sattu 250g → Cart shows 1 item
  - [ ] Add Dry Fruit Sattu 500g → Cart shows 2 SEPARATE items (not merged)
  - [ ] Add different product → Cart shows as separate line
  - [ ] Quantity +/- works
  - [ ] Remove item works
  - [ ] Cart total calculates correctly

- [ ] **Checkout Flow**
  - [ ] Open cart → Click "Proceed to Checkout"
  - [ ] Fill in name, mobile, address
  - [ ] Click "Send OTP" → Shows "OTP Sent" message
  - [ ] Enter any 4-digit code → Click "Verify OTP" → Should enable Place Order
  - [ ] Click "Place Order" → WhatsApp opens with order details
  - [ ] ⚠️ Note: SMS not actually sent (UI mockup only)

- [ ] **Footer Links**
  - [ ] Privacy Policy → Opens modal with content
  - [ ] Terms & Conditions → Opens modal
  - [ ] Delivery & Porter Terms → Opens modal
  - [ ] Track Your Order → Opens orders modal
  - [ ] Instagram link → Opens in new tab
  - [ ] All buttons are clearly clickable (cursor changes)

- [ ] **Modals**
  - [ ] Product detail modal opens correctly
  - [ ] Close (X) button works
  - [ ] Click outside modal closes it
  - [ ] Scroll works inside modal
  - [ ] All modals display properly on mobile

---

### Visual/Design Tests

- [ ] **Colors Match Catalogue**
  - [ ] Headings are dark forest green (#1F4A2C)
  - [ ] Buttons/badges are dusty rose/mauve (#B5697A)
  - [ ] Gold accents (#D4A245) visible
  - [ ] Footer is mauve background with white text (readable)

- [ ] **Typography**
  - [ ] Tagline "Rooted in Tradition..." uses cursive/script font
  - [ ] Headings use serif font (Playfair Display)
  - [ ] Body text is readable and consistent

- [ ] **Responsive Design**
  - [ ] Test on mobile (375px width - iPhone SE)
  - [ ] Test on tablet (768px - iPad)
  - [ ] Test on desktop (1920px - Full HD)
  - [ ] All images scale properly
  - [ ] Text doesn't overflow
  - [ ] Buttons are touch-friendly on mobile (min 44px height)

- [ ] **Product Cards**
  - [ ] Show real nutrition numbers (Energy, Protein)
  - [ ] "0g Added Sugar" badge visible and green
  - [ ] Product images load
  - [ ] Prices displayed correctly
  - [ ] "Add" buttons work

---

### Browser Compatibility

Test on:
- [ ] Chrome/Edge (latest)
- [ ] Safari (iOS and macOS)
- [ ] Firefox (latest)
- [ ] Samsung Internet (Android)

---

## 📊 SEO & Performance

### SEO Checks

- [ ] **Meta Tags**
  - [ ] Homepage title includes "GuiltFree Cravings | Order Handcrafted Desi Ghee Laddoos"
  - [ ] Description is compelling and under 160 characters
  - [ ] Each product page has unique title and description

- [ ] **Open Graph Tags**
  - [ ] Test sharing on Facebook → Image and description show correctly
  - [ ] Test sharing on WhatsApp → Product details visible
  - [ ] Test sharing on Instagram → Preview looks good

- [ ] **Structured Data**
  - [ ] Validate with Google Rich Results Test: https://search.google.com/test/rich-results
  - [ ] Product schema includes price, rating, availability
  - [ ] No errors in structured data

- [ ] **Sitemap**
  - [ ] Create/update sitemap.xml with new product URLs
  - [ ] Submit to Google Search Console
  - [ ] Include: homepage, product pages, about section

- [ ] **Performance**
  - [ ] Run Google PageSpeed Insights
  - [ ] Optimize images (compress JPGs to 80-85% quality)
  - [ ] Check mobile speed score (aim for 90+)
  - [ ] Desktop speed score (aim for 95+)

---

## 🔐 Security & Backend

### Current Status (Frontend Only)
- ⚠️ **OTP Verification:** UI mockup only - no SMS sent
- ⚠️ **Order History:** Placeholder - no real user data
- ⚠️ **Personalized Offers:** Documented but not implemented

### To Implement (Future):

- [ ] **SMS/OTP Service**
  - [ ] Choose provider (Twilio, MSG91, AWS SNS)
  - [ ] Set up account and get API credentials
  - [ ] Create backend endpoints:
    - `POST /api/send-otp` - Send SMS with code
    - `POST /api/verify-otp` - Validate code
  - [ ] Update frontend to call real API instead of mock

- [ ] **User Authentication**
  - [ ] Implement login system (Firebase Auth, Auth0, custom)
  - [ ] Store user profiles (name, email, phone)
  - [ ] Link orders to userId

- [ ] **Order Database**
  - [ ] Set up database (Firestore, PostgreSQL, MongoDB)
  - [ ] Schema: orders table with userId, items, totalAmount, status, date
  - [ ] Create API endpoints:
    - `POST /api/orders` - Create new order
    - `GET /api/orders?userId={id}` - Fetch user's orders

- [ ] **Personalized Offers Engine**
  - [ ] Track order frequency and total spent
  - [ ] Calculate discount tiers:
    - First order: 10% off next
    - 2-3 orders: Free delivery
    - 5+ orders: 15% off + priority
  - [ ] Auto-generate coupon codes
  - [ ] Display on orders modal

---

## 🎯 Go-Live Steps

### 1. Final Code Review
- [ ] Remove any console.log() debugging statements
- [ ] Check for broken image links
- [ ] Verify all links work (no 404s)
- [ ] Test with empty cache (Ctrl+Shift+R)

### 2. Vercel Deployment
```bash
# From project directory
vercel --prod
```

- [ ] Check build succeeds
- [ ] Test production URL
- [ ] Verify environment is "Production"
- [ ] Check Vercel dashboard for any errors

### 3. Domain Configuration
- [ ] Ensure custom domain points to Vercel
- [ ] HTTPS certificate is active
- [ ] www and non-www both work
- [ ] Redirects are set up correctly

### 4. Analytics Setup
- [ ] Add Google Analytics tracking code
- [ ] Set up Google Search Console
- [ ] Create conversion goals (WhatsApp clicks, checkout initiated)
- [ ] Set up Facebook Pixel (if running ads)

### 5. Marketing Launch
- [ ] Update Instagram bio link
- [ ] Post announcement about new product pages
- [ ] Share individual product links on social media
- [ ] Print QR codes for packaging/catalogue
- [ ] Send WhatsApp broadcast with new links

---

## 📞 Post-Launch Monitoring

### First 24 Hours
- [ ] Monitor Vercel logs for errors
- [ ] Check Google Analytics for traffic
- [ ] Test QR codes from printed materials
- [ ] Monitor WhatsApp for orders
- [ ] Check for any customer complaints

### First Week
- [ ] Review most visited product pages
- [ ] Check conversion rate (visits → orders)
- [ ] Identify any broken links from external sources
- [ ] Gather customer feedback on new design
- [ ] Monitor mobile vs desktop usage ratio

### Ongoing
- [ ] Weekly: Check Google Search Console for crawl errors
- [ ] Monthly: Review product page performance
- [ ] Monthly: Optimize slow-loading images
- [ ] Quarterly: Update SEO meta descriptions based on performance

---

## 🆘 Troubleshooting

### Common Issues

**QR Code doesn't scroll to products**
- Check that URL ends with `/#products` (not `/products`)
- Verify JavaScript QR landing code is uncommented
- Test with `?` parameter: `/?qr=true#products`

**Footer text not visible**
- Confirm footer uses `text-stone-100` class
- Check background is `bg-brand-mauve`
- Verify contrast ratio meets WCAG standards

**Product images not loading**
- Check file paths are relative: `../../assets/images/...`
- Verify image files exist in assets folder
- Confirm file names match exactly (case-sensitive)

**WhatsApp links don't work**
- Check URL encoding (spaces = `%20`)
- Verify phone number includes country code: +91
- Test link format: `https://wa.me/919667760119?text=...`

**Cart items merging incorrectly**
- Verify itemKey includes: `${productId}_${weight}_${packaging}`
- Check variant index is passed correctly
- Console.log cart array to debug

---

## ✅ Sign-Off

**Deployed By:** _________________  
**Date:** _________________  
**Production URL:** https://guiltfree-dasktopversion.vercel.app

**Verified By:** _________________  
**Date:** _________________

---

**All Green? Ready to Launch! 🚀**
