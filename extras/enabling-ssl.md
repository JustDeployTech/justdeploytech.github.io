---
title:  Enabling SSL
layout: default
nav_order: 3.8
parent: 🛸 Extras
---

# Enabling SSL with Cloudflare

This guide will walk you through the process of enabling SSL for your website using Cloudflare.

## Prerequisites

- A domain name
- A website hosted on a web server
- A Cloudflare account

## Steps to Enable SSL

1. Sign up for a Cloudflare account:
   - Go to [cloudflare.com](https://www.cloudflare.com) and create an account if you haven't already.

2. Add your website to Cloudflare:
   - After logging in, click on "Add a Site" and enter your domain name.
   - Follow the prompts to add your site to Cloudflare.

3. Update your domain's nameservers:
   - Cloudflare will provide you with new nameservers.
   - Log in to your domain registrar and replace the existing nameservers with the ones provided by Cloudflare.

4. Configure SSL settings:
   - In your Cloudflare dashboard, go to the "SSL/TLS" section.
   - Choose Flexible.

5. Enable HTTPS Rewrites:
   - In the Cloudflare dashboard, go to the "SSL/TLS" section.
   - Click on the "Edge Certificates" tab.
   - Scroll down to "Always Use HTTPS" and toggle it on.

6. Create Page Rules (optional):
   - In the Cloudflare dashboard, go to the "Rules" section.
   - Click on "Create Page Rule" and add a rule to force HTTPS:
     - URL pattern: `http://*yourdomain.com/*`
     - Then choose "Always Use HTTPS"

7. Wait for SSL to be provisioned:
   - Cloudflare will automatically provision and deploy an SSL certificate for your domain.
   - This process usually takes less than 15 minutes.

8. Test your SSL configuration:
   - Visit your website using `https://` to ensure it loads correctly.
   - You can also use online SSL checker tools to verify your configuration.

## Troubleshooting

If you encounter any issues:

- Make sure your nameservers are correctly set to Cloudflare's nameservers.
- Check that your SSL mode is appropriate for your setup.

By following these steps, you should have successfully enabled SSL for your website using Cloudflare, providing a secure connection for your visitors.
