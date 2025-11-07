# Unity Game Development Skill

Specialized skill for creating games using Unity with modern C# practices and efficient workflows.

## Auto-Activation
- **File patterns**: `*.unity`, `Assets/`, `ProjectSettings/`
- **Project indicators**: Unity project files, `.csproj` with Unity references
- **Folder structures**: `Assets/Scripts/`, `Assets/Scenes/`, `Assets/Prefabs/`

## Current Stack (Dynamic - Check Current Date First)
**IMPORTANT**: Always run `date` command and research current versions:
- **Unity**: Research latest stable Unity LTS version as of current date
- **C# Version**: Research Unity's currently supported C# version
- **Rendering**: Universal Render Pipeline (URP) - check for updates
- **Input System**: New Input System (research current version)
- **Version Control**: Git with Git LFS for large assets
- **Package Manager**: Unity Package Manager + custom packages

## Project Structure
```
Assets/
├── Features/
│   ├── Player/
│   │   ├── Scripts/
│   │   ├── Prefabs/
│   │   ├── Animations/
│   │   └── Materials/
│   ├── UI/
│   ├── Audio/
│   └── [FeatureName]/
├── Shared/
│   ├── Scripts/
│   │   ├── Managers/
│   │   ├── Utils/
│   │   └── Extensions/
│   ├── Materials/
│   ├── Textures/
│   └── Prefabs/
├── Scenes/
└── Settings/
```

## Development Standards
- **Scripts**: PascalCase.cs (e.g., PlayerController.cs)
- **Namespaces**: Use meaningful namespaces for organization
- **Prefabs**: Descriptive names with consistent naming
- **Scenes**: PascalCase scene names
- **Assets**: Organized in feature-based folders

## Core Programming Patterns
- **Component-Based**: Favor composition over inheritance
- **ScriptableObjects**: Use for data containers and configurations
- **Events**: UnityEvents or custom event systems for decoupling
- **Singletons**: Use sparingly, prefer dependency injection when possible
- **Object Pooling**: For frequently instantiated/destroyed objects

## Modern Unity Practices
```csharp
// Use ScriptableObjects for data
[CreateAssetMenu(fileName = "PlayerData", menuName = "Game/Player Data")]
public class PlayerData : ScriptableObject
{
    [SerializeField] private float moveSpeed = 5f;
    [SerializeField] private int health = 100;
    
    public float MoveSpeed => moveSpeed;
    public int Health => health;
}

// Component-based architecture
public class PlayerController : MonoBehaviour
{
    [SerializeField] private PlayerData playerData;
    [SerializeField] private Rigidbody2D rb;
    
    private PlayerInput playerInput;
    
    private void Awake()
    {
        playerInput = new PlayerInput();
        playerInput.Player.Move.performed += OnMove;
    }
    
    private void OnMove(InputAction.CallbackContext context)
    {
        Vector2 moveDirection = context.ReadValue<Vector2>();
        rb.velocity = moveDirection * playerData.MoveSpeed;
    }
}
```

## Input System Setup
- **New Input System**: Always use the new Input System
- **Input Actions**: Create Input Action assets for all controls
- **Multi-Platform**: Design controls for multiple input devices
- **Rebinding**: Allow players to customize controls
- **Touch Controls**: Mobile-specific touch input handling

## Performance Optimization
- **Object Pooling**: Pool bullets, enemies, effects
- **Sprite Atlases**: Combine sprites to reduce draw calls
- **Occlusion Culling**: Use for complex 3D scenes
- **LOD Groups**: Multiple detail levels for 3D models
- **Profiler**: Regular profiling to identify bottlenecks

## Testing Strategy
- **Unit Testing**: Unity Test Framework for game logic
- **Play Testing**: Automated play testing where possible
- **Performance Testing**: Regular profiling and optimization
- **Platform Testing**: Test on target devices early and often
- **Integration Testing**: Test feature interactions

## Asset Management
- **Version Control**: Git with Git LFS for large assets
- **Asset Organization**: Feature-based folder structure
- **Addressable Assets**: For dynamic loading and memory management
- **Asset Bundles**: Legacy support, prefer Addressables
- **Texture Compression**: Platform-specific compression settings

## UI Development
- **UI Toolkit**: For complex editor tools and runtime UI (newer projects)
- **uGUI**: For traditional game UI (established projects)
- **Canvas Groups**: For UI state management
- **Responsive Design**: Handle different screen sizes and aspect ratios
- **Accessibility**: Consider colorblind and other accessibility needs

## Audio Integration
- **Audio Mixer**: Use Audio Mixers for sound management
- **Audio Sources**: 3D spatial audio where appropriate
- **Music**: Background music with proper looping
- **SFX**: Sound effect management and pooling
- **Dynamic Audio**: Audio that responds to game state

## Mobile-Specific Considerations
- **Performance**: Optimize for lower-end mobile devices
- **Battery Usage**: Minimize battery drain
- **Touch Controls**: Intuitive touch input design
- **Screen Sizes**: Support various aspect ratios
- **Platform Guidelines**: Follow iOS and Android design guidelines

## Build & Deployment
- **Build Profiles**: Separate profiles for different platforms
- **Automated Building**: CI/CD with Unity Cloud Build or GitHub Actions
- **Platform Settings**: Optimize settings per platform
- **Testing Builds**: Regular builds for testing
- **Distribution**: Platform-specific distribution (Steam, mobile stores)

## Common Unity Packages
```json
{
  "dependencies": {
    "com.unity.inputsystem": "1.7.0",
    "com.unity.render-pipelines.universal": "14.0.8",
    "com.unity.addressables": "1.21.17",
    "com.unity.cinemachine": "2.9.7",
    "com.unity.timeline": "1.7.5",
    "com.unity.textmeshpro": "3.0.6"
  }
}
```

## Editor Tools Development
- **Custom Inspectors**: PropertyDrawers for better editor experience
- **Editor Windows**: Custom tools for designers and artists
- **Gizmos**: Visual debugging aids in scene view
- **Asset Processors**: Automatic asset processing
- **Build Pipeline**: Custom build steps and validation

## Version Control Best Practices
- **Git LFS**: Large assets (textures, audio, models)
- **.gitignore**: Proper Unity .gitignore file
- **Merge Tools**: Smart merge for Unity scenes and prefabs
- **Branch Strategy**: Feature branches with clear naming
- **Asset Locking**: For collaborative work on scenes/prefabs

## Debugging & Profiling
- **Console Logs**: Structured logging with context
- **Debug Drawing**: Gizmos and Debug.DrawLine for visual debugging
- **Profiler**: Unity Profiler for performance analysis
- **Frame Debugger**: Graphics debugging tool
- **Memory Profiler**: Memory usage analysis