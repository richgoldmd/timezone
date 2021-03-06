# TimeZoneSelect
Creating a time zone select in PHP can get unruly quickly, as DateTimeZone::listIdentifiers() returns over 415 Zones and Links. This is an attempt to take a page from Ruby on Rails' ActiveSupport::TimeZone time_zone_select(), largely by using their curated list of about 150 Zones, and also by allowing for 'priority_zones' to be at the top of the list.

![Screenshot of timezone select](timezone-select-screenshot.png?raw=true "Screenshot of timezone select")

Example:

`echo TimeZoneSelect::get_select(['country'=>'US']);`

Simple demo avaiable: http://scott.connerly.net/TimeZone/example.php

Available args w/ default values:
```
[
    'country'        => '',          //ISO-3116 2-letter country code
    'priority_zones' => [],          //If you want to specify a list of zones that aren't country-specific
    'priority_label' => 'Regional',  //The label of the optgroup for the priority zones

    'selected'       => '',          //which option is selected
    
    'name'           => 'time_zone', //name for the <select>
    'class'          => '',          //class for the <select>
    'id'             => '',          //id for the <select>
    'data'           => [],          //list of data attributes to add to the <select>
]
```


 * This repo involves occasionally scraping the rails repo. Here is the ticket asking Rails to make their data file more easily accessible: https://github.com/rails/rails/issues/22088
 * It would be much easier if there was a similarly curated list inside of PHP. Here's the request to them for that: https://bugs.php.net/bug.php?id=70801
