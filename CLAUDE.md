# Claude Code Instructions

## Development Context
- **Date Checking**: Always run `date` command first to get current date
- **Developer**: Solo developer working on diverse project types
- **Focus**: Always use latest stable versions and modern practices

## Tech Stack & Preferences

### Primary Technologies
- **C# .NET**: Blazor (web), Avalonia (desktop), ASP.NET Core APIs
- **JavaScript/TypeScript**: React (frontend), Node.js Express (APIs)
- **Mobile**: React Native for cross-platform development
- **Game Development**: Unity with modern C# practices
- **Databases**: EF Core for CRUD, Dapper for performance queries

### Development Standards
- **Naming**: PascalCase for all files, projects, and C# elements
- **Structure**: Feature-based folders, separate repositories per project
- **Configuration**: appsettings.json (C#), .env files (Node.js)
- **Testing**: xUnit (C#), Jest + React Testing Library, Playwright (E2E)
- **Coverage**: 70% minimum overall, 80% for business logic
- **Deployment**: Containers (non-desktop), Static hosting (React), Manual (desktop)

## Critical Instructions

### Version Management
🚨 **ALWAYS CHECK CURRENT DATE FIRST**: Run `date` command
- Research latest stable versions as of the ACTUAL current date
- Never suggest outdated libraries or deprecated approaches
- Use web search for current best practices: "latest stable version [tech] [current year]"
- Prioritize security patches and LTS versions where available

### Project Structure Standards
```
ProjectName/
├── Features/
│   ├── [FeatureName]/
│   │   ├── Components/ (or Controllers/, Views/, etc.)
│   │   ├── Models/
│   │   └── Services/
├── Shared/
│   ├── Components/
│   ├── Utils/
│   └── Types/
└── [Platform-specific folders]
```

### Code Quality Requirements
- **Linting**: ESLint + Prettier (JS/TS), StyleCop + EditorConfig (C#)
- **Pre-commit Hooks**: Format code, run tests, lint
- **Error Handling**: Centralized error handling patterns
- **Security**: Never expose secrets, follow OWASP guidelines

## Project Detection & Skill Loading

**CRITICAL**: On your first message in any project session, you MUST:

### 1. Detect Project Type
Analyze the working directory for these indicators:

| Project Type | Detection Pattern | Skill File |
|--------------|------------------|------------|
| **Blazor Web** | `*.csproj` with Blazor/AspNetCore references | `.claude/skills/dotnet-blazor-web.md` |
| **Avalonia Desktop** | `*.csproj` with Avalonia packages | `.claude/skills/dotnet-avalonia-desktop.md` |
| **React Frontend** | `package.json` with `react` + `vite.config.ts` | `.claude/skills/react-frontend.md` |
| **Node.js API** | `package.json` with `express` + `Dockerfile` | `.claude/skills/nodejs-api.md` |
| **React Native** | `package.json` with `react-native` + `android/` or `ios/` | `.claude/skills/react-native-mobile.md` |
| **Unity Game** | `*.unity` files or `Assets/` folder | `.claude/skills/unity-game-development.md` |

### 2. Load the Skill File
Once detected, **USE THE READ TOOL** to load the appropriate skill file from `.claude/skills/[type].md`

### 3. Apply Throughout Session
- Follow all guidance from the loaded skill file
- Use skill-specific patterns and standards
- Reference skill documentation for decisions

### 4. Multi-Project Detection
If multiple project types detected:
- List all detected types
- Ask user which project they're working on
- Load the appropriate skill for that context

Each skill file provides:
- Dynamic version checking instructions (always check current date first)
- Project structure templates
- Technology-specific best practices
- Testing strategies and deployment patterns

## Workflow Standards

### Development Process
1. **Project Setup**: Use appropriate skill template with latest versions
2. **Code Quality**: Set up linting, formatting, and testing from start
3. **Testing Strategy**: Implement tests with proper coverage
4. **Documentation**: Focus on code clarity over extensive documentation
5. **Deployment**: Follow containerization or static hosting patterns

### CI/CD with GitHub Actions
- **Testing**: Run all tests on pull requests
- **Quality**: Enforce linting and formatting
- **Deployment**: Manual approval gates for production
- **Security**: Automated dependency scanning

## Key Preferences

### Database Strategy
- **EF Core**: Standard CRUD operations, rapid development
- **Dapper**: Performance-critical queries, complex reporting
- **Local Infrastructure**: Host databases on local servers
- **Migrations**: Automated database versioning

### Deployment Preferences
- **Web Applications**: Containerized deployment
- **Frontend**: Static hosting (Vercel, Netlify, Azure Static Web Apps)
- **Desktop**: Manual distribution with proper packaging
- **Mobile**: Platform stores with automated CI/CD

### Package Management
- **Node.js**: npm (not yarn or pnpm)
- **.NET**: NuGet with PackageReference format
- **Dependencies**: Always latest stable, regular security updates

## Important Reminders

### For Claude
1. **Date Awareness**: ALWAYS run `date` command first to get current date
2. **Version Currency**: Research latest stable versions as of current date before suggesting
3. **Web Research**: Use web search when unsure about current versions
4. **Standards Consistency**: Follow established naming and structure patterns
5. **Testing**: Include appropriate test setup for each project type
6. **Security**: Never compromise on security best practices

### Project Detection Workflow
On first message in a project session:
1. **Detect**: Check working directory for project type indicators (see Detection table above)
2. **Load**: Use Read tool to load appropriate skill file from `.claude/skills/`
3. **Confirm**: Notify user which skill was loaded
4. **Apply**: Follow skill-specific standards throughout the session
5. **Research**: Always check current date and research latest stable versions before suggestions

This infrastructure ensures Claude provides current, consistent, and high-quality assistance by explicitly loading project-specific guidance at the start of each session.