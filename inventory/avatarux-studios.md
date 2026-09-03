# AvatarUX Studios inventory (discovery seed 2026-09-02)
# NOTE: hosts below are discovery candidates from passive DNS/CT; confirm in-scope vs program scope before active testing.
avatarux.com
mail.avatarux.com
www.avatarux.com

## PASSIVE RECON 2026-09-02 (read-only, non-intrusive)

> Recon observations only. These are NOT confirmed vulnerabilities; ownership/in-scope of each host must be confirmed against the program scope before any active testing. Hosts resolve + serve HTTP — investigation requires scoped authorization.

**Probed:** 3 hosts | **Live HTTP:** 1

| Host | Status | Server/Tech |
|---|---|---|
| `www.avatarux.com` | 301 | Server: cloudflare -> https://avatarux.com/ |

**CNAME review signals (1):**
- `www.avatarux.com` -> `secure.cloudways.cloud`

## DEEP SERVICE SCAN 2026-09-02 (read-only connect+banner)
**Host:** `www.avatarux.com` | **Ports:** [80, 443, 2082, 2083, 2086, 2087, 8080, 8443]
**Non-web ports observed:** [2082, 2083, 2086, 2087, 8080, 8443]
> NOTE: repeated identical non-web port sets (e.g. 2082,2083,2086,2087,8080,8443) across many hosts and wide port sets are likely a shared edge/proxy answering EOF, NOT confirmed real services. Verify with a proper port scanner (e.g. nmap) under authorization before treating as real. These are surface-map hints only, not findings.

## DEEP ENUM (wildcard-cleaned) 2026-09-03
**Root zone:** `avatarux.com` | **dedicated hosts after wildcard-filter: 6**
> Audit: brute+passive subfinder produced 10,083 resolving hostnames; zone-wildcard + IP-fingerprint filtering dropped 9,973 (98.9%) DNS-wildcard noise (random labels resolving to shared wildcard IPs e.g. account.cineplex.de, a.hypofriend.de, account.live-manager.de, docker.jtl-software.de, *.ggamdom.com, *.dev.alfaview.com). Only genuine dedicated hosts listed below. These are surface-map observations; live HTTP status captured read-only (GET / via curl). No findings claimed; scope must be confirmed with the program.
- `autoconfig.avatarux.com`  [HTTP 200]
- `autodiscover.avatarux.com`  [HTTP 400]
- `cpanel.avatarux.com`  [HTTP unprobed]
- `cpcalendars.avatarux.com`  [HTTP 500]
- `cpcontacts.avatarux.com`  [HTTP 500]
- `help.desk.avatarux.com`  [HTTP 302]

## 2026-09-02 21:53:50 UTC

## 2026-09-02 23:52:05 UTC

## 2026-09-03 02:58:06 UTC
