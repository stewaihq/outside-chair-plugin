# Connection and setup recovery

1. Call `get_profile` once. Report the connected email, workspace role, read/write permission and selected workspace name when present. Explain that Viewers are read-only when this accounts for a write failure. Keep other technical connection details internal unless the user asks or recovery requires them.
2. If there are no workspaces, explain that the connection works and offer to create one after the user confirms its name and kind.
3. If selection is required, call `list_workspaces` once and ask the user to choose by name. Never ask for or display a workspace ID.
4. If read or write permission is missing, give the single concrete remedy in plain language. Do not volunteer implementation-level permission details.
5. On authentication failure, stop and give one concrete reconnect instruction. Do not inspect local databases or substitute another identity.
6. Do not repeat diagnostics after a successful read unless the connection state changes.
