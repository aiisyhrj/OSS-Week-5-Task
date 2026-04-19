Open Track — Documentation
Overview
Open Track is a Python program that collects contributor and issue data using input(), analyses it, and saves reports to disk. It runs top to bottom as a single file.

Sections

Section 1 — Project Setup
- Project info is stored in a tuple (name, version, year, language, lead)
- 4 contributors are collected and stored as dictionaries in a list
- Names are sorted, and each contributor gets a status field added via update()

Section 2 — Issue Tracking
- 5 issues are collected and stored as dictionaries in a list
- Open issues are counted using a loop
- Sets are used for reporters and tech stack — union, intersection, and difference are shown
- A priority_count dict and status_groups dict are built by looping through issues
- The top reporter is found using a loop (no max())
- pop() removes the type key from the first issue

Section 3 — File Output
- A folder is created using os.mkdir() and os.path.exists()
- project_report.txt — full report saved as plain text
- issues.csv — one row per issue with a header
- Files are read back using read(), readline(), and readlines()
- All output uses f-strings only

Language
Python 3 
