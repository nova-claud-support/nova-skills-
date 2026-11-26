# Google Skills Import Notes

## Included

- 226 `SKILL.md` instruction files, kept under `skills/google/` with their original category and package paths.
- A path index in `GOOGLE_SKILLS_INDEX.md`.
- The Apache 2.0 license text in `THIRD_PARTY_LICENSES/GOOGLE_SKILLS_APACHE_2.0.txt`.
- Cross-model portability and execution-safeguard guidance appended to each imported skill.

## Not included in this import

This import focused on the 226 skill instruction files. It does not include the upstream repository's auxiliary `references/`, `scripts/`, `assets/`, plugin manifests, marketplace configuration, or Git submodule contents. Some skill instructions may mention optional companion files or runtime integrations; check that the referenced file or tool actually exists before relying on it. Do not assume an omitted script, template, MCP server, plugin, or submodule was installed.

## Adaptation

External hyperlinks were removed from the imported skill text as requested. Required license text is retained. Google Cloud actions, API access, credentials, product availability, and host-native skill discovery remain dependent on the current runtime and explicit permissions.
