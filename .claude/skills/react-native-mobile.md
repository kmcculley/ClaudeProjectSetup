# React Native Mobile Application Skill

Specialized skill for creating cross-platform mobile applications using React Native.

## Auto-Activation
- **File patterns**: `package.json` with React Native dependencies
- **Project indicators**: `metro.config.js`, `android/`, `ios/`, `App.tsx`
- **Commands**: `react-native`, `npx react-native`

## Current Stack (Dynamic - Check Current Date First)
**IMPORTANT**: Always run `date` command and research current versions:
- **React Native**: Research latest stable React Native version as of current date
- **TypeScript**: Research latest stable TypeScript version
- **Navigation**: Research latest React Navigation version
- **State Management**: Research current React Native state management options
- **UI Components**: Research current React Native UI libraries
- **Build Tool**: Metro bundler (check for updates)
- **Package Manager**: npm

## Project Structure
```
ProjectName/
├── src/
│   ├── features/
│   │   ├── authentication/
│   │   │   ├── components/
│   │   │   ├── screens/
│   │   │   ├── hooks/
│   │   │   └── types/
│   │   └── [feature-name]/
│   ├── shared/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── utils/
│   │   ├── types/
│   │   └── constants/
│   ├── navigation/
│   ├── assets/
│   └── App.tsx
├── android/
├── ios/
└── package.json
```

## Development Standards
- **Components**: PascalCase.tsx (e.g., UserProfile.tsx)
- **Screens**: PascalCase + "Screen" suffix (UserProfileScreen.tsx)
- **Hooks**: camelCase starting with "use" (useUserData.ts)
- **Navigation**: Type-safe navigation with TypeScript
- **Styling**: StyleSheet.create() for performance

## Component Patterns
- **Functional Components**: Always use function components with hooks
- **Platform Specific**: Use Platform.select() or platform files (.ios.tsx/.android.tsx)
- **Responsive Design**: Handle different screen sizes and orientations
- **Accessibility**: Proper accessibility props for screen readers

## Navigation Setup
```typescript
// Type-safe navigation
export type RootStackParamList = {
  Home: undefined;
  Profile: { userId: string };
  Settings: undefined;
};

// Navigation hook
export function useTypedNavigation() {
  return useNavigation<NavigationProp<RootStackParamList>>();
}
```

## State Management Strategy
- **Local State**: useState/useReducer for component state
- **Global State**: Zustand for app-wide state
- **Server State**: React Query for API data caching
- **Persistent State**: AsyncStorage for device storage
- **Secure Storage**: Keychain (iOS) / Keystore (Android) for sensitive data

## Styling Approach
```typescript
// Consistent styling patterns
const styles = StyleSheet.create({
  container: {
    flex: 1,
    backgroundColor: '#ffffff',
    padding: 16,
  },
  title: {
    fontSize: 24,
    fontWeight: 'bold',
    marginBottom: 16,
  },
});

// Theme system
export const theme = {
  colors: {
    primary: '#007AFF',
    secondary: '#5856D6',
    background: '#F2F2F7',
    text: '#000000',
  },
  spacing: {
    xs: 4,
    sm: 8,
    md: 16,
    lg: 24,
    xl: 32,
  },
};
```

## Platform-Specific Features
- **Permissions**: Handle camera, location, storage permissions
- **Native Modules**: Integration with device APIs
- **Push Notifications**: Firebase Cloud Messaging setup
- **Deep Linking**: URL scheme and universal links
- **Biometric Authentication**: Touch ID, Face ID, fingerprint

## Performance Optimization
- **Images**: Optimize image sizes and use lazy loading
- **Lists**: FlatList with proper keyExtractor and getItemLayout
- **Memory**: Monitor memory usage and avoid memory leaks
- **Bundle Size**: Analyze bundle and implement code splitting
- **Animations**: Use native animations with React Native Reanimated

## Testing Setup
- **Unit Testing**: Jest + React Native Testing Library
- **Component Testing**: Test user interactions and state changes
- **E2E Testing**: Detox for automated testing
- **Device Testing**: Test on both iOS and Android devices
- **Coverage**: 70% minimum for business logic

## API Integration
```typescript
// API client with error handling
export const apiClient = {
  baseURL: 'https://your-api.com',
  
  async request<T>(endpoint: string, options?: RequestOptions): Promise<T> {
    try {
      const response = await fetch(`${this.baseURL}${endpoint}`, {
        ...options,
        headers: {
          'Content-Type': 'application/json',
          ...options?.headers,
        },
      });
      
      if (!response.ok) {
        throw new Error(`API Error: ${response.status}`);
      }
      
      return response.json();
    } catch (error) {
      console.error('API Request failed:', error);
      throw error;
    }
  },
};
```

## Development Workflow
- **Metro**: Use Metro bundler with proper configuration
- **Debugging**: Flipper or React Native Debugger
- **Hot Reloading**: Fast Refresh for development
- **Code Push**: Consider CodePush for over-the-air updates
- **Environment**: Separate development, staging, production configs

## Build & Deployment
- **Android**: Generate APK/AAB for Play Store
- **iOS**: Archive and upload to App Store Connect  
- **Signing**: Proper certificate and provisioning profile management
- **CI/CD**: GitHub Actions for automated building and testing
- **Version Management**: Semantic versioning with automated incrementing

## Security Considerations
- **API Keys**: Never expose API keys in client code
- **Data Storage**: Encrypt sensitive data in AsyncStorage
- **Network Security**: Use HTTPS and certificate pinning
- **Code Obfuscation**: Minimize reverse engineering risks
- **App Transport Security**: Configure ATS for iOS

## Common Libraries Integration
```json
{
  "dependencies": {
    "@react-navigation/native": "latest",
    "@react-navigation/stack": "latest",
    "react-native-async-storage": "latest",
    "react-native-keychain": "latest",
    "react-native-vector-icons": "latest",
    "@react-native-community/netinfo": "latest"
  }
}
```

## Accessibility Standards
- **Screen Readers**: Proper accessibilityLabel and accessibilityHint
- **Touch Targets**: Minimum 44pt touch targets
- **Color Contrast**: Meet accessibility contrast requirements  
- **Voice Control**: Support for voice navigation
- **Reduced Motion**: Respect reduced motion preferences