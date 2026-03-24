# OpenClaw Skill: browser-ops-high-autonomy

This workspace contains an OpenClaw skill named **browser-ops-high-autonomy**.

## Purpose
Autonomously complete browser-based workflows across approved domains with minimal human interruption.

## Escalate only when required
The skill escalates only for:
- Legal documents, signatures, binding agreements, or legal acknowledgements
- Payment/payout/billing/bank or tax-payment setup, or movement of money
- Login verification steps (OTP, 2FA, SMS/email code)
- Security challenges (CAPTCHA, anti-bot, Cloudflare, unusual activity checks)

Everything else is handled automatically when technically possible, including customer support, email operations, CRM updates, ordinary forms, admin workflows, product/platform management, routine communication, and data extraction/research.

## Security boundary
The skill never bypasses security controls or access restrictions.

## Structured statuses
- `DONE`
- `BLOCKED`
- `LOGIN_REQUIRED`
- `SECURITY_CHALLENGE`
- `LEGAL_REVIEW_REQUIRED`
- `PAYMENT_REVIEW_REQUIRED`
- `DOMAIN_NOT_ALLOWED`

## Files
- `skills/browser-ops-high-autonomy/skill.yaml` — primary skill definition and execution policy.
- `skills/browser-ops-high-autonomy/SKILL.md` — skill overview required by ClawHub publish flow.

## Open source
This project is open-sourced under the MIT license.

## GitHub + ClawHub sync deployment

### One-time local publish
```bash
clawhub publish ./skills/browser-ops-high-autonomy \
	--slug browser-ops-high-autonomy \
	--name "Browser Ops High Autonomy" \
	--version 1.0.0 \
	--changelog "Initial public release"
```

### Automated publish from Git tags
This repo includes a GitHub Actions workflow that will:
1. Trigger on tags like `v1.0.0`
2. Verify the tag matches `version` in `skill.yaml`
3. Create a GitHub Release
4. Publish the skill to ClawHub

Required GitHub secret:
- `CLAWHUB_TOKEN`: token from `clawhub login --token ...`
