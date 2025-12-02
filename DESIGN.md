# Design System

This document outlines the design principles, visual language, and interaction patterns for the TodoManager application.

## Color Palette

### Primary Colors
- **Yellow/Gold**: `#FFB800` - Primary action color (Export button, add button, highlights)
- **White**: `#FFFFFF` - Card backgrounds, main content areas
- **Light Gray**: `#F5F5F5` - Page background, subtle borders

### Semantic Colors
- **Green**: `#00A86B` - Success, Low Hanging Fruit category
- **Yellow**: `#FFB800` - Transformation Anchor category
- **Purple**: `#7B2CBF` - Tactical Utility category
- **Red**: `#DC3545` - Containment Liability category

### Text Colors
- **Primary Text**: `#1F1F1F` - Headers, main content
- **Secondary Text**: `#6C757D` - Subtitles, descriptions
- **Muted Text**: `#ADB5BD` - Placeholders, disabled states

### UI Elements
- **Border**: `#E0E0E0` - Table borders, dividers
- **Hover**: `#F8F9FA` - Row hover states
- **Focus**: `#FFB800` with 20% opacity - Input focus rings

## Typography

### Font Family
- Primary: System font stack (`-apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif`)

### Font Sizes
- **Navigation**: 16px, medium weight
- **Page Title**: 24px, bold
- **Section Header**: 20px, semi-bold
- **Body Text**: 14px, regular
- **Table Headers**: 12px, uppercase, semi-bold, letter-spacing: 0.5px
- **Small Text**: 12px, regular

### Font Weights
- Regular: 400
- Medium: 500
- Semi-bold: 600
- Bold: 700

## Layout

### Spacing System (8px base unit)
- **xs**: 4px
- **sm**: 8px
- **md**: 16px
- **lg**: 24px
- **xl**: 32px
- **2xl**: 48px
- **3xl**: 64px

### Container
- Max width: 1200px
- Padding: 32px horizontal, 24px vertical
- Centered with auto margins

### Cards
- Background: White
- Border radius: 16px
- Box shadow: `0 2px 8px rgba(0, 0, 0, 0.08)`
- Padding: 24px

### Grid System
- Portfolio cards: 4 columns on desktop, 2 on tablet, 1 on mobile
- Gap: 24px

## Components

### Navigation
- **Style**: Horizontal tab navigation
- **Height**: 60px
- **Background**: White with subtle shadow
- **Active State**: Underline or bold text
- **Hover**: Slight opacity change (0.7)
- **Transition**: `color 0.2s ease`

### Buttons

#### Primary Button (Export)
- Background: `#FFB800`
- Color: `#1F1F1F`
- Padding: 10px 20px
- Border radius: 8px
- Font weight: 600
- Icon: Download icon on left
- Hover: Darken by 10%, transform scale(1.02)
- Transition: `all 0.2s ease`

#### Icon Buttons (Actions)
- Size: 32px × 32px
- Border radius: 6px
- Background: Transparent
- Hover: `#F8F9FA` background
- Transition: `background-color 0.15s ease`
- Icons: Plus, Edit, Delete

#### Floating Action Button (Add)
- Size: 56px × 56px
- Background: `#FFB800`
- Border radius: 50%
- Position: Fixed or inline
- Icon: Plus
- Box shadow: `0 4px 12px rgba(255, 184, 0, 0.3)`
- Hover: Scale(1.1), increase shadow
- Transition: `all 0.3s cubic-bezier(0.4, 0, 0.2, 1)`

#### Call-to-Action Button
- Background: `#FFB800`
- Color: `#1F1F1F`
- Padding: 12px 24px
- Border radius: 8px
- Icon: Arrow or plus on left
- Hover: Transform scale(1.05)
- Transition: `all 0.2s ease`

### Search Bar
- Height: 48px
- Border: 1px solid `#E0E0E0`
- Border radius: 8px
- Background: White
- Padding: 12px 16px
- Icon: Search icon (magnifying glass) on left
- Placeholder: "Search all fields..."
- Focus: Border color `#FFB800`, box-shadow with yellow tint
- Transition: `border-color 0.2s ease, box-shadow 0.2s ease`

### Tables
- **Header Background**: `#F8F9FA`
- **Header Text**: 12px, uppercase, semi-bold, `#6C757D`
- **Row Height**: 56px
- **Row Border**: 1px solid `#E0E0E0`
- **Hover**: Background `#F8F9FA`, slide-in effect for action buttons
- **Cell Padding**: 16px
- **Transition**: `background-color 0.2s ease`

### Portfolio Cards
- **Size**: Equal height, responsive width
- **Background**: White
- **Border**: 3px solid (color based on category)
- **Border Radius**: 12px
- **Padding**: 24px
- **Icon**: 48px × 48px, colored background matching border
- **Number**: Large (48px), bold
- **Label**: Small (14px), category text
- **Hover**: Scale(1.03), increase shadow
- **Transition**: `all 0.3s ease`

### Info Cards (Yellow bordered)
- **Background**: `#FFFBF0`
- **Border-left**: 4px solid `#FFB800`
- **Border Radius**: 8px
- **Padding**: 20px
- **Title**: Bold, 16px, with yellow bullet point
- **List Items**: 14px with yellow arrow bullets
- **Spacing**: 8px between items

### Status Indicators
- **Size**: 12px circle
- **Colors**: Match semantic categories
- **Inline**: Displayed next to text labels
- **Transition**: Fade in `0.3s ease`

### Settings Icon
- **Size**: 24px
- **Color**: `#6C757D`
- **Hover**: Rotate 90deg, color change to `#1F1F1F`
- **Transition**: `transform 0.3s ease, color 0.2s ease`

## Animations & Transitions

### Timing Functions
- **Ease**: General purpose `ease`
- **Ease In Out**: For scales and transforms `ease-in-out`
- **Cubic Bezier**: For sophisticated animations `cubic-bezier(0.4, 0, 0.2, 1)`

### Animation Types

#### Fade In
```
opacity: 0 → 1
duration: 0.3s
timing: ease
```

#### Slide Up
```
transform: translateY(20px) → translateY(0)
opacity: 0 → 1
duration: 0.4s
timing: ease-out
```

#### Slide In (Actions)
```
transform: translateX(10px) → translateX(0)
opacity: 0 → 1
duration: 0.2s
timing: ease
```

#### Scale
```
transform: scale(1) → scale(1.03)
duration: 0.3s
timing: ease
```

#### Hover Effects
- Buttons: Scale(1.02-1.05), 0.2s
- Cards: Scale(1.03), shadow increase, 0.3s
- Icons: Rotate or color change, 0.2-0.3s
- Table rows: Background fade, action buttons slide in, 0.15-0.2s

#### Loading States
- Skeleton screens with shimmer effect
- Pulse animation: `opacity: 1 → 0.5 → 1`, 1.5s infinite

### Page Transitions
- Route changes: Fade in new content, 0.3s
- Modal/Dialog: Fade background + scale content from 0.95 to 1, 0.3s

## Interaction Patterns

### Search
- Focus: Border highlight with yellow
- Clear button appears when text entered (fade in)
- Live filtering with debounce (300ms)

### Table Interactions
- Row hover: Background change + action buttons slide in from right
- Sortable columns: Cursor pointer, arrow icon rotates
- Click row: Navigate to detail (optional)

### Add/Create Flow
- Click floating action button
- Modal/drawer slides up from bottom or right
- Form appears with fade in
- Submit: Loading state, then success message (slide down from top)

### Empty States
- Large icon (64px)
- Title + description
- Call-to-action button
- All content fade in on load

### Feedback
- **Success**: Green toast/banner, slide down from top, auto-dismiss in 3s
- **Error**: Red toast/banner, slide down from top, manual dismiss
- **Info**: Blue toast/banner
- **Loading**: Spinner or skeleton with pulse animation

## Responsive Behavior

### Breakpoints
- **Mobile**: < 768px
- **Tablet**: 768px - 1024px
- **Desktop**: > 1024px

### Mobile Adaptations
- Navigation: Convert to hamburger menu or bottom tabs
- Tables: Convert to card list view
- Multi-column layouts: Stack to single column
- Search: Full width
- Floating action button: Bottom right, 16px margin
- Reduced padding: 16px instead of 24-32px

### Touch Interactions
- Increase tap targets to minimum 44px × 44px
- Add visual feedback (ripple effect)
- Swipe gestures for table row actions

## Accessibility

### Focus States
- Visible focus ring: 2px solid `#FFB800`
- Focus order: Logical tab sequence
- Skip links for navigation

### Color Contrast
- Text on white: Minimum 4.5:1 ratio
- Text on colored backgrounds: Minimum 4.5:1 ratio
- Icon-only buttons: Include aria-labels

### Motion
- Respect prefers-reduced-motion
- Provide option to disable animations

## Icons

### Icon Library
- Use consistent icon set (e.g., Heroicons, Lucide, or Material Icons)
- Size: 20px (default), 24px (larger actions), 16px (inline)
- Stroke width: 2px
- Color: Inherit from parent or semantic color

### Common Icons
- Search: Magnifying glass
- Add: Plus
- Edit: Pencil
- Delete: Trash
- Export: Download
- Settings: Gear
- Check: Checkmark
- Warning: Triangle with exclamation

## Best Practices

1. **Consistency**: Use the same spacing, colors, and patterns throughout
2. **Feedback**: Provide immediate visual feedback for all interactions
3. **Progressive Disclosure**: Show information when needed, avoid clutter
4. **Loading States**: Always show loading indicators for async operations
5. **Error Prevention**: Use validation and confirmations for destructive actions
6. **Mobile First**: Design for small screens, enhance for larger ones
7. **Performance**: Optimize animations, use CSS transforms over position changes
8. **Accessibility**: Keyboard navigation, screen reader support, sufficient contrast
