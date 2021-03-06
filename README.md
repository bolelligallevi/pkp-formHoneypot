# Form Honeypot anti-bot plugin for OJS

This plugin verifies new user registrations by creating a honeypot on the User Registration form.

## Requirements

* OJS 3.1.x
* PHP 5.3 or later

## Installation

Install this as a "generic" plugin in OJS. The preferred installation method is through the Plugin Gallery. To install manually via the filesystem, extract the contents of this archive to a "formHoneypot" directory under "plugins/generic" in your OJS root.  To install via Git submodule, target that same directory path: `git submodule add https://github.com/ulsdevteam/pkp-formHoneypot plugins/generic/formHoneypot` and `git submodule update --init --recursive plugins/generic/formHoneypot`.  Run the upgrade script to register this plugin, e.g.: `php tools/upgrade.php upgrade`

## Configuration

The plugin has two main features. First, it can be used to block registrations that take suspiciously little time, or that take a very long time. The settings form takes two settings: minimum and maximum times. Users visiting the registration page must complete the registration form between the minimum and maximum time or the form will be rejected. Setting both values to zero deactivates this feature. The second feature is that it adds and hides a field with a randomly-generated name on the registration page. Scripts and bots that fill this field and submit the form will have their registration attempts rejected.

## Usage

When a new user registers within a journal context, a new field will be added to the page and hidden by javascript.  A form submission which includes this field is assumed to be generated by a bot, and an error will be displayed.

## Author / License

Written by Clinton Graham and Alex Wreschnig for the [University of Pittsburgh](http://www.pitt.edu).  Copyright (c) University of Pittsburgh.

Released under a license of GPL v2 or later.
