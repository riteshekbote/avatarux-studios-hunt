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

## RANKED HYPOTHESES 2026-09-05 10:03:08 UTC
- [75] affiliates.betpanda.io/rest/player/uid/{id}: cPanel Subdomain Takeover via Cloudflare 1001 / Dangling DNS (from art/lead_nemotron3.txt)
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

## RANKED HYPOTHESES 2026-09-05 13:24:54 UTC
- [75] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on /rest/player/uid/{id} with Auth Session (from art/lead_nemotron3.txt)
- [72] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on /rest/player/uid/{id} (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://affiliates.betpanda.io/rest/public/recover-password/email/admin@betpanda.io (measure response time ms, body length) && GET https://affiliates
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

## RANKED HYPOTHESES 2026-09-05 16:10:25 UTC
- [58] affiliates.betpanda.io/rest/public/recover-password/email/{email}: Password reset timing differential enables account enumeration on affiliates (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://affiliates.betpanda.io/rest/public/recover-password/email/admin@betpanda.io (capture time_total via curl -w) && GET https://affiliates.betpan
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 no body — timing enumeration unvalidated
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: ACCEPTED OTHER @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-gated;

## RANKED HYPOTHESES 2026-09-05 18:26:01 UTC
- [75] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on /rest/player/uid/{id} with Auth Session (from art/lead_nemotron3.txt)
- [58] affiliates.betpanda.io/rest/public/recover-password/email/{email}: BetPanda Password Reset Timing Differential for Account Enumeration (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://affiliates.betpanda.io/rest/public/recover-password/email/admin@betpanda.io (capture time_total via curl -w) && GET https://affiliates.betpan
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://affiliates.betpanda.io/rest/public/recover-password/email/admin@betpanda.io (measure response time ms via curl -w "%{time_total}", capture bo
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 no body — timing enumeration unvalidated
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: ACCEPTED OTHER @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-gated;
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

## RANKED HYPOTHESES 2026-09-05 20:45:53 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on /rest/player/uid/{id} with Auth Session (from art/lead_nemotron3.txt)
- [72] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on /rest/player/uid/{id} (from art/lead_bigpickle.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://cpanel.avatarux.com/ -H "User-Agent: AvatarUX-Recon/1.0" (confirm Cloudflare 1001 persists) && GET https://crt.sh/?q=%.avatarux.com -H "User-
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 no body — timing enumeration unvalidated
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 HTTP 200 — expands attack surface for tenant ID e
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL

## RANKED HYPOTHESES 2026-09-05 22:43:57 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- [58] affiliates.betpanda.io/rest/public/recover-password/email/{email}: BetPanda Password Reset Timing Differential for Account Enumeration (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://affiliates.betpanda.io/rest/public/recover-password/email/admin@betpanda.io (capture time_total via curl -w) && GET https://affiliates.betpan
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://cpanel.avatarux.com/ -H "User-Agent: AvatarUX-Recon/1.0" (confirm Cloudflare 1001 persists) && GET https://crt.sh/?q=%.avatarux.com -H "User-
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 no body — timing enumeration unvalidated
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: ACCEPTED OTHER @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-gated;
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 no body — timing enumeration unvalidated
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: ACCEPTED OTHER @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-gated;
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 no body — timing enumeration unvalidated
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 HTTP 200 — expands attack surface for tenant ID e
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked

## RANKED HYPOTHESES 2026-09-06 00:24:07 UTC
- [80] cpanel.avatarux.com: cPanel Subdomain Takeover via Cloudflare 1001 Dangling DNS (from art/lead_nemotron3.txt)
- [55] betpandacasino.io/rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt}: BetPanda Casino Tenant Isolation on Financial POST Endpoints (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): PROBE: GET https://betpandacasino.io/rest/public/config with `curl -s -o /tmp/opencode/casino_cfg.json -w "%{http_code} %{content_type}"` — real Spring JSON (af
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://cpanel.avatarux.com/ -H "User-Agent: AvatarUX-Recon/1.0" (confirm Cloudflare 1001 persists) && GET https://crt.sh/?q=%.avatarux.com -H "User-
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: ACCEPTED OTHER @ betpandacasino.io: only remaining cheap passive gap is /rest/public/config mirror; all other passive surfaces closed (actuator/api-docs 404, SP
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: 48h+ stable dangling DNS reconfirmed; claim mechanism remains the sole unknown — NS/SOA delegation check still unevide
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 no body — timing enumeration unvalidated
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 HTTP 200 — expands attack surface for tenant ID e
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked

## RANKED HYPOTHESES 2026-09-06 04:49:30 UTC
- [80] cpanel.avatarux.com: cPanel Subdomain Takeover via Cloudflare 1001 Dangling DNS (from art/lead_nemotron3.txt)
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: request program-authorized credentialed sessions for affiliates.betpanda.io and betpandacasino.io (or written authorization to test the two AUTH_HELPED e
- NEXT(hypotheses-nemotron3.txt): PROBE: DIG cpanel.avatarux.com NS + SOA (verify delegation chain) && GET https://crt.sh/?q=%.avatarux.com -H "User-Agent: AvatarUX-Recon/1.0" (check CT logs for
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED AUTH @ affiliates.betpanda.io: Password reset endpoint accepts email in URL path, returns 204 no body — timing enumeration unvalidated
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 HTTP 200 — expands attack surface for tenant ID e
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no

## RANKED HYPOTHESES 2026-09-06 09:25:36 UTC
- [82] cpanel.avatarux.com: cPanel Subdomain Takeover via Cloudflare 1001 Dangling DNS (from art/lead_nemotron3.txt)
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: request program-authorized credentialed sessions for affiliates.betpanda.io and betpandacasino.io (or written authorization to test the two AUTH_HELPED P
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://crt.sh/?q=%.avatarux.com -H "User-Agent: AvatarUX-Recon/1.0" (confirm CT logs show wildcard cert to Cloudflare only, no dedicated cpanel cert
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no

## RANKED HYPOTHESES 2026-09-06 13:04:49 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID (from art/lead_bigpickle.txt)
- [72] cpanel.avatarux.com: cPanel Subdomain Takeover via Cloudflare 1001 Dangling DNS — Delegation Gap Unproven (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: request program-authorized credentialed sessions for affiliates.betpanda.io and betpandacasino.io (or written authorization to test the two AUTH_HELPED e
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://crt.sh/?q=%.avatarux.com -H "User-Agent: AvatarUX-Recon/1.0" (confirm CT logs show wildcard cert to Cloudflare only, no dedicated cpanel cert
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa

## RANKED HYPOTHESES 2026-09-06 16:10:39 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: request program-authorized credentialed sessions for affiliates.betpanda.io and betpandacasino.io (or written authorization to test the two AUTH_HELPED e
- NEXT(hypotheses-nemotron3.txt): HUMAN: request program-authorized credentialed sessions for affiliates.betpanda.io and betpandacasino.io (or written authorization to test the two AUTH_HELPED h
- LEARN: ACCEPTED OTHER @ all live in-scope hosts: re-verified stable (cpanel 000/1001, affiliates 200, casino 200, help.desk 302); casino /rest/public/config 404 vs aff
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, las
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa

## RANKED HYPOTHESES 2026-09-06 18:20:28 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: request program-authorized credentialed sessions for affiliates.betpanda.io and betpandacasino.io (or written authorization to test the two AUTH_HELPED e
- NEXT(hypotheses-nemotron3.txt): HUMAN: request program-authorized credentialed sessions for affiliates.betpanda.io and betpandacasino.io (or written authorization to test the two AUTH_HELPED h
- LEARN: ACCEPTED OTHER @ all live in-scope hosts: re-verified stable (cpanel 000/1001, affiliates 200, casino 200, help.desk 302); casino /rest/public/config 404 vs aff
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, las
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa

## RANKED HYPOTHESES 2026-09-06 20:34:49 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: request program-authorized credentialed sessions for affiliates.betpanda.io and betpandacasino.io (or written authorization to test the two AUTH_HELPED e
- NEXT(hypotheses-nemotron3.txt): HUMAN: request program-authorized credentialed sessions for affiliates.betpanda.io and betpandacasino.io (or written authorization to test the two AUTH_HELPED h
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa

## RANKED HYPOTHESES 2026-09-06 22:21:47 UTC
- [100] (none: No GitHub org candidates configured for source-code audit (from art/lead_bigpickle.txt)
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: request program-authorized credentialed sessions for affiliates.betpanda.io and betpandacasino.io (or written authorization to test the two AUTH_HELPED e
- NEXT(hypotheses-nemotron3.txt): HUMAN: request program-authorized credentialed sessions for affiliates.betpanda.io and betpandacasino.io (or written authorization to test the two AUTH_HELPED h
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa

## RANKED HYPOTHESES 2026-09-07 00:11:09 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID (from art/lead_bigpickle.txt)
- [62] betpandacasino.io/rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt}: BetPanda Casino Tenant Isolation Bypass via x-site-name-id Header on Financial Endpoints (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: request program-authorized credentialed sessions for affiliates.betpanda.io and betpandacasino.io (or written authorization to test the two AUTH_HELPED h
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unproven
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa

## RANKED HYPOTHESES 2026-09-07 04:55:57 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID (from art/lead_bigpickle.txt)
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://cable.betpanda.io/ — capture full response body/headers; GET https://cable.betpanda.io/health; GET https://cable.betpanda.io/api; GET https:/
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS/SOA confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unpr
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa

## RANKED HYPOTHESES 2026-09-07 10:05:27 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: both remaining high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 55) are AUTH_HELPED and blocked on authorized credentialed sessions that
- NEXT(hypotheses-nemotron3.txt): PROBE: GET https://cable.betpanda.io/ — capture full response body/headers; GET https://cable.betpanda.io/health; GET https://cable.betpanda.io/api; GET https:/
- LEARN: REJECTED MISCONFIG @ cable.betpanda.io: cleared nemotron3-queued PROBE — root 200 text/plain decorative ASCII banner, all other paths (/health /api /graphql /ac
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS/SOA confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unpr
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa

## RANKED HYPOTHESES 2026-09-07 15:56:14 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: both remaining high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 55) are AUTH_HELPED and blocked on authorized credentialed sessions that
- LEARN: REJECTED MISCONFIG @ cable.betpanda.io: cleared nemotron3-queued PROBE — root 200 text/plain decorative ASCII banner, all other paths (/health /api /graphql /ac

## RANKED HYPOTHESES 2026-09-07 19:36:48 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: both remaining high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) are AUTH_HELPED and blocked on authorized credentialed sessions that
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: bare Express server confirmed — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /event
- LEARN: REJECTED MISCONFIG @ cable.betpanda.io: undocumented endpoint exposure hypothesis FALSIFIED — no surface to enumerate
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS/SOA confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unpr
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa

## RANKED HYPOTHESES 2026-09-07 22:25:31 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_bigpickle.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: both remaining high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 55) remain AUTH_HELPED and blocked — passive surface fully exhausted (cm
- LEARN: REJECTED MISCONFIG @ affiliates.betpanda.io/cms: strapiApiUrl:"/cms" resolves to the SPA index.html shell (Vite main.ef021e68.js, title=Affiliate), identical to
- LEARN: ACCEPTED OTHER @ betpandacasino.io/config/config.json: 200 returns {"baseUrl":"https://betpandacasino.io/rest"} — mirrors affiliate baseUrl config, corroborates

## RANKED HYPOTHESES 2026-09-08 00:31:28 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: both remaining high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 55) remain AUTH_HELPED and blocked — passive surface re-verified exhaust
- NEXT(hypotheses-nemotron3.txt): HUMAN: both remaining high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) are AUTH_HELPED and blocked on authorized credentialed sessions that
- LEARN: ACCEPTED OTHER @ affiliates.betpanda.io: /rest/public/config re-verified 200 this cycle — operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms 
- LEARN: ACCEPTED OTHER @ betpandacasino.io: manifest 200 + /config/config.json 200 (baseUrl=/rest) + OPTIONS /rest/user/authenticate 200 leaking x-site-name-id/x-prefer
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: bare Express server confirmed — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /event
- LEARN: REJECTED MISCONFIG @ cable.betpanda.io: undocumented endpoint exposure hypothesis FALSIFIED — no surface to enumerate
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS/SOA confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unpr
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa

## RANKED HYPOTHESES 2026-09-08 05:14:58 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: both high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 55) re-verified blocked this cycle — all passives stable (affiliates leak body unc
- NEXT(hypotheses-nemotron3.txt): HUMAN: both remaining high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) are AUTH_HELPED and blocked on authorized credentialed sessions that
- LEARN: ACCEPTED OTHER @ affiliates.betpanda.io/rest/public/config: re-verified 200 with byte-identical body (operatorId=1, supportEmail=deals@bamboopartners.io, strapi
- LEARN: ACCEPTED OTHER @ betpandacasino.io: manifest 200 + /config/config.json 200 (baseUrl=/rest) + OPTIONS /rest/user/authenticate 200 — passive surface stable, no ne
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: both JSM portals now 303-gated, root 302 — reduced attack surface stable.
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: bare Express server confirmed — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /event
- LEARN: REJECTED MISCONFIG @ cable.betpanda.io: undocumented endpoint exposure hypothesis FALSIFIED — no surface to enumerate
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS/SOA confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unpr
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa

## RANKED HYPOTHESES 2026-09-08 09:53:23 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- NEXT(hypotheses-nemotron3.txt): HUMAN: Both high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) are AUTH_HELPED and blocked on authorized credentialed sessions. Request progr
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: bare Express server confirmed — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /event
- LEARN: REJECTED MISCONFIG @ cable.betpanda.io: undocumented endpoint exposure hypothesis FALSIFIED — no surface to enumerate
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS/SOA confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unpr
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target

## RANKED HYPOTHESES 2026-09-08 14:17:39 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: both remaining high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 55) remain AUTH_HELPED and blocked — passive surface re-verified exhaust
- NEXT(hypotheses-nemotron3.txt): HUMAN: Both high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) are AUTH_HELPED and blocked on authorized credentialed sessions. Request progr
- LEARN: ACCEPTED OTHER @ affiliates.betpanda.io/rest/public/config: re-verified 200 this cycle — operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms l
- LEARN: ACCEPTED OTHER @ betpandacasino.io: manifest 200 + /config/config.json 200 (baseUrl=/rest) + OPTIONS /rest/user/authenticate 200 — passive surface stable, no ne
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: both JSM portals now 303-gated, root 302 — reduced attack surface stable.
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 — casino does NOT mirror affiliates leak; hypothesis falsified.
- LEARN: REJECTED MISCONFIG @ cable.betpanda.io: undocumented endpoint exposure hypothesis FALSIFIED — bare Express server, no functional endpoints.
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig.
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: bare Express server confirmed — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /event
- LEARN: REJECTED MISCONFIG @ cable.betpanda.io: undocumented endpoint exposure hypothesis FALSIFIED — no surface to enumerate
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS/SOA confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unpr
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target

## RANKED HYPOTHESES 2026-09-08 18:04:37 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Casino Tenant Isolation on Financial POST Endpoints (from art/lead_bigpickle.txt)
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: both remaining high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 55) remain AUTH_HELPED and blocked — passive surface re-verified exhaust
- NEXT(hypotheses-nemotron3.txt): HUMAN: Both high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) are AUTH_HELPED and blocked on authorized credentialed sessions. Request progr
- LEARN: ACCEPTED OTHER @ affiliates.betpanda.io/rest/public/config: re-verified 200 this cycle — operatorId=1, supportEmail=deals@bamboopartners.io, strapiApiUrl=/cms l
- LEARN: ACCEPTED OTHER @ betpandacasino.io: manifest 200 + /config/config.json 200 (baseUrl=/rest) + OPTIONS /rest/user/authenticate 200 — passive surface stable, no ne
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: both JSM portals now 303-gated, root 302 — reduced attack surface stable.
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 — casino does NOT mirror affiliates leak; hypothesis falsified.
- LEARN: REJECTED MISCONFIG @ cable.betpanda.io: undocumented endpoint exposure hypothesis FALSIFIED — bare Express server, no functional endpoints.
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig.
- LEARN: ACCEPTED OTHER @ affiliates.betpanda.io/rest/public/config: re-verified 200 with byte-identical body this cycle (operatorId=1, supportEmail=deals@bamboopartners
- LEARN: ACCEPTED OTHER @ affiliates.betpanda.io/rest/player/uid/1: 401-gated confirmed — auth boundary intact anonymously, supporting AUTH_HELPED classification rather 
- LEARN: ACCEPTED OTHER @ betpandacasino.io: manifest 200 + /config/config.json 200 (baseUrl=/rest) — passive surface stable, no new exposure.
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: JSM portals 303-gated, root 302 — reduced attack surface stable.
- LEARN: REJECTED OTHER @ affiliates.betpanda.io/rest/public/recover-password: 200 response on path-email variant — reconfirmed as REJECTED class (forgot-password enumer
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: bare Express server confirmed — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /event
- LEARN: REJECTED MISCONFIG @ cable.betpanda.io: undocumented endpoint exposure hypothesis FALSIFIED — no surface to enumerate
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS/SOA confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unpr
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target

## RANKED HYPOTHESES 2026-09-08 20:53:56 UTC
- [78] affiliates.betpanda.io/rest/player/uid/{id}: BetPanda Affiliate IDOR on Player UID Endpoint (from art/lead_nemotron3.txt)
- NEXT(hypotheses-bigpickle.txt): HUMAN: passive surface now fully closed — this cycle confirmed the casino properties family is exhausted (/rest/properties/{home,config} 404) and the affiliates
- NEXT(hypotheses-nemotron3.txt): HUMAN: Both high-value hypotheses (Affiliate IDOR 78, Casino tenant-isolation 62) are AUTH_HELPED and blocked on authorized credentialed sessions. Request progr
- LEARN: ACCEPTED IDOR @ affiliates.betpanda.io: API backend same-origin at /rest; endpoint map complete; IDOR pattern confirmed but requires second credentialed session
- LEARN: ACCEPTED MISCONFIG @ betpandacasino.io: /rest/user/{account-balances-and-bonuses,authenticate,refresh,zendesk/jwt} all GET→405 — financial/JWT endpoints POST-ga
- LEARN: ACCEPTED OTHER @ help.desk.avatarux.com: Second JSM customer portal instance at /servicedesk/customer/portal/2 now 303 — attack surface reduced
- LEARN: ACCEPTED OTHER @ custom-lp.betpanda.io: Live behind Cloudflare challenge, new BetPanda infrastructure discovered via crt.sh
- LEARN: ACCEPTED OTHER @ fp.betpanda.io: Live behind Cloudflare challenge, likely fingerprint/fraud detection service
- LEARN: ACCEPTED OTHER @ flags.betpanda.io: Flipt feature-flag service (env=betpanda) confirmed via casino bundle GLOBAL_FLIPT_URL
- LEARN: REJECTED MISCONFIG @ betpandacasino.io x-site-name-id: header ignored on public manifest — no passive multi-tenant switch (evidence contradicts hypothesis)
- LEARN: REJECTED MISCONFIG @ help.desk.avatarux.com Confluence /wiki/rest/api/space: 303 to root stable — anonymous space enumeration closed behind Atlassian Edge
- LEARN: REJECTED OTHER @ nano-public S3: bucket listing AccessDenied — NOT a bucket-listing misconfig; objects public by ACL only
- LEARN: REJECTED MISCONFIG @ betpandacasino.io/rest actuator|api-docs|swagger: all 404 — no exposed management surface
- LEARN: REJECTED MISCONFIG @ cpcalendars: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED MISCONFIG @ cpcontacts: HTTP 500 confirmed benign disabled feature, parked
- LEARN: REJECTED AUTH @ affiliates.betpanda.io/rest/public/recover-password: forgot-password timing enumeration is a REJECTED class (program scope) — leads list must no
- LEARN: REJECTED OTHER @ betpandacasino.io/rest/public/config: returned real Spring JSON 404 → casino does NOT mirror the affiliates leak; hypothesis falsified, last pa
- LEARN: ACCEPTED MISCONFIG @ cable.betpanda.io: bare Express server confirmed — root 200 text/plain ASCII banner, all /health /api /graphql /actuator /socket /ws /event
- LEARN: REJECTED MISCONFIG @ cable.betpanda.io: undocumented endpoint exposure hypothesis FALSIFIED — no surface to enumerate
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: NS/SOA confirms apex Bluehost zone delegation (ns1/ns2.bluehost.com), no separate claimable delegation; mechanism-unpr
- LEARN: ACCEPTED MISCONFIG @ cpanel.avatarux.com: Cloudflare 1001 persists 48h+ — stable dangling DNS confirmed, subdomain takeover candidate remains top passive target
