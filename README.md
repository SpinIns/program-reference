# Program Reference Tool

An internal reference tool for Spinnaker Insurance that allows team members to look up which states and lines of business (LOBs) each insurance program writes in. Built as a self-contained HTML/JavaScript application with no backend, no database, and no installation required.

---

## Access

The tool is hosted via GitHub Pages and embedded on the Spinnaker Operations SharePoint site.

**Direct URL:** `https://yourusername.github.io/program-reference/`

---

## Features

### Program Lookup
- Search and filter all 79 programs by name, code, LOB, or description
- Filter by **Active** or **Run-off** status
- View all states a program writes in and all applicable ASLOB codes
- Status indicator (Active / Run-off) displayed on every program card

### Cross-Reference
- **Programs by State** — select any US state to see every program writing there, with status and LOB detail
- **Programs by Line of Business** — filter by keyword or select an ASLOB code to see every program writing that LOB, with status and states written
- Click any result to jump directly to the full program detail

### Editing (Data Manager only)
- **Edit States** — checkbox grid to add or remove states for any program
- **Edit LOBs** — checklist of all 54 ASLOB codes to add or remove LOBs
- **Edit Info** — update program name, LOB category, description, notes, and status
- **Add Program** — full form to create a new program with states and LOBs
- **Remove Program** — requires typing the program code to confirm deletion
- All edits auto-save to browser localStorage on the data manager's machine

### Export & Share
- Generates a new self-contained HTML file with all current data baked in
- Upload the exported file to this repository to publish updates to the team

---

## Data Structure

All program data is embedded directly in `index.html` as a JavaScript constant. No external files or APIs are required. The data includes:

| Field | Description |
|---|---|
| `code` | Short program identifier used in reporting systems |
| `full_name` | Full program name |
| `lob` | Line of business category |
| `description` | Program description |
| `notes` | Additional info (e.g. state restrictions, admitted/E&S) |
| `status` | `Active` or `Run-off` |
| `states` | Array of US state codes the program writes in |
| `lobs` | Array of ASLOB code + description objects |

---

## Updating the Tool

### To update program data

1. Open your local master copy of the tool in a browser
2. Make all necessary edits using the built-in edit features
3. Click **Export & Share** — this downloads a new `Program_Reference_YYYY-MM-DD.html` file
4. Rename the downloaded file to `index.html`
5. In this repository, click on `index.html` → edit or replace the file
6. Commit the change — the live tool updates immediately

### To add a new program

1. Open the tool, click **＋ Add Program**
2. Fill in the program code, name, LOB, description, notes, status, states, and ASLOB codes
3. Save — the program appears immediately in the list
4. Export & Share and upload to this repository to publish to the team

### To update program states or LOBs

1. Select the program from the list
2. Click **✎ Edit States** or **✎ Edit LOBs**
3. Check or uncheck as needed and save
4. Export & Share and upload to this repository

---

## ASLOB Reference

ASLOB (Annual Statement Line of Business) codes are the standardized regulatory codes used in insurance statutory reporting. The tool includes all 54 standard ASLOB codes. Reference the `ASLOB_Reference` tab in the companion Excel workbook for the full list.

---

## Files in This Repository

| File | Description |
|---|---|
| `index.html` | The live tool — self-contained HTML/JS application |
| `README.md` | This file |

---

## Technology

- Plain HTML, CSS, and JavaScript — no frameworks, no dependencies
- Google Fonts (IBM Plex Sans, IBM Plex Mono, Fraunces) loaded via CDN
- Browser `localStorage` for persistent editing sessions
- Self-contained export generates a ready-to-share HTML file

---

## Maintained By

Operations Team — Spinnaker Insurance  
For questions or data corrections, contact the designated data manager.

