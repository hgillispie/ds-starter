# Hearsay Design System - AI Usage Instructions

## Overview

This repository contains the Hearsay Design System (HDS), a comprehensive React component library with design tokens, icons, and styling system. When working in a workspace alongside this design system repository, use this guide to properly import and implement HDS components.

## Package Information

- **Package Name**: `@hearsaycorp/hearsay-design-system`
- **Current Version**: `9.4.1`
- **Design System Context**: `hds-v9`

## Quick Start

### 1. Essential Setup - DesignSystemDecorator

**CRITICAL**: Before using any HDS components, you MUST wrap your application with `DesignSystemDecorator` to enable CSS custom properties:

```tsx
import { DesignSystemDecorator } from '@hearsaycorp/hearsay-design-system';

function App() {
  return (
    <DesignSystemDecorator>
      {/* Your application content with HDS components */}
    </DesignSystemDecorator>
  );
}
```

### 2. Component Imports

**Main Components** (import from root):
```tsx
import { 
  Button, 
  Alert, 
  Modal, 
  TextInput,
  Select,
  Checkbox,
  // ... other components
} from '@hearsaycorp/hearsay-design-system';
```

**Individual Icons** (import specific icons for bundle optimization):
```tsx
import { CircleCheckRegular } from '@hearsaycorp/hearsay-design-system/icons/CircleCheckRegular';
import { UserRegular } from '@hearsaycorp/hearsay-design-system/icons/UserRegular';
```

## Components Reference

### Available Components
Located in `library/src/components/`, each component includes:
- **Component file**: `Component.tsx` 
- **Styles**: `Component.scss`
- **TypeScript types**: `Component.types.ts`
- **Tests**: `Component.test.tsx`
- **Index export**: `index.ts`

**Complete component list**:
Alert, Avatar, Badge, Button, Checkbox, DesignSystemDecorator, DropdownButton, ElevatedContainer, Heading, Icon, Link, Lozenge, Menu, Modal, Popover, ProgressBar, Radio, Search, Select, Spinner, SplitButton, StripBanner, Tabs, Tag, Textarea, TextInput, TimedToast, Toast, Toggle, Tooltip

### Component Architecture
- **Individual folder structure**: Each component is self-contained
- **BEM class naming**: Components use `.hds-v9` and BEM methodology (e.g., `.hds-button__icon`)
- **Static enums**: Components expose static properties for sizes, colors, themes
- **TypeScript support**: Full type definitions available

### Common Component Patterns

**Button with size and theme:**
```tsx
<Button 
  text="Click me"
  size={Button.SIZE.LARGE}
  theme={Button.THEME.PRIMARY}
  onClick={handleClick}
/>
```

**Icon with semantic color:**
```tsx
<CircleCheckRegular 
  color={CircleCheckRegular.COLOR.SUCCESS}
  size={CircleCheckRegular.SIZE.SM}
  ariaLabel="Success indicator"
/>
```

## Design Tokens & Styling

### Token Locations

**Source Definitions**: `library/src/scss/_variables.scss`
- Raw token values (colors, spacing, typography, etc.)
- Single source of truth for all design system values

**Token Maps**: `library/src/scss/_variable-maps.scss` 
- Organized maps for generating utilities and CSS custom properties
- Groups tokens by category (colors, spacing, fonts, etc.)

**CSS Custom Properties**: `library/src/scss/_root.scss`
- Emits CSS variables scoped to `[data-design-system-context="hds-v9"]`
- Only available when DesignSystemDecorator is used

### Design Token Categories

#### Colors
**Semantic Color System** (from `_variables.scss`):
```scss
// Brand colors
$hds-color-brand-25: #F7F9FE;
$hds-color-brand-300: #1C1D20;

// Text colors  
$hds-color-text-50: #B7B9BC;
$hds-color-text-400: #1C1D20;

// State colors
$hds-color-success-200: #198754;
$hds-color-error-200: #B02A37;
$hds-color-warning-200: #FFCD39;
$hds-color-info-200: #5A58F2;

// Social/Channel colors
$hds-color-channel-facebook: #3b5998;
$hds-color-channel-google: #4285f4;
```

**CSS Custom Properties** (available after DesignSystemDecorator):
```css
--hds-color-brand-300
--hds-color-text-400
--hds-color-success-200
--hds-color-error-200
```

#### Spacing Scale
```scss
$hds-spacing-3xs: 0.125rem;  // 2px
$hds-spacing-2xs: 0.25rem;   // 4px
$hds-spacing-xs: 0.5rem;     // 8px
$hds-spacing-sm: 0.75rem;    // 12px
$hds-spacing-md: 1rem;       // 16px
$hds-spacing-lg: 1.5rem;     // 24px
$hds-spacing-xl: 2rem;       // 32px
$hds-spacing-2xl: 2.5rem;    // 40px
$hds-spacing-3xl: 3rem;      // 48px
$hds-spacing-4xl: 4rem;      // 64px
$hds-spacing-5xl: 5rem;      // 80px
$hds-spacing-6xl: 6rem;      // 96px
$hds-spacing-7xl: 10rem;     // 160px
```

#### Typography
```scss
// Font families
$hds-font-family-text: "Roboto Regular", -apple-system, BlinkMacSystemFont, Tahoma, sans-serif;
$hds-font-family-medium: "Roboto Medium", -apple-system, BlinkMacSystemFont, Tahoma, sans-serif;
$hds-font-family-bold: "Roboto Bold", -apple-system, BlinkMacSystemFont, Tahoma, sans-serif;

// Font sizes
$hds-font-size-smaller: 0.75rem;
$hds-font-size-small: 0.875rem;
$hds-font-size-base: 1rem;
$hds-font-size-h1: 2rem;
$hds-font-size-h2: 1.75rem;
$hds-font-size-h3: 1.5rem;

// Font weights
$hds-font-weight-base: 400;
$hds-font-weight-medium: 500;
$hds-font-weight-bold: 700;
```

#### Border Radius & Shadows
```scss
$hds-border-radius-subtle: 0.125rem;
$hds-border-radius-base: 0.5rem;
$hds-border-radius-circle: 50%;

$hds-box-shadow-base: 0 1px 4px 0 rgba(46, 55, 65, 0.3);
$hds-box-shadow-hover: 0 5px 25px 0 rgba(46, 55, 65, 0.4);
```

## Icon System

### Location & Structure
- **Icon components**: `library/src/components/Icon/icons/`
- **370+ icons available**: Actions, UI elements, social media, navigation, business concepts

### Icon Usage Patterns

**Optimal Import** (recommended for bundle size):
```tsx
import { CircleCheckRegular } from '@hearsaycorp/hearsay-design-system/icons/CircleCheckRegular';
import { UserRegular } from '@hearsaycorp/hearsay-design-system/icons/UserRegular';
```

**Icon Properties**:
```tsx
// Size options
ICON_SIZE.XS    // 12px
ICON_SIZE.SM    // 16px  
ICON_SIZE.MD    // 24px (default)
ICON_SIZE.LG    // 32px
ICON_SIZE.XL    // 48px
ICON_SIZE.2XL   // 64px

// Semantic colors
ICON_COLOR.ACTION
ICON_COLOR.BRAND
ICON_COLOR.SUCCESS
ICON_COLOR.ERROR
ICON_COLOR.WARNING
ICON_COLOR.INFO
ICON_COLOR.TEXT
ICON_COLOR.WHITE
ICON_COLOR.DISABLED
// Plus social media colors: FACEBOOK, GOOGLE, TWITTER, etc.
```

**Common Icon Patterns**:
```tsx
// Status indicator
<CircleCheckRegular 
  color={CircleCheckRegular.COLOR.SUCCESS}
  size={CircleCheckRegular.SIZE.SM}
  ariaLabel="Success"
/>

// Navigation
<ChevronRightRegular 
  color={ChevronRightRegular.COLOR.ACTION}
  size={ChevronRightRegular.SIZE.SM}
/>

// Social media
<Facebook 
  color={Facebook.COLOR.FACEBOOK}
  size={Facebook.SIZE.MD}
/>
```

## Documentation Reference

### Component Documentation
- **Location**: `design-system-docs/`
- **Format**: MDX files for each component
- **Contents**: Props, usage examples, accessibility guidelines

**Key Documentation Files**:
- `design-system-docs/DesignSystemDecorator.mdx` - Context setup (essential)
- `design-system-docs/Icon.mdx` - Icon usage patterns
- `design-system-docs/Button.mdx` - Button component guide
- `design-system-docs/[Component].mdx` - Individual component guides

### Style Documentation
- **Location**: `docs/src/style-guide/sass-variables/`
- **Contents**: Visual examples and token references
- **Files**: Colors.mdx, FontSize.mdx, Spacing.mdx, etc.

## Build & Export Structure

### Package Exports (from `library/package.json`)
```json
{
  "main": "./lib/cjs/index.js",
  "module": "lib/index.js", 
  "types": "lib/types/src/index.d.ts",
  "exports": {
    ".": "standard component imports",
    "./*": "per-component imports", 
    "./icons/*": "individual icon imports",
    "./types": "TypeScript type definitions"
  }
}
```

### File Locations
- **Source**: `library/src/`
- **Built output**: `library/lib/`
- **Global styles**: `library/src/scss/hearsay-design-system.scss`
- **Component exports**: `library/src/index.ts`

## Best Practices for AI Implementation

### 1. Always Use DesignSystemDecorator
```tsx
// ✅ Correct - Wrap app with context
<DesignSystemDecorator>
  <MyApp />
</DesignSystemDecorator>

// ❌ Incorrect - HDS components won't have proper styles
<MyApp />
```

### 2. Use Semantic Colors and Sizes
```tsx
// ✅ Correct - Use semantic color enums
<Button theme={Button.THEME.PRIMARY} />
<CircleCheckRegular color={CircleCheckRegular.COLOR.SUCCESS} />

// ❌ Avoid - Don't use arbitrary color values  
<Button style={{backgroundColor: '#blue'}} />
```

### 3. Import Individual Icons
```tsx
// ✅ Correct - Import specific icons
import { UserRegular } from '@hearsaycorp/hearsay-design-system/icons/UserRegular';

// ❌ Incorrect - Imports entire icon library
import { UserRegular } from '@hearsaycorp/hearsay-design-system';
```

### 4. Use TypeScript Types
```tsx
import { ButtonProps } from '@hearsaycorp/hearsay-design-system';

const MyButton: React.FC<ButtonProps> = (props) => {
  return <Button {...props} />;
};
```

### 5. Accessibility Considerations
- Provide `ariaLabel` for icons that convey meaning
- Use semantic HTML elements provided by components
- Leverage built-in focus management and keyboard navigation

## Common Implementation Patterns

### Form Layout
```tsx
<DesignSystemDecorator>
  <form>
    <TextInput 
      label="Email"
      type="email"
      required
    />
    <Select 
      label="Department"
      options={departmentOptions}
    />
    <Checkbox 
      label="Subscribe to newsletter"
    />
    <Button 
      type="submit"
      theme={Button.THEME.PRIMARY}
      text="Submit"
    />
  </form>
</DesignSystemDecorator>
```

### Modal Dialog
```tsx
<Modal
  isOpen={isModalOpen}
  onClose={handleClose}
  title="Confirm Action"
>
  <Alert
    type={Alert.TYPE.WARNING}
    message="This action cannot be undone."
  />
  <div style={{marginTop: 'var(--hds-spacing-md)'}}>
    <Button 
      theme={Button.THEME.SECONDARY}
      text="Cancel"
      onClick={handleClose}
    />
    <Button 
      theme={Button.THEME.PRIMARY}
      text="Confirm"
      onClick={handleConfirm}
    />
  </div>
</Modal>
```

### Navigation with Icons
```tsx
<nav>
  <Link href="/dashboard">
    <HomeRegular 
      color={HomeRegular.COLOR.ACTION}
      size={HomeRegular.SIZE.SM}
    />
    Dashboard
  </Link>
  <Link href="/users">
    <UsersRegular 
      color={UsersRegular.COLOR.ACTION}
      size={UsersRegular.SIZE.SM}
    />
    Users
  </Link>
</nav>
```

## Troubleshooting

### Styles Not Applying
- **Issue**: Components appear unstyled
- **Solution**: Ensure `DesignSystemDecorator` wraps your application
- **Check**: Look for `data-design-system-context="hds-v9"` attribute in DOM

### Bundle Size Issues
- **Issue**: Large bundle size from icons
- **Solution**: Import individual icons instead of bulk imports
- **Check**: Use `import { SpecificIcon } from '@hearsaycorp/hearsay-design-system/icons/SpecificIcon'`

### TypeScript Errors
- **Issue**: Missing type definitions
- **Solution**: Import types from `'@hearsaycorp/hearsay-design-system'`
- **Check**: Verify component prop interfaces match expected types

### CSS Custom Properties Not Available
- **Issue**: `var(--hds-color-*)` properties undefined
- **Solution**: Confirm DesignSystemDecorator is applied to correct container
- **Check**: CSS custom properties only work within `[data-design-system-context="hds-v9"]` scope

---

## Quick Reference

**Essential imports for most applications**:
```tsx
import { 
  DesignSystemDecorator,
  Button,
  TextInput,
  Alert
} from '@hearsaycorp/hearsay-design-system';
```

**Most commonly used icons**:
```tsx
import { CircleCheckRegular } from '@hearsaycorp/hearsay-design-system/icons/CircleCheckRegular';
import { TriangleExclamationRegular } from '@hearsaycorp/hearsay-design-system/icons/TriangleExclamationRegular';
import { UserRegular } from '@hearsaycorp/hearsay-design-system/icons/UserRegular';
```

**Key design tokens**:
- Colors: `--hds-color-brand-300`, `--hds-color-success-200`, `--hds-color-error-200`
- Spacing: `--hds-spacing-sm`, `--hds-spacing-md`, `--hds-spacing-lg`
- Typography: `--hds-font-size-base`, `--hds-font-family-text`
