# TaskMover UI Mockups and Component Reference

## Main Application Layout

### Primary Application Window
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ TaskMover                                              [─] [□] [×]          │
├─────────────────────────────────────────────────────────────────────────────┤
│ File  Edit  View  Tools  Help                                              │
├─────────────────────────────────────────────────────────────────────────────┤
│ [🏠] [📁] [⚙️] [📝] [📊]     Search: [________________] [🔍]    [👤] Profile │
├─────────────────────────────────────────────────────────────────────────────┤
│ ┌─────────────────┐ ┌─────────────────────────────────────────────────────┐ │
│ │                 │ │                                                     │ │
│ │   SIDEBAR       │ │               MAIN CONTENT AREA                     │ │
│ │                 │ │                                                     │ │
│ │  📁 Dashboard   │ │  ┌─ Patterns ─┐ ┌─ Rules ─┐ ┌─ Rulesets ─┐        │ │
│ │  📋 Patterns    │ │  │             │ │          │ │            │        │ │
│ │  📏 Rules       │ │  │   Content   │ │ Content  │ │  Content   │        │ │
│ │  📦 Rulesets    │ │  │    Area     │ │   Area   │ │   Area     │        │ │
│ │  ⚡ Execute     │ │  │             │ │          │ │            │        │ │
│ │  📈 History     │ │  └─────────────┘ └──────────┘ └────────────┘        │ │
│ │  ⚙️  Settings   │ │                                                     │ │
│ │  ❓ Help        │ │                                                     │ │
│ │                 │ │                                                     │ │
│ └─────────────────┘ └─────────────────────────────────────────────────────┘ │
├─────────────────────────────────────────────────────────────────────────────┤
│ Ready │ 0 patterns │ 0 rules │ 0 rulesets │ Last run: Never    [📊] Status │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Requirements:**
- Responsive layout adapting to window size
- Collapsible sidebar (150px min, 300px max)
- Tab system for main content
- Status bar with real-time information
- Modern toolbar with icon buttons
- Global search functionality

**Features:**
- Window state persistence
- Theme switching capability
- Keyboard navigation support
- Drag and drop between panels
- Context-sensitive help

## Navigation Components

### Sidebar Navigation
```
┌─────────────────┐
│ NAVIGATION      │
├─────────────────┤
│ 🏠 Dashboard    │ ← Active state (highlighted)
│ 📋 Patterns     │
│   └ 📝 Library  │ ← Nested items
│   └ ➕ New      │
│ 📏 Rules        │
│   └ 📃 All      │
│   └ ⚡ Active   │
│   └ 🚫 Disabled │
│ 📦 Rulesets     │
│   └ 📋 All      │
│   └ 🏷️  Tagged  │
│ ⚡ Execute      │
│ 📈 History      │
│   └ 📊 Stats    │
│   └ 📜 Logs     │
│ ⚙️  Settings    │
│ ❓ Help         │
│                 │
│ [◀] Collapse    │ ← Collapse button
└─────────────────┘
```

**Requirements:**
- Hierarchical menu structure
- Visual state indicators
- Hover effects and animations
- Badge notifications for status
- Keyboard navigation (arrows, enter)

**Features:**
- Menu item search/filter
- Custom icon support
- Dynamic menu generation
- Context menus on right-click
- Collapsible sections

### Toolbar Component
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ [🏠] [📁] [⚙️] [📝] [📊] │ [↶] [↷] │ [📋] [📋+] [📏] [⚡] │ [🔍] [❓] [⚙️] │
│ Home File  Set  New Stats│ Undo Redo│ Copy  New  Rules Run │Search Help Set │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Requirements:**
- Icon buttons with text labels
- Button groups with separators
- Disabled state visualization
- Tooltips on hover
- Responsive overflow menu

**Features:**
- Customizable button layout
- Quick action access
- Keyboard shortcuts display
- Loading states for operations
- Badge notifications

## Data Display Components

### Pattern Library View

#### Grid View (Default)
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ Pattern Library                                           [+ New Pattern]   │
├─────────────────────────────────────────────────────────────────────────────┤
│ Search: [_______________] Category: [All ▼] Status: [All ▼] Sort: [Name ▼]  │
│                                                   View: [📱 Grid] [📋 Table] │
├─────────────────────────────────────────────────────────────────────────────┤
│ ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐               │
│ │ Documents       │ │ Images          │ │ Code Files      │               │
│ │ *.pdf,*.doc     │ │ *.jpg,*.png     │ │ *.py,*.js       │               │
│ │ 📊 Used in 3    │ │ 📊 Used in 1    │ │ 📊 Not used     │               │
│ │ [✏️] [📋] [🗑️]   │ │ [✏️] [📋] [🗑️]   │ │ [✏️] [📋] [🗑️]   │               │
│ └─────────────────┘ └─────────────────┘ └─────────────────┘               │
│                                                                             │
│ ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐               │
│ │ Archives        │ │ Videos          │ │ + Add Pattern   │               │
│ │ *.zip,*.rar     │ │ *.mp4,*.avi     │ │                 │               │
│ │ 📊 Used in 2    │ │ 📊 Used in 1    │ │   Click to      │               │
│ │ [✏️] [📋] [🗑️]   │ │ [✏️] [📋] [🗑️]   │ │   create new    │               │
│ └─────────────────┘ └─────────────────┘ └─────────────────┘               │
├─────────────────────────────────────────────────────────────────────────────┤
│ 6 patterns total │ 4 active │ 2 unused                    [◀ 1 2 3 ▶]     │
└─────────────────────────────────────────────────────────────────────────────┘
```

#### Table View (Alternative)
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ Pattern Library                                           [+ New Pattern]   │
├─────────────────────────────────────────────────────────────────────────────┤
│ Search: [_______________] Category: [All ▼] Status: [All ▼] Sort: [Name ▼]  │
│                                                   View: [📱 Grid] [📋 Table] │
├─────────────────────────────────────────────────────────────────────────────┤
│ ┌───┬─────────────────┬─────────────────┬─────────────┬─────────┬─────────┐ │
│ │ ☐ │ Name            │ Pattern         │ Category    │ Used In │ Actions │ │
│ ├───┼─────────────────┼─────────────────┼─────────────┼─────────┼─────────┤ │
│ │ ☐ │ Documents       │ *.pdf,*.doc     │ Office      │   3     │ [✏️📋🗑️] │ │
│ │ ☐ │ Images          │ *.jpg,*.png     │ Media       │   1     │ [✏️📋🗑️] │ │
│ │ ☐ │ Code Files      │ *.py,*.js       │ Development │   0     │ [✏️📋🗑️] │ │
│ │ ☐ │ Archives        │ *.zip,*.rar     │ Compressed  │   2     │ [✏️📋🗑️] │ │
│ │ ☐ │ Videos          │ *.mp4,*.avi     │ Media       │   1     │ [✏️📋🗑️] │ │
│ └───┴─────────────────┴─────────────────┴─────────────┴─────────┴─────────┘ │
│                                                                             │
│ [☑️ Select All] [Enable Selected] [Disable Selected] [Delete Selected]      │
├─────────────────────────────────────────────────────────────────────────────┤
│ 6 patterns total │ 4 active │ 2 unused                    [◀ 1 2 3 ▶]     │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Requirements:**
- Card-based layout with hover effects (Grid view)
- Sortable table with column headers (Table view)
- View toggle with smooth transitions between layouts
- Multi-criteria filtering and sorting in both views
- Usage statistics display
- Bulk selection and operations
- Pagination for large sets
- Consistent data presentation across both views

**Features:**
- Drag and drop reordering (both views)
- Quick preview on hover (Grid view)
- Inline editing capability (Table view)
- Right-click context menus
- Tag-based organization
- Export/import functionality
- User preference persistence for view mode
- Responsive grid columns that adapt to screen size

### Rule Management Interface

#### Table View (Default)
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ Rules                                                      [+ New Rule]     │
├─────────────────────────────────────────────────────────────────────────────┤
│ [🔍 Search rules...] [All ▼] [Active ▼] [Priority ▼]    View: [📋 Table] [📱 Grid] │
├─────────────────────────────────────────────────────────────────────────────┤
│ ┌───┬────────────────────────────────────────────────────────────────────┐   │
│ │ ↕ │ Priority │ Name        │ Pattern     │ Destination │ Status │ Used │   │
│ ├───┼──────────┼─────────────┼─────────────┼─────────────┼────────┼──────┤   │
│ │ ⠿ │    1     │ Documents   │ Documents   │ ~/Docs/     │  ✅ ON │  3   │   │
│ │ ⠿ │    2     │ Images      │ Images      │ ~/Pictures/ │  ✅ ON │  2   │   │
│ │ ⠿ │    3     │ Downloads   │ Downloads   │ ~/Downloads/│  🚫 OFF│  1   │   │
│ │ ⠿ │    4     │ Archives    │ Archives    │ ~/Archives/ │  ✅ ON │  1   │   │
│ └───┴──────────┴─────────────┴─────────────┴─────────────┴────────┴──────┘   │
│                                                                             │
│ [☑️ Select All] [Enable Selected] [Disable Selected] [Delete Selected]      │
├─────────────────────────────────────────────────────────────────────────────┤
│ 4 rules │ 3 active │ 1 inactive                         [◀ 1 ▶]           │
└─────────────────────────────────────────────────────────────────────────────┘
```

#### Grid View (Alternative)
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ Rules                                                      [+ New Rule]     │
├─────────────────────────────────────────────────────────────────────────────┤
│ [🔍 Search rules...] [All ▼] [Active ▼] [Priority ▼]    View: [📋 Table] [📱 Grid] │
├─────────────────────────────────────────────────────────────────────────────┤
│ ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐               │
│ │ 1️⃣ Documents    │ │ 2️⃣ Images       │ │ 3️⃣ Downloads    │               │
│ │ Pattern: Office │ │ Pattern: Media  │ │ Pattern: All    │               │
│ │ → ~/Documents/  │ │ → ~/Pictures/   │ │ → ~/Downloads/  │               │
│ │ ✅ Active       │ │ ✅ Active       │ │ 🚫 Inactive     │               │
│ │ 📊 Used in 3    │ │ 📊 Used in 2    │ │ 📊 Used in 1    │               │
│ │ [✏️] [🔄] [🗑️]   │ │ [✏️] [🔄] [🗑️]   │ │ [✏️] [🔄] [🗑️]   │               │
│ │      ⠿↕         │ │      ⠿↕         │ │      ⠿↕         │               │
│ └─────────────────┘ └─────────────────┘ └─────────────────┘               │
│                                                                             │
│ ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐               │
│ │ 4️⃣ Archives     │ │ + Add Rule      │ │                 │               │
│ │ Pattern: Compress│ │                │ │                 │               │
│ │ → ~/Archives/   │ │   Click to      │ │                 │               │
│ │ ✅ Active       │ │   create new    │ │                 │               │
│ │ 📊 Used in 1    │ │   rule          │ │                 │               │
│ │ [✏️] [🔄] [🗑️]   │ │                 │ │                 │               │
│ │      ⠿↕         │ │                 │ │                 │               │
│ └─────────────────┘ └─────────────────┘ └─────────────────┘               │
│                                                                             │
│ [☑️ Select All] [Enable Selected] [Disable Selected] [Delete Selected]      │
├─────────────────────────────────────────────────────────────────────────────┤
│ 4 rules │ 3 active │ 1 inactive                         [◀ 1 ▶]           │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Requirements:**
- Sortable table with drag handles (Table view)
- Card-based layout with priority indicators (Grid view)
- View toggle with smooth transitions between layouts
- Multi-selection with checkboxes in both views
- Status indicators and toggles
- Inline editing capability (Table view)
- Visual priority display (Grid view)
- Batch operations toolbar
- Consistent data presentation across both views

**Features:**
- Priority visualization with drag-and-drop reordering
- Rule conflict detection and warnings
- Usage analytics and statistics
- Rule templates and quick creation
- Export to various formats
- User preference persistence for view mode
- Visual status indicators (active/inactive)
- Quick action buttons in both views

### Pattern Editor Dialog
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ Edit Pattern: Documents                                        [×]          │
├─────────────────────────────────────────────────────────────────────────────┤
│ ┌─ Pattern Details ──────────────────────────────────────────────────────┐  │
│ │ Name: [Documents                                                      ] │  │
│ │ Description: [Office documents and PDFs                              ] │  │
│ │                                                                        │  │
│ │ Pattern Type: [●] Glob  [○] Regex  [○] Advanced                       │  │
│ │ Pattern: [*.pdf,*.doc,*.docx,*.xls,*.xlsx,*.ppt,*.pptx             ] │  │
│ │                                                                        │  │
│ │ Case Sensitive: [○] Yes  [●] No                                        │  │
│ │ Include Hidden Files: [○] Yes  [●] No                                  │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│ ┌─ Pattern Testing ──────────────────────────────────────────────────────┐  │
│ │ Test Files: [Browse Folder...] [Clear]                                │  │
│ │                                                                        │  │
│ │ ✅ report.pdf        (matches)                                         │  │
│ │ ✅ document.docx     (matches)                                         │  │
│ │ ❌ image.jpg         (no match)                                        │  │
│ │ ✅ spreadsheet.xlsx  (matches)                                         │  │
│ │ ❌ video.mp4         (no match)                                        │  │
│ │                                                                        │  │
│ │ Matches: 3/5 files (60%)                                               │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│ ┌─ Advanced Options ─────────────────────────────────────────────────────┐  │
│ │ File Size: [Any ▼] Min: [____] Max: [____] KB/MB/GB                   │  │
│ │ Date Modified: [Any ▼] From: [________] To: [________]                 │  │
│ │ File Attributes: [☐] Read-only [☐] Hidden [☐] System                  │  │
│ │                                                                        │  │
│ │ Tags: [office] [work] [important] [+ Add Tag]                          │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│ [Test Pattern] [Save as Template] [Cancel] [Save]                          │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Requirements:**
- Multi-section collapsible layout
- Real-time pattern validation
- File browser integration
- Visual match indicators
- Form validation and feedback

**Features:**
- Syntax highlighting for patterns
- Auto-completion for common patterns
- Pattern explanation tooltips
- Save as template functionality
- Undo/redo for changes

## File Organization Components

### Organization Dashboard
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ Organization Dashboard                                                      │
├─────────────────────────────────────────────────────────────────────────────┤
│ ┌─ Quick Start ──────────────────────────────────────────────────────────┐  │
│ │ Source Folder: [C:\Users\Downloads            ] [📁]                  │  │
│ │ Ruleset:      [Work Files                   ▼] [⚙️]                  │  │
│ │                                                                        │  │
│ │ [🔍 Preview] [⚡ Start Organization] [⏸️ Schedule]                      │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│ ┌─ Recent Activity ──────────────────────────────────────────────────────┐  │
│ │ 📊 Today: 45 files organized, 3 conflicts resolved                    │  │
│ │                                                                        │  │
│ │ 🕐 2 minutes ago: 25 files moved to Documents                         │  │
│ │ 🕐 5 minutes ago: 12 images organized to Pictures                     │  │
│ │ 🕐 10 minutes ago: 3 conflicts resolved manually                      │  │
│ │ 🕐 1 hour ago: Ruleset "Media Files" executed                         │  │
│ │                                                                        │  │
│ │ [View Complete History] [Export Report]                               │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│ ┌─ Statistics ───────────────────────────────────────────────────────────┐  │
│ │ This Week:     📁 156 files   ⚡ 8 runs   ⏱️ 45min saved            │  │
│ │ This Month:    📁 672 files   ⚡ 34 runs  ⏱️ 3.2hrs saved           │  │
│ │ All Time:      📁 2,341 files ⚡ 89 runs  ⏱️ 12hrs saved            │  │
│ │                                                                        │  │
│ │ [📊 Detailed Statistics] [🎯 Effectiveness Report]                     │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Requirements:**
- Clean dashboard layout with cards
- Real-time activity updates
- Visual statistics display
- Quick action buttons
- Recent activity timeline

**Features:**
- Customizable dashboard widgets
- Activity filtering and search
- Statistics visualization charts
- Export reports functionality
- Scheduled operations management

### File Conflict Resolution Dialog
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ File Conflict Resolution                                       [×]          │
├─────────────────────────────────────────────────────────────────────────────┤
│ A file with this name already exists at the destination.                   │
│                                                                             │
│ ┌─ Source File ──────────────────────┐ ┌─ Destination File ──────────────┐ │
│ │ 📄 presentation.pptx                │ │ 📄 presentation.pptx             │ │
│ │ 📁 C:\Downloads\                    │ │ 📁 C:\Documents\Work\            │ │
│ │ 📅 Modified: Today 2:30 PM          │ │ 📅 Modified: Yesterday 4:15 PM   │ │
│ │ 📏 Size: 2.5 MB                     │ │ 📏 Size: 2.1 MB                  │ │
│ │ [🔍 Preview]                        │ │ [🔍 Preview]                     │ │
│ └─────────────────────────────────────┘ └──────────────────────────────────┘ │
│                                                                             │
│ ┌─ Resolution Options ───────────────────────────────────────────────────┐  │
│ │ [●] Rename source: presentation (1).pptx                               │  │
│ │ [○] Overwrite destination (⚠️ This will replace the existing file)     │  │
│ │ [○] Skip this file                                                     │  │
│ │ [○] Custom name: [________________________]                            │  │
│ │                                                                        │  │
│ │ [☑️] Apply this action to similar conflicts (3 remaining)              │  │
│ │ [☐] Remember this choice for this file type                            │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│ [⏮️ Previous] [Skip All] [Apply] [Cancel] [⏭️ Next (3 remaining)]           │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Requirements:**
- Side-by-side file comparison
- Visual file information display
- Multiple resolution options
- Batch operation controls
- Clear action buttons

**Features:**
- File preview thumbnails
- Difference highlighting
- Auto-resolve similar conflicts
- Custom resolution rules
- Operation history tracking

## Advanced UI Components

### Settings Management Interface
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ Settings                                                           [×]      │
├─────────────────────────────────────────────────────────────────────────────┤
│ ┌───────────────┐ ┌─────────────────────────────────────────────────────┐   │
│ │ General       │ │ 🔍 [Search settings...]                              │   │
│ │ Appearance    │ ├─────────────────────────────────────────────────────┤   │
│ │ File Ops      │ │ File Organization                                   │   │
│ │ Rules         │ │                                                     │   │
│ │ Patterns      │ │ Default conflict resolution:                        │   │
│ │ Performance   │ │ [Ask user ▼]                                        │   │
│ │ Advanced      │ │                                                     │   │
│ │ Privacy       │ │ Default operation mode:                             │   │
│ │ Updates       │ │ [○] Move files  [●] Copy files                      │   │
│ │ Plugins       │ │                                                     │   │
│ │               │ │ File handling:                                      │   │
│ │ [Import...]   │ │ [☑️] Create backups before operations               │   │
│ │ [Export...]   │ │ [☑️] Verify file integrity after operations         │   │
│ │ [Reset All]   │ │ [☐] Process hidden files                            │   │
│ │               │ │ [☑️] Follow symbolic links                          │   │
│ └───────────────┘ │                                                     │   │
│                   │ Notification preferences:                           │   │
│                   │ [☑️] Show completion notifications                   │   │
│                   │ [☑️] Show error notifications                        │   │
│                   │ [☐] Play sound on completion                        │   │
│                   │                                                     │   │
│                   │ [Restore Defaults] [Apply] [Cancel] [OK]            │   │
│                   └─────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Requirements:**
- Category-based organization
- Search functionality across settings
- Various input control types
- Settings validation and feedback
- Import/export capabilities

**Features:**
- Settings profiles management
- Advanced settings mode
- Contextual help for each setting
- Settings backup and restore
- Real-time preview of changes

### Progress and Status Components

#### Progress Dialog
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ Organizing Files...                                            [×]          │
├─────────────────────────────────────────────────────────────────────────────┤
│ Overall Progress:                                                           │
│ [████████████████████████████████████████              ] 68% (68/100)      │
│                                                                             │
│ Current Operation:                                                          │
│ Moving: presentation.pptx → Documents/Work/                                 │
│                                                                             │
│ Time Elapsed: 00:02:15    Estimated Remaining: 00:01:25                    │
│ Transfer Speed: 2.3 MB/s  Files/sec: 1.2                                   │
│                                                                             │
│ ┌─ Recent Activity ──────────────────────────────────────────────────────┐  │
│ │ ✅ report.pdf → Documents/                                             │  │
│ │ ✅ image.jpg → Pictures/                                               │  │
│ │ ✅ video.mp4 → Media/Videos/                                           │  │
│ │ ⚠️  conflict: presentation.pptx (resolved: renamed)                    │  │
│ │ ➡️ processing: spreadsheet.xlsx                                         │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│ [⏸️ Pause] [⏹️ Stop] [🔙 Background] [📊 Details]                            │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Requirements:**
- Real-time progress visualization
- Detailed operation information
- Activity log with status icons
- Control buttons for operation
- Performance metrics display

**Features:**
- Estimated time calculation
- Background operation mode
- Detailed operation logs
- Error recovery options
- Operation statistics

#### Notification System
```
┌─ Notifications ─────────────────────────────────────────────────────────────┐
│ ┌─────────────────────────────────────────────────────────────────────────┐ │
│ │ ✅ Organization Complete                                    [×]   2m ago │ │
│ │ Successfully organized 45 files in 'Downloads' folder.                 │ │
│ │ [View Details] [Run Again]                                              │ │
│ └─────────────────────────────────────────────────────────────────────────┘ │
│                                                                             │
│ ┌─────────────────────────────────────────────────────────────────────────┐ │
│ │ ⚠️ Conflicts Detected                                       [×]   5m ago │ │
│ │ 3 file conflicts require your attention.                               │ │
│ │ [Resolve Now] [View Details]                                            │ │
│ └─────────────────────────────────────────────────────────────────────────┘ │
│                                                                             │
│ ┌─────────────────────────────────────────────────────────────────────────┐ │
│ │ ℹ️ New Pattern Suggestions                                  [×]  15m ago │ │
│ │ Found patterns that could improve your rules.                           │ │
│ │ [Review Suggestions] [Dismiss]                                          │ │
│ └─────────────────────────────────────────────────────────────────────────┘ │
│                                                                             │
│ [Clear All] [Settings]                                                     │
└─────────────────────────────────────────────────────────────────────────────┘
```

**Requirements:**
- Toast-style notifications
- Multiple notification types
- Action buttons in notifications
- Notification history
- Auto-dismiss timing

**Features:**
- Priority-based stacking
- Sound notifications
- Rich content support
- Notification grouping
- Custom notification rules

## Component Feature Specifications

### Interactive Elements

#### Drag and Drop Zones
- **Visual States**: Default, drag-over, drag-active, disabled
- **Drop Feedback**: Highlight drop zones, show insertion points
- **Drag Preview**: Semi-transparent ghost of dragged item
- **Constraints**: Type checking, validation, restricted zones

#### Multi-Selection
- **Selection Methods**: Click, Ctrl+click, Shift+click, rectangular selection
- **Visual Indicators**: Checkboxes, highlighted rows, selection count
- **Batch Operations**: Toolbar appears with selected items
- **Context Menus**: Actions available for selected items

#### Context Menus
- **Positioning**: Smart positioning to stay within viewport
- **Dynamic Content**: Menu items based on context and permissions
- **Keyboard Navigation**: Arrow keys, Enter, Escape
- **Visual Grouping**: Separators and section headers

#### View Toggle Component
- **Toggle States**: Clear visual indication of active/inactive view modes
- **Icon Design**: Distinctive icons for Table (📋) and Grid (📱) views
- **Transition Animation**: Smooth crossfade between view modes
- **Accessibility**: Screen reader announcements for view changes
- **Keyboard Shortcuts**: Quick switching with keyboard (Ctrl+T for table, Ctrl+G for grid)
- **State Persistence**: Remember user's preferred view mode per component
- **Responsive Behavior**: Automatically switch to appropriate view on mobile devices
- **Loading States**: Show loading indicator during view transitions for large datasets

### Responsive Design

#### Breakpoints
- **Large (>1200px)**: Full desktop layout with sidebar
- **Medium (768-1200px)**: Compact desktop with collapsible sidebar
- **Small (<768px)**: Mobile-first with bottom navigation

#### Adaptive Layouts
- **Grid Systems**: Flexible column layouts
- **Component Scaling**: Buttons, inputs, and cards scale appropriately
- **Content Prioritization**: Hide less important elements on small screens
- **Touch Targets**: Larger touch areas for mobile devices

### Accessibility Features

#### Keyboard Navigation
- **Tab Order**: Logical navigation sequence
- **Focus Indicators**: Clear visual focus states
- **Shortcuts**: Application-wide and context-specific
- **Focus Management**: Proper focus handling in modals and menus

#### Screen Reader Support
- **ARIA Labels**: Descriptive labels for all interactive elements
- **Role Definitions**: Proper semantic roles
- **State Announcements**: Dynamic content changes announced
- **Alternative Text**: Meaningful alt text for images and icons

### Animation and Transitions

#### UI Animations
- **Page Transitions**: Smooth navigation between views
- **Component States**: Hover, focus, and interaction feedback
- **Loading States**: Progress indicators and skeleton screens
- **Micro-interactions**: Button presses, toggle switches, form validation

#### Performance Considerations
- **Hardware Acceleration**: CSS transforms for smooth animations
- **Reduced Motion**: Respect user preferences for reduced motion
- **Frame Rate**: Maintain 60fps for all animations
- **Animation Queuing**: Prevent animation conflicts

This comprehensive UI reference provides the visual foundation for TaskMover's interface, ensuring all components are well-defined before implementing the underlying business logic. Each component includes detailed requirements, features, and implementation considerations for a professional, accessible, and user-friendly application.
