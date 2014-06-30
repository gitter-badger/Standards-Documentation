# Browser and form factor support


## Introduction

The modern browser landscape is quite complex and rapidly changing all the time.  In all our projects, FULLSIX try to strike the right balance between delivering features efficiently by using modern technologies, whilst trying to ensure the maximum reach for the site through compatibility with legacy browsers, minor and edge case browsers and deprecated platforms.

Website code is interpreted at runtime by browser clients, and the various implementations of rendering engines in different browser clients interpret code differently.  It is the aim of all projects to implement features in such a way to provide a consistent experience across all browsers, however there will always be variation in the way browsers interpret and render code and content, and in the level of support for features of the code.  There is more information on this in our coding standards documentation and we refer to [http://www.caniuse.com/](http://www.caniuse.com/) for a guide to compatibility of specific features within web technology.  

Since there is a limit to what we can naturally support completely without branching code for specific platforms (to be avoided wherever possible), we take a graded approach to browser support with the following levels:

+ Grade A - Fully supported, both functionally and visually.  These are normally the major or latest versions of a browser in common circulation.  This information is taken from global and local market statistics as well as previous traffic reporting for incumbent sites where relevant.  We would expect these browsers to appear both functionally and visually as per all proposed designs, wireframes expected functionality.  There may be certain variations in the way that even Grade A browsers render some elements, particularly in the way rich fonts appear.  The aim is for consistency and robustness.

+ Grade B - As much functional support as possible, with some degradation of visual elements and performance.  Grade B browsers are expected to make all functions of the site (i.e. navigation, links, scripts, forms, interactions) available – the user should not be constricted from interacting with the site.  Where a function set is not supported, it should be entirely removed from display in Grade B browsers.  Visually, the site should not appear ‘broken’ but some degradation in the visual fidelity is to be expected (e.g. rounded corners appearing square, minor layout or spacing issues etc.).    Any degradation in visual or functional fidelity should be handled gracefully without impairment to the end users enjoyment of the site.

+ Grade C - No direct support for site function provided. We do not QA on Grade C browsers.  Sites may well work to a significant level on these platforms but we do not test on them and we do not, except if explicitly required, guarantee functional or visual compatibility on them.  This normally includes deprecated browser versions, niche/edge cases (i.e. games console browsers) or instances of a web rendering engine in non-browser applications.
A matrix is given below on current browser grading. If any exceptions are required, please inform FullSIX. If internal IT policies cannot support a grade A browser, please also flag this so we can identify in detail elements of the site build that likely to be degraded.

### Desktop Browser Grade A

Platform  Name  Version
OS X, Vista, Win7, Win8 Chrome  Latest*
OS X, Vista, Win7, Win8 Firefox Latest*
OSX Safari  7+
Win7, Win8  IE  9+


*Both Firefox and Chrome implement a rapid release cycle with background updating.  We therefore work to the current stable build.


### Desktop Browser Grade B

Platform  Name  Version
WinXP IE  8


### Desktop Browser Grade C

Platform  Name  Version
WinXP IE  <8
OS X, WinXP, Vista, Win7, Win8  Opera All versions
Alternate platforms not covered above (e.g. games consoles, linux, non-browser based implementations of a web rendering engine) Various Various


### Mobile Browser Grading

FULLSIX only support grade A browsers on mobile. All others will not be included within test scope unless otherwise agreed. This also includes native application in-built webviews (i.e. Twitter clients).

Platform  Name  Version
iOS6+ Mobile Safari 6+
IOS6+ Chrome  Current vers only
Android 4.1 Chrome* Current vers only

*please note, as of Jellybean, Chrome is the default browser on Android devices and we will test this as our target Android platform.  Android browser is not supported directly as a result, however since all versions of the browser from 4.0 (Ice Cream Sandwich) onward are built on the same version of Webkit, we don’t anticipate there being much variance in the rendering of pages.  We don’t, however, test thoroughly on ICS since the platform is in steep decline.  



### Mobile test devices

FULLSIX test on the following devices:
• iOS6, iOS7 (iPad 3, iPad Mini, iPhone 5)
• Android 4.0.3, 4.2.1, 4.4.1 (Samsung Galaxy S4, Samsung Galaxy S2, Nexus 7)
Additional devices can be targeted on request. Devices outside this configuration may incur extra charges. 



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
