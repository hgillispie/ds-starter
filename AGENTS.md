# AI Agent Instructions

## UI Framework
Always use Material-UI (MUI) components for building user interfaces. Do not use plain HTML elements or other UI libraries unless specifically requested.

### MUI Component Usage
- Import MUI components from `@mui/material`
- Use MUI's theming system with `ThemeProvider` when needed
- Prefer MUI's built-in styling solutions (sx prop, styled components)
- Use MUI icons from `@mui/icons-material` when icons are needed

### Example imports:
```javascript
import { Button, TextField, Container, Box, Typography } from '@mui/material';
import { ThemeProvider, createTheme } from '@mui/material/styles';
```

## Routing Setup
When building multiple pages, always use React Router for navigation.

### React Router Configuration
1. Wrap the app with `BrowserRouter` in the main App component
2. Use `Routes` and `Route` components to define page routes
3. Use `Link` or `useNavigate` for navigation between pages
4. Create a consistent navigation structure (e.g., AppBar with navigation links)

### Example routing setup:
```javascript
import { BrowserRouter, Routes, Route, Link } from 'react-router-dom';
import { AppBar, Toolbar, Button } from '@mui/material';

function App() {
  return (
    <BrowserRouter>
      <AppBar position="static">
        <Toolbar>
          <Button component={Link} to="/" color="inherit">Home</Button>
          <Button component={Link} to="/about" color="inherit">About</Button>
        </Toolbar>
      </AppBar>
      <Routes>
        <Route path="/" element={<HomePage />} />
        <Route path="/about" element={<AboutPage />} />
      </Routes>
    </BrowserRouter>
  );
}
```

## Project Structure
When creating multiple pages:
- Create a `pages` or `views` directory under `src/`
- Each page should be its own component file
- Use consistent naming conventions (PascalCase for components)
- Create reusable components in `src/components/` directory