# Travel Website Architecture

## Overview

This is a modern travel website application built with a React frontend and Express.js backend. The application allows users to explore travel destinations, view detailed country information, check off travel preparation items, and browse an interactive gallery. It follows a monorepo structure with shared type definitions and uses modern web technologies for both client and server components.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for client-side routing
- **State Management**: TanStack React Query for server state management
- **UI Components**: Radix UI primitives with shadcn/ui component library
- **Styling**: Tailwind CSS with CSS variables for theming
- **Build Tool**: Vite for development and production builds

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Runtime**: Node.js with ES modules
- **Database Setup**: Drizzle ORM configured for PostgreSQL (currently using in-memory storage)
- **API Design**: RESTful API with JSON responses
- **Development**: Hot reloading with Vite middleware integration

### Data Storage Strategy
- **Current Implementation**: In-memory storage with mock data for countries and gallery images
- **Future Database**: PostgreSQL configured via Drizzle ORM (schema defined but not yet connected)
- **Schema Management**: Centralized schema definitions using Zod for validation

## Key Components

### Frontend Components
1. **Layout Components**
   - Header with theme toggle and navigation
   - Footer with links and social media
   - ThemeProvider for dark/light mode switching

2. **Feature Components**
   - DestinationCard: Displays country information with type badges
   - CountryModal: Detailed country information in a modal dialog
   - FilterSection: Category-based filtering for destinations
   - TravelChecklist: Interactive checklist with local storage persistence
   - InteractiveGallery: Image gallery with hover effects
   - HeroSection: Landing section with search functionality

3. **UI Foundation**
   - Complete shadcn/ui component library
   - Consistent theming with CSS custom properties
   - Responsive design patterns

### Backend Components
1. **API Routes** (`/api/countries`, `/api/countries/:id`, `/api/gallery`)
2. **Storage Interface**: Abstracted storage layer for easy database integration
3. **Request Logging**: Custom middleware for API request monitoring
4. **Error Handling**: Centralized error handling middleware

### Shared Components
- **Schema Definitions**: Zod schemas for type safety across client/server
- **Type Exports**: TypeScript types generated from schemas

## Data Flow

1. **Client Requests**: React components use TanStack React Query for data fetching
2. **API Layer**: Express routes handle HTTP requests and call storage methods
3. **Data Storage**: Currently in-memory, designed for easy PostgreSQL integration
4. **Response Flow**: JSON responses with error handling and request logging
5. **Client State**: React Query manages server state, local storage for user preferences

## External Dependencies

### Frontend Dependencies
- **UI Framework**: React, Radix UI primitives, Lucide icons
- **Data Fetching**: TanStack React Query
- **Styling**: Tailwind CSS, class-variance-authority for component variants
- **Forms**: React Hook Form with Zod resolvers
- **Date Handling**: date-fns
- **Carousel**: Embla Carousel

### Backend Dependencies
- **Database**: Drizzle ORM, @neondatabase/serverless
- **Session Management**: connect-pg-simple (prepared for PostgreSQL sessions)
- **Development**: tsx for TypeScript execution

### Development Tools
- **Build**: Vite with React plugin
- **TypeScript**: Strict configuration with path mapping
- **Linting**: ESM modules, bundler module resolution
- **Replit Integration**: Custom plugins for development environment

## Deployment Strategy

### Development Setup
- **Database**: Drizzle configured for PostgreSQL with migrations
- **Environment**: Vite dev server with Express API integration
- **Hot Reloading**: Full-stack hot reloading with Vite middleware

### Production Build
- **Frontend**: Vite build to `dist/public`
- **Backend**: esbuild bundling to `dist/index.js`
- **Static Assets**: Served from Express in production
- **Environment Variables**: DATABASE_URL required for PostgreSQL connection

### Key Architectural Decisions

1. **Monorepo Structure**: Shared types and schemas between client and server for consistency
2. **Storage Abstraction**: Interface-based storage design allows easy transition from in-memory to PostgreSQL
3. **Component Architecture**: Composition-based React components with consistent theming
4. **Build Strategy**: Separate bundling for client (Vite) and server (esbuild) with optimized outputs
5. **Type Safety**: End-to-end TypeScript with Zod validation for runtime type checking
6. **State Management**: Server state via React Query, local state via React hooks, persistent state via localStorage