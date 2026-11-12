# alex-claude-skills

Personal skills for Claude (Claude Code, the Claude apps, and the Agent SDK).

| Skill | What it does |
|---|---|
| [`meta-ads`](skills/meta-ads/SKILL.md) | Meta (Facebook / Instagram) ads strategy and account operations, current to November 2026. Built to be used with a Meta Ads MCP server: audit an account from live data, diagnose problems, plan campaigns, brief creative, read tests, decide on budget changes, and make approved changes safely. |

## Install

A skill is a folder containing a `SKILL.md`. Claude Code loads skills from `~/.claude/skills/` (all projects) or `<project>/.claude/skills/` (one project). Link the folder so that updates to this repository apply immediately:

```bash
# all projects
ln -s "$(pwd)/skills/meta-ads" ~/.claude/skills/meta-ads

# or one project
mkdir -p /path/to/project/.claude/skills
ln -s "$(pwd)/skills/meta-ads" /path/to/project/.claude/skills/meta-ads
```

If you use a non-default Claude configuration directory, link into that directory's `skills/` folder instead. Start a new session afterwards; the skill appears as `meta-ads` and triggers on Meta ads work, or run it explicitly with `/meta-ads`.

For the Claude apps, zip `skills/meta-ads` and upload it under Settings → Capabilities → Skills.

## meta-ads

### Use with a Meta Ads MCP

The skill does not depend on one particular server. It tells Claude to look at the tools that are connected and map them to capabilities (list accounts, read structure, pull insights with breakdowns, create and edit). It has been written with two kinds of server in mind:

- Meta's own Ads MCP (`ads_*` tools);
- community servers in the style of Pipeboard's `meta-ads-mcp` (`get_campaigns`, `get_insights`, …).

Without an MCP the skill still works as a strategy reference: paste an Ads Manager export or describe the account.

Changes to a live account are always proposed first and made only after you approve them; new objects are created paused.

### Layout

```
skills/meta-ads/
├── SKILL.md                             operating model, quick reference, workflow, guardrails
└── references/                          loaded only when the task needs them
    ├── mcp-playbooks.md                 tool mapping, data pulls, computed metrics, playbooks, change protocol
    ├── analysis-and-troubleshooting.md  metrics, benchmarks, breakdowns, pattern → cause → action
    ├── platform-changes.md              changelog 2024 → Nov 2026, glossary, reversed advice
    ├── campaign-setup.md                structure, objectives, performance goals, budgets, checklists
    ├── targeting.md                     controls vs suggestions, audiences, value rules
    ├── creative.md                      formats, styles, hooks, copy, creator ads, enhancements
    ├── testing-and-scaling.md           test methods, sample sizes, scaling rules
    ├── offers-and-economics.md          unit economics, lifetime value, offers, funnels, pages
    ├── lead-generation.md               instant forms, qualification, booking, follow-up
    ├── ecommerce.md                     value optimisation, existing customers, sale events
    ├── local-and-high-ticket.md         local playbook, high-ticket funnels, omnipresent content
    ├── tracking-and-attribution.md      pixel, Conversions API, attribution, reconciliation
    ├── account-health-and-policy.md     new accounts, policy, bans, support
    └── sources.md                       source video index for the [vNNN] tags
└── evals/                               test prompts with expected outcomes (not loaded by the skill)
```

### Where the knowledge comes from

The skill is a synthesis, in its own words, of the public YouTube videos of Ben Heath (Heath Media), a Meta ads practitioner: 600 transcripts were collected, the 250 or so most relevant were read in full, and the newest were given priority wherever advice had changed. Source tags such as `[v043]` in the reference files point to the video a statement came from; lower numbers are newer. The transcripts themselves are not in this repository.

It is one practitioner's method, not Meta documentation. Thresholds are working rules of thumb, and platform details are as of November 2026.

### Tests

`skills/meta-ads/evals/` holds four test cases, each a prompt a user might type, a description of a good answer, and the statements a grader checks: an account audit with a wrong performance goal and a fragmented structure, a test readout with too little data, the November 2026 gender change, and a scaling request without headroom. They use the layout that `claude plugin eval` reads, so from `skills/meta-ads` they can be run with and without the skill:

```bash
claude plugin eval .
```

These are real, billed model runs.

### Keeping it current

Meta changes the product constantly. When something moves:

1. add the change to `references/platform-changes.md` (dated, with the practical consequence);
2. fix the rule in the file that owns the topic;
3. if it reverses a core habit, update the "What changed" table in `SKILL.md`.
