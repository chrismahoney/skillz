# Product Context: skillz

**Purpose:** Why this project exists and how it should work  
**Last Updated:** October 23, 2026

---

## 🎯 Problem Statement

Developers and teams need a structured way to:
1. **Discover** individual, reusable skills (automation scripts, utilities, tools)
2. **Manage** skills with consistent documentation and metadata
3. **Visualize** available skills through an intuitive interface
4. **Organize** skills into collections (personal, organizational, by category)

Without a standardized approach, skills become scattered, undocumented, and difficult to find or reuse.

---

## 💡 Solution Overview

The **skillz** project provides:

### 1. Skills Repository Framework
A standardized structure for individual skills:
```
skills/
└── skill-name/
    ├── skill-name.skill    # YAML frontmatter + trigger
    └── SKILL.md            # Full documentation
```

### 2. Visual Catalog UI
A modern React application that:
- Displays skills in interactive 2D/3D views
- Supports search, filtering, and faceted grouping
- Enables collection management
- Provides update status indicators

### 3. Command-Line Integration
```bash
npx skills list --json      # Discover available skills
npx skills use <url> --skill <name>  # Apply skill guidelines
```

---

## 🎯 User Experience Goals

### For Skill Consumers
- **Easy Discovery** - Browse skills via UI or CLI
- **Clear Documentation** - Understand what each skill does
- **Quick Actions** - Install, preview, save with one click
- **Collection Building** - Organize skills that matter to you

### For Skill Contributors
- **Simple Structure** - Well-documented template to follow
- **Validation** - Frontmatter requirements enforced
- **Visibility** - Skills automatically indexed and discoverable

### For Teams/Organizations
- **Centralized Repository** - Single source of truth for skills
- **Collection Sharing** - Organize skills by team/department
- **Update Tracking** - Know when skills need updates
---

## 🔄 How It Should Work

### Discovery Flow
```
User opens catalog
    ↓
Skills load from `skills/` directory
    ↓
User searches/filter browses
    ↓
User clicks skill card
    ↓
User installs/saves skill
    ↓
Skill available for use
```

### Data Flow
```
skills/ directory (source of truth)
    ↓
npx skills list --json (CLI extraction)
    ↓
useSkills hook (data fetching + caching)
    ↓
React components (rendering)
    ↓
LocalStorage (persistent collections)
```

---

## 🎨 Key User Stories

### As a Developer, I want to...

| Story | Acceptance Criteria |
|-------|---------------------|
| Discover new skills | Browse grid view with search |
| Understand a skill | Read SKILL.md documentation |
| Save skills for later | Add to personal/organization collection |
| Find skills by category | Use facet grouping (org/individual/collection) |
| See which skills need updates | View color-coded update badges |
| Install a skill | Click install button, skill becomes available |
| Search quickly | Type-ahead search with kbar palette |

---

## 🚦 Success Criteria

### MVP (Minimum Viable Product)
- Skills repository structure established
- Visual catalog UI displaying skills
- Search and filter functionality
- Collection management (personal only)
- TypeScript compilation with zero errors

### Phase 2
- Organization collections support
- 3D skill card miniatures
- Update badge system
- Production build optimization

### Phase 3
- Additional skills beyond prototypes
- Team collaboration features
- Skill sharing/export
- Advanced filtering (tags, categories)

---

## 🧩 Component Relationships

Main components:
- **SkillCatalog** - Main container
- **SearchBar** - Type-ahead filtering
- **FilterChips** - Project/global/both toggle
- **SkillsGrid** - Grid view with skill cards
- **SkillCard** - Individual skill display
- **RefreshButton** - Reload data
- **KbarOverlay** - Cmd+Ctrl+K command palette
- **useSkills** - Data fetching hook
- **Stars** - 3D background

---

## 🌍 Platform Considerations

### Web Browser
- Desktop (Chrome, Firefox, Safari, Edge)
- Mobile (responsive design)
- Tablet (adaptive layouts)

### Build Targets
- Development: Fast hot-reload, source maps
- Production: Minified, optimized CSS/JS

### Browser Support
Based on `browserslist`:
- Last 2 versions
- > 1% usage
- Not dead browsers
- Not IE 11

---

## 🔄 State Management

### Client-Side State
- `skills`: Array of SkillNode objects
- `collections`: Personal/organization collections
- `viewMode`: 'grid' | 'facet'
- `searchQuery`: Current search term
- `selectedSkills`: Skills in current selection

### Persistence
- **LocalStorage**: Collections, search history
- **Memory**: Current session state
- **Source of Truth**: `skills/` directory files

---

## 🎯 Future Enhancements

1. **Skill Execution** - Run skills directly from catalog
2. **API Integration** - Fetch skills from remote repositories
3. **Export/Import** - Share collections across users
4. **Analytics** - Track most-used skills
5. **Notifications** - Alert on skill updates
