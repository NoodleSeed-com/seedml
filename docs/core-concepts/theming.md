# Theming

Seed Spec provides a simple hierarchical theming system that controls all visual aspects of your application.

## Basic Usage

```yaml
app MyApp {
  ui {
    theme: "light"  # Use built-in light theme
  }
}
```

## Theme Properties

Themes control these visual aspects:

### Colors
```yaml
colors:
  primary: "#0066cc"
  secondary: "#6c757d"
  background: "#ffffff"
  surface: "#f8f9fa"
  text: "#212529"
  error: "#dc3545"
  warning: "#ffc107"
  success: "#28a745"
```

### Typography
```yaml
typography:
  fontFamily: 
    base: "Inter, system-ui, sans-serif"
    heading: "Poppins, sans-serif"
  fontSize:
    xs: "0.75rem"
    sm: "0.875rem"
    base: "1rem"
    lg: "1.125rem"
    xl: "1.25rem"
  fontWeight:
    normal: "400"
    medium: "500"
    bold: "700"
  lineHeight:
    tight: "1.25"
    normal: "1.5"
    relaxed: "1.75"
```

### Spacing
```yaml
spacing:
  xs: "0.25rem"
  sm: "0.5rem"
  md: "1rem"
  lg: "1.5rem"
  xl: "2rem"
  xxl: "3rem"
```

### Borders & Shadows
```yaml
borders:
  radius:
    sm: "0.25rem"
    md: "0.5rem"
    lg: "1rem"
    full: "9999px"
  width:
    thin: "1px"
    medium: "2px"
    thick: "4px"

shadows:
  sm: "0 1px 2px rgba(0,0,0,0.05)"
  md: "0 4px 6px rgba(0,0,0,0.1)"
  lg: "0 10px 15px rgba(0,0,0,0.1)"
```

## Theme Hierarchy

Themes inherit from parent themes:
```ascii
           ┌─────────┐
           │ default │ Base theme
           └────┬────┘
                │
        ┌───────┴───────┐
        │               │
    ┌───┴───┐       ┌───┴───┐
    │ light │       │ dark  │
    └───────┘       └───────┘
```

## Theme Overrides

Override specific values while keeping other defaults:

```yaml
app MyApp {
  ui {
    theme: "light"
    overrides: {
      colors.primary: "#0066cc"
    }
  }
}
```

## Smart Defaults

The theme system follows Seed's smart defaults principle:
- Built-in themes provide production-ready styling
- Override only what needs to be different
- Maintain consistent visual patterns
