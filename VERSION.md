# TodoManager Version History

## Version 1.7.0 (Current)

### Release Date
December 2025

### New Features
- **Compact Daily Plan Items**: Daily Plan items now display in a compact single-line layout
  - Checkbox, title, effort, and deadline all on one line
  - Long titles truncated with ellipsis ("...")
  - Hover tooltip shows full title for truncated items
  - Container auto-sizes to content (no fixed height, no scrollbars)
  - Block/unblock buttons remain functional

### Data Migrations
- No data migrations required for v1.7.0

---

## Version 1.6.0

### Release Date
December 2025

### New Features
- **Read-Only Todo Modal**: Clicking a todo now opens a read-only view modal
  - Displays all todo fields in a clean, non-editable format
  - Edit pen icon in header to switch to edit mode
  - Removed edit button from todo cards in the list
  - Checkbox and block buttons remain on todo cards
- **Modal Close Behavior**: Different close behavior based on mode
  - Read-only mode: Escape key or clicking backdrop closes modal
  - Edit mode: Must use Save or Cancel buttons (prevents accidental data loss)
- **Daily Plan Integration**: Clicking todo titles in Daily Plan opens read-only modal

### Data Migrations
- No data migrations required for v1.6.0

---

## Version 1.5.0

### Release Date
December 2025

### New Features
- **Future Todo Groups**: Organize upcoming todos into collapsible sections based on deadline proximity
  - "Upcoming in a Week" section (8-14 days) with blue accent color
  - "Upcoming in 2 Weeks" section (15 days to end of month) with purple accent color
  - "In the Horizon (Over 1 Month)" section with gray accent color
  - Immediate todos (1-7 days) remain in main active list
  - All sections collapsed by default with count badges

### Data Migrations
- No data migrations required for v1.5.0

---

## Version 1.4.0

### Release Date
December 2025

### New Features
- **Collapsible Completed/Dropped Sections**: Completed and dropped todos are now grouped into collapsible sections below the active todo list
  - "Recently Completed" section with green accent color
  - "Recently Dropped" section with red accent color
  - Sections collapsed by default, user can expand to view
  - Count badge shows number of items in each section
- **Tasks Settings**: New "Tasks" section in Settings page
  - Configurable visibility threshold (1-365 days, default: 5 days)
  - Todos older than the threshold are hidden from UI but remain in system
  - All todos included in exports regardless of visibility

### Data Migrations
- No data migrations required for v1.4.0

---

## Version 1.3.0

### Release Date
December 2025

### New Features
- **Conflict Detection Modal**: When adding holidays, PTO, or disabling work days, the system detects conflicts with scheduled todos and meetings
  - Shows a modal dialog listing all conflicting items grouped by type (Todos, Meetings, Recurring Meetings)
  - Individual item selection with checkboxes
  - "Move Selected" action moves items to the next available work day
  - "Delete Selected" action removes selected items
  - "Select All" and "Deselect All" buttons for bulk selection
  - "Keep All (No Changes)" to dismiss without changes

### Data Migrations
- No data migrations required for v1.3.0

---

## Version 1.2.0

### Release Date
December 2025

### New Features
- **Meetings**: New entity type to track meetings with title, description, date, and duration
  - Shift+M keyboard shortcut to create meetings on Todo's page
  - Duration defaults to 1 hour, supports flexible input (e.g., "30 min", "1.5h")
  - Meetings integrated into Daily Load KPI with purple color coding
- **Meetings List**: Dedicated section below Daily Load showing upcoming meetings
  - Grouped by Today/Tomorrow/Date labels
  - Single-row display with truncated titles and duration
  - Delete button on hover

### Data Migrations
- No data migrations required for v1.2.0

---

## Version 1.1.0

### Release Date
December 2025

### New Features
- **Minimal Work Effort**: New effort level for quick 30-minute tasks
- **Updated Very Low**: Very Low effort is now 1 hour instead of 30 minutes
- **Holiday Templates**: Quickly add public holidays for NL, DE, UK, US, or India

### Data Migrations
- **v1.1.0**: Todos with `very_low` effort migrated to `minimal` effort level

---

## Version 1.0.0

### Release Date
December 2025

### New Features
- **Work Calendar System**: Configure available work days, hours per day, holidays, and PTO
  - Calendar Settings section in Settings page
  - Variable hours per day (default: 8hrs Mon-Fri)
  - Saturday and Sunday disabled by default
  - Add/remove holidays and PTO dates
- **DateTimePicker Integration**: Disabled days (weekends, holidays, PTO) cannot be selected
- **Daily Load KPI Updates**: "Tomorrow" column renamed to "Next Day" showing the next available work day
- **App Versioning**: Introduction of version tracking system

### Data Migrations
- **v1.0.0**: Todos with deadlines on disabled days are automatically moved to the closest future enabled work day

### Migration Code Status
- Migration code for v1.0.0 is ACTIVE
- To be cleaned up in next version (v1.1.0)

---

## Previous Versions

### Pre-1.0 (Legacy)
- Initial development phase
- No formal versioning
