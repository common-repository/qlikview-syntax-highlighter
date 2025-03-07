=== Qlik for WordPress ===
Contributors: mattfryer
Tags: highlight, syntax, qlik, qlikview, qlik sense, post, page, shortcode, plugin
Requires at least: 4.0
Tested up to: 4.9.4
Stable tag: 2.0
License: GPLv3 or later
License URI: https://www.gnu.org/licenses/gpl-3.0.en.html

Tools for Qlik bloggers including inserting Qlik UI icons and automatic syntax highlighting of QlikView and Qlik Sense script/expressions on any WordPress page or post.

== Description ==
This WordPress plugin provides automatic syntax highlighting of QlikView and Qlik Sense script on any WordPress page or post. Additionally, it allows for easy addition of QlikView and Qlik Sense user interface icons within pages and posts. It was developed by Matt Fryer, a highly experienced Qlik consultant and author of the popular blog [QlikViewAddict.com](http://www.qlikviewaddict.com).

== Features ==
It currently supports highlighting of the following Qlik script and expression elements:

* Line comments //
* Block comment /*..*/
* REM comment REM...;
* Most QlikView 11.20+ and Qlik Sense keywords, statements and functions (that are permitted within the script or expressions)
* Variable definitions (using SET and LET) and variable use (within $())
* Field names in most common situations

Currently, all Qlik Sense Hub and Management Console icons are supported as well as a small number of additional generic icons (eg. Qlik logo).

== How to use ==
The plugin utilises WordPress shortcodes to apply the highlighting and insert icons.

= Syntax highlighting =
Simply wrap any Qlik code blocks within the [qlik-code] ... [/qlik-code] shortcode tags. By default, the plugin will assume that the code contained in the tags is Qlik script and will highlight it accordingly. You can specify an alternative code type using the type parameter within the opening tag. For example [qlikview type="exp"]=num(MyField)[/qlikview]. Currently supported code types are "qvs", "exp" (or "qve"), "sql", "vbscript" and "javascript". If no code type is specified then "qvs" will be assumed. 

Alternatively, the shortcode can be entered using the buttons within the WordPress text and visual post/page editors. Select the block of code within the post or page, then click the Qlik Code button on the editor menu. You will be prompted for what code type the block should be highlighted as. Once complete, click OK and the shortcode will be added around the code block for you.

= Icons =
Simply place the shortcode tag [qlik-icon icon=""] in your post or page where you wish the icon to appear. You can specify the icon you wish to use within the icon parameter of the tag. For example [qlik-icon icon="qicon-qlik"] will insert the Qlik logo. Possible icons and their related codes can be found within the Qlik for WordPress settings page in the WordPress Admin Portal.

Alternatively, the shortcode can be entered using the buttons within the WordPress text and visual post/page editors. Place the cursor within the post or page where you wish the icon to be placed, then click the Qlik Icon button on the editor menu. You will be prompted for the icon code for the icon you wish to insert. Once complete, click OK and the shortcode will be added for you.

== Feedback ==
If you spot any issues or have any suggestions to improve the plugin, please let me know either via the support tab here, or via a comment on [QlikViewAddict.com](http://www.qlikviewaddict.com/p/qlikview-wordpress-plugin.html).

== Credits ==
I'd like to thank Ivan Sagalaev and all the other contributors of Highlight.js which this plugin is based upon.

== Installation ==
There are 3 possible methods to install this plugin. We would highly recommend using method 1 as this is the easiest and will give notification of future updates.
= Method 1 =
1. Login to your WordPress Admin Portal.
1. On the left hand navigation panel, select "Plugins". 
1. Towards the top of the plugins list, click the "Add New" button. 
1. In the search box towards the right hand side, type "Qlik" and hit enter to search.
1. The Qlik for WordPress plugin is currently one of only two results returned. Click the "Install Now" button next to it.
1. WordPress will then download and install the plugin for you. Once complete, click the "Activate" button to complete the installation.
1. The plugin is now installed and the shortcode is ready to use.

= Method 2 =
1. Download the plugin zip file by clicking the link above.
1. Login to your WordPress Admin Portal.
1. On the left hand navigation panel, select "Plugins". 
1. Towards the top of the plugins list, click the "Add New" button. Note, if you have a previous version of this plugin installed it must be removed before proceeding.
1. Again, towards the top, click the "Upload Plugin" button.
1. Click the "Browse" button and navigate to the location where you saved the plugin zip file and select it.
1. Click the "Install Now" button
1. Once back on the plugins page, activate the "Qlik for Wordpress" plugin.

= Method 3 =
1. Download the plugin zip file by clicking the link above.
1. Extract the contents of the zip file to a folder on your computer.
1. Upload the entire directory "/qlik-highlight/" and its contents from the .zip file to the "/wp-content/plugins/" directory of your Wordpess site. If a previous version of this plugin has been installed, overwrite the entire folder.
1. Login to your WordPress Admin Portal.
1. On the left hand navigation panel, select "Plugins".
1. Activate the "Qlik for WordPress" plugin.

== Frequently Asked Questions ==
= Is the syntax highlighting perfect? =
The syntax highlighting is an approximation of the default highlighting within the Qlik Edit Script dialogs. It is not a perfect replication.

= Does it check if my code is valid? = 
This plugin is not designed to validate your Qlik code. Just because it is highlighted it doesn't mean your code is valid. For example, the highlighting engine has no way of knowing if field names within an expression/measure are actually contained within a QlikView or Qlik Sense data model. 

= Can it highlight other languages? =
As well as Qlik script and expressions/measures, it can currently highlight a handful of other languages that are associated with Qlik products. These currently include SQL, VBScript and JavaScript. If you think there is a need for it to support another language, please let me know.

= Can I use it with another highlighting plugin? =
The plugin has not been tested with any other highlighting plugins (syntax or otherwise) and so it cannot be guaranteed to work alongside them, especially those also based on highlight.js.

= How does it work? =
It uses a custom build of highlight.js to provide the highlighting. The highlighting is applied client-side using javascript when the page is loaded in the browser.

= Are the icons identical to Qlik? =
All Qlik Sense icons are generated using the LeonardoUI vector based font that Qlik Sense uses and so are identical to those seen in the Qlik Sense Hub and Management Console. QlikView icons are approximate representations of the icons found in QlikView desktop and web UI.

== Screenshots ==

1. An example section of QlikView script showing the syntax highlighting provided by this plugin. 
2. Includes a support for adding shortcode via the WordPress visual post/page editor.

== Changelog ==
= 2.0 =
* Added Qlik Sense connection string support
* Added the missing keywords DERIVE and FLUSHLOG
* Added support for DIRECT QUERY statements
* Fixed issue with REM comments not supporting whitespace before them
* Fixed issue with clicking cancel on shortcode prompts results in shortcode still being entered
* Fixed issue with variable declarations containing a full stop (AKA period) not highlighting correctly
* Fixed issue with backslash incorrectly operating as an escape character in strings
* Other minor highlighting improvements
* Significant speed improvements
* Added custom vector font to allow insertion of some Qlik icons
* Added the LUIicons vector font from LeonardoUI to allow insertion of all Qlik Sense UI icons
* Added optional extra line numbers to code block (should be used with caution as can prevent correct highlighting of code than spans multiple lines eg. /* */ block comments)
* Changes specific to Qlik for Wordpress Plugin:
* Changed [qlikview] shortcode to [qlik-code] to better represent Qlik Sense support. The old shortcode is still supported for backwards compatibility
* Button "Qlik Code" added to text editor to insert shortcode
* Visual editor button updated
* Corrected issue with plugin clashing with some other shortcodes resulting in incorrect display. Some Google Maps plugins were amongst those affected.
* Rewritten core code to prevent code being loaded on all pages of a site irrespective of whether or not the shortcode is present
* Added admin settings page allowing turning on/off features and detailing icon codes
* Ability to load CSS and JS files from the a CDN instead of the local webserver
* Added new shortcode [qlik-icon] to allow insertion of new vector font icons.

= 1.2 =
* Updated the highlight.js core to resolve a known bug.

= 1.1 =
* Added correct identification of set analysis and its composite parts within expressions allowing highlighting of items within it.
* Corrected list of functions within expressions as not all functions are possible in both script and expressions.
* Corrected an issue with the incorrect shortcode being added by the TinyMCE button.
* Added highlighting of format specification within a "LOAD...FROM..." statement in QlikView script.
* Updated the Highlight.js core.

= 1.0 =
* General code improvements.
* Corrected issue with $() variable use within a load statement not being highlighted correctly.
* Corrected issue with nesting of interpretation functions (those ending with a #) and those functions for which a keyword exists with the same name.
* Added highlighting of field names in most common situations.

= 0.2 =
* Added support for highlighting QlikView expressions
* Added the ability to hightlight a handful of other languages that are related to QlikView.
* Added variable definition and use support (SET, LET and $()).
* Fixed issue with interpretation functions (those ending with a #) not being highlighted correctly.
* Corrected an issue where the if function is confused with the IF statements causing incorrect highlighting.
* Fixed issue where keywords were highlighted within SQL statements.
* Added button to TinyMCE to insert the shortcode within the visual editor

= 0.1 =
* Initial pre-release.

== Upgrade Notice ==
= 2.0 =
Version 2.0 is the most significant release yet, providing major highlighting improvements, the ability to insert Qlik icons, a WordPress Admin settings page and much more. 

= 1.2 =
This release provides a fix for a known bug in th highlight.js core.

= 1.1 =
This release includes some significant improvements and bug fixes especially for highlighting of QlikView expressions. 

= 1.0 =
Version 1.0 represents the first official full release of QlikView for WordPress. It includes some minor bug fixes and improvements to the highlighting.

= 0.2 =
This version provides significant improvements and bug fixes over the previous release and marks it's migration to WordPress.org. All previous versions of this plugin should be uninstalled from WordPress before this version is installed.

= 0.1 =
This version provides the initial pre-release.