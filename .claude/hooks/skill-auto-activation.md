# Skill Auto-Activation Hook

This hook automatically detects project types and suggests the appropriate skills based on file patterns and project structure.

## Auto-Activation Rules

### .NET Blazor Web Applications
**Trigger Patterns:**
- `*.csproj` contains `Microsoft.AspNetCore.Blazor` or `Microsoft.AspNetCore.Components.Web`
- Files: `Program.cs`, `App.razor`, `_Imports.razor`
- Folders: `Pages/`, `Components/`, `Shared/`

**Auto-Suggested Skill:** `dotnet-blazor-web`
**Key Reminders:** 
- Check current date and research latest stable .NET version
- Blazor Server or WebAssembly based on requirements
- Feature-based folder structure
- appsettings.json configuration

### .NET Avalonia Desktop Applications
**Trigger Patterns:**
- `*.csproj` contains `Avalonia` packages
- Files: `App.axaml`, `MainWindow.axaml`, `Program.cs`
- Folders: `Views/`, `ViewModels/`, `Assets/`

**Auto-Suggested Skill:** `dotnet-avalonia-desktop`
**Key Reminders:**
- Check current date and research latest stable Avalonia version
- MVVM pattern with CommunityToolkit.Mvvm
- Cross-platform desktop deployment
- EF Core + Dapper data access pattern

### React Frontend Applications
**Trigger Patterns:**
- `package.json` contains `react` dependency
- Files: `App.tsx`, `main.tsx`, `index.html`
- Folders: `src/components/`, `src/features/`
- `vite.config.ts` present

**Auto-Suggested Skill:** `react-frontend`
**Key Reminders:**
- Check current date and research latest stable React + TypeScript + Vite versions
- Static hosting deployment strategy
- Feature-based organization

### Node.js Express APIs
**Trigger Patterns:**
- `package.json` contains `express` dependency
- Files: `server.js`, `app.js`, or `server.ts`
- Folders: `routes/`, `middleware/`, `controllers/`
- `Dockerfile` present (indicates containerized deployment)

**Auto-Suggested Skill:** `nodejs-api`
**Key Reminders:**
- Check current date and research latest LTS Node.js + Express versions
- TypeScript latest stable for type safety
- Direct database connection to local infrastructure
- Containerized deployment

### React Native Mobile Applications
**Trigger Patterns:**
- `package.json` contains `react-native` dependency
- Files: `App.tsx`, `metro.config.js`
- Folders: `android/`, `ios/`
- Platform-specific files (`.ios.tsx`, `.android.tsx`)

**Auto-Suggested Skill:** `react-native-mobile`
**Key Reminders:**
- Check current date and research latest stable React Native version
- Research current React Navigation version
- Cross-platform considerations
- Platform-specific testing required

### Unity Game Development
**Trigger Patterns:**
- Files: `*.unity`, `ProjectSettings/`
- Folders: `Assets/`, `Assets/Scripts/`
- Unity project files and meta files

**Auto-Suggested Skill:** `unity-game-development`
**Key Reminders:**
- Check current date and research latest stable Unity LTS version
- New Input System (not legacy)
- Component-based architecture
- URP for rendering pipeline

## Multi-Project Detection
When multiple project types are detected in the same repository:
1. List all detected project types
2. Ask user to specify which project they're working on
3. Suggest the appropriate skill for the current task
4. Offer to create separate skill contexts for different project areas

## Version Awareness
**Critical:** Always check the ACTUAL current system date first and ensure:
- Run `date` command to get current date
- Research latest stable versions as of that date
- Deprecated libraries are avoided
- Security patches are considered
- Migration paths are suggested for outdated dependencies

## Skill Activation Messages
When auto-activating a skill, display:
```
🎯 Auto-detected: [Project Type]
📋 Activated Skill: [Skill Name]
📅 Checking current date and researching latest stable versions
🔧 Ready to assist with [specific capabilities]
```

## Fallback Behavior
If no patterns match:
1. Analyze file extensions and structure
2. Ask user about project type and goals
3. Suggest creating a custom skill if needed
4. Provide general development assistance with established standards

## Context Preservation
- Remember the activated skill for the session
- Apply the skill's standards to all suggestions
- Maintain consistency across the conversation
- Update skill context if project scope changes