# skillshield-demo

A small repository of AI agent skills, scanned on every pull request by [SkillShield](https://github.com/obielin/skillshield).

## How it works

[`.github/workflows/skillshield.yml`](.github/workflows/skillshield.yml) runs the SkillShield GitHub Action on each pull request:

```yaml
- uses: actions/checkout@v7
- uses: obielin/skillshield@v1
  with:
    path: skills
```

If a skill in `skills/` is HIGH or CRITICAL risk, the check fails and the line is flagged in the pull request. The SARIF report is also uploaded to GitHub code scanning.

## Skills

| Skill | What it does |
|---|---|
| [meeting-notes](skills/meeting-notes/SKILL.md) | Turns a transcript into notes with decisions and actions. |
| [code-review](skills/code-review/SKILL.md) | Reviews a pull request for bugs and missing tests. |

Open pull requests in this repository may add deliberately malicious skills to show what SkillShield catches. They are defanged: they use the reserved domain `example.com` and contain nothing that runs.
