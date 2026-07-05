# Sanitization Checklist

Before publishing anything, confirm that you removed or replaced:

## Credentials

- Passwords
- API keys
- Tokens
- Secret keys
- Cloudflare tokens
- Home Assistant long-lived access tokens
- VPN keys
- Database passwords

## Network Details

- Public IP addresses
- Real internal IP addresses
- MAC addresses
- Router serial numbers
- Wi-Fi SSIDs
- Wi-Fi passwords
- VPN configuration files

## Personal Details

- Home address
- Camera screenshots showing private areas
- Phone numbers
- Personal emails, unless intentionally used professionally
- Family, guest, or roommate names
- Device names that reveal private information

## Domains and Hostnames

Replace real values with:

```text
example.com
service.example.com
host.example.local
10.0.X.0/24
REDACTED
```

## Final Review

- Open every Markdown file
- Search for sensitive words
- Review every image
- Remove metadata from screenshots if needed
- Never publish `.env` files
