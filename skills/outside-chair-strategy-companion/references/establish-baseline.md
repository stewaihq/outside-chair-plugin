# Establish a strategy baseline

1. Select the workspace. Create one only after the user confirms its exact name and kind.
2. Ask only for material information missing from priorities, initiatives, assumptions, signposts, measures or observations. Do not turn the internal categories into a questionnaire.
3. Preserve the user's wording. Mark uncertainty as proposed rather than resolving it silently.
4. Use only exact typed relationships from the main skill. Omit a plausible but invalid link.
5. Present one concise proposal grouped as `Direction`, `Assumptions`, `Measures/signposts` and `Relationships`. Include every persisted status and date, but no internal or transport fields.
6. After one explicit confirmation, call `save_strategy_records` once with `mode: "baseline"`.
7. Read back `get_strategy_context` and report counts, confirmed/proposed status, relationships and anything rejected.
