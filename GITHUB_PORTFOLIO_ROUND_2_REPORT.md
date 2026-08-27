# GitHub Portfolio Round 2 Report

Date: 2026-08-27

## Created

- `acai-finance-case-study`  
  Public case study: https://github.com/filpe19/acai-finance-case-study

- `tickiton-case-study`  
  Public case study: https://github.com/filpe19/tickiton-case-study

- `jornada-contabil-case-study`  
  Public case study: https://github.com/filpe19/jornada-contabil-case-study

- `finance-ai-case-study`  
  Public case study: https://github.com/filpe19/finance-ai-case-study

Each repository was created as a clean public case-study repository, without cloning or publishing the private project Git history.

## Updated

- `filpe19/filpe19` profile README:
  - Reorganized the portfolio around engineering problem classes instead of frameworks.
  - Added public links for Açaí Finance, TickiTon, Jornada Contábil, Club Pass Belém and Finance AI.
  - Removed `ats` from the main featured-work section.
  - Added a clear note that a dedicated public source-code proof is the next portfolio gap.

- `club-pass-belem-case-study`:
  - Standardized the README structure to match the new cases.
  - Preserved the verified subscription, payment, QR access and iOS narrative.
  - Kept iOS positioning honest as hands-on iOS development inside a real product.

## Security

Security approach used in this round:

- New case-study repositories were initialized cleanly.
- No private `.git` history was copied.
- No proprietary source code was copied.
- No `.env`, database dumps, credential files, SSH keys, certificates, customer data or production URLs were published.
- Screenshots were not added to Açaí Finance, TickiTon, Jornada Contábil or Finance AI because available source material may include operational, participant, customer, merchant or financial data.
- Existing Club Pass screenshots were kept because they were already sanitized and passed a binary `strings` scan for secret-like patterns.
- `gitleaks` and `trufflehog` were not installed locally, so a precise `rg`/`git grep` scan was used instead.

Scanned patterns included:

- GitHub tokens.
- Mercado Pago token-like values.
- Telegram/API token-like values.
- Cloud access keys.
- JWT-like values.
- Private key blocks.
- SendGrid/Slack-style token formats.
- `password`, `secret`, `token`, `api_key`, `access_key` and `private_key` assignment patterns.

Scan coverage:

- Current files in each public case-study repository.
- Git history reachable from `git rev-list --all`.
- Branches and tags.
- PNG `strings` output for the existing Club Pass screenshots.

Result:

- No secret-like values were found in the public case-study repositories.
- Each new public case repository currently has only `main` and no tags.

## Public Cases

- Açaí Finance: SaaS / Multi-Tenant / Marketplace / Payments  
  https://github.com/filpe19/acai-finance-case-study

- TickiTon: Ticketing / Events / Payments / Transactional Systems  
  https://github.com/filpe19/tickiton-case-study

- Jornada Contábil: Event Infrastructure / Commerce / Payments / Production Operations  
  https://github.com/filpe19/jornada-contabil-case-study

- Club Pass Belém: Subscriptions / QR Access / Payments / iOS  
  https://github.com/filpe19/club-pass-belem-case-study

- Finance AI: AI / Telegram / Automation / Financial Assistant  
  https://github.com/filpe19/finance-ai-case-study

## Private Codebases

The original commercial repositories remain private:

- `acaifinace`
- `tickiton`
- `jornada-contabil-fiscal`
- `clubpassbelem`
- `assistenteia-finance`

## Pinned Repositories

Recommended pin order:

1. `acai-finance-case-study`
2. `tickiton-case-study`
3. `jornada-contabil-case-study`
4. `club-pass-belem-case-study`
5. `finance-ai-case-study`
6. Leave empty until a stronger public source-code repository exists.

Do not pin `ats`.

Current status:

- GitHub GraphQL `pinnedItems` for `filpe19` returned an empty list.
- The available GitHub CLI/API schema did not expose a repository-pin mutation in this environment.
- Pins were therefore not configured automatically.

Manual action required:

1. Open https://github.com/filpe19 while logged in.
2. In the pinned repositories area, click `Customize your pins`.
3. Select:
   - `acai-finance-case-study`
   - `tickiton-case-study`
   - `jornada-contabil-case-study`
   - `club-pass-belem-case-study`
   - `finance-ai-case-study`
4. Do not select `ats`.
5. Save the pinned repositories.

This will replace the automatic "Popular repositories" presentation and remove `ats` from the main profile showcase without deleting it or changing its visibility.

## Public Code Repository Recommendation

There is still a code-level portfolio gap because the main production systems should remain private.

Recommended future repository:

`transactional-platform-api`

Suggested scope:

- Laravel API.
- Authentication and authorization.
- Orders/payments domain.
- Webhook inbox with idempotency.
- Append-only ledger or audit trail.
- MySQL migrations and seeders.
- Feature/unit tests.
- Validation and error handling.
- Queues/events where useful.
- CI workflow.
- Docker-based local environment.
- Architecture documentation.

This should be an independent project inspired by known architectural patterns, not a copy of commercial intellectual property.

## Recruiter Test

**Can a recruiter visiting `github.com/filpe19` for about 30 seconds identify the main real systems Felipe built?**  
Yes. The profile now opens with engineering positioning and links to five named production-oriented case studies.

**Is it clear that these are products, not exercises?**  
Yes. The cases describe product flows, payments, webhooks, QR validation, subscriptions, event operations, marketplace settlement, admin panels, production runbooks and tests.

**Is the diversity between SaaS, payments, events, subscriptions, iOS and AI clear?**  
Yes. Each project is framed by its engineering problem class instead of by a generic Laravel/PHP label.

**Is there enough evidence of engineering and production?**  
Yes for architecture, product delivery and production-oriented work. For direct code review, the next recommended step is a dedicated public engineering repository with source code, tests and CI.
