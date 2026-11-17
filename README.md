# homeCore skills

[Agent Skills](https://agentskills.io) for [homeCore](https://homecore.io), the
local-first home automation server. Each one is a guide an AI assistant follows
step by step, and people can read them as they are.

| Skill | For |
|---|---|
| [dev-environment](skills/dev-environment/SKILL.md) | Setting up to work on homeCore: the toolchain, the workspace, building and running core and the app, a safe sandbox, tests and CI |
| [install-and-setup](skills/install-and-setup/SKILL.md) | Installing and setting up homeCore: Docker or a binary, configuration, plugins from the Catalog, plugin runtimes, people and access, backups and upgrades |
| [plugin-development](skills/plugin-development/SKILL.md) | Writing a plugin in Rust, Python, JavaScript or .NET: devices, actions, settings, screens, testing and releasing |

Each skill is a `SKILL.md` with the steps, and a `references/` folder with
detail it points to. They link to the docs at https://homecore.io/docs/ for the
rest.

## Using them

**Claude Code:**

```
/plugin marketplace add homeCore-io/skills
/plugin install homecore@homecore
```

Then ask about homeCore, or start one directly with `/homecore:plugin-development`.

**hc-mcp:** the homeCore MCP server ships these skills. MCP clients such as
Claude Desktop see each one as a prompt, read its files as
`homecore-skill://<skill>/<file>` resources, and have `list_skills` and
`read_skill` tools. homeCore's Assistant reads them when someone asks how to do
something.

**Anything else that reads Agent Skills:** copy a folder from `skills/`.

## Changing them

Keep a `SKILL.md` short and put detail in `references/`. Check what a skill
says against the code: the code wins when they disagree. After a change, run
`scripts/sync-skills.sh` in hc-mcp so its copy follows.

## License

MIT or Apache-2.0, at your option.
