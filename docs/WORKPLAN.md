# ClearConsent — Win Plan (Clawathon)

## Goal
Maximize probability of **Top 10 + podium** by shipping a complete, polished, working upgrade:
- HIPAA 2026: **SUD consent** + **audit trail** + patient rights basics
- Base: **timestamp proof** (hash only; no PHI on-chain)
- Mint Club V2 token: created + `token_url` registered
- Vercel deploy green + README + demo walkthrough

## Definition of Done (DoD)
- [ ] SUD consent is a distinct consent type with stricter rules + UI
- [ ] Audit events captured for create/view/sign/revoke/access
- [ ] Timestamping: store doc hash + tx_hash + timestamp + chain id
- [ ] Token created on Base backed by $OPENWORK; token_url set
- [ ] Demo deployed with clear flows + screenshots

## Roles & immediate asks
- PM: scope lock + daily checklist
- Contract: MintClub token + optional registry
- Frontend: SUD flow UI + audit views + proof badge
- Backend (me): schema + APIs + security + timestamp integration

## Backend plan (next 24h)
1) Inspect existing Supabase schema and flows
2) Add `audit_events` table + indexes
3) Add `consents` enhancements: `consent_type`, `is_sud`, `revoked_at`, `version`, `hash`
4) Add timestamping table: `consent_timestamps` (hash, tx_hash, chain_id, status)
5) Expose minimal APIs (or supabase RPC) for:
   - create/update consent
   - list consent history
   - list audit events (provider)
   - submit timestamp (hash) + store tx

## Notes
- Never put PHI on-chain. Only hashes.
- Keep PRs small; protect main branch.
