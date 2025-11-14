# Admin Panel — bez_nicku

Modern, dark admin panel UI built with HTML, CSS and minimal JavaScript. Includes a dashboard, users table and settings with live theming (theme presets). Designed as a lightweight control panel for demos and local admin tooling.

## Features
- Clean glassmorphism-style UI with subtle neon accents
- Dashboard with stats, recent activity and system health bars
- Users view with search, basic actions and status badges
- Settings view: site title, registrations toggle, theme selector
- Two theme presets (Default, Green) with localStorage persistence
- Responsive layout with collapsible sidebar for small screens
- Accessible: respects prefers-reduced-motion

## Demo / Preview
Open `AdminPanel.html` in your browser to view the panel.

Visit [beznicku.pl](https://beznicku.pl/) to see it in action.

## Technologies
- HTML5
- CSS3 (CSS variables for theming)
- Vanilla JavaScript (UI state, localStorage)
- Font Awesome 6.4.0 (icons)

## Installation / Run locally
1. Clone or copy the project.
2. Ensure `AdminPanel.html` and `AdminPanel.css` are present in the same directory.
3. Open `AdminPanel.html` in a modern browser (no build step required).

Quick Windows open example:
```bat
start "" "e:\path\to\AdminPanel.html"
```

## Usage
- Navigation is hash-based: `#dashboard`, `#users`, `#settings`. Dashboard is shown by default.
- Settings form is client-side only — pressing Save shows a toast notification (no server persistence).
- Theme selection is saved to localStorage and applied immediately.
- User search filters the table in real-time.

## Theming & Customization
- **Presets:**
  - Default (loaded on first run — cyan accent)
  - Green (apply via Settings → Theme)
- **Programmatic usage:**
  - Apply green theme:
    ```js
    document.documentElement.setAttribute('data-theme', 'green');
    localStorage.setItem('adminTheme', 'green');
    ```
  - Reset to default:
    ```js
    document.documentElement.removeAttribute('data-theme');
    localStorage.setItem('adminTheme', 'default');
    ```

## Integration notes
- The UI is static. Connect to a backend by:
  - Replacing table rows / stat values with fetched API data.
  - Submitting the settings form to an API endpoint.
  - Implementing real authentication for the admin routes.
- Sidebar navigation is client-side; adjust to server routing if needed.
- Add real user management by connecting the Users section to an API.

## File structure
```
Assets/
├── AdminPanel.html      — main UI (HTML + embedded JS)
├── AdminPanel.css       — styles and theme presets
└── (optional) README.md
```

For larger projects, extract styles and scripts to separate folders:
```
Admin/
├── index.html
├── css/
│   └── admin.css
├── js/
│   └── admin.js
└── README.md
```

## Accessibility & Reduced Motion
- The project respects the `prefers-reduced-motion` media query. To enforce it globally:
```css
@media (prefers-reduced-motion: reduce) {
  * {
    transition: none !important;
    animation: none !important;
  }
}
```

## Contribution
- Issues and PRs welcome.
- Keep changes focused: theming improvements, backend integration examples, accessibility enhancements, or code modularization.

## License
MIT — free to use and modify. Include attribution if reusing in public projects.

## Author & Contact
- Created by **bez_nicku**
- Email: heyitsbeznicku@gmail.com
- Website: [beznicku.pl](https://beznicku.pl/)
- Discord: bez_nicku

---
