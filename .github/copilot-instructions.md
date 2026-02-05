# Copilot Instructions for AI Agents

## Project Overview
This codebase is a WordPress installation, containing both core WordPress files and custom project files. The main entry point is `index.php`, with core logic distributed across `wp-admin/`, `wp-includes/`, and `wp-content/`.

## Key Directories
- `wp-admin/`: WordPress admin dashboard and management scripts.
- `wp-includes/`: Core WordPress functions, classes, and APIs.
- `wp-content/`: User content, including:
  - `plugins/`: Custom and third-party plugins.
  - `themes/`: Site themes.
  - `uploads/`: Media uploads.

## Customization Points
- Custom code should be placed in `wp-content/plugins/` (for plugins) or `wp-content/themes/` (for themes).
- Avoid modifying core files in `wp-admin/` or `wp-includes/` to ensure upgradability.

## Developer Workflows
- **No build step**: PHP files are interpreted directly by the server (XAMPP stack).
- **Testing**: Manual testing via browser is typical. Automated tests are not present by default.
- **Debugging**: Enable `WP_DEBUG` in `wp-config.php` for verbose error output.
- **Plugin/Theme Development**: Develop in `wp-content/plugins/` or `wp-content/themes/`, then activate via the WordPress admin UI.

## Project-Specific Conventions
- Follow WordPress coding standards (see [wp-includes/](../wp-includes/) for examples).
- Use hooks (`add_action`, `add_filter`) for extending functionality.
- Use `wp_enqueue_script` and `wp_enqueue_style` for adding scripts/styles.
- Database access should use `$wpdb` for queries.

## Integration Points
- External integrations (APIs, services) should be implemented as plugins.
- Cross-component communication uses WordPress hooks and filters.

## Examples
- To add a custom admin page, create a plugin in `wp-content/plugins/` and use `add_menu_page()`.
- To enqueue a script, use `wp_enqueue_script()` in a theme or plugin.

## References
- [wp-config.php](../wp-config.php): Site configuration and debug settings.
- [wp-content/plugins/](../wp-content/plugins/): Place for custom plugins.
- [wp-content/themes/](../wp-content/themes/): Place for custom themes.

---
For more, see the [WordPress Developer Handbook](https://developer.wordpress.org/).
