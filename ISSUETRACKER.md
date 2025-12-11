# Issue Tracker

Issue-18: Implemented export/import functionality to save and restore app state via JSON files with timestamped filenames.

Issue-22: Implemented todo sorting by due date (earliest first) with completed todos at bottom sorted by completion time (most recent first).
Issue-20: Implemented Tags Management feature with CRUD operations in Settings, inline tag assignment for Todos and Opportunities via autocomplete dropdown with inline creation, and colored tag pills display in list views.

Issue-24: Implemented Daily Recommendation Engine with collapsible split-panel layout on Todos page, enhanced todo data structure (priority, effort, deadline), urgency scoring algorithm (DeadlineScore + PriorityScore + StalenessBonus), daily plan generation with sections (Overdue, Must Complete Today, Recommended, If Time Permits), warnings and insights, and Planning settings in Settings page.

Issue-26: Fixed recommendation panel scrolling by removing nested scrollbar and made panel fixed width (450px) with collapse functionality removed.

Issue-28: Implemented Save button disable during inline opportunity/contact creation in todo modal. When inline forms are open, the Save button is grayed out (50% opacity) with a tooltip explaining to complete or cancel the inline form first.

Issue-30: Implemented IndexedDB state persistence with auto-save, Storage section in Settings with statistics and clear browser state functionality.

Issue-32: Improved Tab key navigation in autocomplete dropdowns. When dropdown is open with highlighted option, Tab selects the option and moves focus to next field. Updated Priority, Opportunity, Contact, Role, Tags, and Inline Contact dropdowns.

Issue-35: Fixed autocomplete dropdowns resetting to previous value when re-focusing and typing new selection by auto-highlighting first match and using filtered options list.

Issue-37: Fixed Shift+Tab navigation loop in Todo modal. Tab handlers were intercepting Shift+Tab and forcing focus forward to Tags, causing backward navigation to loop. Added `!e.shiftKey` check to all Tab key handlers so Shift+Tab navigates naturally backward through the form.

Issue-39: Added Todo description to card with two-column layout displaying description on the right side of the existing info.

Issue-41: Renamed Opportunities to Engagements throughout the application (UI labels, CSS classes, JavaScript variables/functions, state properties, HTML element IDs). Added edit button to engagement list view that opens modal in edit mode. Implemented inline editing for Name, Description, and Contact fields in side panel with auto-save on blur. Added comment deletion with delete button that appears on hover.

Issue-43: Implemented Engagement Lifecycle Management with types (engagement, pre-project, project), status lifecycle (active, completed, closed, dropped), pre-project allocation tracking with monthly percentages, project phase with timeline and formal allocations, and charge-back system for transitioning pre-project work to formal projects.

Issue-45: Refactored Todo dialog inline creation to horizontal expanding layout with two-column display, smooth CSS transitions, and proper focus management.

Issue-47: Fixed inline engagement form with textarea description, hidden contact separator line, and correct contact linking to engagement.

Issue-49: Implemented custom DateTimePicker component with side-by-side layout (time left, calendar right), keyboard navigation (arrows, Page Up/Down, Home/End, Tab, Escape), mouse wheel scrolling for months, hour/minute spinners with long-press acceleration, month/year picker overlays on hover, yellow/gold theme (#F5A623), and auto-detection of date-only vs datetime mode. Integrated with all 13 date fields.

Issue-51: Fixed Enter key on Deadline control in Todo modal to open date picker instead of closing modal by adding stopPropagation to DateTimePicker keydown handler.

Issue-53: Fixed Tags control Tab behavior to skip tag selection when no text entered, allowing natural focus movement to Save button.

Issue-55: Added expandable tooltip on Engagement Status badge showing status descriptions. Tooltip displays brief description on hover with "Read more" link to expand and show all status states (Active, Completed, Closed, Dropped) with detailed explanations. Implemented in both engagement list and side panel with appropriate positioning.

Issue-59: Implemented global search functionality with Shift+Spacebar keyboard shortcut, real-time filtering for Todos and Engagements pages, and Escape to clear search.

Issue-61: Fixed CSS injection vulnerability by validating hex color format on tag imports and IndexedDB loads.

Issue-63: Added comprehensive JSON import validation with schema sanitization, array size limits, and type/enum validation.

Issue-67: Added "Blocked" status for Todos with visual indicators, block/unblock actions, optional reason capture, and Blocked section in Daily Plan.

Issue-69: Added allocation timeline bar to Engagement list items showing monthly allocations as colored pebbles (yellow for pre-project, green for project) with month labels, percentage display, and left/right arrow scrolling for timelines with more than 6 months.

Issue-72: Extended allocation timeline bar to show 18 months at a time (up from 6), fixed pebble clipping by removing overflow constraints, scrolling appears for timelines exceeding 18 months.

Issue-74: Added Daily Load KPI chart to Todo page with 3-column layout, stacked bar visualization for Overdue/Today/Tomorrow todos, heat gradient colors, workload status messages, click-to-highlight interactivity, and completed todo tracking with remaining hours display.

Issue-76: Added Work Calendar system with configurable work days (Mon-Fri default, 8hrs each), variable hours per day, holidays and PTO management. DateTimePicker now disables non-work days (grayed out, unselectable). Daily Load "Tomorrow" column renamed to "Next Day" showing next available work day with dynamic label. Introduced app versioning (v1.0.0) with VERSION.md, data migration for todos with deadlines on disabled days (moved to next work day), and What's New modal shown on upgrade.

Issue-78: Added "Minimal Work" effort level (30 min), updated "Very Low" to 1 hour, bumped app to v1.1.0 with migration converting existing very_low todos to minimal.

Issue-80: Introduced Meetings feature with new entity type (title, description, date, duration), Shift+M keyboard shortcut to create meetings on Todo's page, dedicated Meetings list section below Daily Load showing upcoming meetings grouped by Today/Tomorrow/Date, integration with Daily Load KPI (purple color coding), IndexedDB persistence, and bumped app to v1.2.0.

Issue-82: Added Conflict Detection Modal for Calendar Exclusions - when adding holidays, PTO, or disabling work days, detects conflicting todos and meetings with options to move to next work day or delete, bumped app to v1.3.0.

Issue-85: Fixed deadline date not populating when editing existing todo by using DateTimePicker's setValue API instead of direct input value assignment.

Issue-86: Fixed todo list sorting to use deadline field instead of legacy dueDate for proper chronological ordering.

Issue-64: Implemented configurable Logger utility with debug toggle in Settings to suppress console output in production mode.

Issue-62: Replaced Math.random() with crypto.getRandomValues() for cryptographically secure ID generation.
