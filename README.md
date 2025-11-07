# Personal Claude Code Infrastructure

A comprehensive Claude Code setup for multi-platform development with automatic skill activation and current version awareness.

## Overview

This infrastructure solves the common problem of Claude suggesting outdated libraries and frameworks by:
- 🗓️ **Dynamic Date Awareness**: Automatically checks current system date and researches latest stable versions
- 🎯 **Auto-Skill Activation**: Detects project type and applies appropriate development standards
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

1. **Copy Configuration**: Place the `.claude/` folder in your development directory
2. **Activate Skills**: Skills auto-activate based on project file detection
3. **Follow Standards**: All generated code follows your established conventions

## Key Features

### Automatic Project Detection
```
🎯 Auto-detected: React Frontend Application
📋 Activated Skill: react-frontend  
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

### `.claude/settings.json`
Core configuration enabling auto-activation and skill discovery.

### `.claude/hooks/`
- `context-enhancer.md` - Dynamically checks system date and provides tech stack context
- `skill-auto-activation.md` - Auto-detects project types and researches current versions

### `.claude/skills/`
Individual skill files for each project type with comprehensive guidance.

## Usage Examples

### Starting a New Blazor Project
Claude detects `.csproj` with Blazor references and automatically:
- Checks current date and researches latest stable .NET version
- Sets up feature-based folder structure
- Configures xUnit testing with proper coverage
- Sets up GitHub Actions with manual deployment gates

### React Frontend Development
Claude detects `package.json` with React and automatically:
- Researches current React + TypeScript + Vite versions
- Configures ESLint + Prettier + Playwright
- Sets up static hosting deployment
- Applies consistent naming conventions

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

The system ensures version currency through:
1. **System Date Checking**: Always runs `date` command first to get actual current date
2. **Web Research**: Searches for "latest stable version [technology] [current year]" 
3. **No Hardcoded Dates**: All version references are research-based, not static
4. **Automatic Updates**: Works correctly in December 2025, 2026, and beyond without any manual updates

This means you'll never get outdated library suggestions, regardless of how much time passes.