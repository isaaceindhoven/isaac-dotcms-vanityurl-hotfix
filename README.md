# dotCMS Vanity URL hotfix

This plugin is a workaround for (clustered) dotCMS issue where sometimes the Vanity urls stop working untill the cache is cleared manually.

This hotfix is based on the dotCMS reported issues:
- https://github.com/dotCMS/core/issues/17278
- https://github.com/dotCMS/core/issues/18364

In this hotfix the merge request of https://github.com/dotCMS/core/pull/18378/ has been implemented. Please note that this is a workaround as it will put the vanity URLs in a timed cache. In other words, in the configured time the issue could still appear. This plugin is meant for dotCMS version 5.2.x, in dotCMS 5.3 this hotfix is already implemented.

In the meantime dotCMS is workig on a clean room re-implementation, which should be implemented in the 5.3.X series. See https://github.com/dotCMS/core/pull/18377 for more information.

## Installation

To use it, you obviously first need to install the static plugin. 
to install the static plugin (isaac-dotcms-vanityurl-hotfix). Here's how you do that:

* Clone this repository.
* Copy the folder "isaac-dotcms-vanityurl-hotfix" to the dotcms-plugins folder
* Stop dotCMS
* Run bin/deploy-plugins.bat or bin/deploy-plugins.sh
* Start dotCMS

That's it, you've installed the plugin.

## Usage

This plugin automatically updates the handling of Vanity URL Cache, it updates it to a "Timed cache" with a timeout of 15 seconds.
When the issue starts with the non working vanity urls dotCMS then after 120 seconds evicts the wrong vanityurls and repopulates the cache and these will then work again.
