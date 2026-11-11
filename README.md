# hushrun's skill for coding agents

hushrun skips CI checks that this exact code already passed. This skill tells a coding agent what
to run before it pushes in a repository that uses hushrun, and how to set hushrun up. The rules
that change from one hushrun to the next come from the binary: the skill has the agent run
`hushrun guide`, which also says whether hushrun and the skill are current.

hushrun's release writes this repository from [hushrun/hushrun](https://github.com/hushrun/hushrun), where the text lives
in `recipes/agents/`. Don't edit it here: a change belongs there.

## Install

| Where | How |
|---|---|
| Any agent, through skills.sh | `npx skills add hushrun/skills` |
| Claude Code | `/plugin marketplace add hushrun/skills`, then `/plugin install hushrun@hushrun` |
| Codex | `codex plugin marketplace add hushrun/skills` |
| GitHub Copilot CLI | `copilot plugin marketplace add hushrun/skills` |
| Gemini CLI | `gemini extensions install https://github.com/hushrun/skills` |
| GitHub CLI | `gh skill install hushrun/skills hushrun` |
| One repository | `npx hushrun init` writes the skill into it, for every clone |
| Your home, from hushrun | `hushrun skill update --global` |

## Support and privacy

- Support: [https://github.com/hushrun/hushrun/issues](https://github.com/hushrun/hushrun/issues), or support@hushrun.com
- Privacy policy: [https://hushrun.com/privacy](https://hushrun.com/privacy)
- Terms: [https://hushrun.com/terms](https://hushrun.com/terms)

The skill sends nothing itself. The hushrun CLI it runs hashes files on the machine and never sends
them; once a person signs in, it records check results with hushrun's service, and about once a day
it asks GitHub whether a newer release is out (`HUSHRUN_NO_UPDATE_CHECK=1` turns that off).

## Updates

Each hushrun release updates this repository, tagged as the release is, and each tool updates
its copy with its own command: `npx skills update`, `claude plugin update hushrun@hushrun`,
`codex plugin marketplace upgrade`, `copilot plugin update hushrun`, `gemini extensions update
hushrun` or `gh skill update`. A copy that is out of date still works: hushrun says so, in
`hushrun guide` and `hushrun ready`.

This is hushrun 0.12.0, skill revision 2. MIT licensed: see LICENSE.
