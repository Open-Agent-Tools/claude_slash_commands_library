---
description: Load all .md files from current or specified directory into context
allowed-tools:
  - glob
  - read
  - ls
---

Please load all markdown (.md) files from the current directory or specified directory into context for analysis and reference.

**Process**:
1. Use glob to find all .md files in the target directory
2. Read each file found to bring it into context
3. Provide a brief summary of what files were loaded

**Directory Selection**:
- If no directory is specified in arguments, use current directory
- If directory is specified, use that path
- Validate directory exists before processing

**Output Format**:
- List each file loaded with its path
- Provide brief description of total files processed
- Note any files that couldn't be read

$ARGUMENTS