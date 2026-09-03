## 2026-09-03 16:48:16 UTC [target] (model nemotron3)
[NEW] `affiliates.betpanda.io` — BetPanda affiliate portal (Vite SPA, Cloudflare-fronted), in-scope brand asset discovered
[NEW] `help.desk.avatarux.com` confirmed as Atlassian Edge (Jira/Confluence help desk), AvatarUX infrastructure
[NEW] `autoconfig.avatarux.com` [200], `autodiscover.avatarux.com` [400], `cpcalendars.avatarux.com` [500], `cpcontacts.avatarux.com` [500] — dedicated hosts with live HTTP status
[CHANGED] `www.avatarux.com` CNAME → `secure.cloudways.cloud` (shared hosting edge), not direct AvatarUX infra
[NEW] Out-of-scope noise identified: alfaview (OpenAPI spec), BASF (Azure Functions), daimlertruck (locked), elringklinger — all unrelated to AvatarUX Studios program
[PRIO] `affiliates.betpanda.io`,7.8,attack_surface=7,business_value=9,tech_exposure=5,gate_ease=10,cloud_surface=6,freshness=8
[PRIO] `help.desk.avatarux.com`,6.5,attack_surface=6,business_value=6,tech_exposure=7,gate_ease=10,cloud_surface=5,freshness=6
[PRIO] `cpanel.avatarux.com`,6.2,attack_surface=8,business_value=8,tech_exposure=6,gate_ease=5,cloud_surface=6,freshness=5
[PRIO] `autoconfig.avatarux.com`,4.1,attack_surface=4,business_value=3,tech_exposure=4,gate_ease=10,cloud_surface=5,freshness=5
[PRIO] `api.roobet.com` (undiscovered),9.5,attack_surface=10,business_value=10,tech_exposure=10,gate_ease=3,cloud_surface=8,freshness=10
[PRIO] `api.stake.com` (undiscovered),9.5,attack_surface=10,business_value=10,tech_exposure=10,gate_ease=3,cloud_surface=8,freshness=10
[PRIO] `api.gamdom.com` (undiscovered),9.5,attack_surface=10,business_value=10,tech_exposure=10,gate_ease=3,cloud_surface=8,freshness=10
[PRIO] `api.rainbet.com` (undiscovered),9.5,attack_surface=10,business_value=10,tech_exposure=10,gate_ease=3,cloud_surface=8,freshness=10
[HYP] BetPanda Affiliate Portal IDOR/BOLA on Affiliate IDs
class: IDOR
asset: affiliates.betpanda.io
confidence: 65
reasoning: Vite SPA affiliate portal for in-scope brand BetPanda; affiliate systems typically use numeric/sequential affiliate_id or campaign_id in API calls; no API routes found in JS bundle suggests API is on separate subdomain or obfuscated
evidence_needed: API endpoint discovery via JS bundle analysis or network interception showing affiliate_id/campaign_id parameters; unauthorized access to other affiliates' stats/commissions/payouts
verify_steps: GET https://affiliates.betpanda.io/ (analyze JS bundles for API base URLs); GET https://api.betpanda.io/ or similar (passive DNS for API subdomains); if API found, test IDOR on /affiliates/{id}/stats, /campaigns/{id}/commissions with different affiliate IDs
impact: Cross-affiliate PII dump (email, payment details), commission theft, campaign manipulation — HIGH
testability: PASSIVE
[HYP] Atlassian Help Desk Information Disclosure / Anonymous Access
class: MISCONFIG
asset: help.desk.avatarux.com
confidence: 55
reasoning: Atlassian Edge (Jira Service Management/Confluence) at help.desk.avatarux.com [302]; public help desks often leak project names, issue types, component names, or allow anonymous issue creation/viewing; 302 suggests redirect to login or portal front
evidence_needed: Anonymous access to /servicedesk/customer/portal/, /rest/servicedeskapi/ endpoints, or Confluence spaces; enumeration of internal project keys, component names, or customer emails
verify_steps: GET https://help.desk.avatarux.com/ (follow 302); GET https://help.desk.avatarux.com/servicedesk/customer/portal/; GET https://help.desk.avatarux.com/rest/servicedeskapi/servicedesk; GET https://help.desk.avatarux.com/wiki/ (Confluence); check for unauthenticated REST API responses
impact: Internal project/infrastructure disclosure, customer ticket data exposure, AvatarUX employee enumeration — MEDIUM
testability: PASSIVE
[HYP] cPanel Hosting Control Panel Exposure / Credential Reuse
class: AUTH
asset: cpanel.avatarux.com
confidence: 45
reasoning: cPanel subdomain exists but unprobed (HTTP unprobed); cPanel on Cloudways shared hosting; if accessible, default/weak credentials or credential reuse from other breaches could grant hosting control; cPanel exposes file manager, databases, email accounts, SSL certs
evidence_needed: Live HTTP service on cpanel.avatarux.com:2083 (HTTPS) or :2082; login panel accessibility; version disclosure
verify_steps: GET https://cpanel.avatarux.com:2083/ (HEAD first); GET https://cpanel.avatarux.com:2082/; check for cPanel login page, version in headers/html; passive SSL cert check for cpanel.avatarux.com
impact: Full hosting compromise — file access, DB access, email takeover, subdomain takeover, SSL key theft — CRITICAL
testability: PASSIVE
[PARKED] cPanel Hosting Control Panel Exposure / Credential Reuse: confidence<50 (45), cpanel.avatarux.com unprobed — may not be live or may be Cloudways-managed with no direct access; verify_steps passive-only but need live confirmation first
[FINAL] 1. BetPanda Affiliate Portal IDOR/BOLA on Affiliate IDs (65)
[FINAL] 2. Atlassian Help Desk Information Disclosure / Anonymous Access (55)
[NEXT] PROBE: GET https://affiliates.betpanda.io/ — fetch main page + all referenced JS bundles (main.*.js, chunk.*.js) for API endpoint discovery; analyze for affiliate_id, campaign_id, user_id, apiBaseUrl, or GraphQL endpoints
[LEARN] REJECTED alfaview OpenAPI/IDOR @ apis.alfaview.com: out of scope (not AvatarUX Studios brand or infrastructure)
[LEARN] REJECTED BASF Azure Functions @ ap-digitalconnect.api.basf.com: out of scope
[LEARN] REJECTED daimlertruck/elringklinger: out of scope
[LEARN] ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed, in-scope AvatarUX infrastructure
[LEARN] ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered
[RISK] avatarux-studios: 75 — High-value gaming brands (Roobet, Stake, Gamdom, BetPanda, RainBet) with undiscovered game/API infrastructure; discovered BetPanda affiliate portal shows brand assets exist and are testable; AvatarUX corporate infra (Atlassian, cPanel) exposes secondary risk; main game API attack surface likely large but unmapped
## 2026-09-03 19:45:57 UTC [target] (model nemotron3)
[NEW] `help.desk.avatarux.com` probe: root 200, `/servicedesk/customer/portal/` 303 (active customer portal), `/rest/servicedeskapi/servicedesk` 401 (auth required), `/wiki/` 200 (Confluence accessible)
[NEW] `cpanel.avatarux.com`: SSL handshake failure on :2083, wrong version on :2082, root SSL failure — cPanel ports not directly accessible via HTTPS; Cloudflare 1001 persists
[NEW] `cpcalendars.avatarux.com` confirmed HTTP 500 (benign disabled feature per knowledge)
[NEW] `affiliates.betpanda.io` confirmed Vite SPA (main.1ae50aab.js), Cloudflare-fronted, **no API routes in JS bundle** — API likely on separate subdomain (e.g., api.betpanda.io, affiliates-api.betpanda.io)
[CHANGED] `help.desk.avatarux.com` was 302, now 200 with active portal/wiki — higher attack surface than redirect suggested
[PRIO] `affiliates.betpanda.io`,7.7,attack_surface=7,business_value=9,tech_exposure=5,gate_ease=10,cloud_surface=6,freshness=8
[PRIO] `cpanel.avatarux.com`,6.5,attack_surface=8,business_value=8,tech_exposure=6,gate_ease=3,cloud_surface=6,freshness=5
[PRIO] `help.desk.avatarux.com`,6.4,attack_surface=6,business_value=6,tech_exposure=7,gate_ease=8,cloud_surface=5,freshness=6
[PRIO] `autoconfig.avatarux.com`,4.9,attack_surface=4,business_value=3,tech_exposure=4,gate_ease=10,cloud_surface=5,freshness=5
[PRIO] `api.roobet.com` (undiscovered),8.8,attack_surface=10,business_value=10,tech_exposure=10,gate_ease=3,cloud_surface=8,freshness=10
[PRIO] `api.stake.com` (undiscovered),8.8,attack_surface=10,business_value=10,tech_exposure=10,gate_ease=3,cloud_surface=8,freshness=10
[PRIO] `api.gamdom.com` (undiscovered),8.8,attack_surface=10,business_value=10,tech_exposure=10,gate_ease=3,cloud_surface=8,freshness=10
[PRIO] `api.rainbet.com` (undiscovered),8.8,attack_surface=10,business_value=10,tech_exposure=10,gate_ease=3,cloud_surface=8,freshness=10
[HYP] BetPanda Affiliate Portal API Subdomain Discovery + IDOR on Affiliate IDs
class: IDOR
asset: affiliates.betpanda.io
confidence: 70
reasoning: Vite SPA affiliate portal for in-scope brand BetPanda; no API routes in JS bundle indicates separate API subdomain; affiliate systems typically use numeric/sequential affiliate_id or campaign_id in API calls; Cloudflare-fronted suggests API also behind Cloudflare
evidence_needed: API subdomain discovery (api.betpanda.io, affiliates-api.betpanda.io, api.affiliates.betpanda.io); API endpoint showing affiliate_id/campaign_id parameters; unauthorized access to other affiliates' stats/commissions/payouts
verify_steps: GET https://affiliates.betpanda.io/ (re-fetch JS bundles for apiBaseUrl, GraphQL endpoint, websocket URLs); passive DNS for *.betpanda.io subdomains (crt.sh, subfinder); GET https://api.betpanda.io/ (HEAD); GET https://affiliates-api.betpanda.io/ (HEAD); if API found, test IDOR on /affiliates/{id}/stats, /campaigns/{id}/commissions with different affiliate IDs
impact: Cross-affiliate PII dump (email, payment details), commission theft, campaign manipulation — HIGH
testability: PASSIVE
[HYP] Atlassian Confluence Wiki Anonymous Space Enumeration / Internal Project Disclosure
class: MISCONFIG
asset: help.desk.avatarux.com
confidence: 60
reasoning: Probe confirms `/wiki/` returns 200 (Confluence accessible); `/servicedesk/customer/portal/` returns 303 (active customer portal); `/rest/servicedeskapi/servicedesk` returns 401 (REST API auth required); public Confluence wikis often expose space names, page titles, user mentions, or allow anonymous space listing via `/rest/api/space` or `/spaces/viewdefaultdecorator.action`
evidence_needed: Anonymous access to Confluence REST API `/rest/api/space`, `/rest/api/content`, `/rest/api/user`; enumeration of space keys, page titles, user accounts; JSM customer portal project enumeration via `/servicedesk/customer/portal/` or `/rest/servicedeskapi/servicedesk/{id}/requesttype`
verify_steps: GET https://help.desk.avatarux.com/wiki/ (analyze HTML for space links, user mentions); GET https://help.desk.avatarux.com/rest/api/space (JSON space list); GET https://help.desk.avatarux.com/rest/api/content (recent content); GET https://help.desk.avatarux.com/servicedesk/customer/portal/ (follow 303, enumerate project keys); GET https://help.desk.avatarux.com/rest/servicedeskapi/servicedesk (already 401, but try without auth for info disclosure)
impact: Internal project/infrastructure disclosure, customer ticket data exposure, AvatarUX employee enumeration, Confluence space content leak — MEDIUM
testability: PASSIVE
[HYP] cPanel Subdomain Takeover via Cloudflare 1001 / Dangling DNS
class: MISCONFIG
asset: cpanel.avatarux.com
confidence: 55
reasoning: Cloudflare error 1001 ("DNS points to prohibited IP") indicates DNS record exists but target IP is blocked by Cloudflare; classic subdomain takeover indicator when DNS points to deprovisioned Cloudways/shared hosting; cPanel subdomain on shared hosting (Cloudways) — if hosting account cancelled but DNS remains, attacker could claim the IP/hosting slot
evidence_needed: DNS resolution for cpanel.avatarux.com (A/AAAA/CNAME); confirm target IP is unclaimed Cloudways/hosting IP; verify no active cPanel service on resolved IP (port 2083/2082)
verify_steps: DIG cpanel.avatarux.com (A, AAAA, CNAME); check resolved IP against Cloudways IP ranges; HEAD https://cpanel.avatarux.com/ (port 443); HEAD http://cpanel.avatarux.com/ (port 80); check for cPanel login page or takeover placeholder
impact: Full hosting compromise — file access, DB access, email takeover, subdomain takeover, SSL key theft, pivot to www.avatarux.com — CRITICAL
testability: PASSIVE
[PARKED] cPanel Subdomain Takeover via Cloudflare 1001 / Dangling DNS: confidence 55 but verify_steps require DNS resolution + IP ownership check which may need active probing beyond passive; Cloudflare 1001 could also be misconfiguration not takeover — keep monitoring but deprioritize until DNS/IP confirmed
[FINAL] 1. BetPanda Affiliate Portal API Subdomain Discovery + IDOR on Affiliate IDs (70)
[FINAL] 2. Atlassian Confluence Wiki Anonymous Space Enumeration / Internal Project Disclosure (60)
[NEXT] PROBE: GET https://affiliates.betpanda.io/ — fetch main page + all referenced JS bundles (main.*.js, chunk.*.js, polyfills.*.js) for API endpoint discovery; extract apiBaseUrl, GraphQL endpoint, websocket URLs, affiliate_id/campaign_id patterns; concurrent passive DNS enumeration for *.betpanda.io via crt.sh/subfinder
[LEARN] ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed live with active JSM customer portal (303) and Confluence wiki (200), in-scope AvatarUX infrastructure
[LEARN] ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered, Vite SPA with no API in bundle — API subdomain hunt required
[LEARN] REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
[LEARN] ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — subdomain takeover candidate, but cPanel ports (2082/2083) not accessible via standard HTTPS (SSL failures)
[RISK] avatarux-studios: 78 — High-value gaming brands (Roobet, Stake, Gamdom, BetPanda, RainBet) with undiscovered game/API infrastructure; discovered BetPanda affiliate portal shows brand assets exist and are testable; AvatarUX corporate infra (Atlassian JSM/Confluence live, cPanel 1001) exposes secondary risk; main game API attack surface likely large but unmapped — priority on API discovery for Roobet/Stake/Gamdom/RainBet
