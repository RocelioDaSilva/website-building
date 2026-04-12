# Email Configuration & Integration Guide

## 1. Professional Email Setup

### Option A: Google Workspace (Recommended for Small-Medium Businesses)

**Step 1: Purchase Google Workspace**
1. Go to [workspace.google.com](https://workspace.google.com)
2. Click "Get started"
3. Enter your business domain (e.g., yourbusiness.com)
4. Choose a plan (Business Starter: $7/user/month recommended)
5. Follow the setup wizard

**Step 2: Verify Domain Ownership**
1. In Google Workspace admin console, go to "Domains"
2. Click "Add domain"
3. Verify ownership by adding DNS records provided by Google
4. Update your domain registrar's DNS settings

**Step 3: Create Email Accounts**
1. Go to "Users and accounts" in Admin console
2. Click "Add the user"
3. Create accounts for team members (e.g., info@yourbusiness.com, support@yourbusiness.com)
4. Set temporary passwords

**Step 4: MX Records Configuration**
1. Log into your domain registrar (GoDaddy, Namecheap, etc.)
2. Add MX records provided by Google:
   ```
   Priority 5: gmail-smtp-in.l.google.com
   Priority 10: alt1.gmail-smtp-in.l.google.com
   Priority 20: alt2.gmail-smtp-in.l.google.com
   Priority 30: alt3.gmail-smtp-in.l.google.com
   Priority 40: alt4.gmail-smtp-in.l.google.com
   ```
3. Add SPF record: `v=spf1 include:_spf.google.com ~all`
4. Add DKIM records as provided by Google

**Step 5: Email Implementation on Website**
1. Update contact form backend to send from professional email
2. Update auto-reply email address
3. Test email delivery

---

### Option B: Microsoft 365 (For Advanced Features)

**Step 1: Purchase Microsoft 365**
1. Go to [microsoft365.com/business](https://microsoft365.com/business)
2. Choose Business Basic or Business Standard
3. Enter your business domain
4. Follow the setup wizard

**Step 2: Domain Verification**
1. In Microsoft 365 admin center, verify domain ownership
2. Add TXT records to your domain registrar

**Step 3: Configure DNS Records**
- MX records for email routing
- SPF records for authentication
- DKIM for email signing
- DMARC for email protection

**Step 4: Create Mailboxes**
1. In admin center, create email addresses
2. Assign to team members
3. Configure forwarding rules

---

### Option C: Zoho Mail (Budget-Friendly)

**Step 1: Sign Up**
1. Go to [zoho.com/mail](https://zoho.com/mail)
2. Create account with your domain name
3. Choose free or paid plan

**Step 2: Verify Domain**
1. Add DNS records provided by Zoho
2. Wait for verification (can take 24-48 hours)

**Step 3: Create Email Accounts**
1. Add user accounts in Zoho Mail
2. Configure forwarding if needed

**Step 4: Configure SPF & DKIM**
1. Add SPF record: `v=spf1 include:zohomail.com ~all`
2. Enable DKIM signing in settings

---

## 2. Email Integration with Website Contact Form

### Node.js/Express Example

```javascript
const nodemailer = require('nodemailer');

// Configure transporter
const transporter = nodemailer.createTransport({
    host: 'smtp.gmail.com',
    port: 465,
    secure: true,
    auth: {
        user: process.env.EMAIL_USER,
        pass: process.env.EMAIL_PASSWORD
    }
});

// Function to send contact form email
async function sendContactEmail(name, email, subject, message) {
    try {
        await transporter.sendMail({
            from: 'info@yourbusiness.com',
            to: 'info@yourbusiness.com',
            replyTo: email,
            subject: `New Contact: ${subject}`,
            html: `
                <h2>New Contact Form Submission</h2>
                <p><strong>Name:</strong> ${name}</p>
                <p><strong>Email:</strong> ${email}</p>
                <p><strong>Subject:</strong> ${subject}</p>
                <p><strong>Message:</strong></p>
                <p>${message.replace(/\n/g, '<br>')}</p>
            `
        });
        
        // Send confirmation to user
        await transporter.sendMail({
            from: 'info@yourbusiness.com',
            to: email,
            subject: 'We received your message',
            html: `
                <h2>Thank You for Contacting Us</h2>
                <p>Hi ${name},</p>
                <p>We received your message and will get back to you shortly.</p>
                <p>Best regards,<br>YourBusiness Team</p>
            `
        });
        
        return { success: true };
    } catch (error) {
        console.error('Email error:', error);
        return { success: false, error: error.message };
    }
}

module.exports = { sendContactEmail };
```

### Python/Flask Example

```python
from flask import Flask
from flask_mail import Mail, Message
import os

app = Flask(__name__)

# Configure email
app.config['MAIL_SERVER'] = 'smtp.gmail.com'
app.config['MAIL_PORT'] = 465
app.config['MAIL_USE_SSL'] = True
app.config['MAIL_USERNAME'] = os.environ.get('MAIL_USERNAME')
app.config['MAIL_PASSWORD'] = os.environ.get('MAIL_PASSWORD')

mail = Mail(app)

def send_contact_email(name, email, subject, message):
    try:
        # Email to business
        msg = Message(
            subject=f'New Contact: {subject}',
            sender='info@yourbusiness.com',
            recipients=['info@yourbusiness.com'],
            reply_to=email,
            html=f'''
                <h2>New Contact Form Submission</h2>
                <p><strong>Name:</strong> {name}</p>
                <p><strong>Email:</strong> {email}</p>
                <p><strong>Subject:</strong> {subject}</p>
                <p><strong>Message:</strong></p>
                <p>{message.replace(chr(10), '<br>')}</p>
            '''
        )
        mail.send(msg)
        
        # Confirmation email to user
        confirmation = Message(
            subject='We received your message',
            sender='info@yourbusiness.com',
            recipients=[email],
            html=f'''
                <h2>Thank You for Contacting Us</h2>
                <p>Hi {name},</p>
                <p>We received your message and will get back to you shortly.</p>
                <p>Best regards,<br>YourBusiness Team</p>
            '''
        )
        mail.send(confirmation)
        
        return {'success': True}
    except Exception as e:
        return {'success': False, 'error': str(e)}
```

---

## 3. Email Signature Template

### HTML Email Signature

```html
<div style="font-family: Arial, sans-serif; font-size: 14px; color: #333;">
    <strong style="color: #003366; font-size: 16px;">John Smith</strong><br>
    <span style="color: #ff0000; font-weight: bold;">CEO & Founder</span><br>
    <a style="color: #003366; text-decoration: none;" href="https://yourbusiness.com">YourBusiness</a><br>
    <br>
    <span style="color: #666;">📧 john@yourbusiness.com</span><br>
    <span style="color: #666;">📱 (555) 123-4567</span><br>
    <span style="color: #666;">🌐 www.yourbusiness.com</span><br>
    <br>
    <a href="https://yourbusiness.com" style="margin-right: 10px;">
        <img src="https://yourbusiness.com/logo.png" alt="YourBusiness" height="30">
    </a>
</div>
```

---

## 4. Auto-Reply Email Template

```
Subject: Thank you for your email

Hi [Name],

Thank you for reaching out to YourBusiness. We've received your message and appreciate you taking the time to contact us.

We typically respond to inquiries within 24 business hours. If your matter is urgent, please call us at [phone number].

Best regards,
YourBusiness Team
[email@yourbusiness.com]
[phone]
[website]
```

---

## 5. Email Best Practices for Business

### Authentication Setup

1. **SPF (Sender Policy Framework)**
   - Authenticates domain ownership
   - Add to DNS: `v=spf1 include:[email-service] ~all`

2. **DKIM (DomainKeys Identified Mail)**
   - Digitally signs emails
   - Configure in email provider settings

3. **DMARC (Domain-based Message Authentication)**
   - Establishes policy for SPF/DKIM
   - Add to DNS starting with: `v=DMARC1; p=quarantine;`

### Email Deliverability Tips

- Keep sender name consistent (e.g., always "YourBusiness")
- Use clear, professional subject lines
- Avoid spam trigger words (FREE, BUY NOW, ACT NOW)
- Include unsubscribe link for newsletters
- Monitor bounce rates
- Keep list clean and remove inactive addresses
- Use plain text and HTML versions

### Important Email Addresses to Create

```
info@yourbusiness.com           - General inquiries
support@yourbusiness.com        - Customer support
sales@yourbusiness.com          - Sales inquiries
noreply@yourbusiness.com        - Automated notifications
hello@yourbusiness.com          - Friendly greeting email
contact@yourbusiness.com        - General contact
newsletter@yourbusiness.com     - Newsletter sender
```

---

## 6. Email Management Best Practices

### Email Organization

1. **Create folders:**
   - Sent
   - Archives
   - Spam/Junk filter
   - Important/Starred

2. **Set up filters** for automatic organization
3. **Create labels** for project tracking
4. **Schedule check times** (e.g., 9am, 12pm, 3pm)

### Response Time Standards

- Urgent: Within 2 hours
- Normal: Within 24 hours
- General inquiry: Within 48 hours

### Email Templates for Common Responses

Create templates for:
- Greeting new clients
- Responding to proposals
- Follow-up emails
- Thank you messages
- Out of office messages

---

## 7. Troubleshooting Email Issues

### Email Not Sending

1. Check SMTP settings
2. Verify credentials are correct
3. Check firewall/antivirus settings
4. Verify DNS records
5. Check email provider status page

### Emails Going to Spam

1. Verify SPF record is set up
2. Configure DKIM signing
3. Set up DMARC policy
4. Use consistent sender name
5. Avoid trigger words
6. Monitor spam reports

### Slow Email Delivery

1. Check server load
2. Verify DNS settings
3. Check recipient server status
4. Review email size (keep under 25MB)
5. Contact email provider support

---

## 8. Email Security

### Protect Your Email Account

1. Use strong, unique password (16+ characters)
2. Enable two-factor authentication
3. Review account recovery options
4. Monitor login activity
5. Never share credentials
6. Use VPN for public WiFi access

### Email Forwarding Setup

```
Original: john@yourbusiness.com
Forward to: john.personal@gmail.com
```

### Backup Important Emails

- Use Google Takeout for Gmail backups
- Download archive regularly
- Store securely locally

---

## 9. Integration with Website Contact Form

### Contact Form Code Example (HTML)

```html
<form action="/api/contact" method="POST">
    <input type="text" name="name" placeholder="Your Name" required>
    <input type="email" name="email" placeholder="Your Email" required>
    <input type="text" name="subject" placeholder="Subject" required>
    <textarea name="message" placeholder="Your Message" required></textarea>
    <button type="submit">Send Message</button>
</form>
```

### Backend Processing

1. Validate form data
2. Send confirmation email to user
3. Send notification email to business
4. Store in database
5. Return confirmation message

---

## Environmental Variables Template

Create `.env` file in project root:

```
MAIL_SERVER=smtp.gmail.com
MAIL_PORT=465
MAIL_USE_SSL=true
MAIL_USERNAME=your-email@yourbusiness.com
MAIL_PASSWORD=your-app-password
BUSINESS_EMAIL=info@yourbusiness.com
```

**Important:** Never commit .env to version control!

---

## Testing Your Email Setup

1. Send test email to yourself
2. Verify it arrives in inbox (not spam)
3. Check email authentication (DKIM, SPF)
4. Test reply functionality
5. Test with spam check tools
6. Verify signature formatting
7. Test on multiple email clients

---

**Estimated Setup Time:** 2-4 hours for full configuration
**Ongoing Maintenance:** 5-10 minutes daily for management
