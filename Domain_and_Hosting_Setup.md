# Domain & Hosting Setup Guide

## 1. Domain Registration

### Step 1: Choose Your Domain Name

**Best Practices for Domain Selection:**
- Keep it short (2-3 words max)
- Make it memorable and easy to spell
- Include your main keyword if possible
- Avoid hyphens and numbers when possible
- Use .com if available (most trusted)
- Alternative extensions: .co, .business, .io, .net

**Domain Name Examples:**
```
yourbusiness.com          ✓ Good
your-business.com         ○ Acceptable
yourbiz.com              ✓ Good
yourBusinessServices.com  ✗ Too long
```

### Step 2: Register Your Domain

**Recommended Domain Registrars:**

1. **Namecheap** (Best overall)
   - Cheap domain pricing
   - Free WHOIS protection
   - Good customer support
   - Go to: namecheap.com

2. **GoDaddy** (Largest registrar)
   - Wide availability
   - Bundle deals with hosting
   - 24/7 support
   - Go to: godaddy.com

3. **Google Domains** (Simple & integrated)
   - Google-backed
   - Excellent support
   - Automatic DNS forwarding
   - Go to: domains.google.com

4. **Bluehost** (Great for WordPress)
   - Domain + hosting bundle
   - One-click WordPress install
   - 24/7 support
   - Go to: bluehost.com

### Step 3: Domain Registration Process

1. Go to registrar website
2. Search for your desired domain
3. Add to cart
4. Create account or login
5. Review privacy/WHOIS protection options
6. Add domain lock (security feature)
7. Complete payment
8. Verify email address
9. Access domain management panel

### Step 4: DNS Settings

**Access DNS Settings:**
1. Log into domain registrar account
2. Find "Domain Management" or "DNS Settings"
3. Note current nameservers
4. Keep these credentials safe

**Key DNS Records to Know:**

```
A Record: Points to website IP address
CNAME: Alias for another domain
MX Records: Direct email routing
TXT Records: Verification & security
NS Records: Nameserver addresses
```

---

## 2. Web Hosting Selection

### Hosting Types Comparison

| Type | Best For | Cost | Technical Level |
|------|----------|------|-----------------|
| Shared Hosting | Small sites, blogs | $5-10/mo | Beginner |
| VPS | Growing businesses | $20-50/mo | Intermediate |
| Dedicated Server | High traffic | $50-200/mo | Advanced |
| Cloud Hosting | Scalable apps | $10-100/mo | Intermediate |
| Managed WordPress | WordPress sites | $10-30/mo | Beginner |

### Recommended Hosting Providers

**1. Bluehost (Best for WordPress)**
- Domain: $2.95/month (first year)
- Hosting: $4.95-$29.99/month
- Features: One-click WordPress, free SSL, automatic backups
- Best for: Small-medium WordPress sites
- Website: bluehost.com

**2. SiteGround**
- Domain: $2.00/year (via ICANN)
- Hosting: $4.99-$19.99/month
- Features: Excellent support, security tools, backups
- Best for: Small-medium WordPress sites
- Website: siteground.com

**3. Namecheap Hosting**
- Features: Cheap shared hosting, easy control panel
- Hosting: $2.88-$7.77/month
- Best for: Budget-conscious users
- Website: namecheap.com/hosting

**4. WP Engine**
- Premium WordPress hosting
- Hosting: $20-$115/month (and up)
- Features: Automatic updates, security, performance optimization
- Best for: Professional WordPress sites
- Website: wpengine.com

**5. DreamHost**
- Domain: Free with hosting
- Hosting: $3.95-$9.95/month
- Features: Unlimited bandwidth, free SSL, WordPress pre-installed
- Best for: Small-medium WordPress sites
- Website: dreamhost.com

**6. Kinsta (Premium Cloud Hosting)**
- Premium WordPress hosting
- Hosting: $35-$600/month
- Features: Top-tier performance, security, 24/7 support
- Best for: High-performance WordPress sites
- Website: kinsta.com

---

## 3. Hosting Setup Process

### Step 1: Choose Hosting Plan

1. Compare features and pricing
2. Decide between shared, VPS, or cloud hosting
3. Check storage capacity (at least 50GB recommended)
4. Verify bandwidth limits (unlimited recommended)
5. Confirm SSL certificate inclusion
6. Check backup policies

### Step 2: Sign Up for Hosting

1. Go to hosting provider website
2. Select your hosting plan
3. Choose billing period (annual = better price)
4. Enter domain information
5. Create hosting account
6. Complete payment
7. Receive hosting credentials

### Step 3: Connect Domain to Hosting

**Option A: Use Registrar's Nameservers**
1. Log into domain registrar account
2. Go to DNS/Nameserver settings
3. Update to hosting provider's nameservers (provided by host)
4. Example nameservers:
   ```
   ns1.hostingprovider.com
   ns2.hostingprovider.com
   ```
5. Save changes
6. Wait 24-48 hours for propagation

**Option B: Point DNS Records**
1. Log into domain registrar
2. Find DNS/A Records settings
3. Point A record to hosting IP address
4. Keep MX records for email
5. Save settings
6. Wait 24-48 hours for propagation

### Step 4: Access Hosting Control Panel

1. Log into hosting account
2. Navigate to "cPanel" or hosting dashboard
3. Common options:
   - File Manager
   - Databases
   - Email Accounts
   - SSL/TLS
   - Backups
   - Domains

### Step 5: Install Website Platform

**For WordPress (Recommended):**
1. In cPanel, find "WordPress" or "Softaculous"
2. Click "Install"
3. Choose domain
4. Set admin username/password
5. Click install
6. Wait 5-10 minutes
7. Access wp-admin at yourdomain.com/wp-admin

**For HTML/CSS Website:**
1. Use File Manager in cPanel
2. Upload files to public_html folder
3. Name main file "index.html"
4. Wait for propagation
5. Visit yourdomain.com

---

## 4. SSL Certificate Setup

### What is SSL?

SSL encrypts data between browser and server, enabling HTTPS. Essential for trust and SEO.

### Installing SSL Certificate

**Option A: Free Let's Encrypt (Recommended)**

1. Log into hosting control panel
2. Find "AutoSSL" or "Let's Encrypt"
3. Click "Auto Install"
4. Select your domain
5. Click install
6. Wait 5-30 minutes
7. Your site now runs on HTTPS

**Option B: Premium SSL Certificates**

1. Log into hosting control panel
2. Find "SSL Certificates"
3. Purchase certificate (Comodo, DigiCert, etc.)
4. Add domain information
5. Verify domain (usually via email)
6. Wait for certificate
7. Install in control panel

### Verify SSL is Working

1. Visit https://yourdomain.com
2. Check for green lock icon
3. Verify no warnings
4. Test with: https://www.sslshopper.com/ssl-checker.html

---

## 5. Post-Setup Configuration

### Email Setup

1. In cPanel, find "Email Accounts" or "Mail Accounts"
2. Add email account with your domain
3. Set password
4. Configure MX records
5. Test email forwarding

### Database Setup

1. Go to "MySQL Databases" in cPanel
2. Create new database
3. Create database user
4. Assign user to database
5. Note credentials for application use

### Backup Configuration

1. Check hosting backup policy
2. Enable automatic backups if available
3. Set backup frequency (daily recommended)
4. Test backup restoration

### Performance Settings

1. Enable caching (if available)
2. Enable Gzip compression
3. Optimize images
4. Minimize CSS/JavaScript
5. Use CDN (Content Delivery Network)

---

## 6. Subdomain Setup (Optional)

### Create Subdomains

1. In cPanel, find "Addon Domains" or "Subdomains"
2. Enter subdomain name (e.g., "blog")
3. Full domain becomes: blog.yourbusiness.com
4. Select document root folder
5. Click "Create"

### Common Subdomains

```
www.yourbusiness.com        - Main site
blog.yourbusiness.com       - Blog section
shop.yourbusiness.com       - E-commerce
support.yourbusiness.com    - Support portal
api.yourbusiness.com        - API endpoint
```

---

## 7. Domain Propagation

### What is Propagation?

DNS changes take time to spread across the internet (24-48 hours).

### Check Propagation Status

1. During propagation, some users may see old site
2. Use: https://dnschecker.org
3. Monitor global DNS spread
4. Check status across multiple locations

### Propagation Timeline

```
0-6 hours:    20-30% of servers updated
6-12 hours:   50-60% of servers updated
12-24 hours:  80-90% of servers updated
24-48 hours:  99%+ of servers updated
```

---

## 8. Domain Renewal & Management

### Important Domain Dates

- **Expiration Date**: When domain registration expires
- **Renewal Date**: When you should renew (ideally before expiration)
- **Grace Period**: 18 days after expiration to renew without penalty
- **Redemption**: 40 days after expiration to recover (with fee)

### Auto-Renewal Setup

1. Log into domain registrar
2. Find domain settings
3. Enable "Auto-Renewal"
4. Confirm payment method is valid
5. Your domain auto-renews before expiration

### Domain Transfer (If Needed)

1. Unlock domain in current registrar
2. Get authorization code (EPP code)
3. Go to new registrar
4. Initiate transfer
5. Enter authorization code
6. Approve transfer via email
7. Wait 5-7 days for completion

---

## 9. Security Best Practices

### Domain Security

1. **Use WHOIS Privacy** (included with most registrars)
   - Hides your personal information
   - Protects from spam

2. **Enable Domain Lock**
   - Prevents unauthorized transfers
   - Available in all registrar control panels

3. **Set Up Domain Alerts**
   - Get notifications of changes
   - Monitor for unauthorized access

4. **Use Strong Passwords**
   - Unique password for domain account
   - Unique password for hosting account
   - Unique password for email

### Hosting Security

1. Keep WordPress/platform updated
2. Install security plugins
3. Use Web Application Firewall (WAF)
4. Regular backups (daily minimum)
5. Strong passwords for all accounts
6. Two-factor authentication enabled

---

## 10. Troubleshooting

### Domain Not Connecting

1. Check DNS propagation (dnschecker.org)
2. Verify nameservers in registrar
3. Allow 48 hours for propagation
4. Check hosting account is active
5. Contact support if still issues

### HTTPS Not Working

1. Check SSL certificate is installed
2. Verify certificate is for correct domain
3. Check no mixed content (http + https)
4. Clear browser cache
5. Try different browser
6. Contact hosting support

### Email Not Working

1. Check MX records are correct
2. Verify email account is created
3. Check DNS propagation
4. Verify no spam filters blocking
5. Test with different email client
6. Check with ISP blocklists

### Site is Slow

1. Check hosting server load
2. Enable caching (plugin or server-level)
3. Optimize images (compress)
4. Use CDN service
5. Upgrade hosting plan if needed
6. Minify CSS/JavaScript

---

## Cost Estimate (First Year)

| Item | Cost | Notes |
|------|------|-------|
| Domain | $10-20 | Usually discounted first year |
| Hosting | $60-120/year | Basic shared hosting |
| SSL | Free-$100 | Let's Encrypt is free |
| Email | Free-$20/month | If using Google Workspace |
| **Total** | **$130-220/year** | Basic setup |

---

## Recommended Timeline

| Task | Timeline |
|------|----------|
| Register Domain | Day 1 |
| Choose Hosting | Day 1-2 |
| Connect Domain | Day 2-3 |
| Install SSL (auto) | Day 3 |
| Setup Email | Day 3-4 |
| Install Platform | Day 4-5 |
| Create Content | Day 5-10 |
| Test Everything | Day 10-11 |
| Launch | Day 11-12 |

**Total Setup Time: 2 weeks**
