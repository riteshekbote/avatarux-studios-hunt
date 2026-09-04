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
