# PHP 8.6 and the top 100 WordPress plugins

**39 of the 100 most popular WordPress.org plugins use something PHP 8.6 deprecates.
Every file and line, tested on PHP 8.6.0RC4 with WordPress 7.1.1 on 28 October 2026.**

PHP 8.6 is released on 19 November 2026. A deprecation is not an error: the plugin keeps working, but sites with
`WP_DEBUG` on fill their logs, some hosts show the notices, and the code breaks in PHP 9. Plugin authors and site owners
can use this list to see what to fix or to check before upgrading.

## Method

- The current WordPress.org release of each of the 100 most popular plugins (55760 PHP files).
- `php -l` with the official PHP 8.6.0RC4 Windows build (php.net pre-release, checksum matched) for compile-time deprecations.
- PHP 8.6's own tokenizer for calls to functions deprecated in 8.6 (they fire only when that code runs).
- WordPress 7.1.1 on PHP 8.6 with each plugin activated alone: home page, a post, the dashboard and the plugins page
  as admin, recording what WordPress wrote to `debug.log`.
- Only deprecations that are new in PHP 8.6 (php-src `UPGRADING`, section 4) are listed.

## What shows up most

| Kind | PHP 8.6 message | Findings |
|---|---|---|
| `spl_object_hash` | Deprecated: Function spl_object_hash() is deprecated since 8.6, consider using spl_object_id() instead | 58 |
| `constructor-return` | Deprecated: Returning a value from a constructor is deprecated | 55 |
| `is_integer` | Deprecated: Function is_integer() is deprecated since 8.6, use is_int() instead | 28 |
| `namespace-constant` | Deprecated: Declaring class constant called 'namespace' is deprecated | 12 |
| `guzzle-is` | Deprecated: Using "is" as a class name is deprecated since 8.6 | 10 |
| `mbregex` | Deprecated: Function mb_ereg_replace() is deprecated since 8.6 | 5 |
| `is_double` | Deprecated: Function is_double() is deprecated since 8.6, use is_float() instead | 3 |
| `is_a-string` | Deprecated: Calling is_a() with a string when $allow_string is false | 2 |
| `destructor-return` | Deprecated: Returning a value from a destructor is deprecated | 2 |
| `strcoll` | Deprecated: Function strcoll() is deprecated since 8.6 | 1 |

## Plugins with findings

| Plugin | Installs | Version tested | Findings | Kinds |
|---|---|---|---|---|
| [elementor](https://wordpress.org/plugins/elementor/) | 10,000,000+ | 4.3.5 | 4 | constructor-return, namespace-constant, spl_object_hash |
| [wordpress-seo](https://wordpress.org/plugins/wordpress-seo/) | 10,000,000+ | 28.8 | 2 | guzzle-is, spl_object_hash |
| [litespeed-cache](https://wordpress.org/plugins/litespeed-cache/) | 7,000,000+ | 7.9.2 | 1 | spl_object_hash |
| [woocommerce](https://wordpress.org/plugins/woocommerce/) | 7,000,000+ | 11.2.1 | 5 | constructor-return, is_a-string, is_integer, spl_object_hash |
| [google-site-kit](https://wordpress.org/plugins/google-site-kit/) | 5,000,000+ | 1.190.0 | 4 | guzzle-is, is_integer, spl_object_hash |
| [wordfence](https://wordpress.org/plugins/wordfence/) | 5,000,000+ | 9.0.2 | 2 | constructor-return, namespace-constant |
| [seo-by-rank-math](https://wordpress.org/plugins/seo-by-rank-math/) | 4,000,000+ | 1.0.280 | 3 | namespace-constant, spl_object_hash |
| [updraftplus](https://wordpress.org/plugins/updraftplus/) | 4,000,000+ | 1.26.14 | 17 | constructor-return, guzzle-is, is_integer, spl_object_hash |
| [wp-mail-smtp](https://wordpress.org/plugins/wp-mail-smtp/) | 4,000,000+ | 4.10.3 | 2 | guzzle-is, spl_object_hash |
| [really-simple-ssl](https://wordpress.org/plugins/really-simple-ssl/) | 3,000,000+ | 9.8.4 | 1 | namespace-constant |
| [all-in-one-seo-pack](https://wordpress.org/plugins/all-in-one-seo-pack/) | 2,000,000+ | 5.0.4 | 4 | constructor-return, is_a-string |
| [google-analytics-for-wordpress](https://wordpress.org/plugins/google-analytics-for-wordpress/) | 2,000,000+ | 11.3.0 | 5 | constructor-return |
| [complianz-gdpr](https://wordpress.org/plugins/complianz-gdpr/) | 1,000,000+ | 7.5.6 | 6 | mbregex, spl_object_hash, strcoll |
| [duplicator](https://wordpress.org/plugins/duplicator/) | 1,000,000+ | 5.1.0 | 4 | guzzle-is, spl_object_hash |
| [elementskit-lite](https://wordpress.org/plugins/elementskit-lite/) | 1,000,000+ | 4.0.9 | 1 | namespace-constant |
| [ewww-image-optimizer](https://wordpress.org/plugins/ewww-image-optimizer/) | 1,000,000+ | 8.9.0 | 5 | constructor-return |
| [instagram-feed](https://wordpress.org/plugins/instagram-feed/) | 1,000,000+ | 6.14.0 | 2 | constructor-return, spl_object_hash |
| [limit-login-attempts-reloaded](https://wordpress.org/plugins/limit-login-attempts-reloaded/) | 1,000,000+ | 3.3.10 | 3 | constructor-return, spl_object_hash |
| [safe-svg](https://wordpress.org/plugins/safe-svg/) | 1,000,000+ | 2.5.2 | 2 | spl_object_hash |
| [sg-cachepress](https://wordpress.org/plugins/sg-cachepress/) | 1,000,000+ | 7.8.5 | 1 | constructor-return |
| [worker](https://wordpress.org/plugins/worker/) | 1,000,000+ | 4.9.38 | 4 | constructor-return, is_integer, spl_object_hash |
| [wp-smushit](https://wordpress.org/plugins/wp-smushit/) | 1,000,000+ | 4.3.5 | 3 | guzzle-is, spl_object_hash |
| [redux-framework](https://wordpress.org/plugins/redux-framework/) | 900,000+ | 4.5.16 | 2 | is_integer |
| [w3-total-cache](https://wordpress.org/plugins/w3-total-cache/) | 900,000+ | 2.11.0 | 31 | constructor-return, destructor-return, guzzle-is, is_double, spl_object_hash |
| [wpvivid-backuprestore](https://wordpress.org/plugins/wpvivid-backuprestore/) | 900,000+ | 0.9.136 | 13 | is_integer, spl_object_hash |
| [fluentform](https://wordpress.org/plugins/fluentform/) | 800,000+ | 6.2.16 | 3 | is_double, spl_object_hash |
| [google-listings-and-ads](https://wordpress.org/plugins/google-listings-and-ads/) | 800,000+ | 3.10.0 | 9 | guzzle-is, is_double, is_integer, spl_object_hash |
| [woocommerce-paypal-payments](https://wordpress.org/plugins/woocommerce-paypal-payments/) | 800,000+ | 4.2.0 | 4 | namespace-constant |
| [better-wp-security](https://wordpress.org/plugins/better-wp-security/) | 700,000+ | 10.0.6 | 2 | constructor-return |
| [creame-whatsapp-me](https://wordpress.org/plugins/creame-whatsapp-me/) | 700,000+ | 6.4.2 | 1 | namespace-constant |
| [duracelltomi-google-tag-manager](https://wordpress.org/plugins/duracelltomi-google-tag-manager/) | 700,000+ | 2.0.6 | 1 | namespace-constant |
| [fluent-smtp](https://wordpress.org/plugins/fluent-smtp/) | 700,000+ | 2.4.1 | 4 | constructor-return, guzzle-is, spl_object_hash |
| [mainwp-child](https://wordpress.org/plugins/mainwp-child/) | 700,000+ | 6.3 | 3 | mbregex, spl_object_hash |
| [backuply](https://wordpress.org/plugins/backuply/) | 600,000+ | 1.6.0 | 5 | constructor-return, is_integer |
| [coming-soon](https://wordpress.org/plugins/coming-soon/) | 600,000+ | 6.20.10 | 2 | constructor-return |
| [enable-media-replace](https://wordpress.org/plugins/enable-media-replace/) | 600,000+ | 4.2.3 | 2 | constructor-return |
| [forminator](https://wordpress.org/plugins/forminator/) | 600,000+ | 1.58.3 | 4 | guzzle-is, spl_object_hash |
| [post-types-order](https://wordpress.org/plugins/post-types-order/) | 600,000+ | 2.5.9 | 2 | constructor-return |
| [the-events-calendar](https://wordpress.org/plugins/the-events-calendar/) | 600,000+ | 6.18.2 | 7 | constructor-return, is_integer, namespace-constant, spl_object_hash |

`findings.csv` has one row per finding (file, line, when it fires); `results.json` is the full data, including the plugins
that came out clean.

Each plugin's findings with the fix are at [deadlinefix.com/php-8-6-wordpress-plugins](https://deadlinefix.com/php-8-6-wordpress-plugins).
A free plugin, PHP Upgrade Readiness, runs the same checks on your own site's plugins and theme.

Data: CC BY 4.0. Plugin names belong to their authors; this is an independent test, not affiliated with WordPress.org or
the PHP project. Spotted a false positive or a fix that shipped? Open an issue with the plugin version.
