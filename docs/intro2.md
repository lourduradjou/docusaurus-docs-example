# Agent Matters Landing Page Documentation

## Project Overview

This is a responsive landing page for **Agent Matters**, built using **ReactJS**, **ViteJS**, **TypeScript**, and **Chakra UI**. The page is optimized for speed, responsiveness, and accessibility.

## Tech Stack Used

The project is built using the following technologies:

-   **React** — v19.0.0
-   **Vite** — v6.2.0 (for blazing-fast development and build)
-   **TypeScript** — ~v5.7.2 (for type safety and better developer experience)
-   **Chakra UI** — v3.17.0 (for accessible and modular component styling)

## Prerequisites

To get started with this project, ensure the following tools are installed on your system:

-   **Node.js** (version 20 or higher)
-   **npm** (comes bundled with Node.js)
-   **Git** (for version control and cloning the repository)

## Getting Started

### 1) Clone the repo

```bash

git clone https://github.com/deco-25/am_v1.git
```

### 2) Go to the project folder

```bash

cd am_v1
```

### 3) Install dependencies

```bash
npm install
```

### 4) Start the project

```bash
npm run dev
```

---

## Folder Structure

```bash
📦src
 ┣ 📂assets
 ┃ ┣ 📂icons
 ┃ ┃ ┣ 📜arrow-left-activated.webp
 ┃ ┃ ┣ 📜arrow-left-inactivated.webp
 ┃ ┃ ┣ 📜arrow-right-activated.webp
 ┃ ┃ ┣ 📜arrow-right-inactivated.webp
 ┃ ┃ ┗ 📜index.ts
 ┃ ┗ 📂images
 ┃ ┃ ┣ 📜dotted-overlay-white.webp
 ┃ ┃ ┣ 📜dotted-overlay.webp
 ┃ ┃ ┣ 📜index.ts
 ┃ ┃ ┣ 📜logo-activated.webp
 ┃ ┃ ┣ 📜logo-inactivated.webp
 ┃ ┃ ┣ 📜sparkles.webp
 ┃ ┃ ┗ 📜world-dotted.webp
 ┣ 📂components
 ┃ ┣ 📂sections
 ┃ ┃ ┣ 📜Blogs.tsx
 ┃ ┃ ┣ 📜CoreFeatures.tsx
 ┃ ┃ ┣ 📜Hero.tsx
 ┃ ┃ ┣ 📜Highlights.tsx
 ┃ ┃ ┣ 📜index.ts
 ┃ ┃ ┣ 📜InfoAndUpdates.tsx
 ┃ ┃ ┗ 📜ValueProposition.tsx
 ┃ ┃ ┗ 📜Spotlight.tsx
 ┃ ┗ 📂ui
 ┃ ┃ ┣ 📜BlogCard.tsx
 ┃ ┃ ┣ 📜BlogsMobile.tsx
 ┃ ┃ ┣ 📜Button.tsx
 ┃ ┃ ┣ 📜DownArrow.tsx
 ┃ ┃ ┣ 📜FAQ.tsx
 ┃ ┃ ┣ 📜Footer.tsx
 ┃ ┃ ┣ 📜FooterDesktop.tsx
 ┃ ┃ ┣ 📜FooterMobile.tsx
 ┃ ┃ ┣ 📜index.ts
 ┃ ┃ ┣ 📜Navbar.tsx
 ┃ ┃ ┣ 📜NavbarMobileDrawer.tsx
 ┃ ┃ ┣ 📜NewsletterSubscription.tsx
 ┃ ┃ ┗ 📜Provider.tsx
 ┣ 📂constants
 ┃ ┗ 📜index.ts
 ┣ 📂hooks
 ┃ ┗ 📜index.ts
 ┣ 📂layout
 ┃ ┗ 📜MainLayout.tsx
 ┣ 📂pages
 ┃ ┗ 📜LandingPage.tsx
 ┣ 📂theme
 ┃ ┣ 📜colors.ts
 ┃ ┗ 📜index.ts
 ┣ 📜App.css
 ┣ 📜App.tsx
 ┣ 📜main.tsx
 ┗ 📜vite-env.d.ts
```

## Folder Overview for Agent Matters Landing Page

Below is a breakdown of each main folder in your src directory, explaining its purpose and typical contents. This overview will help you and your team navigate and maintain the codebase efficiently.

## assets

Contains static files used throughout the app.

icons: WebP images for navigation arrows and logos, with an index.ts for easy imports.

images: Backgrounds, overlays, and other imagery, also with an index.ts for centralized exports.

## components

Houses all reusable UI and section-level components.

**sections**: High-level page sections (e.g., Hero, Highlights, CoreFeatures, ValueProposition, Blogs, InfoAndUpdates). Each section is a self-contained React component representing a major block of the landing page.

**ui**: Smaller, reusable UI elements (e.g., Button, Navbar, Footer, BlogCard, NewsletterSubscription). Also includes layout helpers like Provider for Chakra UI context setup.

## constants

Centralized location for static values, enums, or configuration objects used throughout the app. Helps avoid magic numbers/strings and keeps code maintainable.

## hooks

Custom React hooks for encapsulating reusable logic. This can include data fetching, state management, or utility hooks tailored for the landing page.

## layout

Contains layout components that define the general page structure.

Example: MainLayout.tsx wraps page content with shared elements like headers and footers, and applies consistent styling and alignment.

## pages

Contains the main page components for routing.

LandingPage.tsx: The entry point for the landing page, assembling all section components into the final layout.

## theme

Custom Chakra UI theme configuration.

colors.ts: Defines the color palette for the app.

## other files

**index.ts**: Exports the complete theme object, possibly merging custom settings with Chakra UI defaults.

**App.css**: Global CSS overrides or base styles.

**App.tsx**: Main React component, typically sets up routing and layout.

**main.tsx**: Application entry point; initializes the React app and wraps it with Chakra's Provider for theming and context.

**vite-env.d.ts**: TypeScript environment definitions for Vite.

This structure supports scalability, maintainability, and clear separation of concerns, following best practices for modern React/TypeScript projects using Chakra UI and Vite




## Component: `Highlights.tsx`

- **Location**: `src/components/sections/Highlights.tsx`
- **Type**: Section Component
- **Used In**: `LandingPage.tsx`

###  Purpose

The `Highlights` component displays a visually impactful circular highlight section with a company logo, animated orbital effects, and a stylized heading. Communicates key messaging through motion-enhanced visuals and layered typography.

###  Structure and Functionality

The component:

- Wraps the section in a centered `Flex` container with responsive height (100vh on xl), padding, and background color from the brand.bgDark theme.

- Uses Chakra UI's `Box`, `Flex`, `Image`, and `Text` components for layout and styling.

- Utilizes `useRef` to reference the container and heading elements for animation.

- Triggers a `GSAP ScrollTrigger` animation on the heading when it enters the viewport.

Renders:

- An absolutely positioned fading top overlay (fade-top).

- A nested visual centerpiece composed of `OuterBorderRing and InnerBorderRing` surrounding the logoActive image.

- A stylized, multi-line heading with animated appearance and additional decorative sparkle image.


###  Dependencies

- `@chakra-ui/react` — for responsive layout and styling.
- `OuterBorderRing` and `InnerBorderRing` components for orbital animations.
- `GSAP with ScrollTrigger` - scroll-based heading animation.

###  Props

This component does **not** accept any props. All data is pulled from constants or managed internally.

###  Notes

Uses `useRef` and `useEffect` to trigger GSAP animation when heading enters viewport.

The nested `ring components` and central image create a strong visual focal point.

Designed for full viewport height (100vh) on large screens, but responsive to smaller viewports.

Layered text below the ring provides branded messaging.

Easy to update visual elements (e.g., central logo, highlight text, or orbital behavior) without affecting layout logic.

---
