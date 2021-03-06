# Changelog

This document details changes to the WP REST API since its public release in version 4.7.0.

## Version 4.9.8

- Add an `object_subtype` argument to the `$args` parameter for `register_meta()`: this parameter allows developers to specify the object subtypes (_i.e._ specific post types or taxonomies) for which the registered meta will appear when `show_in_rest` is true. Introduce new wrapper methods `register_post_meta()` and `register_term_meta()` which are recommended instead of `register_meta` when working with post or term meta. [r43378](https://core.trac.wordpress.org/changeset/43378)


## Version 4.8.1

- Add a filter to allow modifying the response after embedded data is added. [r41093](https://core.trac.wordpress.org/changeset/41093)
- `wp-api.js` client: Correctly interpret `settings` resource as a model rather than a collection. [r41126](https://core.trac.wordpress.org/changeset/41126)
- Fix `PUT` (and other) requests for nginx servers by tweaking REST API URLs. [r41140](https://core.trac.wordpress.org/changeset/41140)

## Version 4.8.0

- Improve strings added after 4.7.0 string freeze. [r40571](https://core.trac.wordpress.org/changeset/40571), [r40606](https://core.trac.wordpress.org/changeset/40606)
- Canonicalize header names in `WP_REST_Request::remove_header()`. [r40577](https://core.trac.wordpress.org/changeset/40577)
- Allow `Origin: null` from `file:` URLs. [r40600](https://core.trac.wordpress.org/changeset/40600)
- Set global `$post` variable when preparing revisions. [r40601](https://core.trac.wordpress.org/changeset/40601)
- Include `featured_media` in embed responses. [r40602](https://core.trac.wordpress.org/changeset/40602)
- Add `author`, `modified`, and `parent` sort order options for posts. [r40605](https://core.trac.wordpress.org/changeset/40605)
- Add endpoint for proxying requests to external oEmbed providers, and use it in the media modal instead of the `parse-embed` AJAX action.  **This is the first usage of the WP REST API in `wp-admin`.** [r40628](http://core.trac.wordpress.org/changeset/40628)
- Do not set `X-WP-Deprecated*` headers as often. [r40782](https://core.trac.wordpress.org/changeset/40782)
- Avoid sending blank `Last-Modified` headers with authenticated requests. [r40805](https://core.trac.wordpress.org/changeset/40805)
- Fix changing parameters with `$request->set_param()` for some requests. [r40815](https://core.trac.wordpress.org/changeset/40815)
- In the admin area, ensure the REST API endpoint URL is forced to `https` when necessary. [r40843](https://core.trac.wordpress.org/changeset/40843)

## Version 4.7.4

- Fix another (DST-related) issue with dates of posts. [r40325](https://core.trac.wordpress.org/changeset/40325)
- Add `gmt_offset` and `timezone_string` to the base `/wp-json` response. [r40336](https://core.trac.wordpress.org/changeset/40336)
- Confirm that the parent post object of an attachment exists in `WP_REST_Posts_Controller::check_read_permission()`. [r40337](https://core.trac.wordpress.org/changeset/40337)
- Allow fetching multiple users and terms at once via the `slug` parameters of the respective endpoints. [r40426](https://core.trac.wordpress.org/changeset/40426), [r40427](https://core.trac.wordpress.org/changeset/40427)

## Version 4.7.3

- Cast revision author ID to int. [r40078](https://core.trac.wordpress.org/changeset/40078)
- Correctly serve the index with `PATH_INFO`. [r40079](https://core.trac.wordpress.org/changeset/40079)
- Include the `status` property in `view` context responses from the Posts endpoints. [r40081](https://core.trac.wordpress.org/changeset/40081)
- `wp-api.js` client: Use `_.extend` instead of `_.union` when merging objects. [r40084](https://core.trac.wordpress.org/changeset/40084)
- To prepare for a full multisite implementation [in 4.8](https://make.wordpress.org/core/2017/02/08/improving-the-rest-api-users-endpoint-for-multisite-in-4-7-3-and-4-8/), do not allow access to users from a different site. [r40111](https://core.trac.wordpress.org/changeset/40111)
- Correctly parse body parameters for `DELETE` requests. [r40113](https://core.trac.wordpress.org/changeset/40113)
- Fix multiple issues with dates of posts and comments. [r40114](https://core.trac.wordpress.org/changeset/40114), [r40115](https://core.trac.wordpress.org/changeset/40115)
- `wp-api.js` client: Fix route discovery for custom namespaces. [r40117](https://core.trac.wordpress.org/changeset/40117)
- Fix the behavior of the `sticky` posts filter when no posts are sticky. [r40136](https://core.trac.wordpress.org/changeset/40136)
- Allow setting all post formats even if they are not supported by the theme. [r40137](https://core.trac.wordpress.org/changeset/40137)

## Version 4.7.2

- Unify object access handling for simplicity. [r39957](https://core.trac.wordpress.org/changeset/39957)

## Version 4.7.1

- Treat any falsy value as `false` in `'rest_allow_anonymous_comments'`. [r39566](https://core.trac.wordpress.org/changeset/39566)
- `wp-api.js` client: Fix setup of models used by `wp.api.collections` objects. [r39604](https://core.trac.wordpress.org/changeset/39604)
- Do not error on empty JSON body. [r39609](https://core.trac.wordpress.org/changeset/39609)
- Do not include the `password` argument for the `GET /wp/v2/media` endpoint. [r39610](https://core.trac.wordpress.org/changeset/39610)
- Allow sending empty or no-op comment updates. [r39628](https://core.trac.wordpress.org/changeset/39628)
- Add support for filename search in the `GET /wp/v2/media` endpoint. [r39629](https://core.trac.wordpress.org/changeset/39629)
- Fix PHP warnings when `get_theme_support( 'post-formats' )` is not an array. [r39630](https://core.trac.wordpress.org/changeset/39630)
- Improve the `rest_*_collection_params` filter docs and fix the terms filter. [r39631](https://core.trac.wordpress.org/changeset/39631)
- Allow schema `sanitization_callback` to be set to `null` to bypass built-in sanitization. [r39642](https://core.trac.wordpress.org/changeset/39642)
- Change which users are shown in the users endpoint. [r39844](https://core.trac.wordpress.org/changeset/39844)

