# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview
This is a static single-page website for Turkett Law Office, a Texas-based law firm focused on estate planning. The entire website is contained in a single `index.html` file with embedded CSS and JavaScript.

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

### Image Loading & Performance Fixes - 2025-07-23

#### Issue: Missing images and poor performance
**Problems Fixed**:
- 8 missing image references in service pages replaced with existing alternatives
- Added error handling with Font Awesome fallback icons for all service page images
- Implemented lazy loading (`loading="lazy"` and `decoding="async"`) for better performance
- Standardized image paths across all pages
- Updated typography scale consistency across all pages
- Changed all "Free Consultation" and "Consultation" text to "Schedule Consultation"

**Technical Implementation**:
- All service page images now have `onerror` handlers with appropriate Font Awesome fallbacks
- Lazy loading reduces initial page load time
- Consistent `../images/` path structure across service and blog pages

## Contact Form Implementation Plan
**Status**: Planned for future implementation

### Current State
- Contact section (index.html:3632) currently has simple CTA with phone number only
- No form capture mechanism for leads
- Limited user engagement options

### Planned Implementation

#### Form Structure
**Location**: Replace/enhance current CTA section in index.html around line 3632
**Layout**: Two-column responsive design:
- Left: Contact form
- Right: Contact information panel

#### Form Fields
- **Full Name** (required, text input)
- **Email Address** (required, email input with validation)
- **Phone Number** (optional, tel input)
- **Service Needed** (dropdown select):
  - Estate Planning
  - Elder Law & Medicaid Planning
  - Probate & Estate Administration
  - Guardianships
  - Divorce & Child Custody
  - Business & Real Estate Law
  - General Legal Question
- **Message** (required, textarea)
- **Preferred Contact Method** (radio buttons: Phone/Email)
- Hidden honeypot field for spam prevention

#### Styling Classes to Add
```css
.contact-form-section     /* Main container */
.form-container          /* Form wrapper with glass morphism */
.form-group              /* Individual field containers */
.form-control            /* Input/textarea/select styling */
.form-label              /* Label styling */
.form-select             /* Dropdown styling */
.form-message            /* Success/error message display */
.contact-info-panel      /* Right side contact information */
.form-radio-group        /* Radio button container */
.form-validation-error   /* Error state styling */
```

#### Contact Information Panel Content
- Office address with Google Maps link
- Phone number (clickable tel: link)
- Email address (clickable mailto: link)
- Office hours
- Emergency contact note
- Professional credentials/bar admissions

#### JavaScript Functionality
- **Form validation**: Real-time validation with helpful error messages
- **Submission handling**: Success/error message display (frontend only initially)
- **Accessibility**: ARIA labels, keyboard navigation support
- **User experience**: Form clearing after successful submission, smooth scroll to form
- **Spam prevention**: Honeypot field validation

#### Backend Integration Notes (Future)
*Frontend-only initially. Backend integration will require:*
- Form submission endpoint (email service/API)
- Server-side validation and sanitization
- Email notification system to law office
- Optional: Database storage for lead management
- CAPTCHA integration recommended for production
- Email auto-responder to confirm receipt

#### Responsive Design Considerations
- Mobile: Single column, form above contact info
- Tablet: Maintain two-column layout with adjusted proportions
- Desktop: Full two-column layout with optimal spacing
- Touch-friendly form controls for mobile users
- Proper viewport handling for form inputs on iOS

#### Implementation Priority
- High: Form structure and styling
- High: Client-side validation
- Medium: Enhanced UX features
- Low: Backend integration (requires hosting/server setup)

# important-instruction-reminders
Do what has been asked; nothing more, nothing less.
NEVER create files unless they're absolutely necessary for achieving your goal.
ALWAYS prefer editing an existing file to creating a new one.
NEVER proactively create documentation files (*.md) or README files. Only create documentation files if explicitly requested by the User.