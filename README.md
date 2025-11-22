# liveLIVE Foundation - Giving Tuesday 2025 Campaign

A compelling, professionally designed landing page for the liveLIVE Foundation's Giving Tuesday campaign to support 100 single-parent families.

## 🎯 Campaign Overview

- **Campaign Dates**: November 23 - December 2, 2025 (10 days)
- **Goal**: Raise $50,000
- **Impact**: Support 100 single-parent families with an average of $500 per family
- **Key Differentiator**: 72-96 hour rapid response time from donation to direct family support

## 📋 Features

### Design
- Professional, responsive design that works on all devices (mobile, tablet, desktop)
- Emotionally engaging purple gradient theme
- Clear call-to-action with prominent donation button
- Comprehensive FAQ section
- Six impact areas highlighting how donations help families

### Technical
- Single HTML file with embedded CSS (no external dependencies)
- Clean, semantic HTML5
- Modern JavaScript (ES6+)
- Fully responsive with mobile-first approach
- Accessible design with proper ARIA labels and semantic structure
- Fast loading with optimized inline styles

### Content
- Compelling copy focused on single-parent families
- Strong emphasis on rapid 72-96 hour impact
- Contact email integration (inquiries@livelive.today)
- Campaign statistics dashboard
- Detailed information about what makes this campaign different

## 🚀 Quick Start

### Option 1: Simple Deployment
1. Upload `index.html` to your web server
2. Configure Stripe integration (see below)
3. Launch!

### Option 2: Local Testing
1. Clone this repository
2. Open `index.html` in your web browser, or
3. Run a local server:
   ```bash
   # Using Python 3
   python3 -m http.server 8000
   
   # Using Node.js (if you have http-server installed)
   npx http-server
   ```
4. Visit `http://localhost:8000` in your browser

## 💳 Stripe Payment Integration

The donate button is ready for Stripe integration. Choose one of these options:

### Option 1: Stripe Payment Link (Recommended - Easiest)

1. Create a Stripe account at [stripe.com](https://stripe.com)
2. Create a Payment Link in your Stripe Dashboard:
   - Go to Products > Payment Links
   - Click "Create payment link"
   - Set up your donation options
   - Copy the generated link
3. In `index.html`, find this line (around line 620):
   ```javascript
   // window.location.href = 'https://buy.stripe.com/your-payment-link';
   ```
4. Uncomment it and replace with your actual Stripe Payment Link:
   ```javascript
   window.location.href = 'https://buy.stripe.com/YOUR_ACTUAL_LINK';
   ```
5. Remove or comment out the placeholder alert

### Option 2: Stripe Checkout (More Customizable)

1. Create a Stripe account at [stripe.com](https://stripe.com)
2. Add Stripe.js to the `<head>` section:
   ```html
   <script src="https://js.stripe.com/v3/"></script>
   ```
3. In the Stripe Dashboard, create a Product and Price
4. Get your Publishable Key from the Stripe Dashboard
5. In `index.html`, find the commented Stripe Checkout code (around line 625)
6. Uncomment and configure with your keys:
   ```javascript
   const stripe = Stripe('pk_live_YOUR_PUBLISHABLE_KEY');
   stripe.redirectToCheckout({
       lineItems: [{price: 'price_YOUR_PRICE_ID', quantity: 1}],
       mode: 'payment',
       successUrl: window.location.origin + '/success.html',
       cancelUrl: window.location.origin + '/index.html',
   });
   ```
7. Remove or comment out the placeholder alert

## 📧 Contact Information

For questions or more information about the campaign:
- Email: inquiries@livelive.today

## 🎨 Customization

### Changing Colors
The main purple gradient can be customized by editing these CSS values in the `<style>` section:
```css
background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
```

### Updating Campaign Dates
Update the dates in the hero section:
```html
<div class="campaign-dates">📅 November 23 - December 2, 2025</div>
```

### Modifying Goals
Update the statistics in the stats section:
```html
<div class="stat-number">$50,000</div>
<div class="stat-number">100</div>
<div class="stat-number">$500</div>
```

## 📱 Browser Support

- Chrome (latest)
- Firefox (latest)
- Safari (latest)
- Edge (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## 🔒 Security

- No external dependencies (reduced attack surface)
- No sensitive data stored in the HTML
- Stripe handles all payment processing securely
- HTTPS recommended for deployment

## 📝 License

© 2025 liveLIVE Foundation. All rights reserved.

## 🙏 Support

This landing page is designed to help single-parent families in need. Every donation makes a real difference within 72-96 hours.

---

**Ready to make an impact?** Deploy this page and start changing lives today!