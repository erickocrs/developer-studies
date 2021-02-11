# WordPress

- Official Developer Documentation

  https://developer.wordpress.org/

- ## Plugins

  - GitHub - Sample Empty Plugin - [WordPress-Plugin-Boilerplate](https://github.com/DevinVinson/WordPress-Plugin-Boilerplate)

  - GitHub - Tutorial with Examples? - https://github.com/JoeSz/WordPress-Plugin-Boilerplate-Tutorial

    

  - Plugin Info / Header Requirements

    https://developer.wordpress.org/plugins/plugin-basics/header-requirements/

    ```php
    /**
     * Plugin Name: YOUR PLUGIN NAME
     */
    ```

    ```php
    /**
     * Plugin Name
     *
     * @package           PluginPackage
     * @author            Your Name
     * @copyright         2019 Your Name or Company Name
     * @license           GPL-2.0-or-later
     *
     * @wordpress-plugin
     * Plugin Name:       Plugin Name
     * Plugin URI:        https://example.com/plugin-name
     * Description:       Description of the plugin.
     * Version:           1.0.0
     * Requires at least: 5.2
     * Requires PHP:      7.2
     * Author:            Your Name
     * Author URI:        https://example.com
     * Text Domain:       plugin-slug
     * License:           GPL v2 or later
     * License URI:       http://www.gnu.org/licenses/gpl-2.0.txt
     */
    ```

    

  - on Activation / Deactivation Plugin Hooks Functions - (custom database tables, option values)

    https://developer.wordpress.org/plugins/plugin-basics/activation-deactivation-hooks/

    ```php
    register_activation_hook( __FILE__, 'pluginprefix_function_to_run' );
    register_deactivation_hook( __FILE__, 'pluginprefix_function_to_run' );
    ```

  

  - ## Hooks - Actions (No Return) / Filters (Return) `htmls here`

    - Actions Add Function

      https://codex.wordpress.org/Plugin_API/Action_Reference

      ```php
      add_action($tag, $function_name, $priority, $numberOfArguments)
      
      //Standard
      function wporg_callback() {
          // do something
      }
      add_action( 'init', 'wporg_callback' );
      
      //Priority 
      add_action('init', 'wporg_callback_run_me_normal');
      add_action('init', 'wporg_callback_run_me_early', 9);
      add_action('init', 'wporg_callback_run_me_later', 11);
      
      //Number of Arguments
      add_action('save_post', 'wporg_custom', 10, 2);
      ```

      

    - Filter Add Function  `htmls here`

      https://codex.wordpress.org/Plugin_API/Filter_Reference

      ```php
      add_filter($tag, $function_name, $priority, $numberOfArguments)
          
      //Standard
      function wporg_filter_title( $title ) {
          return 'The ' . $title . ' was filtered';
      }
      add_filter( 'the_title', 'wporg_filter_title' );
      
      //$tag, $function_name, $priority, $numberOfArguments
      add_filter('save_post', 'wporg_custom', 10, 2);
      ```

      

    - Custom Hooks -  *`!Plugins Comunicate each`*  other used to provide functions to another plugins

      *To create a custom hook, use [do_action()](https://developer.wordpress.org/reference/functions/do_action/) for [Actions](https://developer.wordpress.org/plugins/hooks/actions/) and [apply_filters()](https://developer.wordpress.org/reference/functions/apply_filters/) for [Filters](https://developer.wordpress.org/plugins/hooks/filters/).*

      https://developer.wordpress.org/plugins/hooks/custom-hooks/

      

    - Removing Actions and FIlters

      ```php
      remove_action()
      remove_filter()
      ```

    - Debbung with all 

      ```php
      function wporg_debug() {
          echo '<p>' . current_action() . '</p>';
      }
      add_action( 'all', 'wporg_debug' );
      ```

      

  - uninstall.php

    https://developer.wordpress.org/plugins/plugin-basics/uninstall-methods/#method-2-uninstall-php

    

  - Folder Structure

    ```
    /plugin-name
         plugin-name.php
         uninstall.php
         /languages
         /includes
         /admin
              /js
              /css
              /images
         /public
              /js
              /css
              /images
    ```

    

  - is in ? Admin Mode ?

    ```php
    if ( is_admin() ) {
        // we are in admin mode
        require_once __DIR__ . '/admin/plugin-name-admin.php';
    }
    ```

  - GET Path Url Function

    ```php
    //Plugins
    plugins_url()
    plugin_dir_url()
    plugin_dir_path()
    plugin_basename()
    
    //Themes
    get_template_directory_uri()
    get_stylesheet_directory_uri()
    get_stylesheet_uri()
    get_theme_root_uri()
    get_theme_root()
    get_theme_roots()
    get_stylesheet_directory()
    get_template_directory()
        
    //Site Home
    home_url()
    get_home_path()
        
    //Multi Site
    get_admin_url()
    get_home_url()
    get_site_url()
    network_admin_url()
    network_site_url()
    network_home_url()
        
    //CONSTANTS
    WP_CONTENT_DIR  // no trailing slash, full paths only
    WP_CONTENT_URL  // full url 
    WP_PLUGIN_DIR  // full path, no trailing slash
    WP_PLUGIN_URL  // full url, no trailing slash
    ```

    | [home_url()](https://developer.wordpress.org/reference/functions/home_url/) | Home URL                                | [http://www.example.com](http://www.example.com/)            |
    | ------------------------------------------------------------ | --------------------------------------- | ------------------------------------------------------------ |
    | [site_url()](https://developer.wordpress.org/reference/functions/site_url/) | Site directory URL                      | [http://www.example.com](http://www.example.com/) or http://www.example.com/wordpress |
    | [admin_url()](https://developer.wordpress.org/reference/functions/admin_url/) | Admin directory URL                     | http://www.example.com/wp-admin                              |
    | [includes_url()](https://developer.wordpress.org/reference/functions/includes_url/) | Includes directory URL                  | http://www.example.com/wp-includes                           |
    | [content_url()](https://developer.wordpress.org/reference/functions/content_url/) | Content directory URL                   | http://www.example.com/wp-content                            |
    | [plugins_url()](https://developer.wordpress.org/reference/functions/plugins_url/) | Plugins directory URL                   | http://www.example.com/wp-content/plugins                    |
    | [wp_upload_dir()](https://developer.wordpress.org/reference/functions/wp_upload_dir/) | Upload directory URL (returns an array) | [http://www.example.co](http://www.example.com/wp-content/uploads) |

  

- ## Themes

  - YouTube - How to Create a Custom WordPress Theme - Full Course

    https://www.youtube.com/watch?v=-h7gOJbIpmo&ab_channel=freeCodeCamp.org

  - YouTube - How to Build a WordPress Theme from Scratch with WooCommerce (2019)

    https://www.youtube.com/watch?v=TlmDsU8GirU&ab_channel=MrDigital



- [x] WooCommerce e-commerce plugin

- [ ] Frontity React Framework using the rest API ?

  

## PHP Plus Knowledge

### Check if  exists

- **Variables**: [isset()](http://php.net/manual/en/function.isset.php) (includes arrays, objects, etc.)
- **Functions**: [function_exists()](http://php.net/manual/en/function.function-exists.php)
- **Classes**: [class_exists()](http://php.net/manual/en/function.class-exists.php)
- **Constants**: [defined()](http://php.net/manual/en/function.defined.php)

### PHP Class Definition

```php
if ( !class_exists( 'WPOrg_Plugin' ) ) {
    
    class WPOrg_Plugin
    {
        public static function init() {
            register_setting( 'wporg_settings', 'wporg_option_foo' );
        }
 
        public static function get_foo() {
            return get_option( 'wporg_option_foo' );
        }
    }
 
    WPOrg_Plugin::init();
    WPOrg_Plugin::get_foo();
}
```