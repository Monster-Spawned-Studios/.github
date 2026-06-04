# Security Policy

Copyright © 2025–2026 [Monster Spawned Studios](https://monsterspawned.studio/)

This document describes how to report security vulnerabilities, what we expect from reporters and maintainers, and baseline security practices for software published by [Monster Spawned Studios](https://github.com/Monster-Spawned-Studios) on GitHub and related properties.

For licensing and permitted use of our software, see [The Monster Spawned Studios License](/docs/LICENSE.md).

---

## Our commitment

We take the security of our users, contributors, and infrastructure seriously. We investigate credible reports in good faith and work to remediate confirmed vulnerabilities in supported projects as promptly as practical.

We do **not** operate a paid bug bounty program at this time. We appreciate responsible disclosure and will acknowledge valid reports where appropriate.

---

## Scope

This policy applies to security issues in:

- Repositories under the [**Monster-Spawned-Studios**](https://github.com/Monster-Spawned-Studios) GitHub organization, including this [`.github`](https://github.com/Monster-Spawned-Studios/.github) profile and template repository.
- Official Monster Spawned Studios web properties, including [monsterspawned.studio](https://monsterspawned.studio/) and [The Official Monster Spawned Studios Blog](https://monsterspawned.studio/).
- Actively maintained projects listed in our [organization profile README](/profile/README.md), such as [ComfyUI-MSS-Login](https://github.com/Monster-Spawned-Studios/ComfyUI-MSS-Login), the [Flutter App Template](https://github.com/Monster-Spawned-Studios/Flutter-App-Template), and other in-development or released tools we publish under this org.

If you are unsure whether a repository or service is in scope, report it anyway—we will route or close the report with an explanation.

### Out of scope

The following are generally **not** treated as security vulnerabilities under this policy:

- Reports against third-party services, dependencies, or platforms we do not control (report those to the upstream vendor).
- Social engineering, phishing, or physical attacks against individuals.
- Denial-of-service or load tests without prior written approval.
- Issues that require unlikely user interaction, already-patched versions, or configurations we do not support.
- Missing security headers, cookie flags, or best-practice hardening **without** a demonstrated exploit path.
- Spam, SEO, or content-quality issues on public-facing sites.
- Licensing, trademark, or permission requests (use the [contact page](https://monsterspawned.studio/contact/) instead).

---

## How to report a vulnerability

**Preferred channel:** email our repository administrators using the contact link configured for this organization:

**[Report security issues, bugs, and feature requests (email)](mailto:site-admin@monsterspawned.studio?subject=Security%20Vulnerability%20Report&body=Please%20include%3A%0A-%20Affected%20project%20or%20URL%0A-%20Description%20of%20the%20issue%0A-%20Steps%20to%20reproduce%0A-%20Impact%20assessment%0A-%20Any%20proof-of-concept%20or%20logs%20(redact%20secrets%29)**

Use a subject line that clearly indicates a security report (for example, `Security Vulnerability Report: [project name]`).

**Do not** open a public GitHub issue, discussion, or pull request for an unpatched vulnerability. Public disclosure before we have had a reasonable chance to fix the issue puts users at risk and may delay remediation.

### What to include

To help us reproduce and prioritize your report, please provide:

1. **Affected asset** — repository name, release/tag, URL, or product (e.g., ComfyUI-MSS-Login, Flutter App Template).
2. **Description** — what is wrong and why it matters.
3. **Reproduction steps** — minimal, reliable steps (or a proof-of-concept).
4. **Impact** — confidentiality, integrity, availability, or privilege escalation; who is affected.
5. **Environment** — OS, runtime, browser, or dependency versions if relevant.
6. **Evidence** — logs, screenshots, or PoC (redact tokens, passwords, and personal data).

### Encryption

If you need to share sensitive material and cannot use our standard email channel safely, mention that in your initial message to **[The Monster Spawned Studios Site Admin](mailto:site-admin@monsterspawned.studio)**. We will work with you on an appropriate way to exchange details.

### Other inquiries

| Topic | Channel |
| --- | --- |
| Security vulnerabilities (this policy) | [The Monster Spawned Studios Site Admin](mailto:site-admin@monsterspawned.studio?subject=Security%20Vulnerability%20Report) |
| Licensing and general business inquiries | [monsterspawned.studio/contact/](https://monsterspawned.studio/contact/) |
| Organization and project information | [monsterspawned.studio](https://monsterspawned.studio/) |

These channels mirror the [repository contact links](https://github.com/Monster-Spawned-Studios/.github/blob/main/.github/config.yml) defined for this org.

---

## Coordinated disclosure

We follow a **coordinated disclosure** model:

1. **Report privately** using the channel above.
2. **We acknowledge** receipt when possible (typically within **5 business days**).
3. **We investigate** severity and impact, and develop or coordinate a fix.
4. **We release a fix** or mitigation for supported versions when available.
5. **We disclose** after a fix or accepted mitigation, unless a shorter timeline is required to protect users (e.g., active exploitation).

We ask that you:

- Give us a reasonable time to investigate and remediate before public disclosure (our target is **90 days** from report for most issues; critical issues may need faster action on both sides).
- Avoid accessing, modifying, or destroying data that is not yours.
- Avoid disrupting our services or users.
- Comply with applicable laws.

We may request an extension for complex issues; we will communicate openly if more time is needed.

---

## Supported versions

Security fixes are provided for **actively maintained** repositories and releases. We do not guarantee patches for:

- Archived or unmaintained repositories.
- Forks or unofficial builds.
- End-of-life dependencies we no longer ship.

When reporting, specify the **branch, tag, or release** you tested. We prioritize issues affecting the default branch and the latest tagged release.

---

## Response expectations

| Stage | Target |
| --- | --- |
| Initial acknowledgment | Within 5 business days |
| Triage and severity assessment | Within 15 business days (complex cases may take longer) |
| Fix or mitigation plan | Depends on severity; critical issues prioritized |
| Public disclosure | After fix or documented mitigation, coordinated with reporter when possible |

Timelines are goals, not guarantees. Reports outside scope or lacking reproduction detail may receive a brief explanation and no further action.

---

## Severity (internal triage)

We use impact and exploitability to prioritize work. Examples:

- **Critical** — unauthenticated remote code execution, authentication bypass, or exposure of secrets at scale.
- **High** — privilege escalation, significant data exposure, or reliable account takeover.
- **Medium** — confined XSS, CSRF with meaningful impact, or insecure defaults in common deployments.
- **Low** — defense-in-depth improvements with limited exploitability.

Final severity and response are at the discretion of the maintainers.

---

## Security practices for users and contributors

### For users

- Run only releases from [official Monster Spawned Studios repositories](https://github.com/Monster-Spawned-Studios) or our website unless you explicitly trust another source.
- Keep dependencies, runtimes, and platform firmware (e.g., console/homebrew environments) up to date.
- Do not commit API keys, tokens, passwords, or private keys to issues, PRs, or public chats.
- Review permissions requested by our apps and integrations (e.g., media servers, voice assistants, ComfyUI nodes).

### For contributors

- Follow the [pull request template](https://github.com/Monster-Spawned-Studios/.github/blob/main/.github/PULL_REQUEST_TEMPLATE/GENERAL.yml) and allow [code owner](https://github.com/Monster-Spawned-Studios/.github/blob/main/.github/CODEOWNERS) review where applicable.
- Avoid introducing secrets into the tree; use environment variables or platform secret stores.
- Prefer well-maintained dependencies; report transitive vulnerabilities through the security email when they affect our shipped code.
- Do not include live credentials, production URLs with secrets, or personal data in bug reports or PR descriptions.

### Dependency and supply chain

We monitor dependencies where practical and update them as part of normal maintenance. If you discover a vulnerable dependency in one of our projects, include the advisory identifier (CVE, GHSA, etc.) and the lockfile or manifest path in your report.

---

## GitHub Security Advisories

For repositories that support it, we may publish advisories via [GitHub Security Advisories](https://docs.github.com/en/code-security/security-advisories/working-with-repository-security-advisories/about-repository-security-advisories). Reporters with GitHub accounts may be credited in advisories when they agree and when disclosure is complete.

---

## Legal

Reports conducted in good faith, in line with this policy, will not be pursued as unauthorized access **by Monster Spawned Studios**, to the extent permitted by law. This does not bind third parties.

Unauthorized use of our software remains subject to [The Monster Spawned Studios License](/docs/LICENSE.md) and applicable law.

---

## Policy updates

We may update this policy as our projects and threat landscape evolve. Material changes will be reflected in this file’s revision history on GitHub.

**Last updated:** June 2026

---

## Quick links

- [Monster Spawned Studios](https://monsterspawned.studio/)
- [Contact / licensing](https://monsterspawned.studio/contact/)
- [GitHub organization](https://github.com/Monster-Spawned-Studios)
- [License](/docs/LICENSE.md)
- [Profile & active projects](/profile/README.md)
- [Report a vulnerability (email)](mailto:site-admin@monsterspawned.studio?subject=Security%20Vulnerability%20Report) [The Monster Spawned Studios Site Admin](mailto:site-admin@monsterspawned.studio?subject=Security%20Vulnerability%20Report)
