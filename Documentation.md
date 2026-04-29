# Open Track — Documentation

## Overview

Open Track is a Python program that collects contributor and issue data using `input()`, analyses it, and saves reports to disk. It runs top to bottom as a single file.

## Sections

### Section 1 — Project Setup
- Project info is stored in a **tuple** (name, version, year, language, lead)
- 4 contributors are collected and stored as **dictionaries** in a list
- Names are sorted, and each contributor gets a `status` field added via `update()`

### Section 2 — Issue Tracking
- 5 issues are collected and stored as **dictionaries** in a list
- Open issues are counted using a loop
- **Sets** are used for reporters and tech stack — union, intersection, and difference are shown
- A `priority_count` dict and `status_groups` dict are built by looping through issues
- The top reporter is found using a loop (no `max()`)
- `pop()` removes the `type` key from the first issue

### Section 3 — File Output
- A folder is created using `os.mkdir()` and `os.path.exists()`
- `project_report.txt` — full report saved as plain text
- `issues.csv` — one row per issue with a header
- Files are read back using `read()`, `readline()`, and `readlines()`
- All output uses f-strings only

### Bonus
- A list comprehension builds a list of Critical/High priority issue titles
- The report file is reopened in append mode (`'a'`) to add an urgent issues section

## Files Generated at Runtime

| File | Description |
|------|-------------|
| `project_report.txt` | Full project summary |
| `issues.csv` | Issue data in CSV format |

## Language
Python 3 — no external libraries required

---

## Functions Used

| Function | How it was used |
|----------|----------------|
| `c.update({"status": "Active"})` | Adds the `status` key to every contributor dictionary after they are registered |
| `contributors[0].get('status')` | Retrieves the status value safely — unlike direct access, it won't crash if the key doesn't exist |
| `contributors[0].copy()` | Creates a copy of the first contributor's dictionary so the original stays unchanged |
| `issues[0].pop('types')` | Removes the `types` key from the first issue and returns it — the key is gone from the dictionary after this |
| `tech_stack.discard("Java")` | Removes an item from a set without throwing an error if the item isn't there — safer than `remove()` |
| `reporters.union(tech_stack)` | Combines two sets into one with no duplicates |
| `reporters.intersection(tech_stack)` | Returns only the items that exist in both sets |
| `reporters.difference(tech_stack)` | Returns items in reporters that are not in tech stack |
| `f.read()` | Reads the entire file content as one single string |
| `f.readline()` | Reads one line at a time — each call moves to the next line |
| `f.readlines()` | Reads all lines and returns them as a list — useful for counting lines or filtering specific ones |
| `open(report_path, "a")` | Opens the file in append mode — adds content to the end without overwriting what's already there |
