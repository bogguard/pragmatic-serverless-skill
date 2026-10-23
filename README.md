# Pragmatic Serverless — a Claude Code skill

Engineering standards for building **simple, correct, secure, pleasant and cheap** serverless software on AWS with TypeScript, Node.js and React — written as a [Claude Code skill](https://docs.claude.com/en/docs/claude-code/skills), so Claude follows them whenever it writes, changes or reviews code in your project.

It covers:

- **Engineering**: core principles, a default stack, one repository layout, code style, robustness, testing, short-lived branches and safe releases, and a definition of done.
- **AWS**: SAM conventions, Lambda best practices, DynamoDB single-table modelling, security, privacy (GDPR), observability and cost control.
- **Product quality**: usability reviewed like a demanding UX engineer, visual design aimed at "made by a good designer", accessibility (WCAG 2.2 AA), and printed material (labels, cards, tickets) treated as part of the product.

```
SKILL.md                      the standards (what Claude reads first)
references/
  aws-sam.md                  SAM template, Lambda best practices, gradual deployments, DynamoDB modelling, quiet costs
  security-privacy.md         identity, data protection, privacy, application security
  frontend-ux.md              usability, visual design, printed material, accessibility, i18n
  review-checklist.md         what to check when reviewing a change
```

## Install

**For all your projects** (personal skill):

```bash
git clone https://github.com/bogguard/pragmatic-serverless-skill.git ~/.claude/skills/pragmatic-serverless
```

**For one project**, so everyone working on it gets the same standards — as a plain copy:

```bash
mkdir -p .claude/skills
git clone --depth 1 https://github.com/bogguard/pragmatic-serverless-skill.git .claude/skills/pragmatic-serverless
rm -rf .claude/skills/pragmatic-serverless/.git
```

or as a git submodule, if you want to pull updates with `git submodule update --remote`:

```bash
git submodule add https://github.com/bogguard/pragmatic-serverless-skill.git .claude/skills/pragmatic-serverless
```

## Put the project specifics in CLAUDE.md

The skill is deliberately generic. Everything that belongs to one project goes in that project's `CLAUDE.md`, which wins where it is more specific. A good `CLAUDE.md` for a project using this skill has:

```markdown
# <Project name>

<One paragraph: what it is, for whom.>

**Always follow the `pragmatic-serverless` skill** for code, infrastructure, UI and reviews.
Architecture decisions are logged in `docs/decisions.md`.

## Language rules

- Code, comments, commits, docs and translation keys in English.
- UI languages: <default locale> by default, <other locales>.

## Repository layout

<The skill's layout, with this project's domain areas.>

## Commands

<install, dev, test, build, deploy>

## Users, roles and privacy

- Personas: <who uses it, where, how often>
- Roles: <groups and what each may do; which need MFA>
- Personal data collected: <fields>; third parties receive: <what>
- Privacy notice: <where, for which audience, in which language>
- Region: <AWS region>; accounts: <per environment / per customer>

## Domain glossary

| Code | UI | Meaning |

## Domain rules to keep in mind

- <invariants the database must enforce, time zone, idempotency, …>
```

## Contributing

Improvements from real projects are welcome: keep the skill generic (examples are fine, project facts are not), short enough to read in one go, and pragmatic — every rule should earn its place.

## License

MIT — see [LICENSE](LICENSE).
