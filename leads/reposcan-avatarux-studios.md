## REPOSCAN 2026-09-03 16:30:28 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-03 19:25:35 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-03 21:53:16 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-03 23:43:50 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-04 02:20:59 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-04 07:25:23 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-04 12:15:54 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-04 16:25:07 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-04 19:06:31 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-04 21:32:38 UTC
[HYP] No GitHub org candidates configured for source-code audit
class: OTHER
asset: (none — cands.txt, scope.yml)
confidence: 100
reasoning: |
impact: LOW — no action possible; this is a configuration gap, not a vulnerability
verify_steps: |
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-04 23:16:01 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-05 01:01:23 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-05 05:48:08 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-05 09:46:07 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-05 13:12:34 UTC
[HYP] AWS Resource IDs Hardcoded in BetPanda Casino JS Bundle
class: SECRET
asset: betpandacasino.io (JS bundle: `main.*.js`)
confidence: 85
reasoning: The production JavaScript bundle for `betpandacasino.io` hardcodes `GLOBAL_CLOUDWATCH_IDENTITY_POOL_ID = "eu-west-1:6d112649-3978-47f7-a42f-3b0a41b34d21"` — a Cognito Identity Pool ID used for CloudWatch. This is visible in analyst-bigpickle.log:1566, 1675, 1778, 1980. While Cognito Identity Pool IDs alone don't grant access without IAM role configuration, they expose the AWS account region and pool structure, enabling targeted attacks against the pool's associated IAM roles.
impact: MEDIUM — credential enumeration surface; if pool has weak/unrestricted IAM roles, could lead to AWS service access
verify_steps: `curl -s https://betpandacasino.io/ | grep -o 'GLOBAL_CLOUDWATCH_IDENTITY_POOL_ID[^"]*"[^"]*"'` (read-only GET)
[HYP] S3 Bucket Name and CloudFront Dist ID Leaked in BetPanda Casino Bundle
class: MISCONFIG
asset: betpandacasino.io (JS bundle: `main.*.js`)
confidence: 75
reasoning: Bundle references `nano-public.s3-eu-west-1.amazonaws.com` (S3 bucket) and `d3ec3n7kizfkuy.cloudfront.net` (CloudFront distribution). Bucket listing returns 403 (not listable), but bucket name is exposed. CloudFront dist ID is public knowledge. Combined with Identity Pool ID, this maps the full AWS stack.
impact: LOW — bucket is not listable; CloudFront dist is public by design; but combined with Identity Pool ID, provides attack surface mapping
verify_steps: `curl -s https://betpandacasino.io/ | grep -oP 'nano-public[^"]*|d3ec3n7kizfkuy[^"]*'` (read-only GET)
[HYP] cpanel.avatarux.com Dangling DNS — Subdomain Takeover Candidate
class: MISCONFIG
asset: cpanel.avatarux.com
confidence: 80
reasoning: Cloudflare error 1001 (DNS points to prohibited IP) persists across 20+ probe cycles over 48+ hours. CNAME chain: `cpanel.avatarux.com` → `avatarux.com` → `162.159.136.54` (Cloudflare IP). This is a dangling DNS record that could be claimed by an attacker if they can control the target.
impact: MEDIUM — subdomain takeover could enable phishing, cookie theft, or service impersonation under the avatarux.com domain
verify_steps: `dig cpanel.avatarux.com` + `curl -sI https://cpanel.avatarux.com/` (read-only)
[HYP] help.desk.avatarux.com Atlassian Jira Service Desk — Customer Portal Active
class: MISCONFIG
asset: help.desk.avatarux.com
confidence: 70
reasoning: Atlassian Jira Service Desk customer portal is live and accessible at `/servicedesk/customer/portal/` (HTTP 303 → 200). REST API at `/rest/servicedeskapi/servicedesk` returns 401 (auth required). A second portal instance exists at `/servicedesk/customer/portal/2` (HTTP 200). This exposes internal issue tracking infrastructure.
impact: LOW — portal is auth-gated; but exposed JSM instance may leak tenant info or be targeted for credential stuffing
verify_steps: `curl -sI https://help.desk.avatarux.com/servicedesk/customer/portal/2` (read-only)
[HYP] betpandacasino.io REST API Endpoint Surface with Financial Endpoints
class: IDOR
asset: betpandacasino.io/rest/user/*
confidence: 72
reasoning: REST API at `/rest/user/authenticate`, `/rest/user/refresh`, `/rest/user/account-balances-and-bonuses`, `/rest/user/zendesk/jwt` — all GET→405 (POST-gated). Endpoint `/rest/player/uid/{id}` was previously identified in affiliates.betpanda.io bundle as an IDOR candidate. Multi-tenant header `x-site-name-id` supports brand switching (`betpandacasino_io`, `roobet_com`, `stake_com`), suggesting shared backend across in-scope brands.
impact: MEDIUM — if auth is bypassed or tokens are weak, financial data and user records across brands could be accessed
verify_steps: `curl -s -X POST https://betpandacasino.io/rest/user/account-balances-and-bonuses -H "Content-Type: application/json" -d '{}'` (passive: test without valid auth to confirm 401/403)
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-05 16:06:50 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
## REPOSCAN 2026-09-05 18:20:50 UTC
TARGET_ORG not configured for avatarux-studios; skipping public-org deep scan.
