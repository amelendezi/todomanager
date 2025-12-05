# Issue Tracker

Issue-18: Implemented export/import functionality to save and restore app state via JSON files with timestamped filenames.

Issue-22: Implemented todo sorting by due date (earliest first) with completed todos at bottom sorted by completion time (most recent first).
Issue-20: Implemented Tags Management feature with CRUD operations in Settings, inline tag assignment for Todos and Opportunities via autocomplete dropdown with inline creation, and colored tag pills display in list views.

Issue-24: Implemented Daily Recommendation Engine with collapsible split-panel layout on Todos page, enhanced todo data structure (priority, effort, deadline), urgency scoring algorithm (DeadlineScore + PriorityScore + StalenessBonus), daily plan generation with sections (Overdue, Must Complete Today, Recommended, If Time Permits), warnings and insights, and Planning settings in Settings page.

Issue-26: Fixed recommendation panel scrolling by removing nested scrollbar and made panel fixed width (450px) with collapse functionality removed.

Issue-28: Implemented Save button disable during inline opportunity/contact creation in todo modal. When inline forms are open, the Save button is grayed out (50% opacity) with a tooltip explaining to complete or cancel the inline form first.

Issue-30: Implemented IndexedDB state persistence with auto-save, Storage section in Settings with statistics and clear browser state functionality.

Issue-32: Improved Tab key navigation in autocomplete dropdowns. When dropdown is open with highlighted option, Tab selects the option and moves focus to next field. Updated Priority, Opportunity, Contact, Role, Tags, and Inline Contact dropdowns.
