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

## Auto-Activation Skills

The `.claude/` directory contains specialized skills that auto-activate based on project detection:

### Available Skills
- **dotnet-blazor-web**: Blazor web applications with ASP.NET Core
- **dotnet-avalonia-desktop**: Cross-platform desktop apps with Avalonia
- **react-frontend**: React apps with TypeScript and static hosting
- **nodejs-api**: Express APIs with TypeScript and containerization
- **react-native-mobile**: Cross-platform mobile development
- **unity-game-development**: Game development with modern Unity practices

### Skill Activation
Skills automatically activate when Claude detects:
- Relevant file patterns (*.csproj, package.json, *.unity, etc.)
- Project structure indicators
- Framework-specific files

Each skill provides:
- Dynamic version checking for current tech stack
- Project structure templates
- Development best practices
- Testing and deployment strategies
- Performance optimization guidelines

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

### Project Detection
When working on a project:
1. Analyze file structure and dependencies
2. Auto-activate appropriate skill
3. Apply skill-specific standards and practices
4. Maintain consistency throughout the session
5. Suggest modern alternatives for outdated approaches

This infrastructure ensures Claude provides current, consistent, and high-quality assistance across all your development projects.