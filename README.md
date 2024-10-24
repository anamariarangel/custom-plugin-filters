# Custom WordPress Plugin

## Description
This WordPress plugin adds various custom functionalities to the WordPress admin panel, including category filters, subcategory filters, featured image columns, restricted access to specific categories, and integration with an external API to create posts automatically. This plugin is designed to demonstrate advanced WordPress development capabilities, with a focus on secure coding practices and efficient implementation.

## Features
- **Category Filter in Admin Panel:** Adds a dropdown filter for categories in the WordPress admin, allowing users to filter posts based on selected categories.
- **Subcategory Filter for Custom Post Types:** Provides a subcategory filter specifically for custom post types, enhancing the admin panel's usability for managing large sets of categorized content.
- **Featured Image Column in Admin Table:** Adds a column to the admin post list, displaying the featured image of each post.
- **Restricted Access to Specific Categories:** Limits access to certain categories based on user authentication, redirecting unauthenticated users to the login page.
- **API Integration:** Connects to an external API, retrieves data, and creates posts automatically, saving relevant metadata. The plugin uses secure HTTP headers and variable sanitization to ensure safe data handling.
- **Cron Job for Automated API Calls:** Schedules hourly cron jobs to check for new data from the API and create posts accordingly.

## Requirements
- WordPress 5.0 or higher
- PHP 7.4 or higher

## Installation
1. Download the plugin files.
2. Upload the plugin folder to the `/wp-content/plugins/` directory.
3. Activate the plugin through the 'Plugins' menu in WordPress.

## How It Works
This plugin utilizes WordPress hooks, filters, and actions to add functionality to the admin panel and interact with external APIs. Here is an overview of its key components:

### Category and Subcategory Filters
- **Admin UI Enhancements:** The plugin uses the `restrict_manage_posts` action hook to add dropdown filters for categories and subcategories directly in the admin panel.
- **Post Query Modification:** It filters post queries using the `parse_query` filter, allowing users to view only posts that match the selected category or subcategory.

### Featured Image Column
- **Table Column Modification:** The plugin uses the `manage_posts_columns` filter to add a 'Featured Image' column to the post list.
- **Thumbnail Display:** The `manage_posts_custom_column` action is used to display the post's featured image in the admin panel, providing a quick visual reference.

### API Integration
- **External API Connection:** The plugin connects to an external API using the `wp_remote_get()` function, retrieves data, and creates posts automatically.
- **Post Creation:** The plugin checks for existing posts to avoid duplicates and uses the `wp_insert_post()` function to create new posts, along with `update_post_meta()` to save metadata.
- **Cron Scheduling:** The plugin sets up an hourly cron job using `wp_schedule_event()` to automate API checks and post creation, ensuring content is updated regularly.

## Security Considerations
- **Data Sanitization:** All user inputs and API responses are sanitized using WordPress functions like `sanitize_text_field()` and `esc_url()`.
- **Environment Variables:** Sensitive data, such as API tokens, are stored as environment variables for added security.
- **Error Handling:** The plugin uses error handling to ensure reliable execution and to display error messages in the admin panel if API requests fail.

## Author
**Ana Maria Rangel**  
Web Developer | WordPress Expert

## Why This Plugin Stands Out
This plugin was developed to showcase proficiency in WordPress plugin development, including:
- Deep understanding of WordPress architecture, hooks, and filters.
- Strong focus on secure coding practices and efficient data handling.
- Ability to create custom solutions tailored to specific business needs.
- Experience in working with RESTful APIs and automating processes via cron jobs.

## Future Improvements
Potential enhancements include:
- Adding an admin settings page to manage plugin options directly from the WordPress dashboard.
- Extending API functionality to handle more data types or integrate with additional services.
- Implementing better error logging for improved debugging and maintenance.

## License
This plugin is open-source and can be modified as needed for demonstration purposes.
