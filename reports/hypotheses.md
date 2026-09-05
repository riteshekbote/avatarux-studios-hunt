# Hypotheses (ranked)

## RANKED HYPOTHESES 2026-09-02 21:53:50 UTC

## RANKED HYPOTHESES 2026-09-02 23:52:05 UTC

## RANKED HYPOTHESES 2026-09-03 02:58:06 UTC

## RANKED HYPOTHESES 2026-09-03 07:56:17 UTC

## RANKED HYPOTHESES 2026-09-03 12:38:20 UTC

## RANKED HYPOTHESES 2026-09-03 16:48:27 UTC
- [65] help.desk.avatarux.com: helpdesk_redirect_to_managed_app (from art/lead_bigpickle.txt)
- [65] affiliates.betpanda.io: BetPanda Affiliate Portal IDOR/BOLA on Affiliate IDs (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: curl -sI https://help.desk.avatarux.com && curl -sI http://cpanel.avatarux.com && curl -sI https://cpanel.avatarux.com
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://affiliates.betpanda.io/ — fetch main page + all referenced JS bundles (main.*.js, chunk.*.js) for API endpoint discovery; analyze for affilia
- LEARN: ACCEPTED MISCONFIG @ cPanel/helpdesk: standard recon targets; will confirm with passive probes before escalation.
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 likely benign disabled feature, parked for now.
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 is strong takeover indicator
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM exposes internal configuration in HTML
- LEARN: REJECTED alfaview OpenAPI/IDOR @ apis.alfaview.com: out of scope (not AvatarUX Studios brand or infrastructure)
- LEARN: REJECTED BASF Azure Functions @ ap-digitalconnect.api.basf.com: out of scope
- LEARN: REJECTED daimlertruck/elringklinger: out of scope
- LEARN: ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed, in-scope AvatarUX infrastructure
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered

## RANKED HYPOTHESES 2026-09-03 19:46:06 UTC
- [78] cpanel.avatarux.com: cpanel_subdomain_takeover_cloudflare_1001 (from art/lead_bigpickle.txt)
- [70] affiliates.betpanda.io: BetPanda Affiliate Portal API Subdomain Discovery + IDOR on Affiliate IDs (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://affiliates.betpanda.io/ — fetch main page + all referenced JS bundles (main.*.js, chunk.*.js, polyfills.*.js) for API endpoint discovery; ext
- NEXT(hypotheses-bigpickle.txt): PROBE: Verify cpanel.avatarux.com takeover feasibility - GET https://cpanel.avatarux.com && dig cpanel.avatarux.com CNAME && dig cpanel.avatarux.com A
- LEARN: ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed live with active JSM customer portal (303) and Confluence wiki (200), in-scope AvatarUX in
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered, Vite SPA with no API in bundle — API subdomain hunt required
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — subdomain takeover candidate, but cPanel ports (2082/2083) not accessible via standard HTTPS (SSL failur
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 is strong takeover indicator
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM exposes internal configuration in HTML
- LEARN: REJECTED alfaview OpenAPI/IDOR @ apis.alfaview.com: out of scope (not AvatarUX Studios brand)
- LEARN: REJECTED BASF Azure Functions @ ap-digitalconnect.api.basf.com: out of scope
- LEARN: REJECTED daimlertruck/elringklinger: out of scope
- LEARN: ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed, in-scope AvatarUX infrastructure
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered

## RANKED HYPOTHESES 2026-09-03 21:57:36 UTC
- [70] affiliates.betpanda.io: BetPanda Affiliate Portal API Subdomain Discovery + IDOR on Affiliate IDs (from art/lead_nemotron3.txt)
- [60] help.desk.avatarux.com: cpanel_subdomain_takeover_cloudflare_1001 (from art/lead_bigpickle.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: Passive DNS enumeration for *.betpanda.io via crt.sh (https://crt.sh/?q=%.betpanda.io) and subfinder; concurrent GET https://affiliates.betpanda.io/main.
- NEXT(hypotheses-bigpickle.txt): PROBE: Verify cpanel.avatarux.com takeover feasibility by checking if origin serves content or is abandoned.
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered, Vite SPA with no API in bundle — API subdomain hunt required
- LEARN: ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed live with active JSM customer portal (303) and Confluence wiki (303), in-scope AvatarUX in
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — subdomain takeover candidate, CNAME → avatarux.com → Cloudflare IP (162.159.136.54), cPanel ports (2082/
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 is strong takeover indicator
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM exposes internal configuration in HTML

## RANKED HYPOTHESES 2026-09-03 23:50:02 UTC
- [78] cpanel.avatarux.com: cpanel_subdomain_takeover_cloudflare_1001 (from art/lead_bigpickle.txt)
- [70] affiliates.betpanda.io: BetPanda Affiliate Portal API Subdomain Discovery + IDOR on Affiliate IDs (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: Attempt BetPanda API subdomain discovery by testing common patterns (api.betpanda.io, backend.betpanda.io, app-api.betpanda.io) with DNS lookups and HTTP
- NEXT(hypotheses-nemotron3.txt): PROBE: Passive DNS enumeration for *.betpanda.io via crt.sh (https://crt.sh/?q=%.betpanda.io) and subfinder; concurrent GET https://affiliates.betpanda.io/main.
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — subdomain takeover candidate, CNAME → avatarux.com → Cloudflare IP (162.159.136.54), cPanel ports (2082/
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM customer portal exposes tenant IDs, feature flags, and experiment configurations in page source HTML
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered, Vite SPA with no API in bundle — API subdomain hunt required
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered, Vite SPA with no API in bundle — API subdomain hunt required
- LEARN: ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed live with active JSM customer portal (303) and Confluence wiki (303), in-scope AvatarUX in
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — subdomain takeover candidate, CNAME → avatarux.com → Cloudflare IP (162.159.136.54), cPanel ports (2082/
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: custom Node "BB CABLE" service live, Cloudflare-fronted, in-scope BetPanda brand infrastructure
- LEARN: ACCEPTED OTHER @ betpandacasino.io: SPA catch-all shadows /graphql and /api — real API base URL undiscovered, high-value casino target

## RANKED HYPOTHESES 2026-09-04 03:03:06 UTC
- [70] affiliates.betpanda.io: BetPanda Affiliate Portal API Subdomain Discovery + IDOR on Affiliate IDs (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: Passive DNS enumeration for *.betpanda.io via crt.sh (https://crt.sh/?q=%.betpanda.io) and subfinder; concurrent GET https://affiliates.betpanda.io/main.
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered, Vite SPA with no API in bundle — API subdomain hunt required
- LEARN: ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed live with active JSM customer portal (303) and Confluence wiki (303), in-scope AvatarUX in
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — subdomain takeover candidate, CNAME → avatarux.com → Cloudflare IP (162.159.136.54), cPanel ports (2082/
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: custom Node "BB CABLE" service live, Cloudflare-fronted, in-scope BetPanda brand infrastructure
- LEARN: ACCEPTED OTHER @ betpandacasino.io: SPA catch-all shadows /graphql and /api — real API base URL undiscovered, high-value casino target

## RANKED HYPOTHESES 2026-09-04 07:48:19 UTC
- [70] affiliates.betpanda.io: BetPanda Affiliate Portal API Subdomain Discovery + IDOR on Affiliate IDs (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: Passive DNS enumeration for *.betpanda.io via crt.sh (https://crt.sh/?q=%.betpanda.io) and subfinder; concurrent GET https://affiliates.betpanda.io/main.
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered, Vite SPA with no API in bundle — API subdomain hunt required
- LEARN: ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed live with active JSM customer portal (303) and Confluence wiki (303), in-scope AvatarUX in
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — subdomain takeover candidate, CNAME → avatarux.com → Cloudflare IP (162.159.136.54), cPanel ports (2082/
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: custom Node "BB CABLE" service live, Cloudflare-fronted, in-scope BetPanda brand infrastructure
- LEARN: ACCEPTED OTHER @ betpandacasino.io: SPA catch-all shadows /graphql and /api — real API base URL undiscovered, high-value casino target

## RANKED HYPOTHESES 2026-09-04 12:42:00 UTC
- [78] cpanel.avatarux.com: cpanel_subdomain_takeover_cloudflare_1001 (from art/lead_bigpickle.txt)
- [65] help.desk.avatarux.com: helpdesk_redirect_to_managed_app (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: Fetch https://affiliates.betpanda.io/ — extract all <script> bundle URLs from HTML, then GET the primary bundle and grep for `baseURL`, `apiUrl`, `VITE_`
- NEXT(hypotheses-nemotron3.txt): PROBE: curl -sI https://help.desk.avatarux.com && curl -sI http://cpanel.avatarux.com && curl -sI https://cpanel.avatarux.com
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — 15+ hour stable state confirms dangling DNS, subdomain takeover candidate
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: Vite SPA with zero API routes in bundle — API subdomain hunt remains blocked after NXDOMAIN on common patterns
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM/Confluence behind Atlassian Edge, tenant IDs in HTML, REST endpoints return 401/404/303
- LEARN: ACCEPTED OTHER @ betpandacasino.io: SPA catch-all shadows /graphql and /api — real API undiscovered
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: Custom Node "BB CABLE" service live, WS paths /socket /ws /events all 404
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature
- LEARN: ACCEPTED MISCONFIG @ cPanel/helpdesk: standard recon targets; will confirm with passive probes before escalation.
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 likely benign disabled feature, parked for now.
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 is strong takeover indicator
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM exposes internal configuration in HTML
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 is strong takeover indicator
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM exposes internal configuration in HTML
- LEARN: REJECTED alfaview OpenAPI/IDOR @ apis.alfaview.com: out of scope (not AvatarUX Studios brand)
- LEARN: REJECTED BASF Azure Functions @ ap-digitalconnect.api.basf.com: out of scope
- LEARN: REJECTED daimlertruck/elringklinger: out of scope
- LEARN: ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed, in-scope AvatarUX infrastructure
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 is strong takeover indicator
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM exposes internal configuration in HTML
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — subdomain takeover candidate, CNAME → avatarux.com → Cloudflare IP (162.159.136.54), cPanel ports (2082/
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM customer portal exposes tenant IDs, feature flags, and experiment configurations in page source HTML
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered, Vite SPA with no API in bundle — API subdomain hunt required
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered, Vite SPA with no API in bundle — API subdomain hunt required
- LEARN: ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed live with active JSM customer portal (303) and Confluence wiki (303), in-scope AvatarUX in
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — subdomain takeover candidate, CNAME → avatarux.com → Cloudflare IP (162.159.136.54), cPanel ports (2082/
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: custom Node "BB CABLE" service live, Cloudflare-fronted, in-scope BetPanda brand infrastructure
- LEARN: ACCEPTED OTHER @ betpandacasino.io: SPA catch-all shadows /graphql and /api — real API base URL undiscovered, high-value casino target

## RANKED HYPOTHESES 2026-09-04 16:39:41 UTC
- [72] affiliates.betpanda.io/rest/player/uid/{id}: betpanda_affiliate_idor_on_player_uid (from art/lead_bigpickle.txt)
- [70] affiliates.betpanda.io: BetPanda Affiliate Portal API Subdomain Discovery + IDOR on Affiliate IDs (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: Test password reset timing differential — GET /rest/public/recover-password/email/admin@betpanda.io vs /rest/public/recover-password/email/nonexistent_xy
- NEXT(hypotheses-nemotron3.txt): PROBE: Passive DNS enumeration for *.betpanda.io via crt.sh (https://crt.sh/?q=%.betpanda.io) and subfinder; concurrent GET https://affiliates.betpanda.io/main.
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend confirmed same-origin at /rest; full endpoint map extracted (20+ routes); /rest/public/config leaks operator
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 with no body — potential enumeration vector, rate limitin
- LEARN: ACCEPTED MISCONFIG @ affiliates.betpanda.io: /config/config.json exposes runtime config including operatorId=1, CMS integration details, betpanda.partners link,
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: custom Node "BB CABLE" service live, Cloudflare-fronted, in-scope BetPanda brand infrastructure
- LEARN: ACCEPTED OTHER @ betpandacasino.io: SPA catch-all shadows /graphql and /api — real API base URL undiscovered, high-value casino target
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — 15+ hour stable state confirms dangling DNS, subdomain takeover candidate
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: Vite SPA with zero API routes in bundle — API subdomain hunt remains blocked after NXDOMAIN on common patterns
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM/Confluence behind Atlassian Edge, tenant IDs in HTML, REST endpoints return 401/404/303
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature

## RANKED HYPOTHESES 2026-09-04 19:14:47 UTC
- [78] cpanel.avatarux.com: cpanel_subdomain_takeover_cloudflare_1001 (from art/lead_bigpickle.txt)
- [72] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on /rest/player/uid/{id} with Auth Session (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: Reconfirm cpanel.avatarux.com Cloudflare 1001 persistence (curl status page) and concurrently run passive CT enumeration via certspotter API for avatarux
- NEXT(hypotheses-nemotron3.txt): PROBE: Test password reset timing differential — GET https://affiliates.betpanda.io/rest/public/recover-password/email/admin@betpanda.io vs GET https://affiliat
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend confirmed same-origin at /rest; full endpoint map extracted (20+ routes); /rest/public/config leaks operator
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 with no body — potential enumeration vector, rate limitin
- LEARN: ACCEPTED MISCONFIG @ affiliates.betpanda.io: /config/config.json exposes runtime config including operatorId=1, CMS integration details, betpanda.partners link,
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — 15+ hour stable state confirms dangling DNS, subdomain takeover candidate
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM/Confluence behind Atlassian Edge, tenant IDs in HTML, REST endpoints return 401/404/303
- LEARN: ACCEPTED OTHER @ betpandacasino.io: SPA catch-all shadows /graphql and /api — real API undiscovered
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: Custom Node "BB CABLE" service live, WS paths /socket /ws /events all 404

## RANKED HYPOTHESES 2026-09-04 21:36:26 UTC
- [72] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on /rest/player/uid/{id} with Auth Session (from art/lead_nemotron3.txt)
- [65] help.desk.avatarux.com: helpdesk_redirect_to_managed_app (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: curl -sI https://help.desk.avatarux.com && curl -sI http://cpanel.avatarux.com && curl -sI https://cpanel.avatarux.com
- NEXT(hypotheses-nemotron3.txt): PROBE: Test password reset timing differential — GET https://affiliates.betpanda.io/rest/public/recover-password/email/admin@betpanda.io vs GET https://affiliat
- LEARN: ACCEPTED MISCONFIG @ cPanel/helpdesk: standard recon targets; will confirm with passive probes before escalation.
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 likely benign disabled feature, parked for now.
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 is strong takeover indicator
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM exposes internal configuration in HTML
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 is strong takeover indicator
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM exposes internal configuration in HTML
- LEARN: REJECTED alfaview OpenAPI/IDOR @ apis.alfaview.com: out of scope (not AvatarUX Studios brand)
- LEARN: REJECTED BASF Azure Functions @ ap-digitalconnect.api.basf.com: out of scope
- LEARN: REJECTED daimlertruck/elringklinger: out of scope
- LEARN: ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed, in-scope AvatarUX infrastructure
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered
- LEARN: REJECTED alfaview OpenAPI/IDOR @ apis.alfaview.com: out of scope (not AvatarUX Studios brand or infrastructure)
- LEARN: REJECTED BASF Azure Functions @ ap-digitalconnect.api.basf.com: out of scope
- LEARN: REJECTED daimlertruck/elringklinger: out of scope
- LEARN: ACCEPTED MISCONFIG @ help.desk.avatarux.com: Atlassian Edge confirmed, in-scope AvatarUX infrastructure
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: in-scope brand (BetPanda) affiliate portal discovered
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — 15+ hour stable state confirms dangling DNS, subdomain takeover candidate
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: custom Node "BB CABLE" service live, Cloudflare-fronted, in-scope BetPanda brand infrastructure
- LEARN: ACCEPTED OTHER @ betpandacasino.io: SPA catch-all shadows /graphql and /api — real API base URL undiscovered, high-value casino target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend confirmed same-origin at /rest; full endpoint map extracted (20+ routes); /rest/public/config leaks operator
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 with no body — potential enumeration vector, rate limitin
- LEARN: ACCEPTED MISCONFIG @ affiliates.betpanda.io: /config/config.json exposes runtime config including operatorId=1, CMS integration details, betpanda.partners link,
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM/Confluence behind Atlassian Edge, tenant IDs in HTML, REST endpoints return 401/404/303

## RANKED HYPOTHESES 2026-09-04 23:20:31 UTC
- [72] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on /rest/player/uid/{id} with Auth Session (from art/lead_nemotron3.txt)
- [65] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on /rest/player/uid/{id} (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://betpandacasino.io/rest/user/account-balances-and-bonuses (unauthenticated) — confirm 401 auth-gate vs 200 money-data leak on newly discovered
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://affiliates.betpanda.io/rest/public/recover-password/email/admin@betpanda.io (measure response time ms, body) && GET https://affiliates.betpan
- LEARN: ACCEPTED OTHER @ betpandacasino.io: real API base discovered = same-origin /rest (config/config.json, mirrors affiliates) — SPA catch-all /graphql,/api were pur
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/properties/manifest public; backend = Spring Boot via JSON 404/405 signature; no actuator/swagger/api-docs exposed
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL; new BetPanda subdomain, challenge-ga
- LEARN: ACCEPTED OTHER @ betpandacasino.io: bundle leaks AWS client assets: CloudWatch identity pool (eu-west-1), CloudFront dist d3ec3n7kizfkuy.cloudfront.net, S3 nano
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — 15+ hour stable state confirms dangling DNS, subdomain takeover candidate
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: custom Node "BB CABLE" service live, Cloudflare-fronted, in-scope BetPanda brand infrastructure
- LEARN: ACCEPTED OTHER @ betpandacasino.io: SPA catch-all shadows /graphql and /api — real API base URL undiscovered, high-value casino target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend confirmed same-origin at /rest; full endpoint map extracted (20+ routes); /rest/public/config leaks operator
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 with no body — potential enumeration vector, rate limitin
- LEARN: ACCEPTED MISCONFIG @ affiliates.betpanda.io: /config/config.json exposes runtime config including operatorId=1, CMS integration details, betpanda.partners link,
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM/Confluence behind Atlassian Edge, tenant IDs in HTML, REST endpoints return 401/404/303

## RANKED HYPOTHESES 2026-09-05 01:16:23 UTC
- [78] cpanel.avatarux.com: BetPa[0m (from art/lead_nemotron3.txt)
- [65] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on /rest/player/uid/{id} (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://betpandacasino.io/rest/properties/manifest with headers `x-preferred-app-context: roobet_com` and `x-captcha-token: 1` — any deviation from b
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://affiliates.betpanda.io/rest/public/recover-password/email/admin@betpanda.io (measure response time ms, body) && GET https://affiliates.betpan
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com: /wiki/rest/api/space?limit=5 → 303 to root stable — Confluence anonymous space enumeration closed behind Atlassian 
- LEARN: REJECTED MISCONFIG @ betpandacasino.io: x-site-name-id tenant header ignored on public manifest (roobet_com/stake_com still echo betpandacasino_io) — no passive
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend confirmed same-origin at /rest; full endpoint map extracted (20+ routes); /rest/public/config leaks operator
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 with no body — potential enumeration vector, rate limitin
- LEARN: ACCEPTED MISCONFIG @ affiliates.betpanda.io: /config/config.json exposes runtime config including operatorId=1, CMS integration details, betpanda.partners link,
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: real API base = same-origin /rest; /rest/properties/manifest public; Spring Boot backend; no actuator/swagger/api-docs e
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: bundle leaks AWS client assets: CloudWatch identity pool (eu-west-1), CloudFront dist d3ec3n7kizfkuy.cloudfront.net, S3 
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — 48h stable state confirms dangling DNS, subdomain takeover candidate
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: custom Node "BB CABLE" service live, Cloudflare-fronted, in-scope BetPanda brand infrastructure
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM/Confluence behind Atlassian Edge, tenant IDs in HTML, REST endpoints return 401/404/303

## RANKED HYPOTHESES 2026-09-05 05:51:34 UTC
- [75] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on /rest/player/uid/{id} with Auth Session (from art/lead_nemotron3.txt)
- [40] betpandacasino.io/rest/properties/manifest: Multi-tenant routing header (x-preferred-app-context) on shared casino /rest (from art/lead_bigpickle.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://affiliates.betpanda.io/rest/public/recover-password/email/admin@betpanda.io (measure response time ms, body) && GET https://affiliates.betpan
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend confirmed same-origin at /rest; full endpoint map extracted (20+ routes); /rest/public/config leaks operator
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 with no body — potential enumeration vector, rate limitin
- LEARN: ACCEPTED MISCONFIG @ affiliates.betpanda.io: /config/config.json exposes runtime config including operatorId=1, CMS integration details, betpanda.partners link,
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: real API base = same-origin /rest; /rest/properties/manifest public; Spring Boot backend; no actuator/swagger/api-docs e
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: bundle leaks AWS client assets: CloudWatch identity pool (eu-west-1), CloudFront dist d3ec3n7kizfkuy.cloudfront.net, S3 
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: ACCEPTED MISCONFIG @ cpanel: Cloudflare 1001 persists — 48h stable state confirms dangling DNS, subdomain takeover candidate
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: custom Node "BB CABLE" service live, Cloudflare-fronted, in-scope BetPanda brand infrastructure
- LEARN: ACCEPTED MISCONFIG @ help.desk: JSM/Confluence behind Atlassian Edge, tenant IDs in HTML, REST endpoints return 401/404/303
