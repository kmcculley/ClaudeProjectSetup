# .NET Blazor Web Application Skill

Specialized skill for creating and maintaining Blazor web applications with modern practices.

## Auto-Activation
- **File patterns**: `*.csproj` with Blazor package references
- **Project indicators**: `Program.cs` with Blazor services, `_Imports.razor`
- **Folder structures**: `Pages/`, `Components/`, `Shared/`

## Current Stack (Dynamic - Check Current Date First)
**IMPORTANT**: Always run `date` command and research current versions:
- **.NET**: Research latest stable .NET version as of current date
- **Blazor**: Server or WebAssembly based on requirements
- **UI Framework**: Research current Bootstrap version or custom CSS
- **State Management**: Built-in state or research current state management options
- **Database**: Research latest Entity Framework Core version
- **Authentication**: ASP.NET Core Identity (check current best practices)

## Project Structure
```
ProjectName/
├── Features/
│   ├── Authentication/
│   │   ├── Components/
│   │   ├── Models/
│   │   └── Services/
│   └── [FeatureName]/
├── Shared/
│   ├── Components/
│   ├── Models/
│   └── Services/
├── wwwroot/
├── Program.cs
└── appsettings.json
```

## Development Standards
- **Components**: PascalCase.razor (e.g., UserProfile.razor)
- **Services**: Dependency injection with interfaces
- **Configuration**: appsettings.json + appsettings.Development.json
- **CSS**: CSS isolation per component when possible
- **Validation**: FluentValidation or built-in data annotations

## Testing Setup
- **Unit Testing**: xUnit + bUnit for Blazor components
- **Integration Testing**: ASP.NET Core TestHost
- **E2E Testing**: Playwright for user flows
- **Coverage**: Minimum 70% overall, 80% business logic

## Code Quality
- **Analyzers**: Microsoft.CodeAnalysis.Analyzers, StyleCop.Analyzers
- **Formatting**: EditorConfig with standard .NET conventions
- **Pre-commit**: Format code, run tests, analyze

## Common Patterns
1. **Component Communication**: Parameters down, events up
2. **State Management**: Cascading parameters for shared state
3. **Data Loading**: Loading states with proper error handling
4. **Forms**: EditForm with validation and proper submit handling
5. **Navigation**: NavigationManager for programmatic navigation

## Deployment
- **Containerization**: Dockerfile with multi-stage build
- **Static Files**: Optimized wwwroot with compression
- **Environment**: Configuration via environment variables
- **CI/CD**: GitHub Actions with automated testing

## Performance Considerations
- **Blazor Server**: SignalR connection management, server resources
- **Blazor WebAssembly**: Bundle size optimization, lazy loading
- **Rendering**: @key attributes for list items, minimize re-renders
- **Memory**: Dispose of event handlers and services properly