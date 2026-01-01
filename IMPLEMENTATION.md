# Payment Information Implementation Guide

## Overview
This document provides complete implementation details for adding payment information to all 15 services on the Digital Library website.

## Payment Details

### Bank Accounts:
1. **Al Ahli Bank**: SA6210000024200000066707
2. **Rajhi Bank**: SA554800002456086161270

### Pricing:
1. **Damman Mutawar Registration**: 59 SAR
2. **All Other Services** (14 services): 20 SAR each

## HTML Payment Section Template

Add this section before the closing `</form>` tag or after the "Submit" button on each service page:

```html
<!-- Payment Information Section -->
<div class="payment-section" style="margin-top: 40px; padding: 30px; background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); border-radius: 15px; color: white;">
  <h3 style="text-align: center; margin-bottom: 25px; font-size: 24px;">
    💳 معلومات الدفع
  </h3>
  
  <div style="background: rgba(255,255,255,0.1); padding: 20px; border-radius: 10px; margin-bottom: 20px;">
    <h4 style="margin-bottom: 15px; font-size: 20px;">✅ قيمة الخدمة:</h4>
    <p style="font-size: 32px; font-weight: bold; text-align: center; margin: 10px 0;">
      [SERVICE_PRICE] ريال سعودي
    </p>
  </div>
  
  <div style="background: rgba(255,255,255,0.1); padding: 20px; border-radius: 10px; margin-bottom: 15px;">
    <h4 style="margin-bottom: 15px; font-size: 18px;">🏦 الحسابات البنكية:</h4>
    
    <div style="margin-bottom: 15px; padding: 15px; background: rgba(255,255,255,0.15); border-radius: 8px;">
      <strong>🟢 البنك الأهلي</strong><br>
      <code style="background: rgba(0,0,0,0.3); padding: 5px 10px; border-radius: 5px; display: inline-block; margin-top: 8px; font-size: 14px;">
        SA6210000024200000066707
      </code>
    </div>
    
    <div style="padding: 15px; background: rgba(255,255,255,0.15); border-radius: 8px;">
      <strong>🟢 بنك الراجحي</strong><br>
      <code style="background: rgba(0,0,0,0.3); padding: 5px 10px; border-radius: 5px; display: inline-block; margin-top: 8px; font-size: 14px;">
        SA554800002456086161270
      </code>
    </div>
  </div>
  
  <div style="background: rgba(255,255,255,0.1); padding: 15px; border-radius: 10px; text-align: center;">
    <p style="margin: 0; font-size: 14px;">
      ℹ️ بعد التحويل، يرجى إرسال إيصال الدفع عبر الواتساب
    </p>
  </div>
</div>
```

## Service-Specific Implementations

### 1. damman-form.html (59 SAR)
Replace `[SERVICE_PRICE]` with `59`

### 2-15. All Other Services (20 SAR each)
Replace `[SERVICE_PRICE]` with `20`

Services:
- citizen-account-form.html
- hafiz-form.html
- sanad-form.html
- tamheer-form.html
- towteen-form.html
- cv-form.html
- qiyas-form.html (to be created)
- ecommerce-store-form.html (to be created)
- ecommerce-courses-form.html (to be created)
- home-teaching-form.html (to be created)
- digital-marketing-form.html (to be created)
- followers-form.html (to be created)
- employment-form.html (to be created)
- consultations-form.html (to be created)

## Implementation Steps

1. Extract the digital-library-website.zip file
2. Open each HTML file
3. Locate the form's submit button
4. Add the payment section HTML after the button
5. Replace `[SERVICE_PRICE]` with the appropriate price
6. Save all files
7. Re-upload to Netlify or GitHub
8. Deploy the updated version

## Alternative: JavaScript Implementation

For a dynamic solution, add this script to all pages:

```javascript
// Add to the bottom of each HTML file before </body>
const servicePrices = {
  'damman-form': 59,
  'default': 20
};

const pageName = window.location.pathname.split('/').pop().replace('.html', '');
const price = servicePrices[pageName] || servicePrices['default'];

// Insert payment section dynamically
const paymentHTML = `/* Payment section HTML template with ${price} SAR */`;
document.querySelector('form').insertAdjacentHTML('afterend', paymentHTML);
```

## Status
✅ Payment information documented
✅ Bank accounts configured
✅ Pricing structure defined
🗓️ Ready for implementation
