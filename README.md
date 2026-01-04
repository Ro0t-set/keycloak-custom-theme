# Keycloak Custom Theme

A modern, clean, and professional custom theme for Keycloak login pages.

## Documentation

Full documentation available at: [https://ro0t-set.github.io/keycloak-custom-theme/](https://ro0t-set.github.io/keycloak-custom-theme/)

## Features

- **Modern Design**: Clean and contemporary UI with smooth gradients and subtle shadows
- **Responsive Layout**: Fully responsive design that works on all device sizes
- **Enhanced UX**: Improved form controls, password visibility toggle, and elegant animations
- **Customizable**: Easy to modify colors, spacing, and other design elements
- **Clean Error Handling**: Simple, non-intrusive error messages
- **Accessibility**: ARIA-compliant form controls and labels

## Quick Start with Docker

```dockerfile
FROM quay.io/keycloak/keycloak:26.1.5

COPY ./custom/ /opt/keycloak/themes/custom/

ENTRYPOINT ["/opt/keycloak/bin/kc.sh"]
```

Build and run:

```bash
docker build -t keycloak-custom .

docker run -p 8080:8080 \
  -e KEYCLOAK_ADMIN=admin \
  -e KEYCLOAK_ADMIN_PASSWORD=admin \
  keycloak-custom start-dev
```

## Manual Installation

1. Copy the `custom` folder to your Keycloak themes directory:

   ```bash
   cp -r custom /path/to/keycloak/themes/
   ```

2. Restart Keycloak or reload the themes

3. In Keycloak Admin Console:
   - Go to **Realm Settings** → **Themes**
   - Select `custom` from the **Login Theme** dropdown
   - Save changes

## Theme Structure

```text
custom/
└── login/
    ├── theme.properties      # Theme configuration
    └── resources/
        ├── css/
        │   └── styles.css    # Custom styles
        └── img/
            └── favicon.svg   # Custom favicon
```

## Customization

### Colors

The theme uses HSL colors for easy customization. Main color variables in `styles.css`:

- **Primary Dark**: `hsl(222, 47%, 11%)` - Main buttons and headings
- **Secondary Gray**: `hsl(215, 16%, 47%)` - Links and secondary text
- **Border Gray**: `hsl(214, 32%, 91%)` - Borders and dividers
- **Background**: `hsl(0, 0%, 98%)` - Page background
- **Error Red**: `hsl(0, 70%, 45%)` - Error messages

### Typography

The theme uses system fonts for optimal performance:

```css
font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, "Helvetica Neue", Arial, sans-serif
```

### Styling Elements

The theme includes custom styling for:

- Login forms
- Password fields with visibility toggle
- Error and success messages
- Social provider buttons
- Checkboxes and form controls
- Registration links

## Browser Support

- Chrome/Edge (latest)
- Firefox (latest)
- Safari (latest)
- Mobile browsers (iOS Safari, Chrome Mobile)

## Screenshots

The theme provides:

- Clean card-based login form
- Gradient header text
- Rounded corners and subtle shadows
- Hover effects on interactive elements
- Smooth transitions and animations

## License

This theme is provided as-is for use with Keycloak authentication servers.

## Contributing

Feel free to submit issues or pull requests for improvements.

## Credits

Built with modern CSS practices and designed for optimal user experience.
