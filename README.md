# PHP 8.6 and the top 100 WordPress plugins

**39 of the 100 most popular WordPress.org plugins use something PHP 8.6 deprecates.
Every file and line, tested on PHP 8.6.0RC4 with WordPress 7.1.1 on 28 October 2026.**

**PHP 8.6.0 came out on 19 November 2026. Re-run on the final build that day: 39 of 100, 178 findings, the same as on 17 November; PHP's own compile-time messages match.** See [release day](#release-day-19-november-2026).

**Re-checked on 17 November 2026, two days before the release: still 39 of 100.** See [the re-check](#re-check-17-november-2026).

PHP 8.6.0 was released on 19 November 2026. A deprecation is not an error: the plugin keeps working, but sites with
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

## Release day, 19 November 2026

PHP 8.6.0 was released on 19 November 2026 ([announcement](https://www.php.net/releases/8_6_0.php)). Section 4 (deprecations) of `UPGRADING`
at tag `php-8.6.0` is the same as at tag `php-8.6.0RC4`, line for line.

The static part of the test was run again that day on the final build (official PHP 8.6.0 for Windows, checksum checked)
and the current release of the same 100 plugins (55,989 PHP files):

- Token scan of every file, same rules as before: **39 of 100 plugins, 178 findings**, the same as on 17 November.
- `php -l` with the final build on 54,068 files: PHP's own compile-time messages name exactly the places the
  token scan found (54 constructor returns, 2 destructor returns, 11 `namespace` class constants,
  10 classes named `Is`). The other 1,921 files have paths too long to pass to php.exe on Windows; the token
  scan covers them.
- 20 of the 100 plugins shipped a new version between 17 and 19 November, 8 of the 39 listed:
  `coming-soon` (6.20.12 to 6.20.13), `elementskit-lite` (4.1.0 to 4.2.0), `forminator` (1.58.4 to 1.58.6), `limit-login-attempts-reloaded` (3.4.3 to 3.4.5), `mainwp-child` (6.4.2 to 6.5), `the-events-calendar` (6.18.4 to 6.18.4.1), `updraftplus` (1.26.14 to 1.26.16), `wordpress-seo` (28.8 to 28.9). None of them removed or added a finding.
- WordPress was not run on the final build, so the run-time results (which notices show on a normal page load) are still from RC4.

`recheck-2026-11-19.csv` has one row per finding; `recheck-2026-11-19.json` also lists the clean plugins with both versions.

## Re-check, 17 November 2026

The same token rules were run again on the current release of the same 100 plugins (55,885 PHP files).
`php -l` and the WordPress run were not repeated, so this re-check is static only. On the listed plugins whose version did
not change it gave the same files and lines as the October test.

- 65 of the 100 plugins shipped a new version since 28 October.
- 30 of the 39 plugins listed above shipped a new version. Deprecations removed: `wordfence` (9.0.2 to 9.1.1).
- Joined the list: `svg-support` 2.6.4.
- Still 39 of 100, with 178 findings. 98 of them are inside bundled libraries (Guzzle, Monolog, mPDF,
  svg-sanitize and others); for 10 plugins every finding is in a bundled library, so the fix is a newer library version
  and a rebuilt vendor folder, not a change in the plugin's own code.

| Plugin | Installs | Version 28 Oct | Version 17 Nov | Findings | In bundled libraries |
|---|---|---|---|---|---|
| [elementor](https://wordpress.org/plugins/elementor/) | 10,000,000+ | 4.3.5 | 4.4.1 | 4 | 2 |
| [wordpress-seo](https://wordpress.org/plugins/wordpress-seo/) | 10,000,000+ | 28.8 | 28.8 | 2 | 2 |
| [litespeed-cache](https://wordpress.org/plugins/litespeed-cache/) | 7,000,000+ | 7.9.2 | 7.9.3 | 1 | 0 |
| [woocommerce](https://wordpress.org/plugins/woocommerce/) | 7,000,000+ | 11.2.1 | 11.3.0 | 4 | 1 |
| [google-site-kit](https://wordpress.org/plugins/google-site-kit/) | 5,000,000+ | 1.190.0 | 1.192.0 | 4 | 3 |
| [seo-by-rank-math](https://wordpress.org/plugins/seo-by-rank-math/) | 4,000,000+ | 1.0.280 | 1.0.282 | 3 | 2 |
| [updraftplus](https://wordpress.org/plugins/updraftplus/) | 4,000,000+ | 1.26.14 | 1.26.14 | 17 | 10 |
| [wp-mail-smtp](https://wordpress.org/plugins/wp-mail-smtp/) | 4,000,000+ | 4.10.3 | 4.10.4 | 2 | 2 |
| [really-simple-ssl](https://wordpress.org/plugins/really-simple-ssl/) | 3,000,000+ | 9.8.4 | 9.8.4 | 1 | 0 |
| [all-in-one-seo-pack](https://wordpress.org/plugins/all-in-one-seo-pack/) | 2,000,000+ | 5.0.4 | 5.0.5.1 | 3 | 0 |
| [google-analytics-for-wordpress](https://wordpress.org/plugins/google-analytics-for-wordpress/) | 2,000,000+ | 11.3.0 | 11.3.0 | 5 | 0 |
| [complianz-gdpr](https://wordpress.org/plugins/complianz-gdpr/) | 1,000,000+ | 7.5.6 | 7.5.7 | 6 | 6 |
| [duplicator](https://wordpress.org/plugins/duplicator/) | 1,000,000+ | 5.1.0 | 5.2.0 | 4 | 3 |
| [elementskit-lite](https://wordpress.org/plugins/elementskit-lite/) | 1,000,000+ | 4.0.9 | 4.1.0 | 1 | 0 |
| [ewww-image-optimizer](https://wordpress.org/plugins/ewww-image-optimizer/) | 1,000,000+ | 8.9.0 | 8.9.2 | 5 | 0 |
| [instagram-feed](https://wordpress.org/plugins/instagram-feed/) | 1,000,000+ | 6.14.0 | 6.16.0 | 2 | 1 |
| [limit-login-attempts-reloaded](https://wordpress.org/plugins/limit-login-attempts-reloaded/) | 1,000,000+ | 3.3.10 | 3.4.3 | 3 | 0 |
| [safe-svg](https://wordpress.org/plugins/safe-svg/) | 1,000,000+ | 2.5.2 | 2.5.2 | 2 | 2 |
| [sg-cachepress](https://wordpress.org/plugins/sg-cachepress/) | 1,000,000+ | 7.8.5 | 7.8.6 | 1 | 0 |
| [svg-support](https://wordpress.org/plugins/svg-support/) | 1,000,000+ | 2.6.1 | 2.6.4 | 2 | 2 |
| [worker](https://wordpress.org/plugins/worker/) | 1,000,000+ | 4.9.38 | 4.9.39 | 4 | 0 |
| [wp-smushit](https://wordpress.org/plugins/wp-smushit/) | 1,000,000+ | 4.3.5 | 4.3.7 | 3 | 3 |
| [redux-framework](https://wordpress.org/plugins/redux-framework/) | 900,000+ | 4.5.16 | 4.5.18 | 2 | 0 |
| [w3-total-cache](https://wordpress.org/plugins/w3-total-cache/) | 900,000+ | 2.11.0 | 2.11.0 | 31 | 22 |
| [wpvivid-backuprestore](https://wordpress.org/plugins/wpvivid-backuprestore/) | 900,000+ | 0.9.136 | 0.9.140 | 17 | 10 |
| [fluentform](https://wordpress.org/plugins/fluentform/) | 800,000+ | 6.2.16 | 6.2.17 | 3 | 3 |
| [google-listings-and-ads](https://wordpress.org/plugins/google-listings-and-ads/) | 800,000+ | 3.10.0 | 3.10.1 | 9 | 9 |
| [better-wp-security](https://wordpress.org/plugins/better-wp-security/) | 700,000+ | 10.0.6 | 10.0.6.1 | 2 | 0 |
| [creame-whatsapp-me](https://wordpress.org/plugins/creame-whatsapp-me/) | 700,000+ | 6.4.2 | 6.4.4 | 1 | 0 |
| [duracelltomi-google-tag-manager](https://wordpress.org/plugins/duracelltomi-google-tag-manager/) | 700,000+ | 2.0.6 | 2.1.1 | 1 | 0 |
| [fluent-smtp](https://wordpress.org/plugins/fluent-smtp/) | 700,000+ | 2.4.1 | 2.4.5 | 4 | 3 |
| [mainwp-child](https://wordpress.org/plugins/mainwp-child/) | 700,000+ | 6.3 | 6.4.2 | 3 | 1 |
| [woocommerce-paypal-payments](https://wordpress.org/plugins/woocommerce-paypal-payments/) | 700,000+ | 4.2.0 | 4.2.2 | 4 | 0 |
| [backuply](https://wordpress.org/plugins/backuply/) | 600,000+ | 1.6.0 | 1.6.0 | 5 | 1 |
| [coming-soon](https://wordpress.org/plugins/coming-soon/) | 600,000+ | 6.20.10 | 6.20.12 | 2 | 0 |
| [enable-media-replace](https://wordpress.org/plugins/enable-media-replace/) | 600,000+ | 4.2.3 | 4.2.3 | 2 | 2 |
| [forminator](https://wordpress.org/plugins/forminator/) | 600,000+ | 1.58.3 | 1.58.4 | 4 | 4 |
| [post-types-order](https://wordpress.org/plugins/post-types-order/) | 600,000+ | 2.5.9 | 2.5.9 | 2 | 0 |
| [the-events-calendar](https://wordpress.org/plugins/the-events-calendar/) | 600,000+ | 6.18.2 | 6.18.4 | 7 | 4 |

`recheck-2026-11-17.csv` has one row per finding; `recheck-2026-11-17.json` also lists the plugins that came out clean, with
both versions. The tables above this section stay as tested on 28 October.

### Bundled guzzlehttp/promises: own copy or shared (17 November 2026)

Each plugin was tested alone, so the test cannot show which copy wins when several plugins on one site bundle the same
library (thanks to the reader who pointed this out). A plugin that prefixes its vendor folder (Strauss, PHP-Scoper) always
loads its own copy. A plugin that keeps the original `GuzzleHttp\Promise` namespace shares it: the first copy autoloaded
serves every plugin that uses that namespace.

- 11 of the 100 plugins bundle guzzlehttp/promises; 10 of those copies contain the `Is` class.
- 8 of the 10 prefix their copy. 2 keep the shared namespace: `updraftplus` and `w3-total-cache`.
- 0 of the 11 bundled copies have the `State` class that guzzlehttp/promises 2.6.0 and 3.1.0 added.

| Plugin | Version | Namespace of the bundled copy | Own or shared | Has `Is` class |
|---|---|---|---|---|
| [wordpress-seo](https://wordpress.org/plugins/wordpress-seo/) | 28.8 | `YoastSEO_Vendor\GuzzleHttp\Promise` | own (prefixed) | yes |
| [google-site-kit](https://wordpress.org/plugins/google-site-kit/) | 1.192.0 | `Google\Site_Kit_Dependencies\GuzzleHttp\Promise` | own (prefixed) | yes |
| [updraftplus](https://wordpress.org/plugins/updraftplus/) | 1.26.14 | `GuzzleHttp\Promise` | **shared** | yes |
| [wp-mail-smtp](https://wordpress.org/plugins/wp-mail-smtp/) | 4.10.4 | `WPMailSMTP\Vendor\GuzzleHttp\Promise` | own (prefixed) | yes |
| [duplicator](https://wordpress.org/plugins/duplicator/) | 5.2.0 | `VendorDuplicator\GuzzleHttp\Promise` | own (prefixed) | yes |
| [wp-smushit](https://wordpress.org/plugins/wp-smushit/) | 4.3.7 | `Smush_Vendor\GuzzleHttp\Promise` | own (prefixed) | yes |
| [w3-total-cache](https://wordpress.org/plugins/w3-total-cache/) | 2.11.0 | `GuzzleHttp\Promise` | **shared** | yes |
| [wpvivid-backuprestore](https://wordpress.org/plugins/wpvivid-backuprestore/) | 0.9.140 | `WPvividGuzzleHttp\Promise` | own (prefixed) | no |
| [google-listings-and-ads](https://wordpress.org/plugins/google-listings-and-ads/) | 3.10.1 | `Automattic\WooCommerce\GoogleListingsAndAds\Vendor\GuzzleHttp\Promise` | own (prefixed) | yes |
| [fluent-smtp](https://wordpress.org/plugins/fluent-smtp/) | 2.4.5 | `FluentSmtpLib\GuzzleHttp\Promise` | own (prefixed) | yes |
| [forminator](https://wordpress.org/plugins/forminator/) | 1.58.4 | `ForminatorGoogleAddon\GuzzleHttp\Promise` | own (prefixed) | yes |

`guzzle-promises-copies-2026-11-17.csv` has the folder of each copy. Read from the files of the 17 November releases;
plugins outside the top 100 on the same site can add more shared copies.

Each plugin's findings with the fix are at [deadlinefix.com/php-8-6-wordpress-plugins](https://deadlinefix.com/php-8-6-wordpress-plugins).
A free plugin, PHP Upgrade Readiness, runs the same checks on your own site's plugins and theme.

Site already broken after a PHP or plugin update? [Fixed for you, $49](https://deadlinefix.com/go/buy-wp-fix): I work from
a backup of your site (no logins needed), find the plugin or theme line that breaks, test the fix on a private copy and
send you the fixed files with the steps within 48 hours.

Data: CC BY 4.0. Plugin names belong to their authors; this is an independent test, not affiliated with WordPress.org or
the PHP project. Spotted a false positive or a fix that shipped? Open an issue with the plugin version.
