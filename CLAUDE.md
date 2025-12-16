# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
This is a static single-page website for Turkett Law Office, a Texas-based law firm specializing in estate planning. The entire website is contained in a single `index.html` file with embedded CSS and JavaScript.

## Technology Stack
- Pure HTML5, CSS3, and vanilla JavaScript
- No build process or framework dependencies
- External dependencies: Font Awesome 6.4.0, Google Fonts (Inter, Cormorant Garamond)

## Development Commands
Since this is a static site, there are no build commands. To work with the site:
- Open `index.html` directly in a browser
- Use any static web server (e.g., `python -m http.server 8000` or VS Code Live Server)
- Deploy to any static hosting service

## Architecture & Code Structure
The entire website is in `index.html` (1940 lines) with three main sections:

1. **CSS (lines ~20-850)**: 
   - CSS custom properties for theming
   - Responsive design with mobile-first approach
   - Animation keyframes for smooth transitions

2. **HTML (lines ~850-1700)**:
   - Header with navigation
   - Hero section
   - Service sections (Special Needs, Estate Planning, Probate, Guardianships, Elder Law, Business)
   - About section with attorney profiles
   - Blog section with modal functionality
   - Contact section

3. **JavaScript (lines ~1700-1940)**:
   - `blogPosts` array containing all blog content
   - Modal system for blog post display
   - Smooth scrolling navigation
   - Mobile menu toggle functionality

## Key Implementation Details
- **Blog System**: Blog posts are stored in a JavaScript array and rendered dynamically. Modal functionality shows full posts.
- **Image Handling**: All images are in the `images/` folder. The code includes fallback Font Awesome icons when images fail to load.
- **Responsive Design**: Breakpoints at 768px and 1024px for tablet and desktop views.
- **Navigation**: Fixed header with smooth scroll to sections using anchor links.

## Important Patterns
- CSS classes follow a BEM-like naming convention
- All interactive elements have proper hover states and transitions
- Contact information (phone, email) is repeated throughout for conversion optimization
- Service sections follow a consistent structure with icon, title, description, and "Learn More" button

## Development Log

### Mobile Fixes - 2025-07-23

#### Issue: Mobile website appearing "zoomed in"
**Root Cause**: CSS clamp() functions using excessive viewport width units (8vw, 10vw) in mobile breakpoints causing oversized text scaling.

**Solution**: Reduced viewport width values in mobile media queries:
- @media (max-width: 768px): Reduced from 8vw→4vw, 6vw→3vw, 5vw→2.5vw, 4vw→2vw
- @media (max-width: 480px): Reduced from 10vw→5vw, 8vw→4vw, 6vw→3vw

#### Issue: Service pages missing centered logo on mobile
**Problem**: Service pages in /services/ directory lack the mobile logo centering CSS rule that exists in index.html
**Missing Rule**: `.logo { margin: 0 auto; }` inside @media (max-width: 768px)
**Status**: Identified but not yet fixed - need to add centering to all service pages

#### Technical Notes:
- Single-page app (index.html) vs separate service pages architecture
- Consistent CSS needed across all pages for uniform UX
- Mobile-first responsive design principles applied

### Mobile UI Enhancements - 2025-12-16

#### Touch Target Improvements
- All interactive elements now meet 48px minimum touch target size (Apple/Google guidelines)
- Added `touch-action: manipulation` to remove 300ms tap delay on mobile
- Added `-webkit-tap-highlight-color: transparent` for cleaner touch feedback

#### Touch Feedback States
- Added `:active` states with scale transforms for tactile feedback on:
  - Navigation links (scale 0.97)
  - Buttons (scale 0.97)
  - Service cards (scale 0.98)
  - Floating CTA (scale 0.95)
  - Scroll-to-top button (scale 0.9)
  - Blog modal close button (scale 0.9)

#### Mobile Navigation Drawer
- Added backdrop overlay (`nav-backdrop`) for tap-to-close functionality
- Nav drawer now slides from left with 85% width (max 320px)
- Body scroll lock when menu is open via `body.menu-open` class
- Floating CTA hides when nav menu is open to reduce visual clutter

#### Blog Modal Mobile UX
- Bottom-sheet style on mobile (aligns to bottom, rounded top corners)
- Drag handle indicator for swipe affordance
- Close button increased to 48px with active state
- Improved padding and line-height for readability
- `-webkit-overflow-scrolling: touch` for momentum scrolling

#### Floating Elements
- Scroll-to-top: bottom-left position (avoids thumb conflict)
- Floating CTA: bottom-right position
- Both elements have 48px touch targets on mobile
- CTA hides when mobile nav is open

#### Key CSS Classes Added
- `.nav-backdrop` - Mobile menu backdrop overlay
- `.menu-open` - Body class for scroll lock when menu is open

#### JavaScript Functions Added
- `closeMobileMenu()` - Closes mobile menu and removes all associated states

# important-instruction-reminders
Do what has been asked; nothing more, nothing less.
NEVER create files unless they're absolutely necessary for achieving your goal.
ALWAYS prefer editing an existing file to creating a new one.
NEVER proactively create documentation files (*.md) or README files. Only create documentation files if explicitly requested by the User.