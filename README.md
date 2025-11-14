# Admin Panel — bez_nicku

Modern, dark admin panel UI built with HTML, CSS and minimal JavaScript. Includes a dashboard, users table and settings with live theming (theme presets + accent color picker). Designed as a lightweight control panel for demos and local admin tooling.

## Features
- Clean glassmorphism-style UI with subtle neon accents
- Dashboard with stats, recent activity and system health bars
- Users view with search, basic actions and status badges
- Settings view: site title, registrations toggle, theme selector and accent color picker
- Two theme presets (Default, Green) + custom accent color (saved in localStorage)
- Responsive layout with collapsible sidebar for small screens
- Accessible: respects prefers-reduced-motion

## Demo / Preview
Open:
-[beznicku.pl](https://beznicku.pl/)
in a browser to view the panel.

## Technologies
- HTML5
- CSS3 (CSS variables for theming)
- Vanilla JavaScript (UI state, localStorage)
- Font Awesome (icons)

## Installation / Run locally
1. Clone or copy the project.
2. Ensure `AdminPanel.html` and `AdminPanel.css` are present.
3. Open `AdminPanel.html` in a modern browser (no build step required).


## Usage
- Navigation is hash-based: `#dashboard`, `#users`, `#settings`. Dashboard is shown by default.
- Settings form is client-side only — pressing Save shows a toast (no server persistence).
- Theme selection and accent color are saved to localStorage and applied immediately.

## Theming & Customization
- Presets:
  - Default (loaded on first run)
  - Green (apply via Settings → Theme)
- Accent color:
  - Use Settings → Accent color to change `--accent`. Value is stored in localStorage.
- Programmatic usage:
  - Apply green theme:
    ```js
    document.documentElement.setAttribute('data-theme', 'green');
    localStorage.setItem('adminTheme', 'green');
    ```
  - Set accent color:
    ```js
    document.documentElement.style.setProperty('--accent', '#3adb7f');
    localStorage.setItem('adminAccent', '#3adb7f');
    ```

## Integration notes
- The UI is static. Connect to a backend by:
  - Replacing table rows / stat values with fetched API data.
  - Submitting the settings form to an API endpoint.
  - Implementing real authentication for the admin routes.
- Sidebar navigation is client-side; adjust to server routing if needed.

## File structure
- Assets/
  - AdminPanel.html — main UI (HTML + JS)
  - AdminPanel.css — styles and theme overrides
- (optional) Extract styles or scripts to separate folders for larger projects

## Accessibility & Reduced Motion
- The project includes reduced-motion handling. To further reduce animations, add:
```css
@media (prefers-reduced-motion: reduce){
  *{transition:none!important;animation:none!important}
}
```

## Contribution
- PRs and issues welcome. Keep changes focused: theming, accessibility, backend integration, or modularization.

## License
MIT — free to use and modify. Include attribution if reused publicly.

## Author & Contact
- Created by bez_nicku
- Email: heyitsbeznicku@gmail.com
- Website: https://beznicku.pl
