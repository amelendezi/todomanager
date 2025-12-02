# Architecture Documentation

## Overview

TodoManager is a standalone, single-file web application that runs entirely in the browser without requiring a web server. All functionality is contained within `index.html`.

## Single-File Architecture

### Core Principle
The entire application is self-contained in `index.html` with:
- HTML structure
- CSS styles (inline in `<style>` tags)
- JavaScript code (inline in `<script>` tags)
- SheetJS library (inlined from `resources/xlsx.mini.min.js`)

### Why Single-File?
- No build process required
- No web server needed
- Portable - can be opened directly in any browser
- Easy to distribute and use

## Data Persistence Strategy

### app.json File
- Used to store application data
- User manually loads `app.json` via file input to restore previous session
- User downloads `app.json` to save their work
- JSON format for human-readable data storage

### Data Flow
1. **Load**: User clicks "Load" → selects `app.json` → data restored to application state
2. **Work**: User interacts with the application → changes stored in memory
3. **Save**: User clicks "Save" → browser downloads updated `app.json`

## Excel Import/Export

### SheetJS Integration
- Source: `resources/xlsx.mini.min.js`
- **Must be inlined** directly into `index.html` (not referenced externally)
- Provides Excel file reading and writing capabilities

### Functionality
- Import: Read `.xlsx` or `.xls` files to populate todos
- Export: Generate Excel files from current todo data

## File Structure

```
TodoManager/
├── index.html              # Single-file application (HTML + CSS + JS)
├── app.json                # Data file (user-managed, not in repo)
├── resources/
│   └── xlsx.mini.min.js    # SheetJS source (to be inlined)
├── ARCHITECTURE.md         # This file
└── CLAUDE.md              # Claude Code guidance
```

## Development Guidelines

### Making Changes
- All code modifications happen in `index.html`
- Test by opening `index.html` directly in a browser (file:// protocol)
- No build, compile, or serve steps required

### Adding Features
- Add HTML in the appropriate section
- Add CSS in the `<style>` block
- Add JavaScript in the `<script>` block
- Keep code organized with clear comments

### SheetJS Usage
- Copy entire contents of `resources/xlsx.mini.min.js`
- Paste into a `<script>` tag before the main application JavaScript
- Use the global `XLSX` object for Excel operations

## Browser Compatibility

The application should work in modern browsers supporting:
- ES6+ JavaScript features
- File API for loading files
- Blob/Download API for saving files
- LocalStorage (optional enhancement)

## Security Model

- Runs entirely client-side
- No network requests (fully offline capable)
- No sensitive data transmitted
- User maintains full control of their data files
