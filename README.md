# Personal Claude Code Infrastructure

A comprehensive Claude Code setup for multi-platform development with automatic skill activation and current version awareness.

## Overview

This infrastructure solves the common problem of Claude suggesting outdated libraries and frameworks by:
- 🗓️ **Dynamic Date Awareness**: Instructions force Claude to check current system date and research latest stable versions
- 🎯 **Project Detection & Skill Loading**: Claude detects project type and loads appropriate skill documentation
- 📋 **Consistent Standards**: Enforces naming conventions and project structure across all work
- 🔧 **Modern Practices**: Uses current best practices for each technology stack
- 🔍 **Real-Time Research**: Web searches for current versions instead of relying on static knowledge

## Supported Project Types

### .NET Applications
- **Blazor Web Apps**: Modern web applications with ASP.NET Core
- **Avalonia Desktop**: Cross-platform desktop applications
- **Data Access**: EF Core + Dapper hybrid approach

### JavaScript/TypeScript
- **React Frontend**: Static hosting with modern tooling (Vite)
- **Node.js APIs**: Express-based REST APIs with containerization
- **Mobile**: React Native cross-platform development

### Game Development
- **Unity**: Modern Unity development with C# best practices

## Quick Start

1. **Copy Configuration**: Place `CLAUDE.md` and `.claude/` folder in your development directory
2. **Start Session**: On first message, Claude detects project type and loads appropriate skill
3. **Follow Standards**: All generated code follows your established conventions

## Key Features

### Project Detection on First Message
```
🎯 Detected: React Frontend Application
📋 Loading Skill: .claude/skills/react-frontend.md
📅 Checking current date and researching latest stable versions
🔧 Ready to assist with current React + TypeScript + Vite versions
```

### Dynamic Version Awareness
- Automatically checks current system date before any recommendations
- Researches latest stable versions as of the actual current date
- Prevents outdated library recommendations regardless of when you use it
- Uses web search to verify current best practices
- Includes security considerations and migration paths

### Consistent Standards
- **Naming**: PascalCase for all files and projects
- **Structure**: Feature-based organization
- **Testing**: 70% minimum coverage with appropriate frameworks
- **Code Quality**: Automated linting, formatting, and pre-commit hooks

## Development Standards

### Project Organization
```
ProjectName/
├── Features/
│   └── [FeatureName]/
│       ├── Components/
│       ├── Models/
│       └── Services/
├── Shared/
│   ├── Components/
│   ├── Utils/
│   └── Types/
└── [Platform-specific folders]
```

### Quality Standards
- **C#**: xUnit testing, StyleCop analysis, EditorConfig
- **TypeScript**: Jest + RTL, ESLint + Prettier, Playwright E2E
- **All**: Pre-commit hooks, GitHub Actions CI/CD

### Deployment Strategy
- **Web Apps**: Containerized deployment
- **Frontend**: Static hosting (Vercel, Netlify, Azure)
- **Desktop**: Manual distribution with proper packaging
- **APIs**: Docker containers with health checks

## Skills Reference

Each skill provides:
- Dynamic version checking for current framework versions
- Real-time research of latest stable releases
- Project structure templates
- Development best practices
- Testing strategies
- Performance optimization
- Security guidelines

### Available Skills
- `dotnet-blazor-web` - Blazor web applications
- `dotnet-avalonia-desktop` - Desktop applications  
- `react-frontend` - React applications
- `nodejs-api` - Express REST APIs
- `react-native-mobile` - Mobile applications
- `unity-game-development` - Game development

## Configuration Files

### `CLAUDE.md`
Main project instructions file that auto-loads with Claude Code. Contains:
- Date checking requirements
- Development standards and preferences
- Project detection logic with explicit skill loading instructions

### `.claude/settings.json`
Claude Code configuration with real settings:
- Permission presets (allow/ask/deny patterns)
- Sandbox configuration
- Model and output preferences

### `.claude/skills/`
Technology-specific skill files that Claude reads when a project type is detected:
- `dotnet-blazor-web.md` - Blazor web applications
- `dotnet-avalonia-desktop.md` - Desktop applications
- `react-frontend.md` - React applications
- `nodejs-api.md` - Express REST APIs
- `react-native-mobile.md` - Mobile applications
- `unity-game-development.md` - Game development

## Usage Examples

### Starting a New Blazor Project
On first message, Claude:
1. Detects `.csproj` with Blazor references
2. Loads `.claude/skills/dotnet-blazor-web.md`
3. Checks current date and researches latest stable .NET version
4. Follows skill guidance for structure, testing, and deployment

### React Frontend Development
On first message, Claude:
1. Detects `package.json` with React
2. Loads `.claude/skills/react-frontend.md`
3. Researches current React + TypeScript + Vite versions
4. Applies skill-specific patterns and conventions

## Benefits

1. **Future-Proof Version Management**: Dynamically researches current stable versions regardless of date
2. **No Manual Updates Required**: System stays current automatically without maintenance
3. **Real-Time Technology Research**: Uses web search to verify latest best practices
4. **Consistent Quality**: Every project follows the same high standards  
5. **Reduced Setup Time**: Templates and standards are automatically applied
6. **Better Maintenance**: Consistent structure makes projects easier to maintain
7. **Always Current**: Works correctly whether it's 2025, 2026, or beyond

This infrastructure transforms Claude from a general coding assistant into a specialized development partner that understands your preferences, follows your standards, and dynamically researches current technologies regardless of when you use it.

## How Dynamic Date Awareness Works

The system ensures version currency through explicit instructions in `CLAUDE.md`:
1. **Mandatory Date Checking**: CLAUDE.md instructs Claude to always run `date` command first
2. **Web Research Required**: Instructions force web search for "latest stable version [technology] [current year]"
3. **No Hardcoded Versions**: Skills files instruct research, not hardcoded version numbers
4. **Future-Proof**: Works correctly in 2025, 2026, and beyond without updates

This means you'll never get outdated library suggestions, regardless of how much time passes.

## How the System Actually Works

This is **not** an auto-activation system. Instead:

1. **CLAUDE.md** is automatically loaded by Claude Code as project instructions
2. **CLAUDE.md** explicitly instructs Claude to:
   - Detect project type on first message
   - Use the Read tool to load the appropriate skill file
   - Follow that skill's guidance throughout the session
3. **Skill files** contain detailed technology-specific guidance
4. **settings.json** configures Claude Code's real features (permissions, sandbox, etc.)

The "magic" is simply well-structured instructions that Claude follows reliably.