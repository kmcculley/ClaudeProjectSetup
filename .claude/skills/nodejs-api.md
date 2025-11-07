# Node.js Express API Skill

Specialized skill for creating REST APIs using Node.js with Express, designed for containerized deployment.

## Auto-Activation
- **File patterns**: `package.json` with Express dependencies
- **Project indicators**: `server.js`, `app.js`, Express routes
- **Folder structures**: `routes/`, `middleware/`, `controllers/`

## Current Stack (Dynamic - Check Current Date First)
**IMPORTANT**: Always run `date` command and research current versions:
- **Node.js**: Research latest LTS Node.js version as of current date
- **Express**: Research latest stable Express version
- **TypeScript**: Research latest stable TypeScript version
- **Database**: Direct connection to your local infrastructure
- **Validation**: Research current validation libraries (Zod, Joi, etc.)
- **Authentication**: Research current JWT best practices and libraries
- **Package Manager**: npm

## Project Structure
```
project-name/
├── src/
│   ├── features/
│   │   ├── authentication/
│   │   │   ├── controllers/
│   │   │   ├── routes/
│   │   │   ├── middleware/
│   │   │   └── types/
│   │   └── [feature-name]/
│   ├── shared/
│   │   ├── middleware/
│   │   ├── utils/
│   │   ├── types/
│   │   └── database/
│   ├── app.ts
│   └── server.ts
├── Dockerfile
├── package.json
└── .env.example
```

## Development Standards
- **Files**: PascalCase.ts (e.g., UserController.ts)
- **Routes**: kebab-case endpoints (/api/user-profiles)
- **Environment**: .env files with validation
- **Error Handling**: Centralized error middleware
- **Logging**: Structured logging with correlation IDs

## API Design Patterns
- **RESTful**: Follow REST conventions for endpoints
- **Versioning**: /api/v1/ prefix for version management  
- **Status Codes**: Proper HTTP status code usage
- **Response Format**: Consistent JSON response structure
- **Pagination**: Cursor-based or offset pagination

## Request/Response Flow
```typescript
// Standard response format
interface ApiResponse<T> {
  success: boolean;
  data?: T;
  error?: string;
  message?: string;
}

// Controller pattern
export class UserController {
  async getUser(req: Request, res: Response): Promise<void> {
    try {
      const user = await this.userService.findById(req.params.id);
      res.json({ success: true, data: user });
    } catch (error) {
      throw new AppError('User not found', 404);
    }
  }
}
```

## Database Integration
- **Connection**: Direct connection to your local database servers
- **Migration**: Database versioning and migration scripts
- **Connection Pooling**: Proper connection pool management
- **Transactions**: Database transaction support
- **Query Optimization**: Indexing and query performance monitoring

## Security Implementation
- **Authentication**: JWT tokens with secure refresh mechanism
- **Authorization**: Role-based access control (RBAC)
- **Input Validation**: Zod schemas for all endpoints
- **Rate Limiting**: Express rate limiter middleware
- **CORS**: Proper CORS configuration for your domains
- **Security Headers**: Helmet.js for security headers

## Testing Setup
- **Unit Testing**: Jest with SuperTest for API testing
- **Integration Testing**: Database integration tests
- **E2E Testing**: Playwright for complete user flows
- **Coverage**: 70% minimum, 80% for business logic
- **Test Files**: ComponentName.test.ts

## Environment Configuration
```typescript
// Environment validation with Zod
const envSchema = z.object({
  NODE_ENV: z.enum(['development', 'production', 'test']),
  PORT: z.string().transform(Number),
  DATABASE_URL: z.string(),
  JWT_SECRET: z.string(),
  JWT_REFRESH_SECRET: z.string(),
});

export const env = envSchema.parse(process.env);
```

## Error Handling
```typescript
// Centralized error handling
export class AppError extends Error {
  constructor(
    public message: string,
    public statusCode: number = 500,
    public isOperational: boolean = true
  ) {
    super(message);
    this.name = this.constructor.name;
    Error.captureStackTrace(this, this.constructor);
  }
}

// Global error middleware
export const errorHandler: ErrorRequestHandler = (err, req, res, next) => {
  const { statusCode = 500, message } = err;
  
  logger.error('API Error:', { error: err, req: req.url });
  
  res.status(statusCode).json({
    success: false,
    error: message,
  });
};
```

## Containerization
```dockerfile
FROM node:20-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci --only=production

FROM node:20-alpine AS runtime
WORKDIR /app
COPY --from=builder /app/node_modules ./node_modules
COPY . .
EXPOSE 3000
CMD ["npm", "start"]
```

## Performance Optimization
- **Caching**: Redis for session and data caching
- **Compression**: Gzip compression middleware
- **Connection Pooling**: Optimize database connections
- **Memory Management**: Monitor memory usage and garbage collection
- **Load Testing**: Regular performance testing

## Monitoring & Logging
- **Structured Logging**: JSON format with correlation IDs
- **Health Checks**: /health endpoint for container orchestration
- **Metrics**: Basic performance metrics collection
- **Error Tracking**: Centralized error logging
- **Request Logging**: HTTP request/response logging

## Deployment Strategy
- **Containerization**: Docker multi-stage builds
- **Environment**: Environment-specific configuration
- **Secrets Management**: Environment variables for secrets
- **Database Migrations**: Automated migration on deployment
- **Health Checks**: Container health check endpoints