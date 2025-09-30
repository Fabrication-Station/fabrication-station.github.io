# Contact Form Email Setup Instructions

Your contact form is ready but needs a service to send emails automatically. Here are two easy options:

## 🚀 Option 1: Formspree (Recommended - 5 minutes setup)

**Why Formspree?** Free, simple, and works immediately with no coding required.

### Setup Steps:
1. **Go to [Formspree.io](https://formspree.io/)**
2. **Sign up for free account**
3. **Create new form** and get your form ID (looks like: `xpzgkdqw`)
4. **Edit `pages/booking.html`:**
   - **Comment out** the EmailJS form (lines 498-547)
   - **Uncomment** the Formspree form (lines 459-495)
   - **Replace** `YOUR_FORM_ID` with your actual form ID

```html
<!-- Change this line: -->
<form action="https://formspree.io/f/YOUR_FORM_ID" method="post">
<!-- To this: -->
<form action="https://formspree.io/f/xpzgkdqw" method="post">
```

**That's it!** Form will now send emails directly to fabricationstation@tus.ie

---

## ⚙️ Option 2: EmailJS (Advanced - 15 minutes setup)

**Why EmailJS?** More customization options and templates.

### Setup Steps:
1. **Go to [EmailJS.com](https://www.emailjs.com/)**
2. **Create free account**
3. **Add Email Service:**
   - Go to Email Services
   - Add Gmail, Outlook, or TUS email service
   - Follow connection wizard
4. **Create Email Template:**
   - Go to Email Templates
   - Create new template with these variables:
     ```
     From: {{from_name}} <{{from_email}}>
     Subject: Workshop Inquiry: {{subject}}

     Name: {{from_name}}
     Email: {{from_email}}
     Subject: {{subject}}

     Message:
     {{message}}
     ```
5. **Get Your IDs:**
   - Service ID (looks like: `service_1a2b3c4`)
   - Template ID (looks like: `template_xyz123`)
   - Public Key (looks like: `abcd1234efgh5678`)

6. **Update `pages/booking.html`:**
   - Replace `YOUR_PUBLIC_KEY` with your public key (line 799)
   - Replace `YOUR_SERVICE_ID` with your service ID (line 839)
   - Replace `YOUR_TEMPLATE_ID` with your template ID (line 839)

---

## 🔧 Quick Test

After setup:
1. **Open the booking page**
2. **Fill out the contact form**
3. **Submit and check your email**
4. **You should receive the message automatically!**

---

## 📧 Current Status

- ✅ **Form validation** - Works
- ✅ **Form styling** - Works
- ✅ **Fallback email** - Works (opens email client)
- ⏳ **Automatic sending** - Needs service setup (5 minutes)

Choose **Option 1 (Formspree)** for the quickest setup!