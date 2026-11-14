# Shared architecture index

At the start of repository work, read `.agents/architecture.md` at the target repository root and identify the system in scope. The analyst and arc42 Architect share this Markdown index. Resolve its paths relative to the repository root. Verify the entries needed for the current task and reuse valid ones.

For a missing index or missing or stale entries, follow the repository's instructions, documentation indexes and AsciiDoc includes, build and routing configuration, source, and tests. Search for the locations needed for this task. Record how each location was verified. If multiple plausible locations remain, show the options and their evidence and ask before making dependent edits.

Create the index if absent, with `# Architecture index` and a heading for the system in scope. Maintain it as you discover paths the analyst will need again, including the documentation entry point, arc42 runtime view, use-case directory and index, project template, relevant implementation entry points, and test locations. Add only relevant verified paths and confirmed conventions. Preserve existing headings and entries belonging to other systems and workflows. Keep business rules and findings in their own artifacts. In a read-only task, report proposed index changes for later application. If the project explicitly tracks the shared index elsewhere, use that existing location.

Distinguish a discovered use-case directory from the user's confirmed destination. Record the confirmed destination, filename pattern, and numbering scope under the relevant system. Reuse the confirmation in later chats. Once an agreed new directory is created, verify the path before recording it as an existing location.
