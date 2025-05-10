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

## Component: `CoreFeatures.tsx`

- **Location**: `src/components/sections/CoreFeatures.tsx`
- **Type**: Section Component
- **Used In**: `LandingPage.tsx`

###  Purpose

The `CoreFeatures` renders a horizontally scrollable, auto-playing slider that highlights key platform features, complete with animated transitions, scale effects, and interactive navigation controls.

###  Structure and Functionality

The component:

- Wraps the entire section in a `Box` with full-width and responsive height, background styling, and centered padding.

- Uses Chakra UI’s `Flex` to position and animate horizontally sliding content `(sliderRef)`.

- Constructs `extendedSlides` by duplicating the first two and last two items of `coreFeaturesItems` to simulate an infinite carousel loop.

- Automatically transitions to the next slide every 3 seconds using a timeout.

- Provides `goToSlide` function to handle forward/backward animation with wrap-around logic and GSAP-controlled transitions.

- Applies conditional scale and opacity to the currently active slide for emphasis.

- Adds decorative fade overlays (`slider-fade-left`, `slider-fade-right`) on both sides to create visual fade effects at the edges.

- Renders control buttons:

- Left and right arrow icons with active/inactive states that swap on hover.

- A central rotating `logoActive` image animated on every slide change.


###  Dependencies

- `Chakra UI components` (Box, Flex, Text, Image, useBreakpointValue)

- `gsap and @gsap/react` for animations

- Constants and assets from `@/constants` and `@/assets`

- Uses custom icons: `arrowLeftActive`, `arrowRightActive`, etc.


###  Props

This component does **not** accept any props. All data is pulled from constants or managed internally.

###  Notes

Uses `useRef` and `useEffect` to trigger GSAP animation when heading enters viewport.

The nested `ring components` and central image create a strong visual focal point.

Designed for full viewport height (100vh) on large screens, but responsive to smaller viewports.

Layered text below the ring provides branded messaging.

Easy to update visual elements (e.g., central logo, highlight text, or orbital behavior) without affecting layout logic.

---

## Component: `ValueProposition.tsx`

- **Location**: `src/components/sections/ValueProposition.tsx`
- **Type**: Section Component
- **Used In**: `LandingPage.tsx`

###  Purpose

The `ValueProposition` component creates an engaging hero section with a scroll-based parallax animation. It showcases the platform's core message by emphasizing the brand's value proposition using layered elements, animated visuals, and a dynamic background.

###  Structure and Functionality

The component:

- Wraps the entire section in a `Box` that spans full width and adjusts height responsively. The section has a light background color (`brand.bgLight`), with centered padding and content.

- Uses `Flex` for positioning content vertically and centers the text and images.

- Integrates `GSAP` to control scroll-triggered animations:

- **Brand logo**: Moves vertically and scales down as the user scrolls.

- **Background element**: Moves in the opposite direction of the logo for a parallax effect.

- **Dotter overlay**: Moves down with a slight animation to keep the visual depth.

- Implements the `scrollTrigger` feature of GSAP for smooth parallax animations on the scroll.

- The trigger starts when the section is 200px before entering the viewport and ends 20% before the section leaves.

- Adds a central heading that highlights the core business message with two text lines:

- First line: "Solve Complex"

- Second line: "Business Problems Using"

- A third heading further emphasizes the core message: "Agent Matters", with an animated sparkles icon next to it.

- Features a call-to-action (`DownArrow`) that directs users to the blog section.

- Displays the brand logo in a `Box` with a mask applied, creating a visually appealing design with a dotted overlay.

###  Dependencies

- `Chakra UI components` - Box, Text, Image, Flex, Heading, VStack, HStack for layout and styling.

- `gsap and @gsap/react` for animations - Controls scroll-triggered animations and parallax effects.

- `assets` - `dottedOverlay`, `logoInactive`, `sparkles`, `worldDotted` images used for styling and animation

- `DownArrow` — scroll navigation icon.


###  Props

This component does **not** accept any props. All data is pulled from constants or managed internally.

###  Notes

Uses `useRef` and `useEffect` to trigger GSAP animation when heading enters viewport.

The nested `ring components` and central image create a strong visual focal point.

Designed for full viewport height (100vh) on large screens, but responsive to smaller viewports.

Layered text below the ring provides branded messaging.

Easy to update visual elements (e.g., central logo, highlight text, or orbital behavior) without affecting layout logic.

---
## Component: `SpotlightPreview.tsx`

- **Location**: `src/components/sections/Spotlight.tsx`
- **Type**: Section Component
- **Used In**: `LandingPage.tsx`

###  Purpose

The `SpotlightPreview` component renders a visually engaging hero section with an animated spotlight effect and grid background overlay. It introduces the core hero content (`Hero` component) while layering a custom animated lighting effect (`Spotlight`) and gradient overlays to create visual depth and focus.

###  Structure and Functionality

- Wraps the section in a responsive `Box` with `flex` layout, ensuring content is centered and properly scaled across devices.

- Adds a static background grid layer (`gridBackgroundStyle`) using CSS linear gradients to simulate a dark, retro-style grid texture.

- Implements a custom `Spotlight` component, which animates a vertical radial gradient beam across the section:

- Animates in a pulsing pattern (`spotlightPulse`) that shifts size, position, and opacity.

- Applies a radial gradient, blur, rotation, and opacity for lighting simulation.

- Controlled by class-like props (-top-20, left-0, etc.), parsed via a helper.

- Loads hero content from a separate `Hero` component, which is placed centrally with adjusted padding based on screen width.

- Includes a bottom fade overlay, a full-width linear gradient that blends the section smoothly into the next section of the page.

**Responsive behavior**:

- On medium or larger screens (`window.innerWidth >= 768`), font sizes and paddings are increased for optimal display.

- The spotlight’s position is adjusted depending on screen size using class-name-like strings parsed into inline styles.

###  Dependencies

**Chakra UI**:

    - `Box` from Chakra is used for the outer container, offering consistent styling and responsive height control.

**Custom Components**:

    - `Hero`: Renders the central message or banner of the page.

**Built-in Libraries**:

    - Native CSS for animation (@keyframes spotlightPulse).

    - Inline styles with media query logic handled in JS (not via Tailwind or Chakra responsive props).

###  Props

**`Spotlight` Component Props**:

| Prop Name   | Type      | Description                                                                 |
| ----------- | --------- | --------------------------------------------------------------------------- |
| `className` | `string?` | A Tailwind-like shorthand (e.g., `-top-20 left-0`) to control beam position |
| `fill`      | `string?` | Sets the center color of the spotlight beam (`white` by default)            |

`SpotlightPreview` does not accept props. All data and styling are managed internally.

###  Notes

`Spotlight` is a standalone visual animation component meant to add ambient lighting with blur, radial gradient, and motion.

The `spotlightPulse` animation uses keyframes to animate the light beam’s height, opacity, and horizontal position over time, simulating a subtle ambient motion.

A custom parser (`parsePositionFromClassName`) extracts positioning data from a className-style string. This mimics Tailwind behavior without using Tailwind classes directly.

The component avoids interfering with user interaction by setting `pointerEvents: 'none'` on all visual-only elements.

Ideal for hero sections or introduction panels where ambient motion and a dramatic entrance effect are desired.

Fully responsive and can be reused across sections with different `fill` values or position presets.

---
