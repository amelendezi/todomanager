# Issue Tracker

This file tracks issues for the TodoManager project.

---

## Issue #1: Implement Home Page with Todo List and Navigation from Landing Page

**Status:** Closed
**Created:** 2025-12-02
**Fix:** Issue-1: Implemented home page with header navigation, todo list display, and empty state with "No Todos" message.

### Summary
When the user clicks "Start From Scratch" on the landing page, they should navigate to the home page displaying the todo list with a header navigation.

### Requirements

#### Navigation
- [ ] Clicking "Start From Scratch" on landing page navigates to home page

#### Header
- [ ] Display "Home" text on the left side of the header
- [ ] Settings icon on the right side (placeholder - no functionality on click)
- [ ] Export button on the right side (placeholder - no functionality on click)
- [ ] Follow the navigation design: 60px height, white background with subtle shadow

#### Todo List
- [ ] Display list of all todos
- [ ] Each todo item should be visible in the list area

#### Empty State
- [ ] When no todos exist, display a greyed out icon
- [ ] Show "No Todos" text below the icon
- [ ] Follow empty state design: 64px icon size, centered content

### Design References
- Navigation: See DESIGN.md - Navigation section (60px height, white background)
- Empty States: See DESIGN.md - Empty States section
- Color palette: Primary text `#1F1F1F`, muted text `#ADB5BD`

### Technical Notes
- All implementation in `index.html` (single-file architecture)
- Use inline CSS and JavaScript per ARCHITECTURE.md

### Acceptance Criteria
1. User can click "Start From Scratch" and see the home page
2. Header displays "Home" with settings and export icons
3. Settings and export icons are visible but non-functional
4. Empty state shows greyed icon with "No Todos" text when list is empty
5. Todo items display in a list when todos exist

---

## Issue #3: Add Todo Creation Form with Keyboard Shortcut (Ctrl+N)

**Status:** Closed
**Created:** 2025-12-02
**Related Issues:** #1
**Fix:** Issue-3: Added modal form with Ctrl+N shortcut, description/due date fields, and checkbox completion toggle.

### Summary
Add functionality to create new todos via a keyboard shortcut (Ctrl+N). This opens a modal form where users can enter todo details, and upon saving, the todo appears in the list view.

### Requirements

#### Keyboard Shortcut
- [ ] Pressing `Ctrl+N` on the home page opens the create todo modal
- [ ] Shortcut only works when on the home page (not landing page)

#### Modal Form
- [ ] Modal overlay with backdrop (following DESIGN.md modal pattern)
- [ ] Form title: "New Todo"
- [ ] Fields:
  - **Description** (required): Text input field for todo description
  - **Due Date** (optional): Date input with calendar picker
- [ ] Auto-generated unique ID (hidden from user, internal use)
- [ ] "Save" button to create the todo
- [ ] "Cancel" button to close without saving
- [ ] Pressing `Escape` key closes the modal

#### Todo List Integration
- [ ] New todo appears in the list immediately after saving
- [ ] Empty state disappears when first todo is added
- [ ] Each todo displays: checkbox, description, due date (if set)

#### Todo Completion
- [ ] Clicking checkbox toggles todo completion status
- [ ] Completed todos show visual feedback (checked state)

### Design References
- Modal/Dialog: See DESIGN.md - "Modal/Dialog: Fade background + scale content from 0.95 to 1, 0.3s"
- Buttons: See DESIGN.md - Primary Button and Icon Buttons sections
- Form inputs: Border `#E0E0E0`, focus border `#FFB800`

### Technical Notes
- All implementation in `index.html` (single-file architecture)
- Use native HTML date input for calendar picker
- Generate UUID or timestamp-based unique ID

### Acceptance Criteria
1. Pressing Ctrl+N on home page opens modal form
2. Form has description field and date picker
3. Clicking Save creates todo and closes modal
4. Clicking Cancel or pressing Escape closes modal without saving
5. New todo appears in the list with checkbox
6. Clicking checkbox marks todo as complete/incomplete

---

## Issue #5: Default Due Date Field to Current Date in Todo Creation Form

**Status:** Closed
**Created:** 2025-12-02
**Related Issues:** #3
**Fix:** Issue-5: Pre-populate due date field with today's date when opening the create todo modal.

### Summary
When opening the "New Todo" modal, the due date field should be pre-populated with the current date instead of being empty.

### Requirements
- [ ] When the modal opens, set the due date input to today's date
- [ ] User can still change the date or clear it if desired

### Technical Notes
- Set the date input value using JavaScript's `Date` object formatted as `YYYY-MM-DD`
- Apply default in the `openModal()` function

### Acceptance Criteria
1. Opening the create todo modal shows today's date pre-selected
2. User can modify the date to a different value
3. User can clear the date field if they don't want a due date

---

## Issue #7: Add Edit Functionality to Todos with Edit Icon

**Status:** Closed
**Created:** 2025-12-02
**Related Issues:** #1, #3
**Fix:** Issue-7: Added edit icon to todos that opens modal in edit mode with pre-populated fields.

### Summary
Enable editing of existing todos by adding an edit icon (pencil) to each todo item in the list view. Clicking the edit icon opens the existing modal dialog in "edit mode" with the todo's current values pre-populated.

### Requirements

#### Edit Icon
- [ ] Add pencil/edit icon to each todo item in the list view
- [ ] Icon is always visible (not just on hover)
- [ ] Icon follows DESIGN.md icon button styling (32x32px, transparent background, hover state)

#### Edit Mode Modal
- [ ] Clicking edit icon opens the modal with title "Edit Todo"
- [ ] Pre-populate description field with existing todo description
- [ ] Pre-populate due date field with existing todo due date (if set)
- [ ] "Save" button updates the existing todo (not create new)
- [ ] "Cancel" or Escape closes without saving changes

#### Data Handling
- [ ] Preserve the todo's original ID when updating
- [ ] Preserve the todo's completion status when updating
- [ ] Update the todo in the list immediately after saving

### Technical Notes
- Modify `openModal()` to accept an optional todo parameter for edit mode
- Track whether modal is in "create" or "edit" mode
- Update `saveTodo()` to handle both create and update operations

### Acceptance Criteria
1. Each todo item displays an edit icon (pencil)
2. Clicking edit icon opens modal with "Edit Todo" title
3. Modal fields are pre-populated with todo's current values
4. Saving updates the existing todo without creating a new one
5. Todo's ID and completion status are preserved after edit

---

## Issue #8: Add Opportunity Manager Page with Tab Navigation and Side Panel Details

**Status:** Closed
**Created:** 2025-12-02
**Related Issues:** #1, #3
**Fix:** Issue-8: Added Opportunity Manager page with tab navigation, Shift+N creation modal, opportunity list with status badges, and side panel for viewing/editing details with status dropdown.

### Summary
Create a new "Opportunity Manager" page accessible via tab navigation next to "Home". This page displays a list of opportunities with similar behavior to the Todo list. Users can create opportunities with Shift+N and view/edit details in a right-side panel.

### Requirements

#### Navigation
- [ ] Add horizontal tab navigation in the header (Home | Opportunity Manager)
- [ ] Clicking "Opportunity Manager" tab navigates to the opportunities page
- [ ] Active tab should be visually highlighted

#### Opportunity Data Model
- **ID**: Auto-generated unique ID (hidden)
- **Name**: Required text field
- **Description**: Optional text field
- **Start Date**: Date picker, defaults to current date
- **Contact**: Person's name
- **Status**: Requested (default), Open, Paused, Cancelled, Closed

#### Opportunity List View
- [ ] Each item shows: Name, Status badge, Contact name
- [ ] Status badges with distinct colors
- [ ] Empty state with "No Opportunities" text

#### Create Opportunity (Shift+N)
- [ ] Modal with Name, Description, Start Date, Contact fields
- [ ] Status automatically set to "Requested"

#### Detail Side Panel
- [ ] Click opportunity to open right-side panel
- [ ] Status changeable via dropdown select
- [ ] Close button to dismiss panel

### Acceptance Criteria
1. Tab navigation shows "Home" and "Opportunity Manager"
2. Shift+N opens create opportunity modal
3. Opportunities display with Name, Status, Contact
4. Clicking opportunity opens detail panel
5. Status changeable via dropdown

---

## Issue #9: Link Todos to Opportunities with Autocomplete and Inline Creation

**Status:** Closed
**Created:** 2025-12-02
**Related Issues:** #3, #7, #8
**Fix:** Issue-9: Added autocomplete opportunity linking in todo modal with inline creation form (slide animation) and auto-status to Open when linked.

### Summary
Enhance the todo creation/edit modal to allow users to optionally link a todo to an opportunity. The system provides autocomplete suggestions from existing opportunities. If the user types a name that doesn't exist and presses Enter, an inline opportunity creation form slides down within the modal. The linked opportunity is displayed in the todo list view, and opportunities with at least one non-completed todo automatically have their status set to "Open".

### Requirements

#### Autocomplete Field in Todo Modal
- [ ] Add "Linked Opportunity" field (optional) to todo create/edit modal
- [ ] As user types, show dropdown with matching opportunities
- [ ] Filter matches case-insensitively by opportunity name
- [ ] Clicking a suggestion selects it

#### Inline Opportunity Creation
- [ ] If user types a name not in list and presses Enter, slide down inline creation form
- [ ] Animate with slide-down effect (0.3s ease)
- [ ] Inline form includes: Name (pre-filled), Description, Start Date, Contact
- [ ] Save/Enter in inline form collapses it and links the new opportunity
- [ ] New opportunity is only created when the entire todo is saved

#### Todo List Display
- [ ] Show linked opportunity name as badge/text below todo description
- [ ] Style consistently with existing todo item layout

#### Edit Mode Support
- [ ] Pre-populate linked opportunity field when editing
- [ ] User can change to different opportunity or remove link entirely

#### Auto-Status for Opportunities
- [ ] When a todo is linked to an opportunity and the todo is not completed, automatically set opportunity status to "Open"
- [ ] Check on any link action (create or edit)

### Technical Notes
- Modify todo modal HTML to include autocomplete field
- Add inline opportunity creation section (hidden by default)
- Update todo data model to include `opportunityId` field
- Update `renderTodos()` to display linked opportunity
- Add logic in `saveTodo()` to handle opportunity creation and status updates

### Acceptance Criteria
1. Todo modal shows optional "Linked Opportunity" autocomplete field
2. Typing shows matching opportunities in dropdown
3. Pressing Enter on non-existing name shows inline creation form with slide animation
4. Inline form fields can be filled and saved with Enter or Save button
5. Linked opportunity displays in todo list item
6. Editing todo allows changing or removing linked opportunity
7. Opportunity status auto-updates to "Open" when linked to non-completed todo
8. New opportunity only created when todo is saved (not on inline form close)

---

## Issue #10: Opportunity Status Automation and List Actions (Close/Delete)

**Status:** Closed
**Created:** 2025-12-02
**Related Issues:** #8, #9
**Fix:** Issue-10: Added auto-status Paused when all todos complete, Close/Delete action buttons with confirmation modal, and unlinks todos on delete.

### Summary
Enhance the opportunity lifecycle management with automatic status transitions and direct list actions. When all linked todos are completed, set opportunity status to "Paused". Only Paused opportunities can be Closed. Add always-visible Close and Delete action buttons to each opportunity in the list view.

### Requirements

#### Auto-Status: Paused when All Todos Complete
- [ ] When all todos linked to an opportunity are completed, automatically set status to "Paused"
- [ ] Check status after each todo completion toggle
- [ ] If a new non-completed todo is linked, revert to "Open"

#### Close Action (Only from Paused)
- [ ] Add close button (checkmark icon) to opportunity list items
- [ ] Button always visible (not just on hover)
- [ ] Only enabled when opportunity status is "Paused"
- [ ] Clicking sets status to "Closed"
- [ ] Disabled/greyed out for non-Paused opportunities

#### Delete Action
- [ ] Add delete button (trash icon) to opportunity list items
- [ ] Button always visible (not just on hover)
- [ ] Show confirmation dialog before deleting
- [ ] When deleted, remove opportunity link from all associated todos (set opportunityId to null)
- [ ] Re-render both opportunity list and todo list after deletion

#### Status Flow
```
Requested → Open (when todo linked) → Paused (all todos complete) → Closed
```

### Technical Notes
- Update `toggleTodo()` to check and update opportunity status
- Add `closeOpportunity()` and `deleteOpportunity()` functions
- Add confirmation modal for delete action
- Update `renderOpportunities()` to include action buttons
- Add CSS for disabled button state

### Acceptance Criteria
1. Opportunity auto-changes to "Paused" when all linked todos are completed
2. Opportunity auto-changes back to "Open" if non-completed todo is linked
3. Close button visible on all opportunities, only clickable when Paused
4. Clicking Close sets status to "Closed"
5. Delete button visible on all opportunities
6. Delete shows confirmation dialog
7. Deleting opportunity removes links from associated todos
8. Todos remain after opportunity deletion but without the link

---

## Issue #11: Add Cancel Action with Comments System for Opportunities

**Status:** Closed
**Created:** 2025-12-02
**Related Issues:** #8, #10
**Fix:** Issue-11: Added cancel button with reason modal, comments system with timestamped entries, and red styling for cancellation comments in side panel.

### Summary
Add a Cancel action button to opportunities that sets status to "Cancelled". Cancelling requires entering a comment explaining the reason. Introduce a comments system for opportunities - a list of timestamped comments. Cancellation comments are visually distinguished with red styling.

### Requirements

#### Cancel Action Button
- [ ] Add cancel button (X icon) to opportunity list items
- [ ] Button always visible (not just on hover)
- [ ] Enabled for any status (including Closed)
- [ ] Clicking opens a modal to enter cancellation reason

#### Comments Data Model
- [ ] Add `comments` array field to opportunity data model
- [ ] Each comment contains:
  - `text`: The comment content
  - `timestamp`: Date/time when comment was made
  - `type`: "standard" or "cancellation"

#### Cancellation Modal
- [ ] Modal prompts for cancellation reason (required text field)
- [ ] On confirm: add comment with type "cancellation", set status to "Cancelled"
- [ ] Cancel button to dismiss without action

#### Comments Display (Side Panel Only)
- [ ] Show comments list in opportunity detail side panel
- [ ] Display timestamp and text for each comment
- [ ] Cancellation comments styled with red text to distinguish from standard comments

### Technical Notes
- Add `comments: []` to opportunity data model initialization
- Create cancel modal with textarea for reason input
- Add `cancelOpportunity()` function
- Update side panel rendering to display comments section
- Add CSS for cancellation comment styling (red text)

### Acceptance Criteria
1. Cancel button (X icon) visible on all opportunities
2. Clicking Cancel opens modal with reason text field
3. Reason is required before confirming
4. Confirming adds cancellation comment and sets status to "Cancelled"
5. Comments visible in side panel with timestamps
6. Cancellation comments display in red styling

---

## Issue #12: Make Opportunity Status Read-Only in Side Panel

**Status:** Closed
**Created:** 2025-12-02
**Related Issues:** #8, #10, #11
**Fix:** Issue-12: Replaced status dropdown with read-only badge in side panel to match automated status workflow.

### Summary
Replace the status dropdown in the opportunity details side panel with a read-only display. Since opportunity status is now automatically managed through auto-transitions (Requested → Open when todo linked, Open → Paused when all todos complete) and list action buttons (Close, Cancel), the manual status dropdown is no longer needed and could conflict with the automated workflow.

### Requirements

#### Read-Only Status Display
- [ ] Replace the `<select>` dropdown with a read-only status badge
- [ ] Display status using the same styling as the list view badges
- [ ] Remove the `updateOpportunityStatus()` function (no longer needed)

### Technical Notes
- Modify the side panel status section in HTML
- Update `openSidePanel()` to render a status badge instead of setting dropdown value
- Clean up unused JavaScript function

### Acceptance Criteria
1. Side panel shows status as a styled badge (matching list view)
2. Status cannot be manually changed from side panel
3. Status still updates when using list action buttons (Close, Cancel)

---

## Issue #13: Add Comment Input to Opportunity Side Panel

**Status:** Closed
**Created:** 2025-12-02
**Related Issues:** #11
**Fix:** Issue-13: Added textarea and button in side panel to allow users to add standard comments to opportunities.

### Summary
Add a textarea input in the Comments section of the opportunity side panel, allowing users to manually add standard comments. This extends the comments system introduced in Issue #11 (which only added cancellation comments) to support user-added notes.

### Requirements

#### Comment Input UI
- [ ] Add textarea below the comments list in side panel
- [ ] Include placeholder text (e.g., "Add a comment...")
- [ ] Add "Add Comment" button next to/below textarea
- [ ] Clear textarea after successful submission

#### Comment Submission
- [ ] Create new comment with `type: "standard"`
- [ ] Include current timestamp
- [ ] Add to opportunity's comments array
- [ ] Re-render comments list to show new comment
- [ ] Empty comments should not be submitted

#### Styling
- [ ] Standard comments use default styling (not red like cancellation)
- [ ] Input area styled consistently with other form elements

### Technical Notes
- Add textarea and button HTML to comments section
- Create `addComment()` function
- Comments with `type: "standard"` already styled without red (from Issue #11)

### Acceptance Criteria
1. Textarea visible in side panel Comments section
2. User can type and submit a comment
3. Comment appears in list with timestamp
4. Standard comments display in normal styling (not red)
5. Textarea clears after submission
6. Empty comments are not submitted

---

## Issue #14: Archive Action for Closed/Cancelled Opportunities with Toggle View

**Status:** Open
**Created:** 2025-12-02
**Related Issues:** #10, #11

### Summary
For opportunities with status "Closed" or "Cancelled", disable the Close, Cancel, and Delete action buttons. Replace with an Archive action that hides the opportunity from the default list view. Add a "Show Archived" toggle at the top right of the opportunities list to reveal archived items.

### Requirements

#### Action Button Behavior for Closed/Cancelled
- [ ] Disable Close, Cancel, and Delete buttons for Closed/Cancelled opportunities
- [ ] Show Archive button (box icon) only for Closed/Cancelled opportunities
- [ ] Archive button always visible when applicable

#### Archive Functionality
- [ ] Add `archived` boolean field to opportunity data model
- [ ] Clicking Archive sets `archived: true`
- [ ] Archived opportunities hidden from default list view

#### Show Archived Toggle
- [ ] Add toggle/checkbox at top right of opportunities list
- [ ] Label: "Show Archived"
- [ ] When enabled, show both archived and non-archived opportunities
- [ ] Archived opportunities visually distinguished (e.g., slightly faded)

### Technical Notes
- Add `archived: false` to opportunity data model
- Update `renderOpportunities()` to filter based on archived state
- Add state for `showArchived` toggle
- Conditionally render action buttons based on opportunity status

### Acceptance Criteria
1. Closed/Cancelled opportunities show only Archive button
2. Close, Cancel, Delete buttons disabled for Closed/Cancelled
3. Clicking Archive hides opportunity from list
4. "Show Archived" toggle visible at top right of list
5. Toggle reveals archived opportunities
6. Archived opportunities visually distinguishable

---
