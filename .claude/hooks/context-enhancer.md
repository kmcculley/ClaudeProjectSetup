# Context Enhancer Hook

This hook automatically provides Claude with essential context about the current date, your preferred tech stack, and development standards.

## Auto-Activation Rules
- **Always active**: This hook runs on every prompt to ensure Claude has current context
- **Date awareness**: ALWAYS check current system date first to prevent outdated library suggestions
- **Tech stack detection**: Analyzes project files to determine the appropriate technology stack

## Current Date Verification
**CRITICAL**: Before any technology recommendations, always run:
```bash
date
```
Use this ACTUAL current date for all version recommendations and research.

## Context Provided

### Current Environment Detection
- **Date**: Always check system date with `date` command first
- **Platform**: Windows
- **Development Style**: Solo developer, multiple project types

### Tech Stack Preferences
- **C# .NET**: Blazor, Avalonia, ASP.NET Core, EF Core + Dapper
- **JavaScript/TypeScript**: React, Node.js Express, Vite, npm
- **Mobile**: React Native
- **Game Development**: Unity
- **Testing**: xUnit (C#), Playwright (E2E), Jest + React Testing Library
- **Deployment**: Containers (non-desktop), Static hosting (React), Manual distribution (desktop)

### Development Standards
- **Naming**: PascalCase for all files and projects
- **Structure**: Feature-based folders, separate repositories
- **Configuration**: appsettings.json (C#), .env files (Node.js)
- **Code Quality**: ESLint + Prettier, pre-commit hooks, 70% test coverage minimum
- **Dependencies**: Always use latest stable versions
- **CI/CD**: GitHub Actions with manual approval gates

### Project Type Detection Patterns
- **.csproj + Avalonia references** = Desktop application
- **.csproj + Blazor references** = Web application  
- **package.json + React** = Frontend application
- **package.json + Express** = Backend API
- **package.json + react-native** = Mobile application
- **.unity** = Game development
- **Dockerfile** = Containerized application

## Key Reminders for Claude
1. **ALWAYS check current system date FIRST** using `date` command before any tech recommendations
2. **Research latest stable versions** as of the ACTUAL current date (not static dates)
3. **Use web search** when unsure about current versions: "latest stable version [technology] [current year]"
4. **Follow established naming conventions** (PascalCase)
5. **Prefer feature-based organization** over layer-based
6. **Include appropriate testing setup** for each project type
7. **Set up proper linting/formatting** from the start

## Version Research Pattern
When suggesting any technology stack:
1. Run `date` to get current date
2. Web search for "[technology] latest stable version [current year]"
3. Verify LTS status and security updates
4. Only then provide recommendations