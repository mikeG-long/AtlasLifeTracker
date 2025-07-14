# Daily Wins Dashboard - Replit Configuration

## Overview

This is a full-stack productivity dashboard application built with React, Express, and PostgreSQL. The application provides a personal productivity companion with features for task management, daily wins tracking, thoughts journaling, fixed rules display, daily structure timeline, and AI-powered insights.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

The application follows a monorepo structure with clear separation between client and server code:

### Frontend Architecture
- **Framework**: React with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **UI Library**: Radix UI components with shadcn/ui styling system
- **Styling**: Tailwind CSS with custom glass morphism design
- **State Management**: TanStack Query for server state management
- **Routing**: Wouter for lightweight client-side routing
- **Animations**: Framer Motion for smooth UI transitions

### Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (@neondatabase/serverless)
- **Session Management**: Express sessions with PostgreSQL storage
- **API Design**: RESTful API endpoints

### Database Schema
The application uses PostgreSQL with the following main entities:
- **Users**: User authentication and profile data
- **Tasks**: Todo items with completion status
- **Wins**: Daily achievements and accomplishments
- **Thoughts**: Journal entries for personal reflection
- **Rules**: Fixed personal rules and principles
- **Timeline Blocks**: Daily structure and schedule items

## Key Components

### Frontend Components
- **Dashboard**: Main application layout with grid-based responsive design
- **AnimatedChecklist**: Interactive task management with animations
- **DailyWins**: Achievement tracking with celebration animations
- **ThoughtsJournal**: Terminal-style journaling interface
- **FixedRules**: Display of personal rules with color-coded categories
- **DailyStructure**: Timeline visualization of daily schedule
- **AIRecap**: Simulated AI insights and motivational content

### Backend Components
- **Storage Layer**: Abstract storage interface with PostgreSQL database implementation
- **Routes**: RESTful API endpoints for all CRUD operations
- **Schema**: Drizzle ORM schema definitions with Zod validation
- **Database Layer**: PostgreSQL connection with Neon Database driver
- **Development Server**: Vite integration for hot module replacement

## Data Flow

1. **Client Requests**: React components use TanStack Query for API calls
2. **API Layer**: Express routes handle HTTP requests and validate data
3. **Business Logic**: Controllers process requests and interact with storage
4. **Data Persistence**: Drizzle ORM manages database operations
5. **Response**: JSON responses are cached by TanStack Query
6. **UI Updates**: React components re-render with optimistic updates

## External Dependencies

### Core Dependencies
- **@neondatabase/serverless**: PostgreSQL database connectivity
- **drizzle-orm**: Type-safe database operations
- **@tanstack/react-query**: Server state management
- **@radix-ui/***: Accessible UI primitives
- **framer-motion**: Animation library
- **tailwindcss**: Utility-first CSS framework

### Development Dependencies
- **vite**: Build tool and development server
- **typescript**: Type checking and compilation
- **tsx**: TypeScript execution for development
- **esbuild**: Fast bundler for production builds

## Deployment Strategy

### Development Setup
- Uses Vite development server with HMR
- Express server runs on separate port with API proxy
- TypeScript compilation with strict type checking
- Drizzle migrations for database schema management

### Production Build
- Vite builds optimized React bundle to `dist/public`
- esbuild bundles server code to `dist/index.js`
- Static files served by Express in production
- Database migrations run via `drizzle-kit push`

### Environment Configuration
- `DATABASE_URL` required for PostgreSQL connection
- `NODE_ENV` determines development vs production mode
- Drizzle configuration points to shared schema file
- Tailwind CSS configured for client-side processing

### Key Build Commands
- `npm run dev`: Start development server with hot reload
- `npm run build`: Build both client and server for production
- `npm run start`: Start production server
- `npm run db:push`: Apply database schema changes

The application is designed to be easily deployable on platforms like Replit, with automatic database provisioning and seamless development-to-production workflow.

## Recent Changes

### January 14, 2025
- **Database Integration**: Successfully migrated from in-memory storage to PostgreSQL database
  - Created `server/db.ts` with Neon Database connection
  - Updated `server/storage.ts` to use DatabaseStorage with Drizzle ORM
  - Applied database schema with `npm run db:push`
  - Populated database with default user, rules, and timeline blocks
  - Fixed TypeScript errors for proper null handling
  - All productivity features now persist data permanently

- **WAR ROOM Transformation**: Completely redesigned the dashboard experience
  - Changed title from "Daily Wins Dashboard" to "WAR ROOM" with military-inspired design
  - Added Orbitron and Rajdhani Google Fonts for futuristic, command-center aesthetic
  - Implemented gradient text effects with fire colors (red/orange/yellow)
  - Updated tagline to "Your command center for total domination"

- **Advanced Task Input**: Completely overhauled task creation experience
  - Enhanced glass morphism styling with improved contrast and visibility
  - Added animated bottom border that appears when typing
  - Improved input responsiveness with better focus states
  - Added loading animation for the Add button during task creation
  - Fixed text visibility issues with proper color contrast

- **Keyboard Shortcuts System**: Implemented comprehensive keyboard navigation
  - Created `use-keyboard-shortcuts.ts` hook for customizable shortcuts
  - Added shortcuts for: Ctrl+N (new task), Ctrl+W (new win), Ctrl+J (journal), Ctrl+R (new rule), Ctrl+T (timeline), Ctrl+? (help)
  - Built keyboard shortcuts help modal with visual key representations
  - Added floating help and backup buttons in header

- **Voice Recognition**: Implemented advanced voice command system
  - Created `use-voice-recognition.ts` hook with Web Speech API
  - Added voice commands: "Add task: [description]", "Add win: [description]", "Journal entry: [content]"
  - Built voice controls component with visual feedback
  - Added transcript display and command help overlay
  - Integrated voice controls into main dashboard

- **Particle Effects & Animations**: Enhanced visual feedback system
  - Created `particle-effects.tsx` with celebration particles for task completion
  - Added celebration triggers when tasks are completed or wins are added
  - Implemented smooth particle animations with random colors and trajectories
  - Added ripple effects for click interactions

- **PWA Support**: Made the application installable as a progressive web app
  - Created `manifest.json` with War Room branding and icons
  - Added service worker for offline functionality
  - Implemented app shortcuts for quick actions
  - Added mobile-optimized meta tags and Apple touch icon support

- **Smart Persistence**: Enhanced data backup and restoration
  - Created `use-local-storage.ts` hook for client-side data persistence
  - Added automatic backup functionality with download capability
  - Implemented data export/import system with JSON format
  - Added backup button with keyboard shortcut (Ctrl+Shift+S)

- **Improved Drag & Drop**: Enhanced task reordering functionality
  - Fixed task reordering with proper visual feedback
  - Added toast notifications for successful reordering
  - Improved drag handle visibility and usability
  - Optimized drag and drop performance with better state management

- **Atlas Background Ready**: Prepared for cinematic Atlas image integration
  - Created comprehensive Atlas image prompt specification
  - Added background containers with proper layering
  - Implemented glass UI compatibility for background images
  - Reserved space for dynamic breathing effects and time-based lighting

- **Thoughts Deletion Fix**: Resolved missing deletion functionality
  - Added deleteThought method to IStorage interface and DatabaseStorage implementation
  - Created DELETE /api/thoughts/:id endpoint in routes
  - Added hover delete button with trash icon to each thought entry
  - Implemented proper error handling and toast notifications
  - Users can now delete thoughts by hovering over entries and clicking the trash icon

- **Atlas Background Integration**: Integrated stunning Atlas mythology background
  - Added user-provided cinematic Atlas image with breathing animations
  - Implemented atlantisBreathing keyframes for subtle scale and rotation effects
  - Created timeBasedLighting animation for dynamic hue and brightness changes
  - Added proper layering with atlas-overlay for glass morphism compatibility
  - Enhanced header text with drop shadows for better readability over background
  - Background features: 8s breathing cycle, 20s lighting cycle, smooth transitions