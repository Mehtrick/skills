# Project architecture index

The target repository's `.agents/architecture.md` is the shared source for architecture documentation locations and conventions. Resolve every relative path against the repository root, even though the index lives under `.agents/`. Keep the index in Markdown and use AsciiDoc (`.adoc`) by default for new arc42 documentation. Preserve the format of existing artifacts unless the user requests a migration.

## Find the relevant artifacts

1. Read the index first and select the system in scope. Check the entries needed for this task against the actual files, directories, or include chain. Reuse valid entries without repeating discovery.
2. If the index is missing or the relevant entries are incomplete or stale, give `arc42-explorer` the system scope and the locations that need discovery, when delegation is available and authorized. The Explorer follows repository guidance, build configuration, existing documents, and includes. If delegation is unavailable, perform the same focused discovery yourself.
3. The Explorer returns verified locations with evidence, a proposed Markdown addition or correction, and plausible options for any unresolved location. The acting agent asks the user to resolve ambiguities before making edits that depend on them. For a new artifact with no established destination, propose a location for confirmation.
4. When the user requests repository edits or explicitly asks to set up the index, the acting agent creates or updates the index with confirmed entries relevant to the task. For a chat-only request, return the proposed entries in chat. Preserve other systems and existing entries outside the scope of the change.

When acting as a read-only specialist, report gaps and proposed index changes to the parent agent. The parent handles user questions and writes the confirmed entries.

## Record only what the project uses

Use a heading per system. Record the documentation entry point, language, and format when known. For an artifact type, record the file or directory, plus the include or index file, template, and naming convention when those are relevant. Add entries as work reaches them. Keep architecture decisions and other substantive content in their own documents.

Example for a project with an established ADR layout:

```markdown
# Architecture index

Paths are relative to the repository root.

## Appointment service

- Documentation entry point: `docs/architecture/index.adoc`
- Format: AsciiDoc
- Language: English
- ADR directory: `docs/architecture/decisions/`
- ADRs are included from `docs/architecture/09_decisions.adoc`.
```

For a new arc42 documentation structure, use the official template in the selected documentation language as a starting point. Keep only the sections needed for the requested scope and verify the resulting AsciiDoc includes. [Official arc42 template downloads](https://arc42.org/download/) · [English AsciiDoc template ZIP](https://arc42.org/dl/arc42-template-EN-plain-asciidoc.zip)
