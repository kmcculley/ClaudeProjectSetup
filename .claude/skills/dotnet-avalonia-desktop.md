# .NET Avalonia Desktop Application Skill

Specialized skill for creating cross-platform desktop applications using Avalonia UI.

## Auto-Activation
- **File patterns**: `*.csproj` with Avalonia package references
- **Project indicators**: `App.axaml`, `MainWindow.axaml`, Avalonia.Desktop
- **Folder structures**: `Views/`, `ViewModels/`, `Assets/`

## Current Stack (Dynamic - Check Current Date First)
**IMPORTANT**: Always run `date` command and research current versions:
- **.NET**: Research latest stable .NET version as of current date
- **Avalonia UI**: Research latest stable Avalonia version
- **MVVM**: Research current MVVM frameworks (CommunityToolkit.Mvvm or ReactiveUI)
- **Dependency Injection**: Microsoft.Extensions.DependencyInjection (check current version)
- **Database**: Research latest Entity Framework Core + Dapper versions
- **Configuration**: appsettings.json with IConfiguration

## Project Structure
```
ProjectName/
├── Features/
│   ├── Authentication/
│   │   ├── Views/
│   │   ├── ViewModels/
│   │   └── Models/
│   └── [FeatureName]/
├── Shared/
│   ├── Controls/
│   ├── Services/
│   ├── Models/
│   └── Converters/
├── Assets/
├── App.axaml
├── App.axaml.cs
└── Program.cs
```

## Development Standards
- **Views**: PascalCase.axaml (e.g., UserProfileView.axaml)
- **ViewModels**: PascalCase + "ViewModel" suffix
- **Naming**: Follow C# conventions consistently
- **MVVM**: Strict separation, no code-behind logic
- **Binding**: Use compiled bindings for performance

## MVVM Patterns
- **ViewModels**: Implement INotifyPropertyChanged via CommunityToolkit
- **Commands**: Use RelayCommand/AsyncRelayCommand
- **Navigation**: Service-based navigation with dependency injection
- **Dialogs**: Service pattern for modal dialogs
- **Validation**: INotifyDataErrorInfo for form validation

## Styling & Theming
- **Styles**: Organized in ResourceDictionary files
- **Themes**: Support light/dark mode switching
- **Resources**: Centralized colors, fonts, and dimensions
- **Custom Controls**: UserControl or TemplatedControl based on needs

## Testing Setup
- **Unit Testing**: xUnit for ViewModels and business logic
- **UI Testing**: Limited Avalonia testing capabilities, focus on ViewModels
- **Integration**: Test services and data layers separately
- **Coverage**: 70% minimum, 80% for business logic

## Performance Optimization
- **Virtualization**: Use VirtualizingStackPanel for large lists
- **Binding**: Compiled bindings over reflection-based
- **Images**: Lazy loading and proper disposal
- **Memory**: WeakEventManager for event subscriptions

## Platform-Specific Features
- **Windows**: Native file dialogs, system tray integration
- **Linux**: Desktop integration, file associations
- **macOS**: Menu bar integration, native look and feel
- **Packaging**: Framework-dependent deployment for size optimization

## Deployment Strategy
- **Development**: Framework-dependent deployment
- **Distribution**: Self-contained deployment with trimming
- **Updates**: Manual distribution or implement auto-updater
- **Packaging**: Platform-specific installers (MSI, DEB, DMG)

## Data Access Pattern
```csharp
// EF Core for CRUD operations
public class UserService
{
    private readonly AppDbContext _context;
    
    public async Task<User> GetUserAsync(int id)
        => await _context.Users.FindAsync(id);
}

// Dapper for performance-critical queries
public class ReportService
{
    private readonly IDbConnection _connection;
    
    public async Task<IEnumerable<ReportData>> GetReportAsync()
        => await _connection.QueryAsync<ReportData>("SELECT...");
}
```