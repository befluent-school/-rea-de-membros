# Be Fluent School - Language Learning Management System

## Overview

Be Fluent School is a comprehensive language learning management system built with a modern full-stack architecture. The application serves as a platform for managing language education with role-based access for administrators, teachers, and students. It features a sophisticated UI built with React and shadcn/ui components, backed by a Node.js Express server with PostgreSQL database integration.

## User Preferences

Preferred communication style: Simple, everyday language.

## Recent Updates (Phase 3 - December 2024)

### Rescheduling System Implementation
- **Class Rescheduling**: Students can request rescheduling with teacher approval workflow
- **Conflict Detection**: Automatic validation of time conflicts and teacher availability
- **Approval Process**: Teachers and admins can approve/reject reschedule requests
- **Lead Time Validation**: Minimum 2-hour advance notice for reschedule requests
- **Cancellation System**: Students and teachers can cancel classes with minimum 1-hour notice

### Security Enhancements (Phase 3.5 - September 2025)
- **CSRF Protection**: Complete Cross-Site Request Forgery protection on all state-changing endpoints (POST/PUT)
- **Atomic Operations**: Database transactions for reschedule approvals to prevent race conditions
- **Enhanced Authorization**: Strengthened role-based access control and ownership verification
- **Secure Tokens**: JWT with httpOnly cookies and SameSite=strict for maximum security
- **Input Validation**: Comprehensive Zod schema validation on all user inputs
- **Frontend Security**: React hooks for CSRF token management and secure API calls

### Technical Improvements
- **Type Safety**: Shared type definitions across frontend components
- **API Security**: Enhanced authorization with role-based access control and IDOR protection
- **Data Validation**: Server-side validation for all user inputs with business rule enforcement
- **Error Handling**: Comprehensive error responses with user-friendly messages
- **Frontend Integration**: Toast notifications and reactive UI updates
- **Atomic Database Operations**: Transaction-based operations for critical workflows

### Performance & Scalability (Phase 1.3 - September 2025)
- **Database Optimization**: 29 strategic performance indexes covering all critical query patterns
- **Composite Indexes**: Advanced multi-column indexes for complex queries (student flows, teacher schedules, reschedule listings)
- **Query Performance**: Optimized dashboard KPIs and scheduling queries for enterprise-scale performance
- **Development Flexibility**: Dual-mode operation with automatic PostgreSQL/MemStorage detection
- **Zero-Config Development**: Full development capabilities without database setup requirements
- **Index Coverage**: Complete optimization for student dashboards, teacher availability, class scheduling, and progress tracking

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript and Vite for fast development and building
- **UI Framework**: shadcn/ui component library with Radix UI primitives
- **Styling**: Tailwind CSS with custom design system featuring Be Fluent School brand colors (blue #001929, red #b00001)
- **State Management**: TanStack React Query for server state management
- **Routing**: React Router with protected routes based on authentication status
- **Forms**: React Hook Form with Zod validation for type-safe form handling
- **Class Management**: Complete booking, rescheduling, and cancellation system with approval workflows

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database ORM**: Drizzle ORM for type-safe database operations
- **API Pattern**: RESTful API design with centralized route registration
- **Error Handling**: Global error middleware with structured error responses
- **Development**: Hot module replacement with Vite integration for seamless development
- **Business Logic**: Complete class scheduling system with conflict detection, availability management, and approval workflows

### Authentication & Authorization
- **Provider**: Supabase Authentication with session persistence
- **Storage**: Local storage for session management with auto-refresh tokens
- **Role-Based Access**: Three-tier role system (admin, teacher, student) with protected routes
- **Session Management**: Automatic session validation and redirect logic
- **Security**: JWT with httpOnly cookies, role-based authorization, ownership verification, IDOR protection

### Database Design
- **Primary Database**: PostgreSQL with Neon serverless hosting
- **Schema Management**: Drizzle Kit for migrations and schema evolution
- **Connection**: Connection pooling with @neondatabase/serverless
- **Type Safety**: Full type safety from database to frontend using Drizzle's TypeScript integration
- **Performance Indexes**: 29 optimized indexes including composites for scalable query performance
- **Index Strategy**: Strategic coverage of student flows, teacher queries, reschedule workflows, and dashboard KPIs

### Data Storage Strategy
- **Production**: PostgreSQL database for persistent data storage
- **Development**: In-memory storage implementation for rapid prototyping
- **Abstraction**: Storage interface pattern allowing easy switching between storage backends
- **Scalability**: Designed to support multiple storage implementations

### Component Architecture
- **Design System**: Comprehensive UI component library with consistent styling
- **Accessibility**: Built on Radix UI primitives ensuring WCAG compliance
- **Responsive Design**: Mobile-first approach with adaptive layouts
- **Theming**: CSS custom properties for dynamic theme switching
- **Reusability**: Modular component structure with proper separation of concerns

### External Dependencies

#### Database Services
- **Neon Database**: Serverless PostgreSQL hosting with connection pooling
- **Drizzle ORM**: Modern TypeScript ORM with excellent developer experience

#### Authentication Services
- **Supabase**: Complete authentication solution with user management, session handling, and security features

#### UI/UX Libraries
- **Radix UI**: Accessible component primitives for complex UI interactions
- **Tailwind CSS**: Utility-first CSS framework for rapid styling
- **Lucide React**: Comprehensive icon library with consistent design
- **shadcn/ui**: Pre-built component library with customizable design tokens

#### Development Tools
- **Vite**: Fast build tool with hot module replacement and optimized production builds
- **TypeScript**: Static type checking for enhanced developer experience and code reliability
- **ESBuild**: Fast JavaScript bundler for production builds

#### State Management & API
- **TanStack React Query**: Powerful data fetching and caching library for server state
- **React Hook Form**: Performant form library with minimal re-renders
- **Zod**: TypeScript-first schema validation for runtime type checking