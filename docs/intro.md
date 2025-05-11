# XYZ Documentation

## Project Overview

This is a responsive landing page for **XYZ**, built using **ReactJS**, **ViteJS**, **TypeScript**, and **Chakra UI**. The page is optimized for speed, responsiveness, and accessibility.

## Tech Stack Used

The project is built using the following technologies:

-   **React** — v19.0.0
-   **Vite** — v6.2.0 (for blazing-fast development and build)
-   **TypeScript** — ~v5.7.2 (for type safety and better developer experience)

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
 ┣ 📂components
 ┃ ┣ 📂sections
 ┃ ┃ ┣ 📜xyz.tsx
 ┃ ┗ 📂ui
 ┃ ┃ ┣ 📜BlogCard.tsx
 ┗ 📜vite-env.d.ts
```

## Folder Overview for XYZ

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

## Component: `Blogs.tsx`

- **Location**: `src/components/sections/Blogs.tsx`
- **Type**: Section Component
- **Used In**: `LandingPage.tsx`

###  Purpose

The `Blogs` component is responsible for rendering the "Latest Blogs" or "Insights" section of the landing page. It dynamically displays a grid of blog articles using the `BlogCard` UI component and adapts its layout based on screen size for responsive viewing.

###  Structure and Functionality

The component:

- Wraps the section in a centered `Flex` container with responsive margins and paddings.
- Uses Chakra UI's `Box`, `Grid`, and `GridItem` for layout.
- Fetches blog content from the `blogContent` array in the `constants/index.ts` file.
- Renders:
  - `BlogsMobile` for mobile view (base to `md`).
  - A grid layout with 4 `BlogCard` entries for screens `md` and above.

###  Responsive Behavior

- **Mobile (`base` to `md`)**: Displays a compact mobile-specific version using `<BlogsMobile />`.
- **Desktop (`md` and up)**: Renders a grid with strategically positioned blog cards for visual hierarchy.

###  Dependencies

- `BlogCard` — reusable card UI for displaying individual blog entries.
- `BlogsMobile` — mobile-optimized blog display component.
- `blogContent` — array of blog data (title, description, date) from constants.

###  Props

This component does **not** accept any props. All data is pulled from constants or managed internally.

###  Why It's Modular

Having a dedicated `Blogs.tsx` component allows easy updates to layout, styling, or data source for the blog section. It separates content presentation logic from other sections, keeping the codebase clean and modular.

---

## Component: `Highlights`

- **Location**: `src/components/ui/Highlights.tsx`  
- **Type**: Layout (Interactive Highlights Section with Scroll Animations)

### Purpose

The `Highlights` component displays a set of orbitals with titles and descriptions, arranged around a central logo. It includes smooth scroll-triggered animations to reveal each orbital and its associated content. The component is optimized for mobile and desktop views, providing an interactive and visually dynamic experience.

### Structure and Functionality

- **Orbitals**:
  - The component includes two rings (`OuterBorderRing` and `InnerBorderRing`), each with a set of orbitals. These orbitals are animated and displayed in a circular formation around the central logo.
  - The orbitals are clickable, displaying more information on hover or click.

- **Central Logo**:
  - The central logo is placed inside a white circular container and remains fixed in the center of the viewport.

- **Scroll-Triggered Animations**:
  - GSAP animations are used to animate the orbitals into position as the user scrolls. The animations are triggered by `ScrollTrigger` for smooth, interactive transitions.

- **Responsive Design**:
  - The component is fully responsive, adjusting the orbital sizes and positions based on the screen size. The layout adapts to mobile and desktop views using Chakra UI's responsive design utilities.

### Props

| Prop                | Type              | Default            | Description                                                                                      |
|---------------------|-------------------|--------------------|--------------------------------------------------------------------------------------------------|
| *(No props are directly used in this component)* | 

### Dependencies

- **Chakra UI**: `Box`, `Center`, `Flex`, `Image`, `Text` for layout, content, and styling.
- **GSAP**: For scroll-triggered animations (`ScrollTrigger`).
- **`Orbital`**: Custom component used for individual orbital items.
- **`useHoverSupport`**: Custom hook to detect hover support for interactive effects.

### Notes

- **Animation Trigger**: GSAP's `ScrollTrigger` is used to trigger animations based on the scroll position, giving each orbital its own animation effect.
- **Mobile-First Layout**: The component is designed to work seamlessly on both mobile and desktop. Mobile-specific styles are implemented using Chakra UI's responsive design utilities.
- **Hover Effects**: Each orbital has a hover effect that scales up on hover, providing visual feedback to the user.
- **Performance**: The animations are optimized for smooth performance, ensuring that the layout does not cause unnecessary performance issues.
- **Accessibility**: All interactive elements (e.g., orbitals) are designed to be accessible and clickable, with proper focus and hover interactions.

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
---
## Component: `Hero.tsx`

- **Location**: `src/components/sections/Hero.tsx`  
- **Type**: Section Component  
- **Used In**: `LandingPage.tsx`

### Purpose

The `Hero` component serves as the introductory hero section of the landing page. It presents the platform's core value proposition — a `No Code AI Multi-Agent Platform` — using a bold typographic layout, engaging description, and a prominent call-to-action. This section sets the tone for the rest of the site and aims to capture user interest immediately.

### Structure and Functionality

The `Hero` component is structured as a responsive `Box` container that uses a `Flex` layout to divide its contents into two main areas:

- **Left Section (Text Content)**  
  A `VStack` holds three stacked `Text` elements that collectively form the headline. The middle line includes the phrase `"Multi-Agent"` rendered in an italicized `span`, suggesting animated emphasis.  
  Below the heading, there's a brief description that communicates the platform's purpose.  
  A custom `Button` component labeled `Apply for Beta Access` follows the text, inviting user interaction.

- **Right Section (Image)**  
  An `Image` component displays the imported asset `logoActive`. This image is positioned absolutely and scaled responsively to visually balance the text-heavy left side.

- **Bottom Center (Scroll Cue)**  
  A `DownArrow` component is placed near the bottom center of the section, pointing to the `#highlights-section`. This visual cue suggests further content below the fold.

- **Commented Animation Logic**  
  The file includes commented-out `GSAP` logic, which was originally intended to animate each character in the `Multi-Agent` span using staggered blur, opacity, and rotation effects.

### Responsive Behavior

The `Hero` component is fully responsive:

- On **mobile devices**, the layout stacks and scales down: smaller font sizes, wrapped text, and resized image placement.
- On **larger screens**, the heading grows to `8xl`, the image is repositioned with `absolute` offsets, and additional margins and paddings are applied for spacing harmony.

Chakra UI’s responsive props (`base`, `md`, `xl`) are used throughout to manage these breakpoints.

### Dependencies

- **Chakra UI Components**:  
  Uses `Box`, `Flex`, `VStack`, `Text`, `Image`, and `Center` for layout and styling.

- **Custom Components**:
  - `Button`: Renders the CTA with link and text styling.
  - `DownArrow`: Renders a stylized downward arrow pointing to the next section.

- **Assets**:
  - `logoActive`: An imported image asset used in the hero image.

- **Animation Library (Commented)**:
  - `gsap` and `@gsap/react` were set up to animate the `Multi-Agent` text but are currently inactive.

### Props

The `Hero` component **does not accept any props**. All content and behavior are defined internally within the component.

### Notes

- The heading uses custom font classes (`fontPrimary` and `fontSecondary`) and Chakra UI `Text` props for style and spacing.
- The `Multi-Agent` word was intended to be animated using `GSAP`, though the logic is currently commented out. If enabled, it would create a character-by-character entrance animation.
- The `DownArrow` is visually centered using dynamic `left` positioning (`left: 46%–50%`) to maintain alignment across screen sizes.
- All visual-only elements (like the future animated span) are planned with `userSelect: 'none'` or `pointerEvents: 'none'` to avoid interfering with interaction.
- Ideal for product landing pages where a visually balanced and copy-driven hero is needed.
---

---
## Component: `InfoAndUpdates`

- **Location**: `src/components/sections/InfoAndUpdates.tsx`  
- **Type**: Section Component  
- **Used In**: Likely part of the main landing page or a dedicated updates page

### Purpose

The `InfoAndUpdates` component displays an informational section of the site that combines a frequently asked questions section (`FAQ`) and a newsletter subscription form (`NewsletterSubscription`). It also includes a subtle background image for visual enhancement.

### Structure and Functionality

- The outermost wrapper is a responsive `Box` from Chakra UI, which applies padding and disables text selection (`userSelect: 'none'`) to prevent accidental text highlighting during interaction.

- A semi-transparent background image (`logoActive`) is absolutely positioned behind the content. This image:
  - Is responsive and scales based on screen size.
  - Uses Chakra UI’s responsive style props for `top`, `bottom`, `right`, and `width`.
  - Is slightly faded using `opacity: 0.2` to ensure the image does not overpower foreground content.
  - Has `zIndex: 10` to layer it properly behind foreground components but above the base background.

- Inside the main container (`maxWidth: '1320px'`), the following subcomponents are rendered:
  - The `FAQ` component, which provides answers to commonly asked questions.
  - The `NewsletterSubscription` component, which displays a call-to-action allowing users to sign up for email updates.

### Responsive Behavior

- Padding (`px`) adjusts across screen sizes: `10` on mobile, `40px` on tablets, and `0px` on larger screens.

- The background image adjusts position and size based on device width:
  - On mobile, it shifts slightly left and down.
  - On desktops, it moves further out of view to the right, and its size scales down proportionally.

### Dependencies

**Chakra UI**:
- `Box` and `Image` components for layout, spacing, and responsive behavior.

**Custom Components**:
- `FAQ`: Renders a collapsible accordion or question-answer UI.
- `NewsletterSubscription`: Renders an email input form with a submission button.

**Assets**:
- `logoActive`: A logo or graphic asset used as the section’s visual background.

### Props

The `InfoAndUpdates` component does not accept any props. All content and styling are handled internally and through the imported subcomponents.

### Notes

- The background image is purely decorative and placed behind user-interactable content using absolute positioning and opacity.
- The visual layout is modular and can be reused with different content or background images by replacing `FAQ`, `NewsletterSubscription`, or `logoActive`.
- By using Chakra UI’s responsive prop system, the layout ensures a fluid experience across all device sizes.

---
## Component: `BlogCard`

- **Location**: `src/components/ui/BlogCard.tsx`  
- **Type**: UI Component  
- **Used In**: Likely within blog listings or update sections to display blog summaries

### Purpose

The `BlogCard` component renders an interactive blog preview card that reveals more content on hover. It supports a title, description, and date, and optionally includes a call-to-action button. It is designed to provide a concise yet engaging blog summary experience using smooth transitions and conditional rendering.

### Structure and Functionality

- The component wraps content inside a Chakra `Box` styled as a card. On hover:
  - The **title** fades out.
  - The **description and button** fade in.
  - The **footer (date)** fades out.
  - The **background color** transitions between two custom theme colors (`brand.bgDark` and `brand.bgLight`).

- The `hovered` state is managed using `useState` to trigger conditional styling and transitions.

- The **`clampText()`** utility function limits the blog description to a specified number of words (default: 15) and appends ellipsis (`...`) if it exceeds that limit.

- **Button visibility** is controlled via the `showButton` prop. If true, a custom `Button` component labeled "View Blog" is shown below the description.

- The component uses Chakra's responsive and semantic styling, enhanced by custom fonts and Tailwind-like utility classes via `className`.

- A decorative `fade-bottom` element is placed over the description for visual polish.

### Responsive Behavior

- Font size is adjustable via the `textSize` prop (default: `'lg'`).
- Layout is flexible and scales to the parent container’s size.
- Hover effects apply smoothly with CSS transitions and Chakra-style conditional rendering.

### Dependencies

**Chakra UI**:
- `Box`, `Text`, and `Center` for layout and styling.

**Custom Components**:
- `Button`: A reusable call-to-action button.
  
**React**:
- `useState` for managing hover behavior.

### Props

| Prop Name       | Type      | Default  | Description                                                                 |
|-----------------|-----------|----------|-----------------------------------------------------------------------------|
| `title`         | `string`  | —        | The blog card title.                                                        |
| `description`   | `string`  | —        | The blog summary or excerpt.                                                |
| `date`          | `string`  | —        | The publication date shown at the footer.                                  |
| `showButton`    | `boolean` | `false`  | Whether to display the "View Blog" button.                                 |
| `centerButton`  | `boolean` | —        | *(Unused in the component but defined)* – Presumably to center the button. |
| `numberOfWords` | `number`  | `15`     | Maximum number of words to show in the description.                        |
| `textSize`      | `string`  | `'lg'`   | Sets the font size of the content.                                          |

### Notes

- The component features a dual-layer card design: a visible front face (`brand.bgLight`) that fades away on hover to reveal detailed content underneath.
- The `zIndex` layering ensures the smooth transition of foreground text while preserving background interactions.
- The `centerButton` prop is currently defined but not used — this might be a remnant or placeholder for future logic.
- This component is ideal for use in blog grids, update feeds, or content previews where hover interaction is supported.

---
## Component: `BlogsMobile`

- **Location**: `src/components/ui/BlogsMobile.tsx`  
- **Type**: UI Component  
- **Used In**: Mobile blog carousels, mobile-first blog section layouts

### Purpose

The `BlogsMobile` component creates an auto-sliding horizontal blog carousel specifically optimized for mobile and small screen widths. It cycles through `BlogCard` items at fixed intervals and supports swipe gestures and dot-based manual navigation.

### Structure and Functionality

- **Carousel Layout**:  
  Horizontally scrolls a set of blog cards (`BlogCard`) within a `Flex` container, where each slide is `300px` wide.

- **Auto Sliding**:
  - Automatically advances to the next blog every `3000ms` (3 seconds).
  - Auto-slide resets if the user manually interacts via swipe or dot navigation.

- **Touch Swipe Support**:
  - Detects left/right swipes using `onTouchStart` and `onTouchEnd`.
  - Swiping more than `40px` in either direction triggers a slide change.

- **Dot Navigation**:
  - Renders navigation dots below the carousel.
  - Dots adjust in width depending on which slide is active.
  - Clicking a dot sets the current slide and resets the auto-slide timer.

- **Responsive Container**:
  - The container width is capped at `300px` (`SLIDE_WIDTH`) with `maxW='100vw'`, ensuring it works well on mobile.
  - `transform: translateX(...)` animates the slide transition.

### Dependencies

**Chakra UI**:
- `Box`, `Flex`, `HStack`, and `Button` (aliased as `ChakraButton`) for layout and styling.

**Custom Components**:
- `BlogCard`: Displays individual blog content cards.
- `blogContent`: An array of blog objects imported from `@/constants`.

**React**:
- `useState`, `useEffect`, and `useRef` for managing state, lifecycle behavior, and touch tracking.

### Props

| Prop Name  | Type      | Default | Description                                          |
|------------|-----------|---------|------------------------------------------------------|
| `textSize` | `string`  | —       | Passed down to each `BlogCard` to control text size. |

### Notes

- The constant `SLIDE_WIDTH` defines the width of each card and is used throughout the layout and transform logic.
- A `useEffect` hook handles setting and clearing the interval for automatic sliding.
- Touch-based swipe handling is implemented with basic delta comparison logic (`> 40px`).
- The dot navigation (`HStack`) adjusts the width of the active button for visual emphasis.
- This component is ideal for rendering blog previews in mobile environments, ensuring intuitive interaction via both touch and buttons.

---
## Component: `Navbar`

- **Location**: `src/components/ui/Navbar.tsx`  
- **Type**: Navigation Component  
- **Used In**: All page layouts requiring a top navigation bar with scroll awareness and responsiveness

### Purpose

The `Navbar` component renders a responsive top navigation bar that dynamically hides when the user scrolls down and reappears when scrolling up. It supports both desktop and mobile layouts, adapting its content display based on the screen size.

### Structure and Functionality

- **Scroll Hide/Show**:
  - Uses `window.scrollY` and a `useEffect` hook to detect scrolling direction.
  - Sets `transform: translateY(-100%)` when scrolling down to hide the navbar, and `translateY(0)` when scrolling up to show it again.

- **Responsive Layout**:
  - Uses Chakra UI’s `useBreakpointValue()` to detect whether the current viewport is mobile.
  - Shows a `MobileDrawer` on mobile (`base`, `md`, `lg` breakpoints).
  - Displays inline nav links and a CTA `Button` on wider screens (`xl` and up).

- **Branding Section**:
  - Includes the site logo (`logoActive`) and the brand name “Agent Matters”.
  - Wrapped in a Chakra `Link` that routes to the home page.

- **Nav Links Section** (Desktop only):
  - Dynamically maps over the `navLinks` array from `@/constants`.
  - Each link changes color on hover and uses a custom `underLight` class for underline styling.

- **Call to Action Button**:
  - Uses a reusable `Button` component with the label "Get Started".
  - Also visible only in desktop view.

### Dependencies

- **Chakra UI**:
  - Layout: `Box`, `Flex`, `Link`, `Text`, `Image`
  - Hook: `useBreakpointValue`

- **Assets**:
  - `logoActive`: Branding image used in the top left of the navbar.

- **Constants**:
  - `navLinks`: Array of `{ href, label }` objects used to populate navigation.

- **Custom Components**:
  - `Button`: A styled CTA button
  - `MobileDrawer`: Slide-in drawer for mobile nav menu

- **React**:
  - `useEffect`, `useState` for scroll tracking and visibility control

### Props

This component takes **no props**.

### Notes

- The navbar is `position: fixed` and has a high `zIndex (1000)` to stay above content.
- Padding and spacing are adjusted using responsive Chakra props (`px`, `py`, `ml`, etc.).
- The mobile drawer is shown at breakpoints `base` through `lg`, while desktop links appear only from `xl` and up.
- The `className='underLight'` implies there’s external styling for link underline effects.
- Ideal for layouts requiring visibility control on scroll to maximize content space while retaining brand identity.

---
## Component: `MobileDrawer`

- **Location**: `src/components/ui/MobileDrawer.tsx`  
- **Type**: Navigation Component  
- **Used In**: `Navbar` (mobile layout only)

### Purpose

The `MobileDrawer` component renders a slide-in drawer menu for mobile and tablet viewports. It offers an accessible and compact way to navigate the app's main sections and provides brand identity with a logo and name at the bottom.

### Structure and Functionality

- **Trigger Button**:
  - A small `Button` (Chakra variant `outline`, size `sm`) that contains a `HamburgerIcon`.
  - Clicking it triggers the drawer to open using `Drawer.Trigger`.

- **Drawer Layout**:
  - **Backdrop**: Semi-transparent black overlay using `blackAlpha.600`.
  - **Drawer Content**:
    - Width: 70% of viewport width (`maxW='70vw'`).
    - Background: `brand.bgDark`.
    - Left border and drop shadow for visual separation.

- **Drawer Header**:
  - Title "Menu" styled with `fontSecondary` and `brand.bgLight` color.
  - Close button (`CloseButton`) placed on the right.

- **Drawer Body**:
  - A vertical stack (`VStack`) containing:
    - Navigation links (`navLinks`), styled with bottom borders, center alignment, and hover interaction.
    - Branding section at the bottom with:
      - `logoActive` image (responsive size).
      - Brand name "Agent Matters" under the logo.

### Dependencies

- **Chakra UI**:
  - Layout: `Drawer`, `Button`, `Flex`, `VStack`, `Image`, `Text`, `Link`, `Icon`, `Portal`, `CloseButton`
  - Style tokens: `brand.bgDark`, `brand.bgLight`, `brand.textGray`

- **Assets**:
  - `logoActive`: Image displayed in branding area.
  - `HamburgerIcon`: Custom hamburger icon used as drawer trigger.

- **Constants**:
  - `navLinks`: Array of `{ href, label }` navigation objects used in the drawer.

### Props

This component takes **no props**.

### Notes

- The drawer uses `Drawer.*` subcomponents from Chakra’s new primitive-style composition (`Drawer.Root`, `Drawer.Trigger`, `Drawer.Positioner`, etc.).
- Ideal for use within mobile navigation (`base` to `lg` breakpoints).
- Custom class `fontSecondary` and hover/focus behavior are handled via external styles or Chakra overrides.
- `focusRing='none'` on `Link` disables Chakra's default focus ring, assuming accessibility alternatives are handled elsewhere.

---
## Component: `Button`

- **Location**: `src/components/ui/Button.tsx`  
- **Type**: Reusable UI Component  
- **Used In**: `Navbar`, other components needing a styled CTA

### Purpose

The `Button` component wraps a Chakra `Button` inside a Chakra `Link` to provide a consistent, accessible call-to-action element that functions as an external link (opens in a new tab). It offers customizable padding, sizing, margin, and text styling.

### Structure and Functionality

- **Outer Layer**:  
  - Chakra `Link` acting as an anchor tag (`as='a'`) pointing to the `href` prop.  
  - Opens in a **new tab** (`target='_blank'`, `rel='noopener noreferrer'`) — suitable for external links.

- **Button Styling**:
  - Variant: `outline`
  - Background: `whiteAlpha.800`
  - Border: 2px, `brand.bgLight`
  - Text color: black (default), changes to `brand.bgLight` on hover
  - Hover: transparent background, outline color and text color change
  - Active state: scales slightly for press feedback (`transform: scale(0.95)`)
  - Font: Uses the custom `fontSecondary` class

### Props

| Prop          | Type                          | Default        | Description                                                      |
|---------------|-------------------------------|----------------|------------------------------------------------------------------|
| `text`        | `string`                      | *(required)*   | Text displayed on the button                                     |
| `href`        | `string`                      | *(required)*   | URL the button links to                                          |
| `alt`         | `string`                      | `''`           | Accessible label (fallbacks to `text` if not provided)           |
| `rounded`     | `string`                      | `'full'`       | Border radius of the button                                      |
| `paddingX`    | `number`                      | `4`            | Horizontal padding (`px`)                                        |
| `paddingY`    | `number`                      | `2`            | Vertical padding (`py`)                                          |
| `textSize`    | `string`                      | `'md'`         | Chakra-supported font size                                       |
| `center`      | `boolean \| object`           | *(unused)*     | *(Declared but unused in current implementation)*                |
| `marginTop`   | `number`                      | `0`            | Top margin                                                       |
| `marginBottom`| `number`                      | `0`            | Bottom margin                                                    |
| `marginX`     | `number`                      | `0`            | Horizontal margin                                                |

### Dependencies

- **Chakra UI**: `Button`, `Link`
- **Custom Styles**: Relies on Tailwind or global class `fontSecondary`
- **Color Tokens**: Uses `brand.bgLight` for consistency across themes

### Notes

- **Accessibility**: `aria-label` uses `alt` or `text` as fallback
- **Best Use**: For external CTAs like "Get Started", "Learn More", or contact links
- **Improvement Idea**: Add support for internal routing (e.g., `next/link`) or conditionally render `target='_blank'` only for external links

---

## Component: `DownArrow`

- **Location**: `src/components/DownArrow.tsx`  
- **Type**: UI + Scroll Interaction  
- **Used In**: Hero sections, call-to-scroll prompts

### Purpose

The `DownArrow` component displays a bouncing, rotating arrow icon (`MdDoubleArrow`) that triggers a smooth scroll to a specified element when clicked. It's commonly used as a scroll hint to navigate to the next section of a page.

### Structure and Functionality

- **GSAP Animation**:
  - Uses `gsap.to` with `y: 8` and `yoyo: true` to create an infinite bounce effect.
  - Triggered via `useGSAP` (from `@gsap/react`) with an empty dependency array (runs once on mount).

- **Scroll Behavior**:
  - When clicked, the arrow scrolls smoothly to the element with the ID specified by the `goTo` prop.
  - Uses native `scrollIntoView({ behavior: 'smooth' })`.

- **Style and Transformations**:
  - Accepts rotation via `rotate` prop (e.g., 90° for down, 180° for left, etc.).
  - Uses inline `style={{ transform: rotate(...) }}` and centers the icon via `margin: auto`.

### Props

| Prop        | Type     | Default    | Description                                                              |
|-------------|----------|------------|--------------------------------------------------------------------------|
| `fillColor` | `string` | `"black"`  | Icon color (applied to `MdDoubleArrow`)                                  |
| `goTo`      | `string` | *(required)* | ID of the section to scroll to on click                                  |
| `rotate`    | `number` | `90`       | Rotation in degrees (used to change direction of arrow visually)         |

### Dependencies

- **GSAP**: `gsap`, `ScrollTrigger`, and `@gsap/react`
- **React Icons**: `MdDoubleArrow` from `react-icons/md`

### Notes

- **ID Dependency**: Ensure the `goTo` target ID exists in the DOM; otherwise, clicking does nothing.
- **Performance**: Lightweight animation, good for hero/landing page arrows.
- **Extendability**:
  - Could support additional animation styles or speeds via props.
  - Add accessibility features like `aria-label` or `role="button"`.

---
## Component: `Orbital`

- **Location**: `src/components/ui/Orbital.tsx`  
- **Type**: UI (Individual Orbital Item)

### Purpose

The `Orbital` component represents an individual orbital item in the highlights section. Each orbital is clickable and shows a tooltip with a title and description when interacted with. The component includes hover effects and a click-based state for toggling the visibility of the description.

### Structure and Functionality

- **Orbital Circle**:
  - The component renders a circle (`Box`) with a specified size, positioned absolutely within the container. It has hover effects that scale the orbital on mouse over and can be clicked to toggle the visibility of the description.
  
- **Tooltip with Title and Description**:
  - The orbital includes a title (`Text`) that is positioned absolutely inside the orbital.
  - If the orbital is clicked, a description (`Text`) is displayed with a smooth animation. The description is positioned near the orbital and includes the content passed via the `desc` prop.

- **Hover and Click Interactions**:
  - Hover effects enlarge the orbital circle, and when hovered or clicked, the orbital's index is set as the `clickedOrbital`. This triggers the display of the description for that specific orbital.

- **Dynamic Styling**:
  - The component adapts its layout and styles based on the device's screen size, using Chakra UI’s responsive utilities.
  
### Props

| Prop                | Type              | Default            | Description                                                                                      |
|---------------------|-------------------|--------------------|--------------------------------------------------------------------------------------------------|
| `refEl`             | `any`             | `null`             | A reference to the orbital element for scroll-triggered animations.                              |
| `index`             | `number`          | -                  | The unique index of the orbital.                                                                  |
| `posStyles`         | `any`             | `{}`               | Additional positioning styles passed to the orbital container.                                    |
| `title`             | `string`          | -                  | The title to be displayed inside the orbital.                                                     |
| `desc`              | `string`          | -                  | The description shown when the orbital is clicked.                                                |
| `clickedOrbital`    | `number`          | `0`                | The index of the currently clicked orbital, used to toggle the visibility of the description.     |
| `setClickedOrbital` | `(i: number) => void` | -               | Function to set the `clickedOrbital` state, toggling the visibility of the description.          |
| `canHover`          | `boolean`         | `true`             | Determines if the orbital can be hovered to show the description.                                |
| `tooltipPosStyles`  | `any`             | `{}`               | Custom styles for positioning the title and description tooltips.                                |

### Dependencies

- **Chakra UI**: `Box`, `Text` for layout and typography, `useBreakpointValue` for responsive design.
  
### Notes

- **Click and Hover Logic**: The component supports both hover-based and click-based interactions, where hovering triggers a hover effect and clicking toggles the visibility of the description.
- **Responsive Design**: The orbital size adapts to mobile and desktop screen sizes (`w={{ base: '30px', md: '40px' }}`), ensuring it looks appropriate on all devices.
- **Animation**: A smooth scaling animation is applied on hover (`_hover={{ scale: '105%' }}`) and a fade-in effect is used when showing the description on click.
- **Performance**: The use of `position='absolute'` and `zIndex` ensures that the orbital's placement does not interfere with other elements in the layout, keeping performance optimal.
- **Accessibility**: The interactive nature of the orbitals ensures they are accessible, with a cursor set to `pointer` to indicate interactivity.

---


## Component: `FAQ`

- **Location**: `src/components/FAQ.tsx`  
- **Type**: UI (Accordion-based FAQ Section)

### Purpose

The `FAQ` component presents frequently asked questions with collapsible accordion items. Each item displays a question with an expandable answer. It's designed to help users quickly find information by toggling open and closed the FAQ items.

### Structure and Functionality

- **Accordion UI**:
  - Uses `Accordion` and `Accordion.Item` from Chakra UI to create a collapsible FAQ.
  - Each item includes a `title` (question) and `text` (answer), both derived from `faqItems`.
  - The FAQ is designed to have a wide, modern, and clean design with responsive behavior.

- **Accessibility Fixes**:
  - The entire trigger area (question) is a button, improving accessibility.
  - The accordion indicator (arrow) is made part of the clickable area to enhance user interaction.

- **Styling and Layout**:
  - The FAQ is centered using `Flex` with full width for smaller screens (`base: '100%'`).
  - The header text "Answers You're Looking For" is styled with a combination of fonts and colors for emphasis.
  - The content is contained within a `Box`, ensuring consistency in spacing and alignment across screen sizes.
  
### Props

| Prop            | Type        | Default           | Description                                                                  |
|-----------------|-------------|-------------------|------------------------------------------------------------------------------|
| *(No props are directly used in this component)* |

### Dependencies

- **Chakra UI**: `Accordion`, `Box`, `Text`, `Flex`, `Span`, etc.
- **`faqItems`**: Data source for the FAQ questions and answers.

### Notes

- **Responsiveness**: The layout adapts to screen sizes using Chakra UI's responsive design features, with different font sizes and spacing adjustments for mobile and larger screens.
- **Animation**: The accordion items expand and collapse smoothly on click.
- **Style Customization**:
  - The component uses Chakra UI's color palette (`brand.bgLight`, `brand.textGray`, etc.).
  - The font classes like `'fontPrimary'` and `'fontSecondary'` can be customized to match the app's design system.
  - `gradient-border-bottom` is assumed to be a custom CSS class, applied for visual effects on the accordion items.

---
## Component: `NewsLetterSubscription`

- **Location**: `src/components/NewsLetterSubscription.tsx`  
- **Type**: UI (Newsletter Subscription Section)

### Purpose

The `NewsLetterSubscription` component offers a subscription form for users to enter their email and subscribe to a newsletter. It is designed to be visually engaging and mobile-responsive, with an icon representing the newsletter and a clear "Subscribe" button.

### Structure and Functionality

- **Design**:
  - The component includes a gradient border surrounding the subscription form, which is centered within the page.
  - An email input field is provided for the user to enter their email address. The placeholder text is responsive and adjusts based on screen size.
  - A mail icon (`MailIcon`) is displayed on the left side of the input field for a visual cue, styled to be above the input field with a z-index layer.

- **Responsiveness**:
  - The component adjusts for different screen sizes using Chakra UI's `useBreakpointValue`, ensuring that the placeholder text size and form layout respond to screen width (for example, switching between `column` and `row` for the input and button).
  - The input field and button are designed with flexible width, so they adapt to available screen space.

- **Functionality**:
  - When the user clicks the "Subscribe" button, it currently leads to a placeholder route (`href='/'`).
  - The email input field's placeholder and font size adjust for mobile and desktop sizes to ensure readability and usability.

### Props

| Prop                | Type              | Default            | Description                                                                                      |
|---------------------|-------------------|--------------------|--------------------------------------------------------------------------------------------------|
| *(No props are directly used in this component)* |

### Dependencies

- **Chakra UI**: `Box`, `Input`, `Text`, `HStack`, `VStack`, `Flex`, `Icon`, `Center`, etc.
- **`MailIcon`**: Custom icon representing a mail envelope.
- **`Button`**: Custom button component for the subscribe action.

### Notes

- **Responsive Placeholder**: The placeholder text and font size dynamically adjust based on the screen width (`useBreakpointValue`).
- **Styling**:
  - Uses Chakra UI's color palette (`brand.bgLight`, `brand.textGray`, etc.) for cohesive design.
  - The icon is styled with `position: absolute`, placed behind the main input field with a layered z-index approach.
  - The input has a flushed border with a custom `borderColor` to align with the design system.
- **Behavior**: The button currently has no form action but is intended for future integration with a subscription service.

---
## Component: `Footer`

- **Location**: `src/components/Footer.tsx`  
- **Type**: Layout (Footer Section)

### Purpose

The `Footer` component renders different footer content based on the screen size. It provides a responsive design with separate components for desktop and mobile views.

### Structure and Functionality

- **Design**:
  - The footer container is styled with padding, margin, and background color to match the site's overall design.
  - The component has a responsive layout, with different content rendered for desktop and mobile views using the `FooterDesktop` and `FooterMobile` components.

- **Responsiveness**:
  - The footer is designed to be mobile-first, using Chakra UI's `Box` component with responsive `py`, `pt`, and `px` values.
  - `FooterDesktop` is rendered only for larger screen sizes (desktop and tablet views).
  - `FooterMobile` is rendered only for smaller screen sizes (mobile view).
  - The footer text and layout are spaced out with `letterSpacing` for better readability.

- **Styling**:
  - The background color is set to `brand.bgLight`, ensuring consistency with the site's color palette.
  - The font color is set to black for good contrast and readability.

### Props

| Prop                | Type              | Default            | Description                                                                                      |
|---------------------|-------------------|--------------------|--------------------------------------------------------------------------------------------------|
| *(No props are directly used in this component)* |

### Dependencies

- **Chakra UI**: `Box` for layout and styling.
- **`FooterDesktop`**: A component that handles the desktop view footer layout.
- **`FooterMobile`**: A component that handles the mobile view footer layout.

### Notes

- **Conditional Rendering**: `FooterDesktop` and `FooterMobile` are conditionally rendered based on screen size, ensuring the footer adapts to different devices.
- **User Experience**: The `userSelect` is set to `'none'` to prevent text selection within the footer, which may enhance user interaction.

---
## Component: `FooterDesktop`

- **Location**: `src/components/ui/FooterDesktop.tsx`  
- **Type**: Layout (Desktop Footer Section)

### Purpose

The `FooterDesktop` component renders the desktop version of the footer, containing links to various sections (Resources, Company, Products, Social Icons) and a back-to-top button. It also includes a company logo and copyright text. The component adapts to different screen sizes using Chakra UI's responsive layout.

### Structure and Functionality

- **Back to Top Button**:
  - The component includes an "Up Arrow" icon, which scrolls the user back to the "hero-section" when clicked, using `scrollIntoView` with smooth scrolling.
  
- **Footer Content**:
  - **Resources**: Contains a list of resource links.
  - **Company**: Displays company-related links.
  - **Products**: Displays links related to products.
  - **Social Icons**: Provides social media icons that can be clicked for navigation.

- **Logo and Copyright**:
  - The center of the footer features the company logo and a copyright notice, which dynamically reflects the current year.
  
- **Responsive Design**:
  - The layout uses Chakra UI's responsive props to adjust the footer's display for different screen sizes:
    - **Mobile View**: Elements like "Products" and "Social Icons" are displayed side by side at the bottom.
    - **Desktop View**: The footer is displayed in rows with sections for Resources, Company, and Products, while the social icons appear in the last section.
  
### Props

| Prop                | Type              | Default            | Description                                                                                      |
|---------------------|-------------------|--------------------|--------------------------------------------------------------------------------------------------|
| *(No props are directly used in this component)* |

### Dependencies

- **Chakra UI**: `Box`, `Flex`, `Text`, `Link`, `Icon`, `Image` for layout, icons, and styling.
- **`footerLinks`**: Data object containing titles, links, and social icons used to populate the footer sections.
- **`ArrowUpIcon`**: Custom arrow icon used for the back-to-top button.
- **`logoInactive`**: The logo image shown in the footer.

### Notes

- **Conditional Rendering**: The component is designed for desktop layouts only. It uses Chakra UI's `display={{ base: 'none', md: 'flex' }}` to hide the footer on smaller screens.
- **Accessibility**: Links and icons are properly wrapped in `<Link>` components, making them clickable and accessible. Additionally, the "Back to Home" functionality provides better UX on desktop.
- **Smooth Scrolling**: The `goToTop` function ensures a smooth scroll back to the top of the page.
- **User Experience**: Social media icons change color on hover to indicate interactivity.

---
## Component: `FooterMobile`

- **Location**: `src/components/ui/FooterMobile.tsx`  
- **Type**: Layout (Mobile Footer Section)

### Purpose

The `FooterMobile` component renders the mobile version of the footer, with a focus on simplicity and accessibility for smaller screens. It includes the company logo, social media icons, resource links, and copyright information. The layout adapts for mobile views using Chakra UI's responsive design utilities.

### Structure and Functionality

- **Logo and Social Icons**:
  - The footer displays the company logo alongside social media icons in a horizontal alignment.
  - The social media icons are clickable and styled to change on hover.

- **Footer Links**:
  - The component includes three sections (Resources, Company, Products) with links to relevant pages. Each section is styled to provide a clean, minimal layout on mobile screens.

- **Copyright Information**:
  - The footer displays the company name and a copyright message with the current year.

- **Responsive Design**:
  - The layout is designed specifically for mobile devices, with a block display (`display={{ base: 'block', md: 'none' }}`) that hides the footer on larger screens.

### Props

| Prop                | Type              | Default            | Description                                                                                      |
|---------------------|-------------------|--------------------|--------------------------------------------------------------------------------------------------|
| *(No props are directly used in this component)* |

### Dependencies

- **Chakra UI**: `Box`, `Center`, `Flex`, `HStack`, `Icon`, `Image`, `Link`, `Text` for layout, icons, and styling.
- **`footerLinks`**: Data object containing titles, links, and social icons used to populate the footer sections.
- **`logoInactive`**: The logo image shown in the footer.

### Notes

- **Mobile-Only Layout**: The component is displayed only on mobile screens (smaller than `md` breakpoint), using Chakra UI's `display={{ base: 'block', md: 'none' }}`.
- **Hover Effects**: The social media icons have hover effects that change their color to provide a clear indication of interactivity.
- **Content Wrapping**: The links are wrapped in a `Flex` component, ensuring that they adapt responsively, while the `Text` components ensure good readability.
- **Accessibility**: Links are properly wrapped in `<Link>` components, making them interactive and accessible for users.
  
---
