=== WP Max Submit Protect ===
Contributors: judgej
Donate link: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=B4STZL8F5WHK6
Tags: woocommerce, forms, data-integrity
Requires at least: 3.6
Tested up to: 3.8.0
Stable tag: 1.0.3
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Prevent large forms being submitted that may blow the server's field count limit and lose data.

== Description ==

Some appications, such as ecommerce sites, can have administration forms that submit well over a thousand
parameters. PHP, by default, is set to accept only one thousand parameters and so some of the submitted data can get lost.

Most applications don't check whether they received everything, and so data can get broken easily and silently.
A WooCommerce product with 40 variations can have over 1300 submitted form items, and when saving the product you have no idea that much of that data is being discarded.

Luckily [the maximum number of accepted parameters can be changed in php.ini](http://docs.woothemes.com/document/problems-with-large-amounts-of-data-not-saving-variations-rates-etc/)
The problem is, many site owners have no idea this needs to be done until it is too late and their WooCommerce
store has lost half its product variations.

To protect yourself and make sure the server limit does not catch
you unawares, install this plugin and let it run in the background. Each time you try to submit a form in the
admin pages (e.g. updating a WooCommerce product with lots of variatrions) this plugin will check that the
number of form parameters you are about to submit does not exceed the server limit. If it does, then it
will inform you and give you the opportunity to postpone the submit while you increase the server settings.
The link above describes how to set the limits on the server. The PHP ini settings that could affect the
data in large forms are:

* max_input_vars
* suhosin.get.max_vars
* suhosin.post.max_vars
* suhosin.request.max_vars

This plugin has been tested against PHP5.4 but is written to be compatible with PHP5.3. The project repository is here:

[https://github.com/academe/wp-max-submit-protect](https://github.com/academe/wp-max-submit-protect)

Changes have been made so that it works with PHP5.2 and has been reported as working.
However, I work under at least 5.3 so some incompatibilities may creep in by accident from time-to-time - just report them and I will do my best to fix as quickly as possible.

Please let me know how this plugin works for you, whether you like it, and how it can be improved.

== Installation ==

1. Upload wp-max-submit-protect/ to the `/wp-content/plugins/` directory or wp-max-submit-protect-x.y.z.zip through the "Add Plugins" administration page, or install from wordpress.org

== Frequently asked questions ==

= Are there any configuration options? =

Through the plugin no; you just install and go. There may be some server settings to update, and the purpose of this plugin is to warn you about those.

== Screenshots ==

1. 
2. 

== Changelog ==

= Version 1.0.3 =
* Issue #1 (this readme.txt)

= Version 1.0.2 =
* Bugfix to 1.0.1

= Version 1.0.1 =
* Issue #2 and make all text translatable.

= Version 1.0.0 =
* Initial release.

== Upgrade notice ==