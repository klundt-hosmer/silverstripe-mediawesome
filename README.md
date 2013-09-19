# Mediawesome (Dynamic Media Holders)

	A module for SilverStripe which allows creation of a flexible media holder for
	media pages with customisable type (blogs, events, news).

## Requirement

* SilverStripe 3.1.X

## Getting Started

* Place the module under your root project directory.
* Define any custom media types and associated attributes through project configuration.
* `/dev/build`
* Create a media holder.
* Configure media type.
* Create media pages.
* Select the media holder.
* Configure media type attributes.

## Overview

### Custom Media Types & Associated Attributes

There are a number of default media types included, each with their own attributes.

```php
private static $page_defaults = array(
	'Blog' => array(
		'Author'
	),
	'Event' => array(
		'Start Time',
		'End Time',
		'Location'
	),
	'Media Release' => array(
		'Contact Name',
		'Contact Number'
	),
	'News' => array(
		'Author'
	),
	'Publication' => array(
		'Author'
	),
	'Speech' => array(
		'Speaker',
		'Location'
	),
);
```

```php
MediaPage::customise_defaults(array(
	'MediaName' => array(
		'AttributeName'
	)
));
```

### Media Types

Minimises the number of manageable CMS items, where media holder children will inherit the current media type.

### Dynamic Attributes

The attributes for a specific media type may be customised through the CMS by users, including the addition of new attributes (which will automatically be attached to all existing media pages of that type).

### Smart Templating

Custom templates may be defined for your media type (`Blog.ss` for a type Blog). It is also possible to reference a custom attribute directly through a custom template:

```php
$getAttribute(Author)
```

## Maintainer Contact

	Nathan Glasl, nathan@silverstripe.com.au
