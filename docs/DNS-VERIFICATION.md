# DNS verification for OCode.js

This utility provides a browser-side DNS TXT challenge for `ocodejs.dev` (or another domain entered by the operator).

## Preview

When deployed from this branch, the page is available at:

- `/domain-verify/`

## Verification protocol

1. Open the page and generate a one-time random challenge.
2. Create a TXT record at `_ocodejs-verification.<domain>` with the exact generated value.
3. Wait for DNS propagation.
4. Press **Check public DNS**. The browser queries Cloudflare DNS-over-HTTPS and compares the returned TXT answers with the challenge.
5. A successful exact match demonstrates control of the DNS zone at the time of verification.

The challenge is generated and retained in the browser tab only. The page does not collect credentials, write DNS records, or send the challenge to an OCode.js backend. Keep the TXT record until the domain owner has completed any registrar/hosting verification that requires it.

## Important limitations

- This is a DNS control challenge, not domain registration or legal ownership proof.
- The page cannot create DNS records or access the registrar account.
- The check depends on public DNS propagation and the browser's ability to reach Cloudflare DoH.
- Do not change existing A, AAAA, CNAME, MX, NS, or nameserver settings as part of this TXT challenge.
- Do not publish a challenge for a domain unless you control its DNS zone.

## Current rollout status

- [x] Verification page added on a feature branch.
- [ ] Preview URL published and tested.
- [ ] Domain owner publishes the TXT challenge.
- [ ] Public DNS returns the exact challenge.
- [ ] Registrar/hosting provider confirms domain ownership if separately required.
- [ ] Custom domain DNS and HTTPS configured after the domain is registered and controlled.
