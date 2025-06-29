# TaskMover UI Component Reference - Implementation Complete

**Status**: ✅ FULLY IMPLEMENTED (June 29, 2025)  
**Version**: 1.0.0  
**Last Updated**: June 29, 2025

## 🎉 Implementation Status

All UI components described in this reference have been **fully implemented and tested**. The TaskMover application now features a complete, modern user interface with all the components and functionality outlined below.

### ✅ Completed Components
- **Base Component System**: Foundation classes with accessibility and theming
- **Navigation Components**: Sidebar, toolbar, breadcrumbs, and tab navigation
- **Input Components**: Smart pattern input, modern form controls, and validation
- **Pattern Management**: Visual pattern library and interactive builder
- **Execution Interface**: File operation controls with real-time feedback
- **Dialog System**: Modal dialogs for user interaction and progress tracking
- **History Management**: Operation timeline and filtering capabilities
- **Theme System**: Light/dark themes with customizable design tokens
- **Main Application**: Integrated window with all components working together

### 🚀 Ready to Use
The application is now ready for production use with all UI components functioning as designed. Run the application with:
```bash
python -m taskmover
```

---

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

### Modern Sidebar Navigation
```
┌─────────────────┐
│ TaskMover       │ ← App logo/title
├─────────────────┤
│ 🏠 Dashboard    │ ← Active state (highlighted background)
│                 │
│ 📋 Patterns     │ ← Hover state
│   • Library     │ ← Nested items with bullets
│   • Groups      │
│   + New         │ ← Quick actions
│                 │
│ 📏 Rules        │
│   • Active (12) │ ← Badge with count
│   • Disabled    │
│   + New         │
│                 │
│ 📦 Rulesets     │
│   • Recent      │
│   • Templates   │
│   + New         │
│                 │
│ ⚡ Execute      │ ← Action items
│                 │
│ ├─ Activity ────┤ ← Section separator
│ 📈 History      │
│ 📊 Statistics   │
│ 📜 Logs         │
│                 │
│ ├─ System ──────┤
│ ⚙️  Settings    │
│ ❓ Help         │
│                 │
│ [◀] Collapse    │ ← Minimize to icons only
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

#### Grid View (Default) - Updated with System Groups
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ Pattern Library                                           [+ New Pattern]   │
├─────────────────────────────────────────────────────────────────────────────┤
│ Search: [_______________] Group: [All ▼] Status: [All ▼] Sort: [Usage ▼]    │
│                                                   View: [📱 Grid] [📋 Table] │
├─────────────────────────────────────────────────────────────────────────────┤
│ ┌─ System Groups ────────────────────────────────────────────────────────┐   │
│ │ ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐           │   │
│ │ │ @media          │ │ @documents      │ │ @code           │           │   │
│ │ │ Images, Videos  │ │ Office Files    │ │ Source Code     │           │   │
│ │ │ 🎯 Built-in     │ │ 🎯 Built-in     │ │ 🎯 Built-in     │           │   │
│ │ │ 📊 Used in 5    │ │ 📊 Used in 8    │ │ 📊 Used in 3    │           │   │
│ │ │ [✏️] [📋] [ℹ️]   │ │ [✏️] [📋] [ℹ️]   │ │ [✏️] [📋] [ℹ️]   │           │   │
│ │ └─────────────────┘ └─────────────────┘ └─────────────────┘           │   │
│ │                                                                       │   │
│ │ ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐           │   │
│ │ │ @archives       │ │ @temporary      │ │ + Custom Group  │           │   │
│ │ │ Compressed      │ │ Temp & Cache    │ │                 │           │   │
│ │ │ 🎯 Built-in     │ │ 🎯 Built-in     │ │   Click to      │           │   │
│ │ │ 📊 Used in 2    │ │ 📊 Used in 1    │ │   create new    │           │   │
│ │ │ [✏️] [📋] [ℹ️]   │ │ [✏️] [📋] [ℹ️]   │ │   group         │           │   │
│ │ └─────────────────┘ └─────────────────┘ └─────────────────┘           │   │
│ └───────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│ ┌─ Custom Patterns ──────────────────────────────────────────────────────┐   │
│ │ ┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐           │   │
│ │ │ Work Files      │ │ Projects        │ │ + Add Pattern   │           │   │
│ │ │ *.doc,*.xls     │ │ Large Files     │ │                 │           │   │
│ │ │ 👤 Custom       │ │ 👤 Custom       │ │   Click to      │           │   │
│ │ │ 📊 Used in 3    │ │ 📊 Not used     │ │   create new    │           │   │
│ │ │ [✏️] [📋] [🗑️]   │ │ [✏️] [📋] [🗑️]   │ │   pattern       │           │   │
│ │ └─────────────────┘ └─────────────────┘ └─────────────────┘           │   │
│ └───────────────────────────────────────────────────────────────────────┘   │
├─────────────────────────────────────────────────────────────────────────────┤
│ 5 system groups │ 2 custom patterns │ 7 active            [◀ 1 ▶]          │
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
├───┼─────────────────┼─────────────────┼─────────────┼─────────┼─────────┤ │
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

### Pattern Builder - Unified Pattern Language (Updated for v3.0)
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ Pattern Builder - Visual Pattern Constructor                   [×]          │
├─────────────────────────────────────────────────────────────────────────────┤
│ ┌─ Smart Pattern Input ──────────────────────────────────────────────────┐  │
│ │ Pattern: [*.pdf,*.doc AND size > 1MB                               ] 🔍│  │
│ │ ✓ Valid pattern • 23 files match • Estimated performance: Fast        │  │
│ │                                                                        │  │
│ │ 💡 Suggestions: @documents, size > 10MB, modified > today-7           │  │
│ │ 🔤 Quick Groups: [@media] [@documents] [@code] [@archives] [+ Custom] │  │
│ │                                                                        │  │
│ │ Options: [☐] Case Sensitive  [☐] Include Hidden Files                 │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│ ┌─ Pattern Details ──────────────────────────────────────────────────────┐  │
│ │ Name: [Large Documents                                                ] │  │
│ │ Description: [Office documents larger than 1MB                       ] │  │
│ │ Group: [Office ▼] Tags: [work] [important] [+ Add]                    │  │
│ │                                                                        │  │
│ │ Options: [☑️] Case Sensitive  [☐] Include Hidden Files  [☑️] Recursive │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│ ┌─ Visual Builder (Drag & Drop) ─────────────────────────────────────────┐  │
│ │ ┌─────────┐    ┌─────────────┐    ┌─────────────┐    ┌─────────────┐   │  │
│ │ │ *.pdf   │ AND│ size > 1MB  │ AND│ modified >  │ -> │ Documents/  │   │  │
│ │ │ *.doc   │    │             │    │ today-30    │    │ Large/      │   │  │
│ │ └─────────┘    └─────────────┘    └─────────────┘    └─────────────┘   │  │
│ │                                                                        │  │
│ │ Drag from palette: [File Types] [Size] [Date] [Location] [Custom]     │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│ ┌─ Live Preview ─────────────────────────────────────────────────────────┐  │
│ │ Workspace: [C:\Users\Downloads\        ▼] [🔄 Refresh] 23 files match  │  │
│ │                                                                        │  │
│ │ ✅ presentation.pptx (2.5MB, Today)      -> Documents/Large/           │  │
│ │ ✅ report.pdf (1.2MB, Yesterday)         -> Documents/Large/           │  │
│ │ ✅ spreadsheet.xlsx (1.8MB, Today)       -> Documents/Large/           │  │
│ │ ❌ small_doc.docx (500KB, Today)         (too small)                   │  │
│ │ ❌ image.jpg (800KB, Today)              (wrong type)                  │  │
│ │                                                                        │  │
│ │ Performance: ⚡ Fast (< 1s) • Cache: Fresh • Conflicts: None          │  │
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

### Enhanced File Conflict Resolution Dialog
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ File Conflict Resolution - 3 of 8 conflicts                  [×]          │
├─────────────────────────────────────────────────────────────────────────────┤
│ Conflict Type: 📄 File Already Exists                                      │
│                                                                             │
│ ┌─ Source File ──────────────────────┐ ┌─ Destination File ──────────────┐ │
│ │ 📄 presentation.pptx                │ │ 📄 presentation.pptx             │ │
│ │ 📁 C:\Downloads\                    │ │ 📁 C:\Documents\Work\            │ │
│ │ 📅 Modified: Today 2:30 PM          │ │ 📅 Modified: Yesterday 4:15 PM   │ │
│ │ 📏 Size: 2.5 MB (400KB larger)     │ │ 📏 Size: 2.1 MB                  │ │
│ │ [🔍 Preview] [📊 Details]           │ │ [🔍 Preview] [📊 Details]        │ │
│ └─────────────────────────────────────┘ └──────────────────────────────────┘ │
│                                                                             │
│ ┌─ Smart Resolution Options ─────────────────────────────────────────────┐  │
│ │ ⭐ [●] Smart rename: presentation_2025-06-29.pptx (Recommended)        │  │
│ │    [○] Overwrite older file (⚠️ Destination is older)                  │  │
│ │    [○] Skip this file                                                  │  │
│ │    [○] Custom name: [________________________] [✓ Valid]               │  │
│ │                                                                        │  │
│ │ 🔄 Batch Actions:                                                      │  │
│ │ [☑️] Apply to all .pptx conflicts (2 remaining)                       │  │
│ │ [☐] Apply to all size conflicts                                       │  │
│ │ [☐] Remember for this folder pair                                     │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│ ┌─ Preview Result ───────────────────────────────────────────────────────┐  │
│ │ ✅ presentation.pptx → presentation_2025-06-29.pptx                    │  │
│ │ 📁 Final location: C:\Documents\Work\presentation_2025-06-29.pptx      │  │
│ └────────────────────────────────────────────────────────────────────────┘  │
│                                                                             │
│ [⏮️ Previous] [Skip All Similar] [Apply] [Apply to All] [⏭️ Next (5 left)] │
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
│ Moving: presentation.pptx → Documents/                                     │
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

## 🎨 Modern Design Enhancements

### Enhanced Visual Design System

#### Color Scheme and Theme
```
Light Theme:
- Primary: #2563eb (Blue 600)
- Secondary: #64748b (Slate 500) 
- Success: #16a34a (Green 600)
- Warning: #d97706 (Amber 600)
- Error: #dc2626 (Red 600)
- Background: #ffffff (White)
- Surface: #f8fafc (Slate 50)
- Border: #e2e8f0 (Slate 200)

Dark Theme:
- Primary: #3b82f6 (Blue 500)
- Secondary: #94a3b8 (Slate 400)
- Success: #22c55e (Green 500)
- Warning: #f59e0b (Amber 500)
- Error: #ef4444 (Red 500)
- Background: #0f172a (Slate 900)
- Surface: #1e293b (Slate 800)
- Border: #334155 (Slate 700)
```

#### Typography Scale
```
- Display: 32px (2rem) - bold - Page titles
- Heading 1: 24px (1.5rem) - semibold - Section headers
- Heading 2: 20px (1.25rem) - semibold - Subsection headers
- Body Large: 16px (1rem) - regular - Main content
- Body: 14px (0.875rem) - regular - Secondary content
- Caption: 12px (0.75rem) - regular - Labels and hints
- Code: 14px (0.875rem) - monospace - Pattern input
```

#### Spacing System
```
- xs: 4px (0.25rem)
- sm: 8px (0.5rem)
- md: 16px (1rem)
- lg: 24px (1.5rem)
- xl: 32px (2rem)
- 2xl: 48px (3rem)
```

### Enhanced Component States

#### Interactive States
```
Default → Hover → Active → Focus → Disabled

Button Example:
- Default: bg-primary, text-white
- Hover: bg-primary-dark, shadow-md
- Active: bg-primary-darker, shadow-inner
- Focus: ring-2 ring-primary-light
- Disabled: bg-gray-300, text-gray-500, cursor-not-allowed
```

#### Loading States
```
Component Loading:
- Skeleton screens for data tables
- Shimmer effects for cards
- Progress bars for operations
- Spinner overlays for buttons

Examples:
┌─────────────────┐
│ ████████████    │ ← Skeleton card
│ ████████        │
│ ████            │
└─────────────────┘
```

### Smart Pattern Input Component (Enhanced)
```
┌─────────────────────────────────────────────────────────────────────────────┐
│ Smart Pattern Input                                                         │
├─────────────────────────────────────────────────────────────────────────────┤
│ ┌─ Pattern Input with Intelligent Assistance ───────────────────────────┐   │
│ │ [*.py AND size > 1MB AND modified > tod|                            ] │   │
│ │                                        ▲                              │   │
│ │ 💡 Auto-complete suggestions:           │                              │   │
│ │ ┌───────────────────────────────────────┐                              │   │
│ │ │ today-7        (last week)           │                              │   │
│ │ │ today-30       (last month)          │ ← Dropdown suggestions       │   │
│ │ │ today          (today)               │                              │   │
│ │ └───────────────────────────────────────┘                              │   │
│ │                                                                        │   │
│ │ Real-time validation: ✓ Valid syntax • 🎯 23 files match             │   │
│ │ Performance: ⚡ Fast (<100ms) • 🔍 Searchable • 💾 Cacheable         │   │
│ └────────────────────────────────────────────────────────────────────────┘   │
│                                                                             │
│ ┌─ Pattern Assistance Panel ─────────────────────────────────────────────┐   │
│ │ Quick Groups: [@media] [@documents] [@code] [@archives] [@temporary]   │   │
│ │                                                                        │   │
│ │ Recent: [*.pdf] [size > 1MB] [modified > today-7] [content: important]│   │
│ │                                                                        │   │
│ │ Smart Tokens: [$DATE] [$USER] [$HOSTNAME] [Custom...]                 │   │
│ │                                                                        │   │
│ │ Advanced: [📏 Size] [📅 Date] [📁 Path] [🏷️ Tags] [🔍 Content]        │   │
│ └────────────────────────────────────────────────────────────────────────┘   │
└─────────────────────────────────────────────────────────────────────────────┘
```
