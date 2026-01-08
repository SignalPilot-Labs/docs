Signalpilot | #1 AI Agent for Jupyter Lab
Guide


























Overview
Edit and complete code at the single cell level.

SignalPilot makes it easy to improve code directly inside cells with AI-powered editing tools. These tools are designed for fast, localized changes without needing to open a full chat or run a full plan.

Inline Edit
How it works: Select a cell, click Inline Edit, and describe your change.

Scope: Updates only the selected cell.

Best for: Small refactors, quick fixes, renaming variables, adding comments, or adjusting logic.

Example: “Vectorize this loop into a list comprehension.”

Tab Autocomplete
How it works: When a cell is focused and you pause typing for ~1 second, SignalPilot suggests completions.

Scope: Suggests code continuations inline as you type.

Best for: Reducing boilerplate, remembering syntax, and filling in multi-line code patterns.

Example: Typing df.gr → AI suggests df.groupby("region").sum().

When to Use Each
Inline Edit – after code is already written, to modify or improve it.

Tab Autocomplete – while typing, to speed up code writing with context-aware suggestions.

Together, these features let you stay in flow: autocomplete while you type, then refine with inline edits as needed.

FAQ
Q: Does Tab Autocomplete overwrite my code?
Yes. Suggestions appear inline, and you choose whether to accept them.

Q: Can Inline Edit affect multiple cells?
No. Inline Edit is strictly limited to one cell at a time.

Q: Do both features use notebook context?
Yes. Both Inline Edit and Autocomplete are context-aware, using variable names, imports, and recent code.

Q: Can I disable one without disabling the other?
Yes. Tab Autocomplete can be toggled in Settings, while Inline Edit is optional and only applies when you invoke it.


Previous
Bring Your Own Data (BYOD)

Next
Inline Edit
On This Page
Inline Edit
Tab Autocomplete
When to Use Each
FAQ
© 2025 SignalPilot | All Rights Reserved