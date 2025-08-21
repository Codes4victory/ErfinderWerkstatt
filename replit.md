# InnoConnect - Innovation Networking Platform

## Overview

InnoConnect is a full-stack web application designed as a networking platform for innovators, entrepreneurs, and professionals to share ideas, ask questions, and post job opportunities. The platform serves as a community hub where users can create posts categorized as offers (idea sharing), questions (seeking advice), or jobs (hiring opportunities). Users can filter and search through posts based on type, content, and geographical location via postal codes.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React with TypeScript for type safety and developer experience
- **Routing**: Wouter for lightweight client-side routing
- **State Management**: TanStack Query (React Query) for server state management and caching
- **UI Components**: Radix UI primitives with shadcn/ui component library for consistent design
- **Styling**: Tailwind CSS with custom design system including CSS variables for theming
- **Forms**: React Hook Form with Zod validation for type-safe form handling
- **Build Tool**: Vite for fast development and optimized production builds

**Design Rationale**: The frontend uses modern React patterns with a component-based architecture. Radix UI provides accessible, unstyled components while shadcn/ui offers pre-styled variants. This combination ensures both accessibility and design consistency while maintaining customization flexibility.

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript for full-stack type safety
- **API Design**: RESTful API with conventional HTTP methods
- **Data Storage**: In-memory storage implementation (MemStorage) with interface abstraction
- **Validation**: Zod schemas shared between frontend and backend for consistent data validation
- **Development**: Hot module replacement via Vite integration for seamless development experience

**Design Rationale**: The backend follows a clean architecture pattern with storage abstraction, allowing easy migration from in-memory storage to persistent databases. Shared validation schemas eliminate client-server validation discrepancies.

### Data Storage Architecture
- **Current Implementation**: In-memory storage with Map-based data structures
- **Schema Definition**: Drizzle ORM schema ready for PostgreSQL migration
- **Database Prepared**: Configuration exists for PostgreSQL via Neon Database
- **Migration Strategy**: Drizzle migrations setup with schema-first approach

**Design Rationale**: The abstracted storage interface allows seamless transition from development (in-memory) to production (PostgreSQL) without changing business logic. Drizzle provides type-safe database operations with SQL-like syntax.

### Authentication & Authorization
- **Current State**: No authentication system implemented
- **Session Management**: Express session configuration present but not actively used
- **Future Ready**: PostgreSQL session store configured for when authentication is added

**Design Rationale**: The application currently operates as an open platform but includes session infrastructure for future authentication implementation.

### Development & Build Process
- **Development**: Concurrent frontend (Vite) and backend (tsx) development servers
- **Type Checking**: Shared TypeScript configuration across frontend, backend, and shared modules
- **Code Organization**: Monorepo structure with shared schemas and types
- **Production Build**: Vite for frontend assets, esbuild for backend bundling

**Design Rationale**: The monorepo structure with shared code eliminates duplication and ensures consistency. The build process is optimized for both development speed and production performance.

## External Dependencies

### Core Framework Dependencies
- **React Ecosystem**: React 18+ with modern hooks and concurrent features
- **Express.js**: Mature Node.js web framework for REST API development
- **TypeScript**: Full-stack type safety and enhanced developer experience

### UI and Styling
- **Radix UI**: Comprehensive collection of accessible, unstyled UI components
- **Tailwind CSS**: Utility-first CSS framework with custom design system integration
- **shadcn/ui**: Pre-built component library built on Radix UI primitives
- **Lucide React**: Icon library for consistent iconography

### Data Management
- **TanStack Query**: Powerful data synchronization for React applications
- **Drizzle ORM**: TypeScript-first ORM for PostgreSQL integration
- **Zod**: Runtime type validation and parsing library

### Database & Storage
- **Neon Database**: Serverless PostgreSQL provider for production deployment
- **PostgreSQL**: Relational database for persistent data storage (configured but not yet active)

### Development Tools
- **Vite**: Next-generation frontend build tool with HMR
- **esbuild**: Fast JavaScript bundler for backend production builds
- **tsx**: TypeScript execution environment for development

### Form Handling
- **React Hook Form**: Performant forms library with minimal re-renders
- **Hookform Resolvers**: Zod integration for form validation

### Utility Libraries
- **date-fns**: Modern JavaScript date utility library
- **clsx & tailwind-merge**: Conditional CSS class utilities
- **nanoid**: Compact URL-safe unique string ID generator