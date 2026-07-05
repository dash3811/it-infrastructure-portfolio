# Case Study: Reverse Proxy / SSL Issue

## Problem

A self-hosted application was not loading correctly through HTTPS.

## Symptoms

- Browser displayed SSL or redirect errors
- Service worked locally but failed through the public hostname
- Reverse proxy logs showed connection or certificate issues

## Diagnosis

- Reviewed reverse proxy host configuration
- Verified SSL certificate status
- Checked DNS records
- Confirmed backend service port and protocol
- Reviewed application base URL / trusted proxy settings

## Tools Used

- Nginx Proxy Manager logs
- Browser developer tools
- DNS lookup tools
- Container logs
- Cloudflare dashboard

## Root Cause

Sanitized placeholder: mismatch between DNS, proxy configuration, SSL settings, or backend service protocol.

## Resolution

Sanitized placeholder: corrected proxy host settings, validated SSL certificate, and confirmed backend connectivity.

## Prevention

- Document service ports and protocols
- Use a standard reverse proxy checklist
- Validate DNS and certificate status after changes
