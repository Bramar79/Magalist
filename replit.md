# Hospital Inventory Management System

## Overview

This is a full-stack hospital inventory management system built with React, Express.js, and PostgreSQL. The application allows healthcare professionals to manage medical supplies, track inventory levels, and create restocking lists. It features a modern UI with shadcn/ui components and uses Drizzle ORM for database operations.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **UI Library**: shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom medical theme variables
- **State Management**: TanStack React Query for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Form Handling**: React Hook Form with Zod validation

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **Storage**: DatabaseStorage implementation for persistent data
- **API Design**: RESTful API with JSON responses
- **Development**: Hot reload with tsx and Vite integration

### Database Schema
The application uses three main tables:
- `medical_supplies`: Core inventory items with quantity tracking
- `restocking_lists`: Purchase orders and restocking requests
- `restocking_list_items`: Items within each restocking list

## Key Components

### Medical Supply Management
- Inventory tracking with quantity thresholds (min/max quantities)
- Category-based organization (surgical, medication, PPE, diagnostic, emergency)
- Status calculation (available, low_stock, out_of_stock)
- Search and filtering capabilities
- Image support for visual identification

### Restocking System
- Create restocking lists from selected supplies
- Drag-and-drop reordering of items
- Quantity adjustment for each item
- List status tracking (draft, sent, completed)
- Print-ready formatting for purchase orders

### User Interface
- Responsive design optimized for hospital environments
- Medical-themed color scheme with status indicators
- Grid and list view options for inventory
- Real-time inventory statistics dashboard
- Toast notifications for user feedback

## Data Flow

1. **Inventory Display**: Frontend queries `/api/medical-supplies` with optional filters
2. **Search/Filter**: Parameters passed as query strings for server-side filtering
3. **Item Selection**: Client-side state management for multi-select operations
4. **Restocking**: Selected items sent to `/api/restocking-lists` to create new orders
5. **Real-time Updates**: React Query automatically refetches data after mutations

## External Dependencies

### Database
- **Neon Database**: Serverless PostgreSQL provider
- **Connection**: Via `@neondatabase/serverless` driver
- **Migrations**: Managed through Drizzle Kit

### UI Components
- **Radix UI**: Accessible component primitives
- **Lucide Icons**: Consistent icon library
- **Tailwind CSS**: Utility-first styling framework

### Development Tools
- **Replit Integration**: Custom cartographer and error modal plugins
- **TypeScript**: Strong typing across the full stack
- **ESLint**: Code quality and consistency

## Deployment Strategy

### Development Mode
- Vite dev server for frontend with HMR
- Express server with tsx for TypeScript execution
- Concurrent development with shared port setup
- Real-time error overlays and debugging tools

### Production Build
- Vite builds frontend to `dist/public`
- esbuild bundles server code to `dist/index.js`
- Static file serving from Express for SPA routing
- Environment-based configuration for database connections

### Database Management
- Schema defined in `shared/schema.ts` for type safety
- Migrations generated and applied via Drizzle Kit
- Connection pooling through Neon's serverless driver

## User Preferences

Preferred communication style: Simple, everyday language.

## Changelog

Changelog:
- July 04, 2025. Initial setup
- July 04, 2025. Completed full hospital inventory management system with Italian interface, visual supply display, filtering, search, multi-select, and restocking list creation with print functionality
- July 04, 2025. Successfully migrated from in-memory storage to PostgreSQL database with Neon Database provider, including schema creation and data seeding