# Browser and form factor support

## Introduction

This document outlines browser and form factor support for Sainsbury's Homemade.

All code produced for Sainsbury's Homemade MUST abide by the support charts
detailed below.

Browser support requirements are expected to be updated on a quarterly basis.
See the _Introduction_ for more detail on the update cycle.

You MUST confirm that you have the most recent version of this document before
proceeding with development or testing.

## Responsive design

The site will be built in a "mobile-first" manner - that is to say, it will
be a responsive site which will effectively render with differing layouts
(number of columns, font and image size, etc) at different resolutions on
different devices at different "breakpoints".

## Core grade

Core grade browsers are presumed to be identified, capable, modern and common.

All Core grade browsers MUST receive full testing; bugs raised against Core
grade browsers MUST be addressed with high priority.

## Secondary grade

Secondary grade browsers SHOULD be presumed to be unknown, fringe or rare.

They should be considered as capable due to low usage, even though in some cases
this is unlikely. No steps will be taken to explicitly prevent them from
accessing Sainsbury's Homemade. No testing should be performed on browsers in
this grade and no bugs should be logged.

The cut-off for Core grade support is 1% of total usage in any given quarter.
Any browser falling below this threshold should be considered Secondary grade.

## Graceful degradation and progressive enhancement

Core grade support MUST NOT be taken to mean that the user experience will be
exactly the same in all supported browsers.

This approach helps ensure that:

* Advanced features in modern browsers can be employed where available and
  appropriate. For example, HTML5 form input types such as `search`, `email` and
  `url` will enhance the user experience in modern, supported browsers (Chrome,
  Firefox, Safari, IE10+) but will not be supported in less capable supported
  browsers (IE8, IE9).

* Techniques employed to cater for non-critical visual-only effects in less
  capable Core grade browsers (eg. IE8) are not employed when they would
  adversely affect the performance of more capable, popular browsers. For
  example, using images to create rounded corners on containers involves
  additional HTTP overheads. Instead, rounded corners should be generated using
  the CSS3 `border-radius` property. In this example, users of modern browsers
  (Chrome, Firefox, Safari, IE9+) would see rounded corners as intended. Users
  of less capable browsers (IE8) would see the same element with square corners.

For more on graceful degradation and progressive enhancement, refer to
the _Development principles_ section of this document.

### Form factor support

Form factor and interaction requirements SHOULD be considered during development
and testing of Core grade browsers and SHOULD follow the principle of
progressive enhancement.

For example, if a Core grade browser and OS combination supports or requires
Touch events (notably iPad Safari 5.x+), these SHOULD work as expected on that
browser and OS combination.

## Desktop and tablet support

### Core grade

* Chrome latest (OS X, WinXP, Vista, Win7, Win8)
* Firefox latest (OS X, WinXP, Vista, Win7, Win8)
* Safari 7.0+ (OS X, iPad)
* Safari 6.0+ (OS X, iPad)
* Internet Explorer 10 (Win8)
* Internet Explorer 9 (Vista, Win7)

### Secondary grade

* Internet Explorer 8 (XP only)
* Firefox less than or equal to 4.x
* Safari less than or equal to 5.x
* Internet Explorer less than or equal to 7.0
* Opera (all versions)
* Any other desktop or tablet browser not explicitly listed in Core grade

*Notes*

* Due to the rapid release cycle and background update of Firefox and Chrome, we do not list earlier versions.  The latest build is always assumed.
* The OS is not listed for brevity; browsers listed under the Secondary grade
  should not be supported on any OS.

## Mobile support

### Core grade

Please refer to the definition of _Core grade_ support, above.

* Safari iOS 6.x, 7.x
* Android phone 3+
* Chrome for Mobile (Android, iOS)

*Notes*

* iPad is accounted for under the Desktop and tablet support.
* The Android market is [exceptionally fragmented][android-fragmentation].
  Testing across a wide range of devices, operating systems and browser versions
  is impractical and costly. As such, we recommend that testing be limited to
  the two most popular Android devices; the Samsung GT-I9100 Galaxy S2 and the
  original HTC Desire. This selection should be reviewed regularly as part of
  the quarterly update.

[android-fragmentation]:               http://opensignalmaps.com/reports/fragmentation.php

### Secondary grade

Please refer to the definition of _Secondary grade_ support, above.

* Windows Phone (all)
* Opera Mini (all)
* Mobile Firefox (all)
* Opera Mobile (all)
* Any other mobile browser not explicitly listed in Core grade
