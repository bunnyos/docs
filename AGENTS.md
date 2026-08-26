# Documentation project instructions

## About this project

- This is the Mintlify documentation site for Bunny Open Society.
- Pages are MDX files with YAML frontmatter. Configuration lives in `docs.json`.
- Run `mint dev` to preview locally. Run `mint validate` and `mint broken-links` before declaring done.
- The audience includes people who use AI agent harnesses but may not know the game or MCP.

## Source of truth

- Bunny Open Society is a persistent world played by AI agents.
- A human directs an agent. The agent controls a synthetic bunny in the world.
- The product source of truth is `/Users/joe/Files/development/bunnyos/society`.
- The live agent instructions are at `https://world.bunnyos.ai/skill.md`.
- Treat the live skill as the source for current endpoints, rules, and gameplay instructions.
- The canonical concept documents are `master-plan.html` and `v0.1-plan.html` in the society repository.
- Verify current features against service code. Plans include future systems that may not exist yet.

## Documentation scope

- Keep the introduction short.
- Explain the general loop without documenting individual missions, items, recipes, or event objectives.
- Focus on connecting agents through Hermes Agent, OpenClaw, Claude Code, Codex, OpenCode, ChatGPT web, and Claude web.
- Prefer this exact instruction for harnesses that can open URLs.

  `Read https://world.bunnyos.ai/skill.md and follow the instructions to join Bunny Open Society.`

- Use the MCP server for ChatGPT web and Claude web.
- Do not duplicate the API reference from `skill.md`.
- Do not publish specific game balance values. This includes Carrot amounts, item stats, mission odds, durations, recipes, rates, and rewards.
- Do not present planned systems as current features.

## Terminology

- Use **Bunny Open Society** for the world and formal product name.
- Use **bunnyOS** when referring to the skill, API, MCP server, or existing UI label.
- Use lowercase **bunny** for the synthetic creature.
- Capitalize **Carrots** as the world's currency.
- Use **AI agent** or **agent** for the player.
- Use each harness's official name and capitalization.

## Style

- Use active voice and second person.
- Use sentence case for headings.
- Keep sentences short. Prefer one idea per sentence.
- Use plain words and explain MCP the first time it appears.
- Do not use em dashes in published pages.
- Avoid colons inside prose sentences and headings.
- Bold exact UI labels and buttons.
- Use code formatting for commands, file names, URLs in prose, and prompt text.
- End content pages with a `## Related pages` card group.
