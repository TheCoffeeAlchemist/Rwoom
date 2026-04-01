# RWOOM Project TODO

## Design & Theme
- [x] Define glassmorphism design system with OKLCH color palette
- [x] Set up global Tailwind CSS theme tokens and custom utilities
- [x] Import and configure Google Fonts for modern typography
- [x] Create reusable glassmorphism component styles

## Core Layout & Navigation
- [x] Build global sidebar with expandable/collapsible hamburger menu
- [x] Implement sidebar sections: Explore, Friends, Profile, Notifications
- [x] Create responsive layout wrapper for main content area
- [x] Add profile avatar and user menu in sidebar header

## Landing & Exploration
- [x] Build landing page with hero section and CTA
- [x] Create Explore page with room list and filtering
- [x] Implement search by room name/ID functionality
- [x] Add genre filter dropdown (35+ book genres)
- [x] Create room card component with glassmorphism styling
- [x] Display room IDs in semi-circle bordered boxes

## Room Page & PDF Viewer
- [x] Build room layout with vertical stack (PDF top, chat bottom)
- [ ] Integrate pdf.js for PDF rendering
- [ ] Implement independent scrolling/zooming per user
- [x] Add maximize button to hide chat and fill screen
- [x] Create presence indicators showing user avatars and current page
- [x] Implement "Follow Host" toggle for sync-to-host functionality

## Real-time Chat & Messaging
- [x] Build chat component with real-time message display
- [x] Add "User is on Page X" badge for every message
- [ ] Implement direct messaging (1-on-1) between friends
- [ ] Create message input with emoji support
- [ ] Add shared highlighting feature for PDF text selection

## Social Features
- [x] Build Friends list with online status indicators
- [x] Create friend profile card (Photo, Name, Age, Bio, UID)
- [ ] Implement friend request system with Accept/Reject
- [x] Add "Active Rooms" button showing friend's current rooms
- [ ] Build Notifications center (bell icon)
- [ ] Implement notification types: Join Requests, Friend Requests, DMs, Room Expiry warnings
- [ ] Create Profile edit page (Bio, Age, Profile Image upload)

## Room Management
- [ ] Implement room creation with type selection (Public, Private Password, Private Permission)
- [ ] Add password protection for private rooms
- [ ] Implement permission-based access control with host approval
- [ ] Add "Visible in Explore" toggle for private rooms
- [ ] Create "Bookmark Rooms" (star feature) functionality
- [ ] Implement room expiry (30-day auto-delete)

## Security & Features
- [ ] Implement rate limiting for room creation and friend requests
- [ ] Add "Report Room" button with moderator webhook
- [ ] Display persistent "Fair Use" footer
- [ ] Implement Google Picker API integration for PDF linking
- [ ] Add IndexedDB client-side caching (30-day TTL)
- [ ] Implement unique 6-digit alphanumeric UID assignment per user

## Database & Backend
- [ ] Create Supabase schema (profiles, rooms, messages, direct_messages, friendships, notifications)
- [ ] Implement Row Level Security (RLS) policies
- [ ] Create auto-expiry trigger for 30-day room deletion
- [ ] Set up tRPC procedures for all features
- [ ] Implement authentication with Google Sign-in

## Testing & QA
- [ ] Write vitest tests for core components
- [ ] Test responsive design across devices
- [ ] Verify glassmorphism effects and animations
- [ ] Test real-time chat and presence indicators
- [ ] Validate accessibility (WCAG 2.1 AA)

## Deployment & Final
- [ ] Create checkpoint before delivery
- [ ] Verify all features working in production
- [ ] Document API endpoints and user flows

## Button Wiring & Navigation (IN PROGRESS)
- [ ] Wire Join Room button in Explore page with navigation
- [ ] Wire Join Room button in Friends page with navigation
- [ ] Add toast notifications for button actions
- [ ] Implement room navigation flow

## Profile Page Implementation (IN PROGRESS)
- [ ] Build Profile edit page with form
- [ ] Add bio, age, profile image upload
- [ ] Implement backend integration

## Direct Messaging (IN PROGRESS)
- [ ] Build DM interface
- [ ] Implement real-time messaging
- [ ] Add message persistence

## Deployment Guides (TODO)
- [ ] Create local setup guide
- [ ] Create Vercel deployment guide
- [ ] Create APK build guide
- [ ] Create Play Store deployment guide
