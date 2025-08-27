
# Hearsay Design System - AI Usage Instructions (Updated for Direct Imports)

## Overview

This repository contains the Hearsay Design System (HDS), a comprehensive React component library with design tokens, icons, and styling system. When working in a workspace alongside this design system repository, use this guide to properly import and implement HDS components using direct file imports.

## Package Information

- **Package Name**: `@hearsaycorp/hearsay-design-system`
- **Current Version**: `9.4.1`
- **Design System Context**: `hds-v9`
- **Import Method**: Direct source file imports (development setup)

## Quick Start

### 1. Essential Setup - DesignSystemDecorator

**CRITICAL**: Before using any HDS components, you MUST wrap your application with `DesignSystemDecorator` to enable CSS custom properties:

```tsx
import { DesignSystemDecorator } from '../../../hearsay-design-system/library/src/components/DesignSystemDecorator/DesignSystemDecorator';

function App() {
  return (
    <DesignSystemDecorator>
      {/* Your application content with HDS components */}
    </DesignSystemDecorator>
  );
}
```

### 2. Component Imports (Direct Source Files)

**Main Components** (import directly from source):
```tsx
import { Button } from '../../../hearsay-design-system/library/src/components/Button/Button';
import { BUTTON_THEME, BUTTON_SIZE, BUTTON_TYPES } from '../../../hearsay-design-system/library/src/components/Button/Button.types';
import { Alert } from '../../../hearsay-design-system/library/src/components/Alert/Alert';
import { ALERT_THEME } from '../../../hearsay-design-system/library/src/components/Alert/Alert.types';
import { TextInput } from '../../../hearsay-design-system/library/src/components/TextInput/TextInput';
import { TEXT_INPUT_TYPES } from '../../../hearsay-design-system/library/src/components/TextInput/TextInput.types';
import { ElevatedContainer } from '../../../hearsay-design-system/library/src/components/ElevatedContainer/ElevatedContainer';
import { Heading } from '../../../hearsay-design-system/library/src/components/Heading/Heading';
import { HEADING_SIZE } from '../../../hearsay-design-system/library/src/components/Heading/Heading.types';
```

**Individual Icons** (import specific icons):
```tsx
import { CircleCheckRegular } from '../../../hearsay-design-system/library/src/components/Icon/icons/CircleCheckRegular';
import { UserRegular } from '../../../hearsay-design-system/library/src/components/Icon/icons/UserRegular';
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
- **Enum imports**: Import types/enums separately from `.types.ts` files
- **TypeScript support**: Full type definitions available

### Common Component Patterns

**Button with size and theme:**
```tsx
import { Button } from '../../../hearsay-design-system/library/src/components/Button/Button';
import { BUTTON_THEME, BUTTON_SIZE } from '../../../hearsay-design-system/library/src/components/Button/Button.types';

<Button 
  text="Click me"
  size={BUTTON_SIZE.MD}
  theme={BUTTON_THEME.PRIMARY}
  onClick={handleClick}
/>
```

**TextInput with validation:**
```tsx
import { TextInput } from '../../../hearsay-design-system/library/src/components/TextInput/TextInput';
import { TEXT_INPUT_TYPES } from '../../../hearsay-design-system/library/src/components/TextInput/TextInput.types';

<TextInput
  labelText="Email address"
  type={TEXT_INPUT_TYPES.EMAIL}
  value={email}
  onChange={(e) => setEmail(e.target.value)}
  placeholder="Enter your email"
  required
  error={emailError}
/>
```

**Alert with theme:**
```tsx
import { Alert } from '../../../hearsay-design-system/library/src/components/Alert/Alert';
import { ALERT_THEME } from '../../../hearsay-design-system/library/src/components/Alert/Alert.types';

<Alert
  theme={ALERT_THEME.ERROR}
  title="Error occurred"
  onDismiss={() => setError('')}
  dismissText="Dismiss"
>
  Something went wrong. Please try again.
</Alert>
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

**Direct Import** (recommended for bundle size):
```tsx
import { CircleCheckRegular } from '../../../hearsay-design-system/library/src/components/Icon/icons/CircleCheckRegular';
import { UserRegular } from '../../../hearsay-design-system/library/src/components/Icon/icons/UserRegular';
```

**Icon Properties**:
```tsx
// Size options (check individual icon files for available enums)
size="sm"    // 16px  
size="md"    // 24px (default)
size="lg"    // 32px

// Colors (check individual icon files for available enums)
color="action"
color="success"
color="error"
color="warning"
color="info"
```

**Common Icon Patterns**:
```tsx
// Status indicator
<CircleCheckRegular 
  size="sm"
  ariaLabel="Success"
/>

// Navigation
<ChevronRightRegular 
  size="sm"
/>

// User avatar
<UserRegular 
  size="md"
/>
```

## Best Practices for AI Implementation

### 1. Always Use DesignSystemDecorator
```tsx
import { DesignSystemDecorator } from '../../../hearsay-design-system/library/src/components/DesignSystemDecorator/DesignSystemDecorator';

// ✅ Correct - Wrap app with context
<DesignSystemDecorator>
  <MyApp />
</DesignSystemDecorator>

// ❌ Incorrect - HDS components won't have proper styles
<MyApp />
```

### 2. Import Components and Types Separately
```tsx
// ✅ Correct - Import component and types separately
import { Button } from '../../../hearsay-design-system/library/src/components/Button/Button';
import { BUTTON_THEME, BUTTON_SIZE, BUTTON_TYPES } from '../../../hearsay-design-system/library/src/components/Button/Button.types';

// ❌ Incorrect - Trying to import from package root
import { Button, BUTTON_THEME } from '@hearsaycorp/hearsay-design-system';
```

### 3. Use Semantic Themes and Sizes
```tsx
// ✅ Correct - Use semantic enum values
<Button theme={BUTTON_THEME.PRIMARY} size={BUTTON_SIZE.MD} />
<Alert theme={ALERT_THEME.ERROR} />

// ❌ Avoid - Don't use string literals  
<Button theme="primary" size="medium" />
```

### 4. Import Individual Icons
```tsx
// ✅ Correct - Import specific icons
import { UserRegular } from '../../../hearsay-design-system/library/src/components/Icon/icons/UserRegular';

// ❌ Incorrect - Don't import from generic Icon component
import { Icon } from '../../../hearsay-design-system/library/src/components/Icon/Icon';
```

### 5. TypeScript Types
```tsx
import { ButtonProps } from '../../../hearsay-design-system/library/src/components/Button/Button.types';
import { TextInputProps } from '../../../hearsay-design-system/library/src/components/TextInput/TextInput.types';

const MyButton: React.FC<ButtonProps> = (props) => {
  return <Button {...props} />;
};
```

## Common Implementation Patterns

### Form Layout
```tsx
import React, { useState } from 'react';
import { DesignSystemDecorator } from '../../../hearsay-design-system/library/src/components/DesignSystemDecorator/DesignSystemDecorator';
import { TextInput } from '../../../hearsay-design-system/library/src/components/TextInput/TextInput';
import { TEXT_INPUT_TYPES } from '../../../hearsay-design-system/library/src/components/TextInput/TextInput.types';
import { Button } from '../../../hearsay-design-system/library/src/components/Button/Button';
import { BUTTON_THEME, BUTTON_TYPES } from '../../../hearsay-design-system/library/src/components/Button/Button.types';
import { Checkbox } from '../../../hearsay-design-system/library/src/components/Checkbox/Checkbox';

<DesignSystemDecorator>
  <form>
    <TextInput 
      labelText="Email"
      type={TEXT_INPUT_TYPES.EMAIL}
      required
    />
    <TextInput 
      labelText="Department"
      type={TEXT_INPUT_TYPES.TEXT}
    />
    <Checkbox 
      labelText="Subscribe to newsletter"
    />
    <Button 
      type={BUTTON_TYPES.SUBMIT}
      theme={BUTTON_THEME.PRIMARY}
      text="Submit"
    />
  </form>
</DesignSystemDecorator>
```

### Modal Dialog with Alert
```tsx
import { Modal } from '../../../hearsay-design-system/library/src/components/Modal/Modal';
import { Alert } from '../../../hearsay-design-system/library/src/components/Alert/Alert';
import { ALERT_THEME } from '../../../hearsay-design-system/library/src/components/Alert/Alert.types';
import { Button } from '../../../hearsay-design-system/library/src/components/Button/Button';
import { BUTTON_THEME } from '../../../hearsay-design-system/library/src/components/Button/Button.types';

<Modal
  isOpen={isModalOpen}
  onClose={handleClose}
  title="Confirm Action"
>
  <Alert
    theme={ALERT_THEME.WARNING}
    title="Warning"
  >
    This action cannot be undone.
  </Alert>
  <div style={{marginTop: 'var(--hds-spacing-md)'}}>
    <Button 
      theme={BUTTON_THEME.SECONDARY}
      text="Cancel"
      onClick={handleClose}
    />
    <Button 
      theme={BUTTON_THEME.PRIMARY}
      text="Confirm"
      onClick={handleConfirm}
    />
  </div>
</Modal>
```

## Troubleshooting

### Styles Not Applying
- **Issue**: Components appear unstyled
- **Solution**: Ensure `DesignSystemDecorator` wraps your application
- **Check**: Look for `data-design-system-context="hds-v9"` attribute in DOM

### Import Errors
- **Issue**: Cannot resolve module imports
- **Solution**: Use direct file paths for components and types
- **Check**: Ensure paths point to actual component files

### TypeScript Errors
- **Issue**: Missing type definitions
- **Solution**: Import types from `.types.ts` files separately
- **Check**: Verify component prop interfaces match expected types

### CSS Custom Properties Not Available
- **Issue**: `var(--hds-color-*)` properties undefined
- **Solution**: Confirm DesignSystemDecorator is applied to correct container
- **Check**: CSS custom properties only work within `[data-design-system-context="hds-v9"]` scope

---

## Quick Reference

**Essential imports for most applications**:
```tsx
import { DesignSystemDecorator } from '../../../hearsay-design-system/library/src/components/DesignSystemDecorator/DesignSystemDecorator';
import { Button } from '../../../hearsay-design-system/library/src/components/Button/Button';
import { BUTTON_THEME, BUTTON_SIZE, BUTTON_TYPES } from '../../../hearsay-design-system/library/src/components/Button/Button.types';
import { TextInput } from '../../../hearsay-design-system/library/src/components/TextInput/TextInput';
import { TEXT_INPUT_TYPES } from '../../../hearsay-design-system/library/src/components/TextInput/TextInput.types';
import { Alert } from '../../../hearsay-design-system/library/src/components/Alert/Alert';
import { ALERT_THEME } from '../../../hearsay-design-system/library/src/components/Alert/Alert.types';
```

**Most commonly used icons**:
```tsx
import { CircleCheckRegular } from '../../../hearsay-design-system/library/src/components/Icon/icons/CircleCheckRegular';
import { TriangleExclamationRegular } from '../../../hearsay-design-system/library/src/components/Icon/icons/TriangleExclamationRegular';
import { UserRegular } from '../../../hearsay-design-system/library/src/components/Icon/icons/UserRegular';
```

**Key design tokens**:
- Colors: `--hds-color-brand-300`, `--hds-color-success-200`, `--hds-color-error-200`
- Spacing: `--hds-spacing-sm`, `--hds-spacing-md`, `--hds-spacing-lg`
- Typography: `--hds-font-size-base`, `--hds-font-family-text`
