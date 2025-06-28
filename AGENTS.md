# Vite/React + Express App Guidelines

## Default Development State

**ASSUMPTION**: Both client and server are running by default:
- **Client**: `http://localhost:3000` (Vite dev server with hot reload)
- **Server**: `http://localhost:8080` (Express server with nodemon)
- **Ready**: User can immediately access the client preview

## Quick Commands

### Development
```bash
# Start both services (if not running)
cd server && npm run dev    # Terminal 1
cd client && npm run dev    # Terminal 2

# Install dependencies
npm install && cd client && npm install && cd ../server && npm install
```

### Production
```bash
cd client && npm run build    # Build client
cd server && npm run build    # Compile server
cd server && npm run start    # Start production server
```

## Code Standards

### TypeScript (Both)
- Use TypeScript strict mode, avoid `any` type
- Prefer `const` over `let`, avoid unnecessary destructuring
- Use descriptive variable names, avoid `else` statements unless necessary
- camelCase for variables/functions, PascalCase for classes/components

### Frontend (React)
- Functional components with hooks, proper prop typing
- ES module imports, relative paths for local modules
- Tailwind CSS classes instead of custom CSS
- Component-based file organization in `src/`

### Backend (Express)
- ES module `import` statements, organize by feature/route
- Express middleware patterns, proper error handling
- Environment variables for configuration, RESTful conventions
- Route-based file organization in `src/`

## Architecture

```
client/          # React + Vite + Tailwind
├── src/         # Components and pages
├── public/      # Static assets
└── dist/        # Built assets (generated)

server/          # Express + TypeScript
├── src/         # Routes and middleware  
└── dist/        # Compiled JS (generated)
```

**Communication**: HTTP requests from React to Express API
