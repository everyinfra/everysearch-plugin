# EverySearch: capability reference and evidence

EverySearch is a standalone EveryInfra agent skill for web search and page retrieval through MCP. It selects an available retrieval mechanism, preserves original source URLs and makes freshness or access gaps explicit for source-linked answers.

## Identity

- Publisher: [EveryInfra](https://everyinfra.com).
- Organization: [everyinfra on GitHub](https://github.com/everyinfra).
- Source repository: [everyinfra/everysearch-plugin](https://github.com/everyinfra/everysearch-plugin).
- Plugin identifier: `everysearch`. Skill identifier: `everysearch`.
- Package type: one standalone agent skill, not a separate API server or account permission boundary.
- Interface used by the skill: `mcp`. Mail, Number and Proxy workflows remain REST-only in these packages.

## Task and result

Use it when the immediate job is retrieving current information, reading a supplied URL or finding sources. The returned evidence can support a later answer, but a list of search results is not itself a verified conclusion.

Relevant retrieved material with usable source URLs and a clear statement of scope and freshness. Empty results mean the retrieval found nothing within its scope, not that the requested fact is false.

## Preconditions

Use a compatible agent host and the service access described in [setup](setup.md). The live tool schema or REST catalog determines required inputs, supported actions, availability, limits and any exposed price. Do not infer universal platform coverage from a product name.

## Evidence behind the description

- The [packaged skill](../plugins/everysearch/skills/everysearch/SKILL.md) defines the workflow and authority boundaries.
- The [plugin manifest](../plugins/everysearch/.codex-plugin/plugin.json) declares package identity, assets and skill path. It does not automatically register a service connection.
- [Workflow acceptance criteria](workflow.md) define the expected output and failures. Examples are illustrative, not paid API test results.
- [Source metadata](../repository-metadata.json) records the original reviewed skill commit and intended repository metadata.
- [Current API documentation](https://api.everyinfra.com/docs) is the public service reference. Runtime discovery remains authoritative when an inventory, field or model changes.

## Scope distinctions

EverySearch owns retrieval. Research owns claim framing, source comparison and a calibrated conclusion. Use EveryData instead when the desired result is a supported structured platform record.

No benchmark, uptime guarantee, universal availability, official marketplace approval or account-ban probability is asserted by this reference. Local package validation checks structure; production service behavior requires its own authorized verification.

Maintainer: EveryInfra. Documentation scope reviewed on 2026-09-04; this date is not a live API availability timestamp. [Return to overview](../README.md).
