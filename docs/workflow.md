# EverySearch workflow and acceptance criteria

## Intended outcome

Relevant retrieved material with usable source URLs and a clear statement of scope and freshness. Empty results mean the retrieval found nothing within its scope, not that the requested fact is false.

## Execution contract

1. Discover everyinfra_search and inspect its current tool enum and parameter schema.
2. Choose search for discovery, or a supported read/crawl mechanism for a known URL.
3. Constrain the query, result count and site scope to the task.
4. Inspect the actual returned sources, freshness and failures; preserve the original URLs.
5. Cite the evidence used and state which retrieval paths were empty or unavailable.

## Failure handling

If discovery or catalog access fails, stop before a paid action. Read required fields from the current schema instead of copying a remembered payload. Report unavailable capabilities and denied account scopes as distinct conditions. Do not broaden keys, repeatedly retry a permanent error or substitute an unrelated mechanism without disclosure.

- Available search, semantic, academic, forum or page-reading mechanisms must be discovered; none is guaranteed by a static README.
- Do not relabel repeated keyword searches as an independent cross-check.
- A page may be inaccessible or a result stale; disclose that instead of filling the gap with an invented answer.

## Worked request boundaries

### Scenario 1

> Find the current official documentation for this feature and return the original sources, with dates where available.

Accepted behavior: preserve the stated scope; discover the required contract and stop at the explicit no-action boundary. Any broader operation requires new authority.

### Scenario 2

> Read this supplied documentation URL using a live supported page-reading tool. Do not search again unless reading fails.

Accepted behavior: preserve the stated scope; discover the required contract and stop at the explicit no-action boundary. Any broader operation requires new authority.

### Scenario 3

> Search this topic within the requested site and explain whether the available mechanism matches the requested search type.

Accepted behavior: preserve the stated scope; discover the required contract and stop at the explicit no-action boundary. Any broader operation requires new authority.


These are illustrative prompts, not captured API responses or claims of successful live execution. They deliberately avoid guessed JSON payloads and fabricated prices. See [prompt acceptance fixtures](../examples/acceptance.json) for the offline safety assertions.

## Result review

Relevant retrieved material with usable source URLs and a clear statement of scope and freshness. Empty results mean the retrieval found nothing within its scope, not that the requested fact is false.

Check original results rather than relying on the agent's summary alone. Preserve response status and evidence only to the extent safe; redact personal or secret fields. If billing is absent from the response, say it is not observable there rather than inferring a charge from HTTP success.

## Related decision

EverySearch owns retrieval. Research owns claim framing, source comparison and a calibrated conclusion. Use EveryData instead when the desired result is a supported structured platform record.

Return to [README](../README.md) or [setup](setup.md).
