# Email Scouting Tool - Specification

## Concept & Vision
A sleek, professional email scouting dashboard that helps users manage email campaigns efficiently. The tool feels like a command center for outreach—organized, purposeful, and satisfying to use. Dark theme with accent colors creates focus and reduces eye strain during extended use.

## Design Language

### Aesthetic Direction
Modern SaaS dashboard aesthetic—think Linear or Notion meets email marketing tools. Clean, data-dense but not cluttered.

### Color Palette
- **Primary**: `#6366f1` (Indigo - actions, links)
- **Secondary**: `#22c55e` (Green - success, sent emails)
- **Accent**: `#f59e0b` (Amber - pending/hover states)
- **Background**: `#0f172a` (Dark slate)
- **Surface**: `#1e293b` (Elevated cards)
- **Border**: `#334155` (Subtle borders)
- **Text Primary**: `#f8fafc`
- **Text Secondary**: `#94a3b8`

### Typography
- Font: Inter (Google Fonts) with system fallbacks
- Headings: Bold, tracking tight
- Body: Regular weight, comfortable line height

### Motion Philosophy
- Subtle transitions (150-200ms) on all interactive elements
- Progress bar animates smoothly
- Hover states lift cards slightly with shadow

## Layout & Structure

### Page Structure
1. **Header**: Logo, title, progress summary
2. **Main Content** (two-column on desktop):
   - Left: Email input section + message composer
   - Right: Email list with status indicators
3. **Progress Footer**: Visual progress bar with stats

### Responsive Strategy
- Mobile: Single column, stacked sections
- Desktop: Two-column layout with fixed right panel

## Features & Interactions

### 1. Email Input
- **Textarea paste**: Large input area for pasting emails (one per line)
- **File upload**: Drag-drop or click to upload .txt/.csv files
- Parse emails with regex validation
- Invalid emails highlighted in red
- "Add Emails" button processes input

### 2. Email List Display
- Numbered list (1, 2, 3...)
- Each email shows: number, email address, status badge
- Status colors:
  - Gray: Not clicked yet
  - Indigo: Hovered/selected
  - Green: Message sent
  - Amber: In progress
- Click email → opens mailto: link with subject/body pre-filled

### 3. Message Composer
- **Subject line**: Single input field
- **Body**: Large textarea with placeholder text
- Variables: Support {{email}} placeholder replacement
- Save message draft to localStorage

### 4. Progress Tracking
- Progress bar showing sent/total
- Stats: "X of Y emails contacted"
- Percentage indicator
- Clear all button with confirmation

### 5. Persistence (localStorage)
- Save email list with statuses
- Save message draft (subject + body)
- Auto-load on page refresh
- Manual clear data option

## Component Inventory

### EmailInput Section
- Textarea with placeholder instructions
- File drop zone with dashed border
- Parse button with loading state
- Error message display

### EmailList Item
- States: default, hover, clicked/sent, selected
- Number badge, email text, status dot
- Hover: slight scale, shadow lift

### MessageComposer
- Subject input with label
- Body textarea resizable
- Character count
- Save draft indicator

### ProgressBar
- Animated fill
- Fraction display (12/50)
- Percentage badge

## Technical Approach
- Single HTML file with embedded CSS and JavaScript
- No framework dependencies
- localStorage API for persistence
- Mailto: protocol for email launching
- FileReader API for file uploads
- Regex for email validation
