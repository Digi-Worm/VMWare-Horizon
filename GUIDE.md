# VMWare-Horizon Repository Guide

## Project Overview

This is a **security research and vulnerability documentation repository** focused on VMware Horizon, VMware's Virtual Desktop Infrastructure (VDI) platform. The project documents four discovered security vulnerabilities that allow attackers to bypass security controls, execute unauthorized commands, and exfiltrate data from VMware Horizon environments.

**Purpose:** Educational security research and responsible vulnerability disclosure.

**Important:** This repository exists for defensive security awareness. Exploit code must **never** be enhanced, improved, or augmented. Analysis, documentation, and reporting on existing code is acceptable.

---

## Repository Structure

```
VMWare-Horizon/
├── (this file)                      # Repository guide
├── README.md                        # Project overview and vulnerability summary
├── Command-Powershell Execution Bypass          # Vulnerability 4: VBA exploit + documentation
├── VMWare Horizon's URL Policies Bypass         # Vulnerability 2: URL parameter bypass docs
├── VMWare Redirector Exploit: ...               # Vulnerability 3: Localhost data exfiltration docs
├── VMWare-RedirectorPlugin-Bypass-BrowserProfile # Vulnerability 1: Browser profile bypass docs
└── VDI Command Execution/
    └── VDI Command Execution/
        └── VDI Command Execution-Powershell Bypass  # VBA exploit code (standalone)
```

**Total size:** ~6 files, ~180 lines, documentation-focused repository with minimal code.

---

## Documented Vulnerabilities

| # | Name | Type | File |
|---|------|------|------|
| 1 | Browser Redirection Control Bypass | Browser profile manipulation | `VMWare-RedirectorPlugin-Bypass-BrowserProfile` |
| 2 | URL Policies Bypass | Parameter-based URL filter evasion | `VMWare Horizon's URL Policies Bypass` |
| 3 | Localhost Data Exfiltration | Redirector plugin abuse | `VMWare Redirector Exploit: Unauthorized Data Exfiltration through Localhost` |
| 4 | Command/PowerShell Execution Bypass | GPO evasion via VBA | `Command-Powershell Execution Bypass` |

---

## Tech Stack

- **Documentation format:** Plain text and Markdown
- **Exploit language:** VBA (Visual Basic for Applications)
- **Target platform:** Windows (VMware Horizon VDI environment)
- **No build system, package manager, test framework, or CI/CD pipeline**

---

## File Conventions

### Documentation Files
Each vulnerability document follows a consistent structure:
- **Title/Header** - Descriptive name of the exploit
- **Description** - Technical explanation of the vulnerability
- **Payload** - Example attack vector or command
- **Impact** - Consequences of exploitation
- **Remediation** - Defensive recommendations

### VBA Code Files
- Standard VBA subroutine format (`Sub ... End Sub`)
- Uses `WScript.Shell` for Windows command execution
- Output captured to temp files and displayed via Notepad
- Comments use VBA apostrophe (`'`) convention

### Naming
- Files use descriptive names with spaces and hyphens (no extensions)
- Directory names mirror file naming conventions

---

## Development Workflow

### Branching
- **Main branch:** `main`
- **Development:** Feature branches off `main`
- All commits are by `Digi-Worm` (vivek.januskoncepts@gmail.com)

### Commits
- Commit messages are descriptive and reference the vulnerability being documented
- Examples from history: `"VDI Command-PowerShell Execution Bypass"`, `"VMWare Redirector Exploit: Unauthorized Data Exfiltration through Localhost"`
- Use imperative or descriptive style matching existing convention

### No Build or Test Steps
There is no build process, linting, or automated testing. Changes are purely documentation and code-snippet based.

---

## Contribution Guidelines

### Acceptable Changes
- Analyze and explain existing exploit code and vulnerability documentation
- Improve documentation quality (grammar, formatting, structure)
- Add new vulnerability write-ups following the existing document structure
- Suggest remediation strategies and defensive measures
- Create summaries, reports, or comparisons of the documented vulnerabilities
- Organize the repository (file structure, README improvements)

### Not Acceptable
- Enhancing, improving, or augmenting exploit code to be more effective
- Creating new exploit code or attack tools
- Removing educational disclaimers or responsible-use notices
- Providing step-by-step attack instructions beyond what is already documented

### When Editing Documentation
- Preserve the existing section structure (Description, Payload, Impact, Remediation)
- Maintain the educational and defensive tone
- Keep the ethical disclaimer present in relevant files
- Use plain text or Markdown formatting consistent with existing files

---

## Key Context

1. **This is a documentation repo, not a software project.** There are no dependencies to install, no builds to run, and no tests to execute.
2. **File names contain spaces.** Always quote file paths when using shell commands.
3. **The VBA code in two files is identical** — `Command-Powershell Execution Bypass` contains the code with full documentation headers, while `VDI Command Execution/.../VDI Command Execution-Powershell Bypass` contains just the code.
4. **All content dates from October 2023.** The repository has been stable since then.
5. **The remote is a local proxy** (`127.0.0.1:18794`), not a public GitHub instance.
