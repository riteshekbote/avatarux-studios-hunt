# Validated findings (running count 0)

- 20 lead(s) marked VALID at 2026-09-05 23:43:00 UTC
  - | Q1 Scope | **VALID** | `betpandacasino.io` = BetPanda brand, explicitly in scope |
  - | Q2 Reachable | **VALID** | Public JS bundle, no auth needed |
  - | Q4 Provable | **VALID** | `curl -s https://betpandacasino.io/ | grep -o 'GLOBAL_CLOUDWATCH_IDENTITY_POOL_ID[^"]*"[^"]*"'` — read-only GET |
  - | Q1 Scope | **VALID** | BetPanda asset, in scope |
  - | Q2 Reachable | **VALID** | Public JS bundle |
  - | Q4 Provable | **VALID** | `curl -s https://betpandacasino.io/ | grep -oP 'nano-public[^"]*\|d3ec3n7kizfkuy[^"]*'` |
  - | Q1 Scope | **VALID** | `avatarux.com` infrastructure, explicitly in scope |
  - | Q2 Reachable | **VALID** | Public DNS, Cloudflare error 1001 returned to unauthenticated requests |
  - | Q3 Impact | **VALID** | Dangling DNS to prohibited Cloudflare IP could enable subdomain takeover → phishing, cookie theft, service impersonation under avatarux.com |
  - | Q4 Provable | **VALID** | `dig cpanel.avatarux.com` + `curl -sI https://cpanel.avatarux.com/` — read-only, non-invasive. Cloudflare 1001 persists 48h+ across 20+ probe cycles |
  - | Q5 Novel | **VALID** | Persistent dangling DNS with Cloudflare 1001 is a specific, unreported misconfiguration |
  - | Q6 Not rejected | **VALID** | Not on always-rejected list (not DoS, not banner grabbing, not error messages) |
  - | Q7 Reasonable triager | **VALID** | Subdomain takeover via dangling DNS is a well-understood, accepted vulnerability class |
  - **Verdict: VALID**
  - | Q1 Scope | **VALID** | AvatarUX infrastructure |
  - | Q2 Reachable | **VALID** | Publicly accessible, returns HTTP 200/303 |
  - | Q4 Provable | **VALID** | `curl -sI https://help.desk.avatarux.com/servicedesk/customer/portal/2` |
  - | Q1 Scope | **VALID** | BetPanda asset, in scope |
  - | Q2 Reachable | **VALID** | Public REST API endpoints respond to unauthenticated requests |
  - | cpanel.avatarux.com Dangling DNS | **VALID** | 6.1 (Medium) |

- 4 lead(s) marked VALID at 2026-09-07 12:09:22 UTC
  - | Q7 Reasonable triager | YES | Stable dangling DNS with clear escalation path is a valid finding |
  - | Q4 Provable | PARTIAL | Endpoint map confirmed from JS bundle (`/rest/player/uid/{id}?currency={curr}`); but IDOR requires authenticated session to prove — cannot demonstrate without valid affiliate
  - **Verdict: HOLD** — Blocked on auth. Need a valid affiliate session to test `GET /rest/player/uid/1?currency=EUR` vs `uid/2` for response differentiation. Without credentials, this remains a hypothesi
  - | Q4 Provable | NO | All endpoints return 405 on GET; OPTIONS leaks header schema but no data; POST requires valid auth |
