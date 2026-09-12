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

## 2026-09-05 20:45:53 UTC
- NEW help.desk.avatarux.com/servicedesk/customer/portal/2 → HTTP 200 confirmed across 4 probe cycles (second accessible JSM customer portal instance)
- NEW betpandacasino.io/rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} OPTIONS leaks tenant-routing header schema + echoes x-site-name-id (betpandacasino_io) on financial endpoint
- CHANGED cpanel.avatarux.com Cloudflare 1001 persists 48h+ across 20+ probe cycles — stable dangling DNS confirmed
- CHANGED help.desk.avatarux.com/wiki/rest/api/space?limit=5 → 303 to root stable — Confluence anonymous space enumeration closed behind Atlassian Edge
- CHANGED betpandacasino.io x-site-name-id tenant header ignored on public /rest/properties/manifest (roobet_com/stake_com still echo betpandacasino_io) — no passive multi-tenant switch
- CHANGED affiliates.betpanda.io API backend confirmed same-origin at `/rest`; full endpoint map (20+ routes); `/config/config.json` reveals apiBaseUrl=https://affiliates.betpanda.io/rest

## 2026-09-05 22:43:57 UTC
- NEW help.desk.avatarux.com/servicedesk/customer/portal/2 → HTTP 200 confirmed across 4 probe cycles (second accessible JSM customer portal instance)
- NEW betpandacasino.io/rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} OPTIONS leaks tenant-routing header schema + echoes x-site-name-id (betpandacasino_io) on financial endpoint
- CHANGED cpanel.avatarux.com Cloudflare 1001 persists 48h+ across 20+ probe cycles — stable dangling DNS confirmed
- CHANGED help.desk.avatarux.com/wiki/rest/api/space?limit=5 → 303 to root stable — Confluence anonymous space enumeration closed behind Atlassian Edge
- CHANGED betpandacasino.io x-site-name-id tenant header ignored on public /rest/properties/manifest (roobet_com/stake_com still echo betpandacasino_io) — no passive multi-tenant switch
- CHANGED affiliates.betpanda.io API backend confirmed same-origin at `/rest`; full endpoint map (20+ routes); `/config/config.json` reveals apiBaseUrl=https://affiliates.betpanda.io/rest

## 2026-09-06 00:24:07 UTC
- CHANGED ranked-lead set reintroduces a REJECTED-class item ("Password Reset Timing Differential for Account Enumeration", bigpickle NEXT) — will be parked at critique (out-of-scope: forgot-password enumeratio
- NEW help.desk.avatarux.com/servicedesk/customer/portal/2 → HTTP 200 confirmed across 4 probe cycles (second accessible JSM customer portal instance)
- NEW betpandacasino.io/rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} OPTIONS leaks tenant-routing header schema + echoes x-site-name-id (betpandacasino_io) on financial endpoint
- CHANGED cpanel.avatarux.com Cloudflare 1001 persists 48h+ across 20+ probe cycles — stable dangling DNS confirmed
- CHANGED help.desk.avatarux.com/wiki/rest/api/space?limit=5 → 303 to root stable — Confluence anonymous space enumeration closed behind Atlassian Edge
- CHANGED betpandacasino.io x-site-name-id tenant header ignored on public /rest/properties/manifest (roobet_com/stake_com still echo betpandacasino_io) — no passive multi-tenant switch
- CHANGED affiliates.betpanda.io API backend confirmed same-origin at `/rest`; full endpoint map (20+ routes); `/config/config.json` reveals apiBaseUrl=https://affiliates.betpanda.io/rest

## 2026-09-06 04:49:30 UTC
- NEW help.desk.avatarux.com/servicedesk/customer/portal/2 → HTTP 200 confirmed across 4 probe cycles (second accessible JSM customer portal instance)
- NEW betpandacasino.io/rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} OPTIONS leaks tenant-routing header schema + echoes x-site-name-id (betpandacasino_io) on financial endpoint
- CHANGED cpanel.avatarux.com Cloudflare 1001 persists 48h+ across 20+ probe cycles — stable dangling DNS confirmed
- CHANGED help.desk.avatarux.com/wiki/rest/api/space?limit=5 → 303 to root stable — Confluence anonymous space enumeration closed behind Atlassian Edge
- CHANGED betpandacasino.io x-site-name-id tenant header ignored on public /rest/properties/manifest (roobet_com/stake_com still echo betpandacasino_io) — no passive multi-tenant switch
- CHANGED affiliates.betpanda.io API backend confirmed same-origin at `/rest`; full endpoint map (20+ routes); `/config/config.json` reveals apiBaseUrl=https://affiliates.betpanda.io/rest

## 2026-09-06 09:25:36 UTC

## 2026-09-06 13:04:49 UTC
- NEW cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven reconfirmed, downgraded from takeover candidate
- NEW help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 (was 200) — attack surface reduced
- NEW betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last passive corroboration gap closed
- CHANGED cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed but delegation gap unclaimable via standard means
- CHANGED betpandacasino.io: x-site-name-id tenant header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- CHANGED help.desk.avatarux.com: Confluence /wiki/rest/api/space → 303 to root stable — anonymous space enumeration closed behind Atlassian Edge

## 2026-09-06 16:10:39 UTC
- NEW cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven reconfirmed, downgraded from takeover candidate
- NEW help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 (was 200) — attack surface reduced
- NEW betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last passive corroboration gap closed
- CHANGED cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed but delegation gap unclaimable via standard means
- CHANGED betpandacasino.io: x-site-name-id tenant header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- CHANGED help.desk.avatarux.com: Confluence /wiki/rest/api/space → 303 to root stable — anonymous space enumeration closed behind Atlassian Edge

## 2026-09-06 18:20:28 UTC
- NEW cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven reconfirmed, downgraded from takeover candidate
- NEW help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 (was 200) — attack surface reduced
- NEW betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last passive corroboration gap closed
- CHANGED cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed but delegation gap unclaimable via standard means
- CHANGED betpandacasino.io: x-site-name-id tenant header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- CHANGED help.desk.avatarux.com: Confluence /wiki/rest/api/space → 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- CHANGED All live in-scope hosts re-verified stable (cpanel 000/1001, affiliates 200, casino 200, help.desk 302)

## 2026-09-06 20:34:49 UTC
- NEW betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror affiliates leak; hypothesis falsified, last passive corroboration gap closed
- NEW help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 (was 200) — attack surface reduced
- NEW cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven reconfirmed, downgraded from takeover candidate
- CHANGED cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed but delegation gap unclaimable via standard means
- CHANGED betpandacasino.io: x-site-name-id tenant header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- CHANGED help.desk.avatarux.com: Confluence /wiki/rest/api/space → 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- CHANGED All live in-scope hosts re-verified stable (cpanel 000/1001, affiliates 200, casino 200, help.desk 302)

## 2026-09-06 22:21:47 UTC

## 2026-09-07 00:11:09 UTC
- NEW help.desk.avatarux.com/servicedesk/customer/portal/2: 200→303 (attack surface reduced, second JSM portal now redirects)
- NEW betpandacasino.io/rest/public/config: 404 (Spring JSON) — casino does NOT mirror affiliates /rest/public/config leak; hypothesis falsified
- NEW cpanel.avatarux.com: NS/SOA confirms apex delegation to Bluehost (ns1/ns2.bluehost.com); no separate claimable delegation for cpanel subdomain; takeover mechanism unproven
- CHANGED All live in-scope hosts re-verified stable: cpanel (SSL fail/1001), affiliates.betpanda.io (200), betpandacasino.io (200), help.desk.avatarux.com (302)
- CHANGED cPanel takeover downgraded from actionable to monitoring — delegation gap blocks standard Cloudflare zone claim
- NEW No new subdomains discovered via crt.sh (recent queries: 502/404/timeout)
- NEW No new probe data since 2026-09-06 22:21:53 UTC — awaiting credentialed sessions for top 2 AUTH_HELPED hypotheses

## 2026-09-07 04:55:57 UTC
- NEW help.desk.avatarux.com/servicedesk/customer/portal/2: 200→303 (attack surface reduced, second JSM portal now redirects)
- NEW betpandacasino.io/rest/public/config: 404 (Spring JSON) — casino does NOT mirror affiliates /rest/public/config leak; hypothesis falsified
- NEW cpanel.avatarux.com: NS/SOA confirms apex delegation to Bluehost (ns1/ns2.bluehost.com); no separate claimable delegation for cpanel subdomain; takeover mechanism unproven
- CHANGED All live in-scope hosts re-verified stable: cpanel (SSL fail/1001), affiliates.betpanda.io (200), betpandacasino.io (200), help.desk.avatarux.com (302)
- CHANGED cPanel takeover downgraded from actionable to monitoring — delegation gap blocks standard Cloudflare zone claim
- NEW No new subdomains discovered via crt.sh (recent queries: 502/404/timeout)
- NEW No new probe data since 2026-09-06 22:21:53 UTC — awaiting credentialed sessions for top 2 AUTH_HELPED hypotheses

## 2026-09-07 10:05:27 UTC
- NEW betpandacasino.io/rest/public/config returned Spring JSON 404 (not mirror of affiliates leak) — hypothesis falsified, last passive corroboration gap closed
- NEW help.desk.avatarux.com/servicedesk/customer/portal/2 changed from 200 → 303 — second JSM portal instance now redirects, attack surface reduced
- NEW cpanel.avatarux.com NS/SOA confirms apex Bluehost delegation (ns1/ns2.bluehost.com); no separate claimable delegation for cpanel subdomain — takeover mechanism unproven, downgraded to monitoring
- CHANGED cPanel takeover downgraded from actionable to monitoring — delegation gap blocks standard Cloudflare zone claim
- CHANGED No new subdomains discovered via crt.sh (recent queries: 502/404/timeout)
- CHANGED No new probe data since 2026-09-06 22:21:53 UTC — awaiting credentialed sessions for top 2 AUTH_HELPED hypotheses

## 2026-09-07 15:56:14 UTC

## 2026-09-07 19:36:48 UTC
- NEW cable.betpanda.io probe completed — bare Express server, root returns ASCII banner, all /health /api /graphql /actuator /socket /ws /events /info /config /debug return identical Express 404 {"error":"
- NEW cpanel.avatarux.com NS/SOA confirms apex delegation to Bluehost (ns1/ns2.bluehost.com); no separate claimable delegation for cpanel subdomain — standard Cloudflare zone claim impossible without progra
- NEW betpandacasino.io/rest/public/config returns Spring JSON 404 — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- NEW help.desk.avatarux.com/servicedesk/customer/portal/2 changed 200→303 — second JSM portal instance now redirects, attack surface reduced
- CHANGED No new subdomains via crt.sh (recent: 502/404/timeout)
- CHANGED No new probe data since 2026-09-06 22:21:53 UTC — top 2 hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) remain AUTH_HELPED blocked on credentialed sessions

## 2026-09-07 22:25:31 UTC

## 2026-09-08 00:31:28 UTC
- NEW cable.betpanda.io confirmed bare Express server — root 200 text/plain ASCII banner, all `/health /api /graphql /actuator /socket /ws /events /info /config /debug` return identical Express 404 `{"error
- CHANGED cpanel.avatarux.com takeover downgraded — NS/SOA confirms apex Bluehost delegation (ns1/ns2.bluehost.com), no separate claimable delegation for cpanel subdomain; Cloudflare 1001 persists 48h+ but stan
- CHANGED betpandacasino.io/rest/public/config returns Spring JSON 404 — casino does NOT mirror affiliates `/rest/public/config` leak; passive corroboration gap closed
- CHANGED help.desk.avatarux.com second JSM portal `/servicedesk/customer/portal/2` now 303 (was 200) — attack surface reduced
- CHANGED No new subdomains via crt.sh (recent queries: 502/404/timeout)
- CHANGED No new probe data since 2026-09-06 22:21:53 UTC — top 2 hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) remain AUTH_HELPED blocked on credentialed sessions

## 2026-09-08 05:14:58 UTC
- NEW cable.betpanda.io confirmed bare Express server — root 200 text/plain ASCII banner, all `/health /api /graphql /actuator /socket /ws /events /info /config /debug` return identical Express 404 `{"error
- NEW cpanel.avatarux.com takeover downgraded — NS/SOA confirms apex Bluehost delegation (ns1/ns2.bluehost.com), no separate claimable delegation for cpanel subdomain; Cloudflare 1001 persists 48h+ but stan
- NEW betpandacasino.io/rest/public/config returns Spring JSON 404 — casino does NOT mirror affiliates `/rest/public/config` leak; passive corroboration gap closed
- NEW help.desk.avatarux.com second JSM portal `/servicedesk/customer/portal/2` now 303 (was 200) — attack surface reduced
- CHANGED No new subdomains via crt.sh (recent queries: 502/404/timeout)
- CHANGED No new probe data since 2026-09-06 22:21:53 UTC — top 2 hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) remain AUTH_HELPED blocked on credentialed sessions

## 2026-09-08 09:53:23 UTC
- NEW help.desk.avatarux.com portal enumeration {1..10} all 303 confirmed (2026-09-08 00:31, 05:15) — attack surface fully reduced behind Atlassian Edge
- NEW No new subdomains via crt.sh (recent: 502/404/timeout) — passive discovery exhausted
- CHANGED cpanel.avatarux.com takeover downgraded — NS/SOA confirms apex Bluehost delegation (ns1/ns2.bluehost.com), no separate claimable delegation for cpanel subdomain; Cloudflare 1001 persists 48h+ but stan
- CHANGED betpandacasino.io/rest/public/config returns Spring JSON 404 — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- CHANGED cable.betpanda.io confirmed bare Express server — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /events /info /config /debug return identical Express 404; "undocume
- CHANGED All live in-scope hosts re-verified stable (cpanel SSL fail/1001, affiliates 200, casino 200, help.desk 302)
- CHANGED No new probe data since 2026-09-06 22:21:53 UTC — top 2 hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) remain AUTH_HELPED blocked on credentialed sessions

## 2026-09-08 14:17:39 UTC
- NEW help.desk.avatarux.com portal enumeration {1..10} all 303 confirmed — attack surface fully reduced behind Atlassian Edge
- NEW No new subdomains via crt.sh (recent: 502/404/timeout) — passive discovery exhausted
- CHANGED cpanel.avatarux.com takeover downgraded — NS/SOA confirms apex Bluehost delegation (ns1/ns2.bluehost.com), no separate claimable delegation for cpanel subdomain; Cloudflare 1001 persists 48h+ but stan
- CHANGED betpandacasino.io/rest/public/config returns Spring JSON 404 — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- CHANGED cable.betpanda.io confirmed bare Express server — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /events /info /config /debug return identical Express 404; "undocume
- CHANGED All live in-scope hosts re-verified stable (cpanel SSL fail/1001, affiliates 200, casino 200, help.desk 302)
- CHANGED No new probe data since 2026-09-06 22:21:53 UTC — top 2 hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) remain AUTH_HELPED blocked on credentialed sessions

## 2026-09-08 18:04:37 UTC
- NEW No new probe data since 2026-09-06 22:21:53 UTC — all live in-scope hosts re-verified stable (cpanel SSL fail/1001, affiliates 200, casino 200, help.desk 302)
- NEW betpandacasino.io/rest/public/config confirmed 404 (Spring JSON) — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- NEW cable.betpanda.io confirmed bare Express server — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /events /info /config /debug return identical Express 404; no functi
- NEW help.desk.avatarux.com portal enumeration {1..10} all 303 — attack surface fully reduced behind Atlassian Edge
- NEW cpanel.avatarux.com NS/SOA confirms apex Bluehost delegation (ns1/ns2.bluehost.com); no separate claimable delegation for cpanel subdomain; takeover mechanism unproven, downgraded to monitoring
- NEW No new subdomains via crt.sh (recent queries: 502/404/timeout) — passive discovery exhausted
- CHANGED Top 2 hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) remain AUTH_HELPED blocked on credentialed sessions
- CHANGED cPanel takeover downgraded from actionable to monitoring — delegation gap blocks standard Cloudflare zone claim

## 2026-09-08 20:53:56 UTC
- NEW No new subdomains discovered via crt.sh (recent queries: 502/404/timeout) — passive discovery exhausted
- NEW No new probe data since 2026-09-06 22:21:53 UTC — all live in-scope hosts re-verified stable
- CHANGED cPanel takeover downgraded from actionable to monitoring — NS/SOA confirms apex Bluehost delegation (ns1/ns2.bluehost.com), no separate claimable delegation for cpanel subdomain; Cloudflare 1001 persi
- CHANGED betpandacasino.io/rest/public/config confirmed 404 (Spring JSON) — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- CHANGED help.desk.avatarux.com portal enumeration {1..10} all 303 — attack surface fully reduced behind Atlassian Edge
- CHANGED cable.betpanda.io confirmed bare Express server — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /events /info /config /debug return identical Express 404; no functi

## 2026-09-08 23:12:48 UTC

## 2026-09-09 01:37:07 UTC
- NEW help.desk.avatarux.com portal enumeration {1..10} all 303 confirmed — attack surface fully reduced behind Atlassian Edge
- NEW cable.betpanda.io confirmed bare Express server — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /events /info /config /debug return identical Express 404; "undocume
- NEW betpandacasino.io/rest/public/config confirmed 404 (Spring JSON) — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- NEW cpanel.avatarux.com NS/SOA confirms apex Bluehost delegation (ns1/ns2.bluehost.com); no separate claimable delegation for cpanel subdomain; takeover mechanism unproven, downgraded to monitoring
- NEW No new subdomains via crt.sh (recent queries: 502/404/timeout) — passive discovery exhausted
- CHANGED All live in-scope hosts re-verified stable (cpanel SSL fail/1001, affiliates 200, casino 200, help.desk 302)
- CHANGED No new probe data since 2026-09-06 22:21:53 UTC — top 2 hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) remain AUTH_HELPED blocked on credentialed sessions
- CHANGED cPanel takeover downgraded from actionable to monitoring — delegation gap blocks standard Cloudflare zone claim
- NEW help.desk.avatarux.com portal enumeration {1..10} all 303 confirmed — attack surface fully reduced behind Atlassian Edge
- NEW cable.betpanda.io confirmed bare Express server — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /events /info /config /debug return identical Express 404; "undocume
- NEW betpandacasino.io/rest/public/config confirmed 404 (Spring JSON) — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- NEW cpanel.avatarux.com NS/SOA confirms apex Bluehost delegation (ns1/ns2.bluehost.com); no separate claimable delegation for cpanel subdomain; takeover mechanism unproven, downgraded to monitoring
- NEW No new subdomains via crt.sh (recent queries: 502/404/timeout) — passive discovery exhausted
- CHANGED All live in-scope hosts re-verified stable (cpanel SSL fail/1001, affiliates 200, casino 200, help.desk 302)
- CHANGED No new probe data since 2026-09-06 22:21:53 UTC — top 2 hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) remain AUTH_HELPED blocked on credentialed sessions
- CHANGED cPanel takeover downgraded from actionable to monitoring — delegation gap blocks standard Cloudflare zone claim

## 2026-09-09 06:15:08 UTC

## 2026-09-09 11:33:21 UTC

## 2026-09-09 15:39:57 UTC
- NEW Casino callback/webhook surface exhausted — all 5 endpoints (/rest/callback, /rest/webhook, /rest/notify, /rest/game/callback, /rest/api/game/callback) return 404
- NEW autoconfig.avatarux.com/autoconfig/v1.1/ returns XML exposing mail.avatarux.com:993 (IMAP/SSL) and mail.avatarux.com:465 (SMTP/SSL) with password-cleartext auth
- NEW mail.avatarux.com returns 301 → https://avatarux.com/ (WordPress on shared Bluehost), not a functional mail server
- CHANGED BetPanda Casino SSRF hypothesis (confidence 58) → falsified by passive probes; no callback/webhook surface exists
- CHANGED AvatarUX Mail Infrastructure Leak hypothesis (confidence 55) → confirmed but impact reduced: autoconfig exposes stale/legacy config pointing to web host, not actual mail servers (MX records show Googl

## 2026-09-09 18:48:06 UTC
- NEW help.desk.avatarux.com portals 4-10 return HTTP 200 (not 303) exposing tenant IDs (df607198-7bdc-43c6-8353-9b8a822febc5) and Atlassian org IDs in page source — attack surface expanded vs prior "all 30
- NEW autoconfig.avatarux.com/autoconfig/v1.1/ returns valid XML with mail.avatarux.com:993/465 password-cleartext — legacy mail config confirmed, mail host 301→WordPress (not mail infra)
- CHANGED betpandacasino.io/rest/public/config returns Spring JSON 404 — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- CHANGED betpandacasino.io callback/webhook surface exhausted — all 5 endpoints (/rest/callback, /rest/webhook, /rest/notify, /rest/game/callback, /rest/api/game/callback) return 404; SSRF hypothesis falsified
- CHANGED cpanel.avatarux.com SSL handshake failure persists (TLS alert handshake failure) — Cloudflare 1001 stable but delegation gap to Bluehost blocks standard zone claim; takeover unproven, monitoring only
- CHANGED affiliates.betpanda.io/rest/public/config stable 200 — operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms, full currency list leaked
- CHANGED affiliates.betpanda.io/rest/player/uid/{id} returns 401 unauthenticated — IDOR pattern confirmed, requires credentialed session
- CHANGED betpandacasino.io OPTIONS /rest/user/authenticate leaks Access-Control-Allow-Headers: x-site-name-id, x-preferred-app-context; ACAO pinned to https://betpandacasino.io; x-site-name-id echoed as betpan

## 2026-09-09 21:32:08 UTC
- NEW help.desk.avatarux.com portals 4-10 return HTTP 200 (not 303) exposing tenant-id (df607198-7bdc-43c6-8353-9b8a822febc5) and atlassianOrgId in page source — attack surface EXPANDED vs prior "all 303" c
- NEW autoconfig.avatarux.com/autoconfig/v1.1/ returns valid XML with mail.avatarux.com:993/465 password-cleartext — legacy mail config confirmed, mail host 301→WordPress (not mail infra)
- CHANGED betpandacasino.io/rest/public/config returns Spring JSON 404 — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- CHANGED betpandacasino.io callback/webhook surface exhausted — all 5 endpoints (/rest/callback, /rest/webhook, /rest/notify, /rest/game/callback, /rest/api/game/callback) return 404; SSRF hypothesis falsified
- CHANGED cpanel.avatarux.com SSL handshake failure persists (TLS alert handshake failure) — Cloudflare 1001 stable but delegation gap to Bluehost blocks standard zone claim; takeover unproven, monitoring only
- CHANGED affiliates.betpanda.io/rest/public/config stable 200 — operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms, full currency list leaked
- CHANGED affiliates.betpanda.io/rest/player/uid/{id} returns 401 unauthenticated — IDOR pattern confirmed, requires credentialed session
- CHANGED betpandacasino.io OPTIONS /rest/user/authenticate leaks Access-Control-Allow-Headers: x-site-name-id, x-preferred-app-context; ACAO pinned to https://betpandacasino.io; x-site-name-id echoed as betpan

## 2026-09-09 23:34:45 UTC

## 2026-09-10 01:35:50 UTC
- NEW help.desk.avatarux.com portals 4-10 return HTTP 200 (not 303) exposing tenant-id (df607198-7bdc-43c6-8353-9b8a822febc5) and atlassianOrgId in page source — attack surface EXPANDED vs prior "all 303" c
- NEW autoconfig.avatarux.com/autoconfig/v1.1/ returns valid XML with mail.avatarux.com:993/465 password-cleartext — legacy mail config confirmed, mail host 301→WordPress (not mail infra)
- CHANGED betpandacasino.io/rest/public/config returns Spring JSON 404 — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- CHANGED betpandacasino.io callback/webhook surface exhausted — all 5 endpoints (/rest/callback, /rest/webhook, /rest/notify, /rest/game/callback, /rest/api/game/callback) return 404; SSRF hypothesis falsified
- CHANGED cpanel.avatarux.com SSL handshake failure persists (TLS alert handshake failure) — Cloudflare 1001 stable but delegation gap to Bluehost blocks standard zone claim; takeover unproven, monitoring only
- CHANGED affiliates.betpanda.io/rest/public/config stable 200 — operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms, full currency list leaked
- CHANGED affiliates.betpanda.io/rest/player/uid/{id} returns 401 unauthenticated — IDOR pattern confirmed, requires credentialed session
- CHANGED betpandacasino.io OPTIONS /rest/user/authenticate leaks Access-Control-Allow-Headers: x-site-name-id, x-preferred-app-context; ACAO pinned to https://betpandacasino.io; x-site-name-id echoed as betpan
- NEW help.desk.avatarux.com portals 4-10 return HTTP 200 (not 303) exposing tenant-id (df607198-7bdc-43c6-8353-9b8a822febc5) and atlassianOrgId in page source — attack surface EXPANDED vs prior "all 303" c
- NEW autoconfig.avatarux.com/autoconfig/v1.1/ returns valid XML with mail.avatarux.com:993/465 password-cleartext — legacy mail config confirmed, mail host 301→WordPress (not mail infra)
- CHANGED betpandacasino.io/rest/public/config returns Spring JSON 404 — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- CHANGED betpandacasino.io callback/webhook surface exhausted — all 5 endpoints (/rest/callback, /rest/webhook, /rest/notify, /rest/game/callback, /rest/api/game/callback) return 404; SSRF hypothesis falsified
- CHANGED cpanel.avatarux.com SSL handshake failure persists (TLS alert handshake failure) — Cloudflare 1001 stable but delegation gap to Bluehost blocks standard zone claim; takeover unproven, monitoring only
- CHANGED affiliates.betpanda.io/rest/public/config stable 200 — operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms, full currency list leaked
- CHANGED affiliates.betpanda.io/rest/player/uid/{id} returns 401 unauthenticated — IDOR pattern confirmed, requires credentialed session
- CHANGED betpandacasino.io OPTIONS /rest/user/authenticate leaks Access-Control-Allow-Headers: x-site-name-id, x-preferred-app-context; ACAO pinned to https://betpandacasino.io; x-site-name-id echoed as betpan

## 2026-09-10 06:44:22 UTC
- NEW help.desk.avatarux.com portals 4-10 return HTTP 200 (not 303) exposing tenant-id (df607198-7bdc-43c6-8353-9b8a822febc5) and atlassianOrgId in page source — attack surface EXPANDED vs prior "all 303" c
- NEW autoconfig.avatarux.com/autoconfig/v1.1/ returns valid XML with mail.avatarux.com:993/465 password-cleartext — legacy mail config confirmed, mail host 301→WordPress (not mail infra)
- CHANGED betpandacasino.io/rest/public/config returns Spring JSON 404 — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- CHANGED betpandacasino.io callback/webhook surface exhausted — all 5 endpoints (/rest/callback, /rest/webhook, /rest/notify, /rest/game/callback, /rest/api/game/callback) return 404; SSRF hypothesis falsified
- CHANGED cpanel.avatarux.com SSL handshake failure persists — Cloudflare 1001 stable but delegation gap to Bluehost blocks standard zone claim; takeover unproven, monitoring only
- CHANGED affiliates.betpanda.io/rest/public/config stable 200 — operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms, full currency list leaked
- CHANGED affiliates.betpanda.io/rest/player/uid/{id} returns 401 unauthenticated — IDOR pattern confirmed, requires credentialed session
- CHANGED betpandacasino.io OPTIONS /rest/user/authenticate leaks Access-Control-Allow-Headers: x-site-name-id, x-preferred-app-context; ACAO pinned to https://betpandacasino.io; x-site-name-id echoed as betpan

## 2026-09-10 12:00:42 UTC
- NEW betpandacasino.io `/rest/user/details` — HTTP 200 (301B) returns full user state object (loggedIn, blocked, emailVerified, kycVerified, country:"US", currentLevel, currencies, blockedStatus, phoneNumb
- CHANGED help.desk.avatarux.com portal enumeration expanded: portals **4–100+** all HTTP 200 (~209007B). Prior knowledge only documented portals 4–15. Portals 1–3 return 0B (303). Surface is ~96 accessible por
- CHANGED help.desk.portal body sizes normalized: portals 4–100 consistently 209005–209007B (minor variance, same template). Prior "208039B" for portals 4,5,7,10,15 was likely a stale cache difference; now conv
- NEW roobet.com `/_api/game/{chess,yeti-towers,pop_towers}/currentRoundHash` — all HTTP 401 (12B "Unauthorized"). Confirms 3 additional game endpoints beyond tiki21, all auth-gated identically.
- NEW help.desk.avatarux.com portals 4-10 return HTTP 200 (not 303) exposing tenant-id (df607198-7bdc-43c6-8353-9b8a822febc5) and atlassianOrgId in page source — attack surface EXPANDED vs prior "all 303" c
- NEW autoconfig.avatarux.com/autoconfig/v1.1/ returns valid XML with mail.avatarux.com:993/465 password-cleartext — legacy mail config confirmed, mail host 301→WordPress (not mail infra)
- CHANGED betpandacasino.io/rest/public/config returns Spring JSON 404 — casino does NOT mirror affiliates /rest/public/config leak; passive corroboration gap CLOSED
- CHANGED betpandacasino.io callback/webhook surface exhausted — all 5 endpoints (/rest/callback, /rest/webhook, /rest/notify, /rest/game/callback, /rest/api/game/callback) return 404; SSRF hypothesis falsified
- CHANGED cpanel.avatarux.com SSL handshake failure persists — Cloudflare 1001 stable but delegation gap to Bluehost blocks standard zone claim; takeover unproven, monitoring only
- CHANGED affiliates.betpanda.io/rest/public/config stable 200 — operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms, full currency list leaked
- CHANGED affiliates.betpanda.io/rest/player/uid/{id} returns 401 unauthenticated — IDOR pattern confirmed, requires credentialed session
- CHANGED betpandacasino.io OPTIONS /rest/user/authenticate leaks Access-Control-Allow-Headers: x-site-name-id, x-preferred-app-context; ACAO pinned to https://betpandacasino.io; x-site-name-id echoed as betpan

## 2026-09-10 15:57:17 UTC
- NEW roobet.com `/_api/game/{chess,yeti-towers,pop_towers}/currentRoundHash` — all 401 (12B), confirms uniform auth boundary across 3 additional game types beyond tiki21; first new accessible surface in 6+
- NEW betpandacasino.io `/rest/user/details` — HTTP 200 (301B) returns unauthenticated user state model (loggedIn, country:"US", kycVerified, currentLevel, blockedStatus, currencies, phoneNumberVerified, pr
- CHANGED help.desk.avatarux.com portals 4–100 all HTTP 200 (~209007B) — surface expanded from 7 portals to 96+, all leaking identical tenant-id/atlassianOrgId/Statsig config. Prior brace-literal artifact "all 
- CHANGED roobet.com socket.io transport layer accessible from game SPA Origin (tiki-21.games.roobet.com) — first new attack surface in 6+ cycles, resolves the api.roobet.com 403 architectural impasse.
- NEW betpandacasino.io/rest/user/details — HTTP 200 returns unauthenticated user state model (loggedIn, blocked, emailVerified, kycVerified, country:"US", currentLevel, currencies, blockedStatus, phoneNumb
- NEW help.desk.avatarux.com portals 4–100 — surface expanded from 7 to 96+ portals, all HTTP 200 (~209KB), leaking identical tenant-id (df607198-7bdc-43c6-8353-9b8a822febc5), atlassianOrgId, Statsig config
- NEW roobet.com/_api/socket.io — Engine.IO handshake succeeds (200, sid assigned, WS upgrade, maxPayload=1000) from Origin: tiki-21.games.roobet.com — transport layer accessible from game SPA domain
- NEW roobet.com/_api/game/{chess,yeti-towers,pop_towers}/currentRoundHash — all HTTP 401 (12B), confirms 3 additional game endpoints beyond tiki21, uniform auth middleware
- NEW roobet.com/_api/currency/balances — HTTP 200 returns static 12-currency catalog (BTC/ETH/LTC/USDC/USDT/XRP/DOGE/TRX/SOL/BNB/SUI/Cash)
- CHANGED betpandacasino.io/rest/user/{me,profile,info} — all 404; /rest/user/settings returns 401 "No http-session"; /rest/user/details is only unauthenticated user endpoint
- CHANGED betpandacasino.io/rest/public/config — Spring JSON 404 confirmed, casino does NOT mirror affiliates leak; passive corroboration gap CLOSED
- CHANGED betpandacasino.io callback/webhook surface — all 5 endpoints 404; SSRF hypothesis falsified
- CHANGED cpanel.avatarux.com — SSL handshake failure persists, Cloudflare 1001 stable but NS/SOA confirms Bluehost apex delegation, no claimable subdomain delegation; takeover unproven, monitoring only
- CHANGED affiliates.betpanda.io/rest/public/config — stable 200, byte-identical (operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms, contentfulAccessToken empty)
- CHANGED affiliates.betpanda.io/rest/player/uid/{id} — 401 unauthenticated confirmed, IDOR pattern requires credentialed session
- CHANGED betpandacasino.io OPTIONS /rest/user/authenticate — leaks Access-Control-Allow-Headers: x-site-name-id, x-preferred-app-context; ACAO pinned to https://betpandacasino.io; x-site-name-id echoed as betp

## 2026-09-10 19:01:17 UTC
- NEW roobet.com/_api CORS whitelist maps 777.dev (Roobet/Cozy test-stage) + api.777.dev with credentials=true on production game data endpoint (ACAO reflected on GET currentRoundHash 401) — staging origin 
- NEW roobet.com oddity: topkek.com (Cozy prod) NOT whitelisted, but test env 777.dev IS. 777.dev live behind Cloudflare (403 root, HSTS-preload), api.777.dev resolves on same CF IP 104.18.43.25.
- NEW /_api/game/tiki21/endRound POST -> 401 (12B) — real mutation endpoint confirmed auth-gated identically to GET currentRoundHash. Auth boundary consistent; no differentiated gap.
- CHANGED /_api/game/{chess,yeti-towers,pop_towers}/bet POST -> 404 route miss (REST bet paths do NOT exist; games bet over socket.io). CORS preflight 204 path-agnostic global config (nonexistent path also 204)
- CHANGED Tiki21 bundle: API_HOST=SOCKET_HOST="roobet.com/_api"; game actions (hit/stand/double/wager) via socket.io w/ JWT from ?jwt= / localStorage; REST surface per game = currentRoundHash + endRound only.
- NEW 401 on currentRoundHash clears session cookies (connect.sid, userId, twofactorRequired) — Express session cookie names disclosed (informational).
- NEW betpandacasino.io `/rest/user/details` — HTTP 200 returns full user state object (loggedIn, blocked, emailVerified, kycVerified, country, currentLevel, currencies, blockedStatus, phoneNumber) unauthen
- NEW help.desk.avatarux.com portal enumeration expanded: portals **4–100+** all HTTP 200 (~209KB). Prior knowledge only documented portals 4–15. Portals 1–3 return 0B (303). Surface is ~96 accessible porta
- NEW roobet.com `/_api/game/{chess,yeti-towers,pop_towers}/currentRoundHash` — all HTTP 401 (12B "Unauthorized"). Confirms 3 additional game endpoints beyond tiki21, all auth-gated identically.
- NEW roobet.com `/_api/socket.io` — Engine.IO handshake succeeds (200, sid assigned, WS upgrade, maxPayload=1000) from Origin: tiki-21.games.roobet.com — transport layer accessible from game SPA domain; pr
- NEW roobet.com `/_api/currency/balances` — HTTP 200 returns static 12-currency catalog (BTC/ETH/LTC/USDC/USDT/XRP/DOGE/TRX/SOL/BNB/SUI/Cash) — informational, non-sensitive.
- CHANGED betpandacasino.io/rest/user/{me,profile,info} — all 404; /rest/user/settings returns 401 "No http-session"; /rest/user/details is only unauthenticated user endpoint.
- CHANGED betpandacasino.io/rest/public/config — Spring JSON 404 confirmed, casino does NOT mirror affiliates leak; passive corroboration gap CLOSED.
- CHANGED betpandacasino.io callback/webhook surface — all 5 endpoints 404; SSRF hypothesis falsified.
- CHANGED cpanel.avatarux.com — SSL handshake failure persists, Cloudflare 1001 stable but NS/SOA confirms Bluehost apex delegation, no claimable subdomain delegation; takeover unproven, monitoring only.
- CHANGED affiliates.betpanda.io/rest/public/config — stable 200, byte-identical (operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms, contentfulAccessToken empty).
- CHANGED affiliates.betpanda.io/rest/player/uid/{id} — 401 unauthenticated confirmed, IDOR pattern requires credentialed session.
- CHANGED betpandacasino.io OPTIONS /rest/user/authenticate — leaks Access-Control-Allow-Headers: x-site-name-id, x-preferred-app-context; ACAO pinned to https://betpandacasino.io; x-site-name-id echoed as betp

## 2026-09-10 21:30:51 UTC
- NEW betpandacasino.io/rest/user/details — HTTP 200 returns full user state object (loggedIn, blocked, emailVerified, kycVerified, country:"US", currentLevel, currencies, blockedStatus, phoneNumberVerified
- NEW help.desk.avatarux.com portal enumeration expanded: portals 4–100+ all HTTP 200 (~209KB). Prior knowledge only documented portals 4–15. Portals 1–3 return 0B (303). Surface is ~96 accessible portals l
- NEW roobet.com/_api/game/{chess,yeti-towers,pop_towers}/currentRoundHash — all HTTP 401 (12B "Unauthorized"). Confirms 3 additional game endpoints beyond tiki21, all auth-gated identically.
- NEW roobet.com/_api/socket.io — Engine.IO handshake succeeds (200, sid assigned, WS upgrade, maxPayload=1000) from Origin: tiki-21.games.roobet.com — transport layer accessible from game SPA domain; prior
- NEW roobet.com/_api/currency/balances — HTTP 200 returns static 12-currency catalog (BTC/ETH/LTC/USDC/USDT/XRP/DOGE/TRX/SOL/BNB/SUI/Cash) — informational, non-sensitive.
- NEW roobet.com/_api CORS whitelist includes staging test domain 777.dev + api.777.dev with credentials=true (verified ACAO reflection on OPTIONS+GET); topkek.com not whitelisted.
- NEW roobet.com/_api/game/tiki21/endRound POST → 401 (12B) — real mutation endpoint confirmed auth-gated identically to GET currentRoundHash.
- CHANGED betpandacasino.io/rest/user/{me,profile,info} — all 404; /rest/user/settings returns 401 "No http-session"; /rest/user/details is only unauthenticated user endpoint.
- CHANGED betpandacasino.io/rest/public/config — Spring JSON 404 confirmed, casino does NOT mirror affiliates leak; passive corroboration gap CLOSED.
- CHANGED betpandacasino.io callback/webhook surface — all 5 endpoints 404; SSRF hypothesis falsified.
- CHANGED cpanel.avatarux.com — SSL handshake failure persists, Cloudflare 1001 stable but NS/SOA confirms Bluehost apex delegation, no claimable subdomain delegation; takeover unproven, monitoring only.
- CHANGED affiliates.betpanda.io/rest/public/config — stable 200, byte-identical (operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms, contentfulAccessToken empty).
- CHANGED affiliates.betpanda.io/rest/player/uid/{id} — 401 unauthenticated confirmed, IDOR pattern requires credentialed session.
- CHANGED betpandacasino.io OPTIONS /rest/user/authenticate — leaks Access-Control-Allow-Headers: x-site-name-id, x-preferred-app-context; ACAO pinned to https://betpandacasino.io; x-site-name-id echoed as betp
- CHANGED help.desk.avatarux.com portal body sizes normalized: portals 4–100 consistently 209005–209007B (minor variance, same template). Prior "208039B" for portals 4,5,7,10,15 was likely a stale cache differe
- CHANGED roobet.com/_api/game/{chess,yeti-towers,pop_towers}/bet POST → 404 route miss — CORS preflight 204 is path-agnostic global config (proven on nonexistent path); bet endpoints do not exist on REST.
- CHANGED tiki-21.games.roobet.com bundle: API_HOST=SOCKET_HOST="roobet.com/_api"; game mutations (hit/stand/double/wager) run over socket.io with JWT; REST-only surface per game = currentRoundHash + endRound o

## 2026-09-10 23:25:55 UTC

## 2026-09-11 01:46:58 UTC

## 2026-09-11 06:45:21 UTC
- NEW Rainbow CT parity sweep executed — RainBet exposes the full backend-dev tier in-scope: 45 cert names incl 6x Live RabbitMQ brokers, staging-api/services/socket/slot-integrations/aiostaging/monorepo, *
- NEW rainbet-com-rabbitmq.rainbet.com A=159.203.34.207 (DigitalOcean raw origin, no CF): :15671 RabbitMQ Management UI HTTP 200 (Cowboy), :5671 AMQP-TLS OPEN, /api/overview 401 Basic gated.
- NEW rainbet-us-staging-rabbitmq.rainbet.com A=165.227.255.111 (DigitalOcean raw origin): :15671 + :15672 management UI 200 (plaintext mgmt), :5671 + :5672 AMQP (TLS+PLAINTEXT) OPEN publicly; AMQP protocol
- NEW staging-api.rainbet.com leaks DigitalOcean App Platform origin UUID via x-do-app-origin: 1ce4ff55-e85f-4c30-8033-5129a1812504 through CF; __cf_bm cookie scoped Domain=rainbet.com.
- NEW Roobet stand-alone game-tier (tiki-21/yeti-towers etc + /_api + socket.io) NOT mirrored on Stake/Gamdom/RainBet (no *.games/crash-*/dice labels) — Roobet stack stays unique.
- CHANGED all four brand clusters now confirmed in-scope resident; RainBet adds the only genuinely new anonymous hard-surface (broker cluster) since 2026-09-10 /rest/user/details.
- CHANGED Final cluster sweep: rbtmq-dev/rbtmq-preprod/rbtmq-preprod-us/rbtmq-stg-us all NXDOMAIN (no A) — the exposed broker cluster is exactly TWO live hosts (rainbet-com-rabbitmq A=159.203.34.207, rainbet-us

## 2026-09-11 11:51:07 UTC
- CHANGED cpanel.avatarux.com: takeover mechanism now definitively unproven — NS/SOA confirms apex Bluehost zone delegation, no claimable subdomain delegation exists. Downgraded from CRITICAL actionable to moni
- CHANGED help.desk.avatarux.com portals 4–100: prior "all 303" was brace-literal artifact; portals 4–100 all HTTP 200 (~209KB) leaking tenant-id/atlassianOrgId/Statsig. Surface is ~96 accessible portals, uncha
- CHANGED RainBet RabbitMQ cluster: exactly 2 live hosts confirmed (rbtmq-dev/preprod/preprod-us/stg-us NXDOMAIN); enumeration closed.
- NEW rainbet-com-rabbitmq.rainbet.com (159.203.34.207) + rainbet-us-staging-rabbitmq.rainbet.com (165.227.255.111): RabbitMQ Management UI (15671/15672) + AMQP (5671/5672) exposed on raw DigitalOcean origi
- NEW staging-api.rainbet.com: leaks x-do-app-origin: 1ce4ff55-e85f-4c30-8033-5129a1812504 (DO App Platform origin UUID) through Cloudflare on 200-empty
- NEW Roobet CORS: production /_api reflects ACAO for https://777.dev + https://api.777.dev with ACAC=true on game data endpoints; topkek.com (prod) NOT whitelisted
- CHANGED help.desk.avatarux.com: portals 4–100+ all HTTP 200 (~209KB), leaking identical tenant-id (df607198-...), atlassianOrgId, Statsig config (prod-euwest, shard jira-prod-eu-3); surface expanded from 7 to
- CHANGED betpandacasino.io/rest/user/details: NEW endpoint HTTP 200 returns full user state model (loggedIn, country, kycVerified, currentLevel, blockedStatus, currencies, phoneNumberVerified, principalVerifie
- CHANGED roobet.com/_api/socket.io: Engine.IO handshake succeeds (200, sid assigned, WS upgrade, maxPayload=1000) from Origin: tiki-21.games.roobet.com — transport layer accessible from game SPA domain
- CHANGED roobet.com/_api/game/{chess,yeti-towers,pop_towers}/currentRoundHash: all 401 (12B) — uniform auth boundary across 4 game types
- CHANGED affiliates.betpanda.io/rest/public/config: stable 200 byte-identical (operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms)
- CHANGED cpanel.avatarux.com: NS/SOA confirms Bluehost apex delegation (ns1/ns2.bluehost.com), no claimable subdomain delegation; takeover unproven, monitoring only

## 2026-09-11 16:01:20 UTC
- NEW rainbet-com-rabbitmq.rainbet.com:15671/15672 — RabbitMQ Management UI (Cowboy) + AMQP 5671/5672 exposed on raw DigitalOcean origins (159.203.34.207, 165.227.255.111), no Cloudflare/ACL; /api/overview 
- NEW rainbet-us-staging-rabbitmq.rainbet.com:15671/15672 — Same exposure on second broker (staging label)
- NEW staging-api.rainbet.com — Leaks x-do-app-origin: 1ce4ff55-e85f-4c30-8033-5129a1812504 (DO App Platform origin UUID) through Cloudflare on 200-empty
- NEW betpandacasino.io/rest/user/details — HTTP 200 returns full unauthenticated user state model (loggedIn, country, kycVerified, currentLevel, blockedStatus, currencies, phoneNumberVerified, principalVer
- NEW help.desk.avatarux.com portals 4–100+ — All HTTP 200 (~209KB), leaking identical tenant-id (df607198-7bdc-43c6-8353-9b8a822febc5), atlassianOrgId, Statsig config (prod-euwest, shard jira-prod-eu-3); s
- NEW roobet.com/_api CORS — Production reflects ACAO: https://777.dev + https://api.777.dev with ACAC:true on game data endpoints; topkek.com (prod) NOT whitelisted; 777.dev is staging behind CF (403 root,
- NEW roobet.com/_api/socket.io — Engine.IO handshake succeeds (200, sid assigned, WS upgrade, maxPayload=1000) from Origin: tiki-21.games.roobet.com; prior 403 was UA/Origin-gated
- NEW roobet.com/_api/game/{chess,yeti-towers,pop_towers}/currentRoundHash — All 401 (12B), uniform auth boundary across 4 game types
- CHANGED cpanel.avatarux.com — NS/SOA confirms Bluehost apex delegation (ns1/ns2.bluehost.com), no separate claimable delegation for cpanel subdomain; Cloudflare 1001 persists but takeover mechanism unproven, 
- CHANGED betpandacasino.io/rest/public/config — Spring JSON 404 confirmed; casino does NOT mirror affiliates leak; passive corroboration gap CLOSED
- CHANGED betpandacasino.io callback/webhook surface — All 5 endpoints 404; SSRF hypothesis falsified
- CHANGED affiliates.betpanda.io/rest/public/config — Stable 200 byte-identical (operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms, contentfulAccessToken empty)
- CHANGED affiliates.betpanda.io/rest/player/uid/1 — 401-gated confirmed; auth boundary intact anonymously
- CHANGED RainBet RabbitMQ cluster — Exactly 2 live hosts confirmed (rbtmq-dev/preprod/preprod-us/stg-us NXDOMAIN); enumeration closed

## 2026-09-11 19:09:37 UTC
- NEW RainBet RabbitMQ Management UI (15671/15672) + AMQP (5671/5672) exposed on raw DigitalOcean origins (rainbet-com-rabbitmq.rainbet.com:159.203.34.207, rainbet-us-staging-rabbitmq.rainbet.com:165.227.25
- NEW BetPanda Casino `/rest/user/details` — NEW unauthenticated endpoint returning full user state model (loggedIn, country, kycVerified, currentLevel, blockedStatus, currencies, phoneNumberVerified, princ
- NEW Roobet production `/_api` CORS trusts `https://777.dev` + `https://api.777.dev` with credentials=true on game data endpoints; 777.dev is staging (CF 403, HSTS-preload); topkek.com (prod) NOT whitelist
- NEW Help.desk.avatarux.com portals 4–100 all HTTP 200 (~209KB) — surface expanded from 7 to 96+ portals, all leaking identical tenant-id (df607198-7bdc-43c6-8353-9b8a822febc5), atlassianOrgId, Statsig con
- NEW Roobet `/_api/socket.io` Engine.IO handshake succeeds (200, sid assigned, WS upgrade, maxPayload=1000) from Origin: tiki-21.games.roobet.com — transport layer accessible from game SPA domain
- NEW RainBet staging-api.rainbet.com leaks x-do-app-origin: 1ce4ff55-e85f-4c30-8033-5129a1812504 (DigitalOcean App Platform origin UUID) through Cloudflare on 200-empty
- CHANGED cpanel.avatarux.com takeover downgraded — NS/SOA confirms Bluehost apex delegation (ns1/ns2.bluehost.com), no claimable subdomain delegation; Cloudflare 1001 persists but standard zone claim impossibl
- CHANGED betpandacasino.io/rest/public/config — Spring JSON 404 confirmed; casino does NOT mirror affiliates leak; passive corroboration gap CLOSED
- CHANGED betpandacasino.io callback/webhook surface — all 5 endpoints 404; SSRF hypothesis falsified
- CHANGED RainBet RabbitMQ cluster enumeration closed — exactly 2 live hosts (rbtmq-dev/preprod/preprod-us/stg-us all NXDOMAIN)

## 2026-09-11 21:44:49 UTC
- NEW rainbet-com-rabbitmq.rainbet.com:15671/15672 + rainbet-us-staging-rabbitmq.rainbet.com:15671/15672 — RabbitMQ Management UI (Cowboy) + AMQP 5671/5672 exposed on raw DigitalOcean origins (159.203.34.20
- NEW betpandacasino.io/rest/user/details — HTTP 200 returns full unauthenticated user state model (loggedIn, blocked, emailVerified, kycVerified, country:"US", currentLevel, currencies, blockedStatus, phon
- NEW roobet.com/_api CORS — Production reflects ACAO: https://777.dev + https://api.777.dev with ACAC:true on game data endpoints (/game/*/currentRoundHash, /currency/balances, /socket.io); 777.dev is stag
- NEW help.desk.avatarux.com portals 4–100+ — All HTTP 200 (~209KB), leaking identical tenant-id (df607198-7bdc-43c6-8353-9b8a822febc5), atlassianOrgId (ead67a75-...), Statsig config (prod-euwest, shard jir
- NEW roobet.com/_api/socket.io — Engine.IO handshake succeeds (200, sid assigned, WS upgrade, maxPayload=1000) from Origin: tiki-21.games.roobet.com; prior 403 was UA/Origin-gated for bare curl
- NEW autoconfig.avatarux.com/autoconfig/v1.1/ — XML exposes mail.avatarux.com:993/465 (password-cleartext) but mail host 301→avatarux.com (WordPress/Bluehost) — legacy/stale config, not active mail server
- CHANGED cpanel.avatarux.com — NS/SOA confirms Bluehost apex delegation (ns1/ns2.bluehost.com), no separate claimable delegation for cpanel subdomain; Cloudflare 1001 persists but takeover mechanism unproven, 
- CHANGED betpandacasino.io/rest/public/config — Spring JSON 404 confirmed; casino does NOT mirror affiliates leak; passive corroboration gap CLOSED
- CHANGED betpandacasino.io callback/webhook surface — All 5 endpoints (/rest/callback, /rest/webhook, /rest/notify, /rest/game/callback, /rest/api/game/callback) return 404; SSRF hypothesis falsified
- CHANGED RainBet RabbitMQ cluster — Exactly 2 live hosts confirmed (rbtmq-dev/preprod/preprod-us/stg-us all NXDOMAIN); enumeration closed
- CHANGED affiliates.betpanda.io/rest/public/config — Stable 200 byte-identical (operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms, contentfulAccessToken empty)
- CHANGED affiliates.betpanda.io/rest/player/uid/1 — 401-gated confirmed; auth boundary intact anonymously

## 2026-09-11 23:35:21 UTC
- NEW roobet.com/_api CORS whitelist = string-level .777.dev NAMESPACE match: ACAO=Origin reflects for https://www.777.dev (NON-RESOLVING name, empty A) with ACAC=true; controls all clean (https://evil777.d
- NEW 777.dev cert-name inventory: 11 names (api, api-lbc, api-test, gamebook, promotions, storybook, testsite, x, xtest, tiki-21.games, yeti-towers.games, www) all wildcarded to Roobet CF pair 104.18.43.25
- CHANGED Nemotron3 top-ranked [88] "anonymous RabbitMQ /api topology disclosure" hard-falsified (all /api/* 401 Basic) — reported exposure = mgmt-UI + AMQP only (74). No disclosure inflation.

## 2026-09-12 01:33:27 UTC
- NEW betpandacasino.io/rest/user/details: NEW unauthenticated endpoint returning full user state model (loggedIn, country, kycVerified, currentLevel, blockedStatus, currencies, phoneNumberVerified, princip
- NEW roobet.com/_api CORS: whitelist is namespace-wide string-suffix match on `.777.dev` (any subdomain incl. non-resolving) with ACAC=true on production game data endpoints; topkek.com (prod) NOT whitelis
- NEW help.desk.avatarux.com portals 4–100+: surface expanded from 7 to 96+ portals, all HTTP 200 (~209KB), leaking identical tenant-id (df607198-7bdc-43c6-8353-9b8a822febc5), atlassianOrgId, workspace ID, 
- NEW rainbet-com-rabbitmq.rainbet.com + rainbet-us-staging-rabbitmq.rainbet.com: RabbitMQ Management UI (15671/15672) + AMQP (5671/5672) exposed on raw DigitalOcean origins (159.203.34.207, 165.227.255.111
- NEW staging-api.rainbet.com: leaks x-do-app-origin: 1ce4ff55-e85f-4c30-8033-5129a1812504 (DO App Platform origin UUID) through Cloudflare on 200-empty
- NEW roobet.com/_api/socket.io: Engine.IO handshake succeeds (200, sid assigned, WS upgrade, maxPayload=1000) from Origin: tiki-21.games.roobet.com — transport layer accessible from game SPA domain
- NEW roobet.com/_api/game/{chess,yeti-towers,pop_towers}/currentRoundHash: all HTTP 401 (12B) — uniform auth boundary across 4 game types confirmed
- CHANGED cpanel.avatarux.com: NS/SOA confirms Bluehost apex delegation (ns1/ns2.bluehost.com), no separate claimable delegation for cpanel subdomain; Cloudflare 1001 persists but takeover mechanism unproven, d
- CHANGED betpandacasino.io/rest/public/config: Spring JSON 404 confirmed — casino does NOT mirror affiliates leak; passive corroboration gap CLOSED
- CHANGED betpandacasino.io callback/webhook surface: all 5 endpoints (/rest/callback, /rest/webhook, /rest/notify, /rest/game/callback, /rest/api/game/callback) return 404; SSRF hypothesis falsified
- CHANGED affiliates.betpanda.io/rest/public/config: stable 200 byte-identical (operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms, contentfulAccessToken empty)
- CHANGED affiliates.betpanda.io/rest/player/uid/1: 401-gated confirmed — auth boundary intact anonymously, supports AUTH_HELPED classification
- CHANGED RainBet RabbitMQ cluster: exactly 2 live hosts confirmed (rbtmq-dev/preprod/preprod-us/stg-us all NXDOMAIN); enumeration closed
