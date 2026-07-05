# Case Study: DNS Resolution Issue

## Problem

A self-hosted service was not reachable by hostname from a networked computer, even though the service appeared to be online.

## Symptoms

- Hostname did not resolve consistently from internal clients
- Service was reachable by IP in some situations
- External DNS records appeared correct
- Browser access failed from local network

## Diagnosis

- Verified DNS resolution using `nslookup`
- Tested ICMP connectivity using `ping`
- Compared internal and external DNS behavior
- Reviewed router/DNS configuration
- Checked whether local DNS overrides or split-horizon DNS were required

## Tools Used

- `nslookup`
- `ping`
- Router/DNS dashboard
- Browser testing
- DNS record review

## Root Cause

Sanitized placeholder: local network clients were not resolving the service through the intended internal DNS path.

## Resolution

Sanitized placeholder: corrected internal DNS handling and verified client resolution behavior.

## Prevention

- Document internal DNS records
- Maintain consistent DNS source for local clients
- Validate DNS after router, VLAN, or DHCP changes
