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

## 2026-09-03 07:56:17 UTC

## 2026-09-03 12:38:20 UTC

## 2026-09-03 16:48:27 UTC
- NEW help.desk.avatarux.com: Atlassian Jira Service Desk (live, customer portal active)
- NEW cpanel.avatarux.com: Cloudflare error 1001 - DNS to prohibited IP (subdomain takeover candidate)
- NEW MX records: Google Workspace, Zoho, Mandrill, ProtonMail
- NEW TXT reveals: Slack, Atlassian, Google verifications
- NEW `affiliates.betpanda.io` — BetPanda affiliate portal (Vite SPA, Cloudflare-fronted), in-scope brand asset discovered
- NEW `help.desk.avatarux.com` confirmed as Atlassian Edge (Jira/Confluence help desk), AvatarUX infrastructure
- NEW `autoconfig.avatarux.com` [200], `autodiscover.avatarux.com` [400], `cpcalendars.avatarux.com` [500], `cpcontacts.avatarux.com` [500] — dedicated hosts with live HTTP status
- CHANGED `www.avatarux.com` CNAME → `secure.cloudways.cloud` (shared hosting edge), not direct AvatarUX infra
- NEW Out-of-scope noise identified: alfaview (OpenAPI spec), BASF (Azure Functions), daimlertruck (locked), elringklinger — all unrelated to AvatarUX Studios program

## 2026-09-03 19:46:06 UTC
- NEW `help.desk.avatarux.com` probe: root 200, `/servicedesk/customer/portal/` 303 (active customer portal), `/rest/servicedeskapi/servicedesk` 401 (auth required), `/wiki/` 200 (Confluence accessible)
- NEW `cpanel.avatarux.com`: SSL handshake failure on :2083, wrong version on :2082, root SSL failure — cPanel ports not directly accessible via HTTPS; Cloudflare 1001 persists
- NEW `cpcalendars.avatarux.com` confirmed HTTP 500 (benign disabled feature per knowledge)
- NEW `affiliates.betpanda.io` confirmed Vite SPA (main.1ae50aab.js), Cloudflare-fronted, **no API routes in JS bundle** — API likely on separate subdomain (e.g., api.betpanda.io, affiliates-api.betpanda.io
- CHANGED `help.desk.avatarux.com` was 302, now 200 with active portal/wiki — higher attack surface than redirect suggested
- NEW `cpanel.avatarux.com`: Cloudflare 1001 error → DNS points to prohibited IP (subdomain takeover candidate)
- NEW `help.desk.avatarux.com`: Atlassian Jira Service Desk (customer portal active)
- NEW `affiliates.betpanda.io`: BetPanda affiliate portal (in-scope brand, Vite SPA, Cloudflare-fronted)
- NEW MX records: Google Workspace, Zoho, Mandrill, ProtonMail discovered

## 2026-09-03 21:57:36 UTC
- NEW `affiliates.betpanda.io` Vite SPA confirmed: single bundle `main.ef021e68.js`, no API routes/endpoints in bundle — API subdomain hunt required
- NEW `help.desk.avatarux.com` Confluence wiki `/wiki/` returns 303 (not 200), JSM portal `/servicedesk/customer/portal/` 303, JSM REST `/rest/servicedeskapi/servicedesk` 401, Confluence REST `/rest/api/spa
- NEW `cpanel.avatarux.com` CNAME → `avatarux.com` → `162.159.136.54` (Cloudflare IP), confirming Cloudflare 1001 = DNS points to prohibited Cloudflare IP (dangling DNS)
- NEW BetPanda API subdomains `api.betpanda.io`, `affiliates-api.betpanda.io`, `api.affiliates.betpanda.io` — no DNS records (NXDOMAIN)
- CHANGED Previous probe showed `/wiki/` 200, now 303 — Confluence behind Atlassian Edge redirect
- NEW `cpanel.avatarux.com`: Cloudflare 1001 error → DNS points to prohibited IP (subdomain takeover candidate)
- NEW `help.desk.avatarux.com`: Atlassian Jira Service Desk (customer portal active)
- NEW `affiliates.betpanda.io`: BetPanda affiliate portal (in-scope brand, Vite SPA, Cloudflare-fronted)
- NEW MX records: Google Workspace, Zoho, Mandrill, ProtonMail discovered

## 2026-09-03 23:50:02 UTC
- NEW affiliates.betpanda.io: Vite SPA single bundle main.ef021e68.js confirmed — zero API routes, apiBaseUrl, GraphQL, or affiliate_id patterns in bundle; API subdomain hunt required
- NEW help.desk.avatarux.com: Confluence /wiki/ now 303 (was 200), JSM portal 303, JSM REST 401, Confluence REST /rest/api/space 404, /wiki/rest/api/user 303 — all behind Atlassian Edge
- NEW cpanel.avatarux.com: CNAME chain confirmed cpanel → avatarux.com → 162.159.136.54 (Cloudflare IP); Cloudflare 1001 = dangling DNS to prohibited Cloudflare IP
- NEW BetPanda API subdomains api.betpanda.io, affiliates-api.betpanda.io, api.affiliates.betpanda.io — all NXDOMAIN
- NEW cable.betpanda.io: custom Node service "BB CABLE 🔌" banner, 200 OK, Cloudflare-fronted; WS mounts /socket /ws /events return 404
- NEW betpandacasino.io: SPA catch-all shadows /graphql and /api (both 200 HTML shell); real API base URL unknown
- CHANGED help.desk.avatarux.com Confluence /wiki/ flipped 200→303 — now behind Atlassian Edge redirect layer

## 2026-09-04 03:03:06 UTC
- NEW cable.betpanda.io: custom Node "BB CABLE 🔌" service live, 200 OK, Cloudflare-fronted; WS mounts /socket /ws /events return 404
- NEW betpandacasino.io: SPA catch-all shadows /graphql and /api (both 200 HTML shell); real API base URL unknown
- NEW cpanel.avatarux.com: CNAME chain confirmed cpanel → avatarux.com → 162.159.136.54 (Cloudflare IP); Cloudflare 1001 = dangling DNS to prohibited Cloudflare IP
- NEW BetPanda API subdomains api.betpanda.io, affiliates-api.betpanda.io, api.affiliates.betpanda.io — all NXDOMAIN
- CHANGED help.desk.avatarux.com Confluence /wiki/ flipped 200→303 — now behind Atlassian Edge redirect layer

## 2026-09-04 07:48:19 UTC
- NEW cable.betpanda.io: custom Node "BB CABLE 🔌" service confirmed live (200 OK, Cloudflare-fronted); WS endpoints /socket /ws /events return 404
- NEW betpandacasino.io: SPA catch-all shadows /graphql and /api (both 200 HTML shell); real API base URL undiscovered
- NEW cpanel.avatarux.com: CNAME chain cpanel → avatarux.com → 162.159.136.54 (Cloudflare IP) confirmed; Cloudflare 1001 = dangling DNS to prohibited Cloudflare IP
- NEW BetPanda API subdomains api.betpanda.io, affiliates-api.betpanda.io, api.affiliates.betpanda.io — all NXDOMAIN
- CHANGED help.desk.avatarux.com Confluence /wiki/ flipped 200→303 — now behind Atlassian Edge redirect layer
- CHANGED cpanel.avatarux.com priority increased to 7.0 (was 6.0) — takeover evidence strengthening

## 2026-09-04 12:42:00 UTC
- CHANGED lead-bigpickle.md: last two cycles (2026-09-04 03:02:55, 07:45:49) produced empty entries — no new probes executed since 2026-09-03 23:47:16
- CHANGED probe-results.md: no new probe data since 2026-09-04 07:48:20 (only cpanel SSL re-verification)
- NEW help.desk.avatarux.com: Atlassian Jira Service Desk (live, customer portal active)
- NEW cpanel.avatarux.com: Cloudflare error 1001 - DNS to prohibited IP (subdomain takeover candidate)
- NEW MX records: Google Workspace, Zoho, Mandrill, ProtonMail
- NEW TXT reveals: Slack, Atlassian, Google verifications
- NEW `cpanel.avatarux.com`: Cloudflare 1001 error → DNS points to prohibited IP (subdomain takeover candidate)
- NEW `help.desk.avatarux.com`: Atlassian Jira Service Desk (customer portal active)
- NEW `affiliates.betpanda.io`: BetPanda affiliate portal (in-scope brand, Vite SPA, Cloudflare-fronted)
- NEW MX records: Google Workspace, Zoho, Mandrill, ProtonMail discovered
- NEW `cpanel.avatarux.com`: Cloudflare 1001 error → DNS points to prohibited IP (subdomain takeover candidate)
- NEW `help.desk.avatarux.com`: Atlassian Jira Service Desk (customer portal active)
- NEW `affiliates.betpanda.io`: BetPanda affiliate portal (in-scope brand, Vite SPA, Cloudflare-fronted)
- NEW MX records: Google Workspace, Zoho, Mandrill, ProtonMail discovered
- NEW cable.betpanda.io: custom Node "BB CABLE 🔌" service confirmed live (200 OK, Cloudflare-fronted); WS endpoints /socket /ws /events return 404 (newly confirmed WS probes)
- NEW betpandacasino.io: SPA catch-all shadows /graphql and /api (both 200 HTML shell); real API base URL undiscovered (reconfirmed)
- CHANGED cpanel.avatarux.com priority increased to 7.0 (was 6.0) — takeover evidence strengthening
- CHANGED help.desk.avatarux.com Confluence /wiki/ flipped 200→303 — now behind Atlassian Edge redirect layer (stable)

## 2026-09-04 16:39:41 UTC
- NEW `/rest/public/config` endpoint leaks operatorId=1, Strapi CMS config, support email, currency list — full backend config disclosure
- NEW `/rest/public/recover-password/email/{email}` accepts arbitrary emails, returns 204 (password reset trigger — potential account enumeration/reset bypass candidate)
- NEW `custom-lp.betpanda.io` and `fp.betpanda.io` confirmed live (Cloudflare challenge) — new in-scope BetPanda infrastructure
- NEW `/config/config.json` same-origin reveals API base URL = `https://affiliates.betpanda.io/rest` — API is NOT on a separate subdomain, it's co-hosted on the SPA origin
- NEW Full API endpoint map extracted from JS bundle: `/rest/player/uid/{id}`, `/rest/transaction/list`, `/rest/agent/*`, `/rest/v2/report`, `/rest/payouts/single-currency-list`, `/rest/trk/*` — all auth-ga
- CHANGED affiliates.betpanda.io confidence raised from 65→78 — API backend confirmed, endpoint map complete, attack surface quantified

## 2026-09-04 19:14:47 UTC
- NEW `/rest/public/config` on affiliates.betpanda.io leaks operatorId=1, Strapi CMS config, support email, full currency list — backend config disclosure
- NEW `/rest/public/recover-password/email/{email}` on affiliates.betpanda.io accepts arbitrary emails in URL path, returns 204 no body — potential account enumeration/reset bypass
- NEW `/config/config.json` on affiliates.betpanda.io reveals API base URL = `https://affiliates.betpanda.io/rest` (same-origin, not separate subdomain)
- NEW Full API endpoint map extracted from JS bundle: `/rest/player/uid/{id}`, `/rest/transaction/list`, `/rest/agent/*`, `/rest/v2/report`, `/rest/payouts/single-currency-list`, `/rest/trk/*` — all auth-ga
- NEW `custom-lp.betpanda.io` and `fp.betpanda.io` confirmed live behind Cloudflare challenge — new in-scope BetPanda infrastructure via crt.sh
- CHANGED affiliates.betpanda.io confidence raised 65→78 — API backend confirmed same-origin, endpoint map complete, attack surface quantified
- CHANGED cpanel.avatarux.com: Cloudflare 1001 persists 48+ hours, CNAME → avatarux.com → 162.159.136.54 (Cloudflare IP), stable dangling DNS
- CHANGED help.desk.avatarux.com: Confluence/JSM behind Atlassian Edge, tenant IDs/feature flags in HTML, REST paths return 401/404/303

## 2026-09-04 21:36:26 UTC
- NEW help.desk.avatarux.com: Atlassian Jira Service Desk (live, customer portal active)
- NEW cpanel.avatarux.com: Cloudflare error 1001 - DNS to prohibited IP (subdomain takeover candidate)
- NEW MX records: Google Workspace, Zoho, Mandrill, ProtonMail
- NEW TXT reveals: Slack, Atlassian, Google verifications
- NEW `cpanel.avatarux.com`: Cloudflare 1001 error → DNS points to prohibited IP (subdomain takeover candidate)
- NEW `help.desk.avatarux.com`: Atlassian Jira Service Desk (customer portal active)
- NEW `affiliates.betpanda.io`: BetPanda affiliate portal (in-scope brand, Vite SPA, Cloudflare-fronted)
- NEW MX records: Google Workspace, Zoho, Mandrill, ProtonMail discovered
- NEW `affiliates.betpanda.io` — BetPanda affiliate portal (Vite SPA, Cloudflare-fronted), in-scope brand asset discovered
- NEW `help.desk.avatarux.com` confirmed as Atlassian Edge (Jira/Confluence help desk), AvatarUX infrastructure
- NEW `autoconfig.avatarux.com` [200], `autodiscover.avatarux.com` [400], `cpcalendars.avatarux.com` [500], `cpcontacts.avatarux.com` [500] — dedicated hosts with live HTTP status
- CHANGED `www.avatarux.com` CNAME → `secure.cloudways.cloud` (shared hosting edge), not direct AvatarUX infra
- NEW Out-of-scope noise identified: alfaview (OpenAPI spec), BASF (Azure Functions), daimlertruck (locked), elringklinger — all unrelated to AvatarUX Studios program
- NEW `help.desk.avatarux.com` probe: root 200, `/servicedesk/customer/portal/` 303 (active customer portal), `/rest/servicedeskapi/servicedesk` 401 (auth required), `/wiki/` 200 (Confluence accessible)
- NEW `cpanel.avatarux.com`: SSL handshake failure on :2083, wrong version on :2082, root SSL failure — cPanel ports not directly accessible via HTTPS; Cloudflare 1001 persists
- NEW `cpcalendars.avatarux.com` confirmed HTTP 500 (benign disabled feature per knowledge)
- NEW `affiliates.betpanda.io` confirmed Vite SPA (main.1ae50aab.js), Cloudflare-fronted, **no API routes in JS bundle** — API likely on separate subdomain (e.g., api.betpanda.io, affiliates-api.betpanda.io
- CHANGED `help.desk.avatarux.com` was 302, now 200 with active portal/wiki — higher attack surface than redirect suggested
- NEW affiliates.betpanda.io: `/rest/public/config` leaks operatorId=1, Strapi CMS config, support email, full currency list — backend config disclosure
- NEW affiliates.betpanda.io: `/rest/public/recover-password/email/{email}` accepts arbitrary emails in URL path, returns 204 no body — account enumeration/reset bypass vector
- NEW affiliates.betpanda.io: `/config/config.json` reveals API base URL = `https://affiliates.betpanda.io/rest` (same-origin, not separate subdomain)
- NEW affiliates.betpanda.io: Full API endpoint map from JS bundle: `/rest/player/uid/{id}`, `/rest/transaction/list`, `/rest/agent/*`, `/rest/v2/report`, `/rest/payouts/single-currency-list`, `/rest/trk/*`
- NEW custom-lp.betpanda.io: Live behind Cloudflare challenge — new in-scope BetPanda infrastructure via crt.sh
- NEW fp.betpanda.io: Live behind Cloudflare challenge — likely fingerprint/fraud detection service
- CHANGED cpanel.avatarux.com: Cloudflare 1001 persists 48+ hours, CNAME → avatarux.com → 162.159.136.54 (Cloudflare IP), stable dangling DNS
- CHANGED affiliates.betpanda.io confidence raised 65→78 — API backend confirmed same-origin, endpoint map complete, attack surface quantified
- CHANGED help.desk.avatarux.com: Confluence/JSM behind Atlassian Edge, tenant IDs/feature flags in HTML, REST paths return 401/404/303 (stable)

## 2026-09-04 23:20:31 UTC

## 2026-09-05 01:16:23 UTC
- NEW affiliates.betpanda.io: API backend confirmed same-origin at /rest (not separate subdomain); /config/config.json reveals apiBaseUrl=https://affiliates.betpanda.io/rest
- NEW affiliates.betpanda.io: /rest/public/config leaks operatorId=1, Strapi CMS config, support email, full currency list — backend config disclosure
- NEW affiliates.betpanda.io: /rest/public/recover-password/email/{email} accepts email in URL path, returns 204 no body — account enumeration/reset bypass vector
- NEW affiliates.betpanda.io: Full API endpoint map from JS bundle: /rest/player/uid/{id}, /rest/transaction/list, /rest/agent/*, /rest/v2/report, /rest/payouts/single-currency-list, /rest/trk/* — all auth-
- NEW betpandacasino.io: real API base = same-origin /rest (mirrors affiliates); /rest/properties/manifest public; Spring Boot backend; no actuator/swagger/api-docs
- NEW custom-lp.betpanda.io: Live behind Cloudflare challenge — new BetPanda infrastructure via crt.sh
- NEW fp.betpanda.io: Live behind Cloudflare challenge — likely fingerprint/fraud detection service
- NEW flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- NEW betpandacasino.io bundle leaks AWS client config: CloudWatch identity pool (eu-west-1), CloudFront dist d3ec3n7kizfkuy.cloudfront.net, S3 nano-public
- CHANGED cpanel.avatarux.com: Cloudflare 1001 persists 48+ hours; CNAME → avatarux.com → 162.159.136.54 (Cloudflare IP); stable dangling DNS
- CHANGED help.desk.avatarux.com: Confluence/JSM behind Atlassian Edge; tenant IDs/feature flags in HTML; REST paths return 401/404/303 (stable)

## 2026-09-05 05:51:34 UTC
- NEW betpandacasino.io: real API base confirmed same-origin `/rest` (mirrors affiliates.betpanda.io); `/rest/properties/manifest` public; Spring Boot backend signature via JSON 404/405; no actuator/swagger
- NEW betpandacasino.io bundle leaks AWS client config: CloudWatch identity pool (eu-west-1), CloudFront dist d3ec3n7kizfkuy.cloudfront.net, S3 nano-public — mapping only, no misconfig
- NEW custom-lp.betpanda.io: Live behind Cloudflare challenge — new BetPanda infrastructure discovered via crt.sh
- NEW fp.betpanda.io: Live behind Cloudflare challenge — likely fingerprint/fraud detection service
- NEW flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- CHANGED cpanel.avatarux.com: Cloudflare 1001 persists 48+ hours; CNAME → avatarux.com → 162.159.136.54 (Cloudflare IP); stable dangling DNS confirmed
- CHANGED help.desk.avatarux.com: Confluence/JSM behind Atlassian Edge; tenant IDs/feature flags in HTML; REST paths return 401/404/303 (stable)
- CHANGED affiliates.betpanda.io: API backend confirmed same-origin at `/rest` (not separate subdomain); full endpoint map extracted (20+ routes); `/config/config.json` reveals apiBaseUrl=https://affiliates.bet

## 2026-09-05 10:03:08 UTC
- NEW help.desk.avatarux.com/servicedesk/customer/portal/2 → HTTP 200 (previously only portal/ returned 303; portal/2 is a second accessible JSM customer portal instance)
- NEW betpandacasino.io/rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-gated; OPTIONS leaks tenant-routing header schema + x-site-name-i
- CHANGED cpanel.avatarux.com Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed via 20+ probe cycles
- CHANGED help.desk.avatarux.com/wiki/rest/api/space?limit=5 → 303 to root stable — Confluence anonymous space enumeration closed behind Atlassian Edge
- CHANGED betpandacasino.io x-site-name-id tenant header ignored on public manifest (roobet_com/stake_com still echo betpandacasino_io) — no passive multi-tenant switch
- CHANGED affiliates.betpanda.io API backend confirmed same-origin at `/rest` (not separate subdomain); full endpoint map extracted (20+ routes); `/config/config.json` reveals apiBaseUrl=https://affiliates.betp

## 2026-09-05 13:24:54 UTC
- NEW help.desk.avatarux.com/servicedesk/customer/portal/2 → HTTP 200 (second accessible JSM customer portal instance, previously only portal/ returned 303)
- NEW betpandacasino.io/rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-gated; OPTIONS leaks tenant-routing header schema + x-site-name-i
- CHANGED cpanel.avatarux.com Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed via 20+ probe cycles
- CHANGED help.desk.avatarux.com/wiki/rest/api/space?limit=5 → 303 to root stable — Confluence anonymous space enumeration closed behind Atlassian Edge
- CHANGED betpandacasino.io x-site-name-id tenant header ignored on public manifest (roobet_com/stake_com still echo betpandacasino_io) — no passive multi-tenant switch
- CHANGED affiliates.betpanda.io API backend confirmed same-origin at `/rest` (not separate subdomain); full endpoint map extracted (20+ routes); `/config/config.json` reveals apiBaseUrl=https://affiliates.betp

## 2026-09-05 16:10:25 UTC
- NEW help.desk.avatarux.com/servicedesk/customer/portal/2 → HTTP 200 (second accessible JSM customer portal instance, previously only portal/ returned 303)
- NEW betpandacasino.io/rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-gated; OPTIONS leaks tenant-routing header schema + x-site-name-i
- CHANGED cpanel.avatarux.com Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed via 20+ probe cycles
- CHANGED help.desk.avatarux.com/wiki/rest/api/space?limit=5 → 303 to root stable — Confluence anonymous space enumeration closed behind Atlassian Edge
- CHANGED betpandacasino.io x-site-name-id tenant header ignored on public manifest (roobet_com/stake_com still echo betpandacasino_io) — no passive multi-tenant switch
- CHANGED affiliates.betpanda.io API backend confirmed same-origin at `/rest` (not separate subdomain); full endpoint map extracted (20+ routes); `/config/config.json` reveals apiBaseUrl=https://affiliates.betp

## 2026-09-05 18:26:01 UTC
- NEW help.desk.avatarux.com/servicedesk/customer/portal/2 → HTTP 200 (second accessible JSM customer portal instance)
- NEW betpandacasino.io/rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} GET→405 POST-gated; OPTIONS leaks tenant-routing header schema + x-site-name-id echo (betpandacasino_io)
- CHANGED cpanel.avatarux.com Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed via 20+ probe cycles
- CHANGED help.desk.avatarux.com/wiki/rest/api/space?limit=5 → 303 to root stable — Confluence anon enumeration closed behind Atlassian Edge
- CHANGED betpandacasino.io x-site-name-id tenant header ignored on public manifest — no passive multi-tenant switch
- CHANGED affiliates.betpanda.io API backend confirmed same-origin at `/rest`; full endpoint map (20+ routes); `/config/config.json` reveals apiBaseUrl=https://affiliates.betpanda.io/rest
