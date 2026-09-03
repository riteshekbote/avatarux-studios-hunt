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
