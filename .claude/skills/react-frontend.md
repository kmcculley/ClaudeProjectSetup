# React Frontend Application Skill

Specialized skill for creating modern React applications with TypeScript and static hosting deployment.

## Auto-Activation
- **File patterns**: `package.json` with React dependencies
- **Project indicators**: `src/App.tsx`, `public/index.html`, React scripts
- **Folder structures**: `src/components/`, `src/features/`, `src/hooks/`

## Current Stack (Dynamic - Check Current Date First)
**IMPORTANT**: Always run `date` command and research current versions:
- **React**: Research latest stable React version as of current date
- **TypeScript**: Research latest stable TypeScript version
- **Build Tool**: Research latest stable Vite version
- **Styling**: Research current CSS-in-JS or styling solutions
- **State Management**: Research current React state management options (Zustand, React Query, etc.)
- **Routing**: Research latest React Router version
- **Package Manager**: npm

## Project Structure
```
project-name/
├── src/
│   ├── features/
│   │   ├── authentication/
│   │   │   ├── components/
│   │   │   ├── hooks/
│   │   │   └── types/
│   │   └── [feature-name]/
│   ├── shared/
│   │   ├── components/
│   │   ├── hooks/
│   │   ├── utils/
│   │   └── types/
│   ├── App.tsx
│   └── main.tsx
├── public/
├── package.json
└── vite.config.ts
```

## Development Standards
- **Components**: PascalCase.tsx (e.g., UserProfile.tsx)
- **Hooks**: camelCase starting with "use" (useUserData.ts)
- **Types**: PascalCase with .types.ts suffix
- **Utilities**: camelCase.utils.ts
- **Constants**: UPPER_SNAKE_CASE

## Component Patterns
- **Function Components**: Always use function components with hooks
- **Props Interface**: Define props interface for each component
- **Default Props**: Use defaultProps or default parameters
- **Memo**: Use React.memo for expensive components
- **Error Boundaries**: Implement for error handling

## State Management Strategy
- **Local State**: useState/useReducer for component-specific state
- **Server State**: React Query/TanStack Query for API data
- **Global State**: Zustand for cross-component shared state
- **Form State**: React Hook Form for form management

## Testing Setup
- **Unit Testing**: Jest + React Testing Library
- **E2E Testing**: Playwright for user flows  
- **Component Testing**: Focus on user interactions, not implementation
- **Coverage**: 70% minimum, 80% for business logic
- **Test Files**: ComponentName.test.tsx

## Code Quality Tools
```json
{
  "devDependencies": {
    "@typescript-eslint/eslint-plugin": "latest",
    "@typescript-eslint/parser": "latest",
    "eslint": "latest",
    "eslint-plugin-react": "latest",
    "eslint-plugin-react-hooks": "latest",
    "prettier": "latest",
    "husky": "latest",
    "lint-staged": "latest"
  }
}
```

## Performance Optimization
- **Code Splitting**: React.lazy() for route-based splitting
- **Bundle Analysis**: Vite bundle analyzer for optimization
- **Images**: Lazy loading with proper alt attributes  
- **Memoization**: useMemo/useCallback for expensive operations
- **Virtual Scrolling**: For large lists

## API Integration
```typescript
// API client with error handling
export const apiClient = axios.create({
  baseURL: process.env.VITE_API_BASE_URL,
  timeout: 10000,
});

// Custom hook pattern
export function useUserData(id: string) {
  return useQuery({
    queryKey: ['user', id],
    queryFn: () => apiClient.get(`/users/${id}`),
  });
}
```

## Static Hosting Deployment
- **Build Optimization**: Vite production build with compression
- **Environment Variables**: VITE_ prefix for client-side variables
- **Hosting**: Vercel, Netlify, or Azure Static Web Apps
- **CI/CD**: GitHub Actions with automatic deployment on main branch
- **Caching**: Proper cache headers for assets

## Security Considerations
- **Environment Variables**: Never expose secrets in client code
- **XSS Protection**: Sanitize user input, use dangerouslySetInnerHTML carefully
- **CSRF**: Implement proper token handling for forms
- **Content Security Policy**: Configure CSP headers
- **HTTPS**: Always use HTTPS in production

## Accessibility Standards
- **ARIA**: Proper ARIA labels and roles
- **Keyboard Navigation**: Tab order and keyboard shortcuts
- **Screen Readers**: Semantic HTML and proper labels  
- **Color Contrast**: Meet WCAG guidelines
- **Focus Management**: Visible focus indicators