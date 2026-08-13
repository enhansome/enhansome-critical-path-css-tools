# Awesome Critical-path (Above-the-fold) CSS Tools with stars

> Tools to help prioritize above-the-fold CSS

### Prioritize above-the-fold content first.

For best performance, PageSpeed Insights [recommends](https://developers.google.com/speed/docs/insights/PrioritizeVisibleContent) inlining the critical (above-the-fold) CSS of your page directly into your HTML. This eliminates additional roundtrips and allows the browser to paint the above-fold experience to your user's screen sooner. The main idea is:

* Determine the above-the-fold styles for a page and write them between `<style>` tags in the head.
* Load all other stylesheets in the footer, ideally asynchronously.

The following is a list of tools to help generate, inline and report on critical-path CSS.

## Node modules

* [Critical](https://github.com/addyosmani/critical) ⭐ 10,253 | 🐛 37 | 🌐 JavaScript | 📅 2026-08-03 - by Addy Osmani generates & inlines critical-path CSS (uses Penthouse, [Oust](https://github.com/addyosmani/oust) ⭐ 193 | 🐛 7 | 🌐 JavaScript | 📅 2026-04-02 and inline-styles)
* [Penthouse](https://github.com/pocketjoso/penthouse) ⭐ 2,681 | 🐛 26 | 🌐 HTML | 📅 2023-12-03 - by Jonas Ohlsson generates critical-path CSS
* [CriticalCSS](https://github.com/filamentgroup/criticalcss) ⚠️ Archived - by FilamentGroup finds & outputs critical CSS

## Server-side modules

* [ngx\_pagespeed](https://github.com/pagespeed/ngx_pagespeed) ⚠️ Archived - Nginx module for automatic PageSpeed optimization
* [mod\_pagespeed](https://github.com/pagespeed/mod_pagespeed) ⚠️ Archived - Apache module for automatic PageSpeed optimization

## Grunt tasks

* [grunt-critical-css](https://github.com/filamentgroup/grunt-criticalcss) ⚠️ Archived
* [grunt-critical](https://github.com/bezoerb/grunt-critical) ⭐ 156 | 🐛 20 | 🌐 HTML | 📅 2025-12-30
* [grunt-penthouse](https://github.com/fatso83/grunt-penthouse) ⭐ 68 | 🐛 0 | 🌐 JavaScript | 📅 2018-03-21

## CasperJS

* [critical-css-casperjs](https://github.com/ibrennan/critical-css-casperjs) ⭐ 67 | 🐛 0 | 🌐 JavaScript | 📅 2014-04-01 - CasperJS script to pull critical CSS information from pages

## PhantomJS

* [dr-css-inliner](https://github.com/drdk/dr-css-inliner) ⚠️ Archived - PhantomJS script to inline above-the-fold CSS on a page.

## Inline sources (styles, scripts)

* [isomorphic-style-loader](https://github.com/kriasoft/isomorphic-style-loader/) ⭐ 1,272 | 🐛 81 | 🌐 JavaScript | 📅 2026-08-11 for Webpack - allows to extract critical CSS for any given page/screen in React apps and inline it into HTML during server-side rendering (SSR). See [React Starter Kit](https://github.com/kriasoft/react-starter-kit) ⭐ 23,666 | 🐛 9 | 🌐 TypeScript | 📅 2026-08-11 as an example.
* [gulp-inline-source](https://github.com/fmal/gulp-inline-source) ⭐ 208 | 🐛 19 | 🌐 JavaScript | 📅 2019-06-11 - by Filip Malinowski, replaces `<link>` tags with inline `<style>` tags, and replaces `<script src="">` tags with their inline content
* [inline-critical](https://github.com/bezoerb/inline-critical) ⭐ 116 | 🐛 10 | 🌐 HTML | 📅 2024-12-14 - by Ben Zörb, inline critical path CSS and load existing stylesheets with `loadCSS`
* [inline-styles](https://github.com/maxogden/inline-styles) ⭐ 23 | 🐛 2 | 🌐 JavaScript | 📅 2014-07-21 - by Max Ogden, replaces `<link>` tags with inline `<style>` tags + inlines CSS url() calls with data URIs

## Async load CSS

Async loading should be used to fetch the rest of your site-wide styles after you've inlined your critical-path CSS.

* [loadCSS](https://github.com/filamentgroup/loadCSS) ⚠️ Archived - loads CSS asynchronously using JS. [Research](https://gist.github.com/scottjehl/87176715419617ae6994) that led to this is also available.
* [basket.js](http://addyosmani.github.io/basket.js/) - async script/resource loader with support for localStorage caching. Can be [extended](https://github.com/andrewwakeling/basket-css-example) ⭐ 19 | 🐛 1 | 🌐 JavaScript | 📅 2013-12-26 to load stylesheets.
* [asyncLoader](https://github.com/n0mad01/asyncLoader) ⭐ 0 | 🐛 0 | 📅 2014-12-25 - async script/stylesheet loader
* [async & conditional loading](https://gist.github.com/matt-bailey/602b40c77a5d3381ff26) - POC script for loading CSS files asynchronously and conditionally based on body tag classes

Note: The Guardian currently also cache their global styles into localStorage for subsequent page loads. More info in this [comment](https://gist.github.com/scottjehl/87176715419617ae6994).

## Online tools

* [Penthouse online](https://jonassebastianohlsson.com/criticalpathcssgenerator/)

## Bookmarklets/Extensions

* [Snippet](https://gist.github.com/PaulKinlan/6284142) by Paul Kinlan. Patrick Hamann has an [exercise](http://patrickhamann.com/workshops/performance/tasks/2_Critical_Path/2_2.html) using the snippet you can try out.
* [Snippet](https://gist.github.com/scottjehl/b6129da04733e4e0f9a4) by Scott Jehl
* [CSSVacuum](https://github.com/ndreckshage/CSSVacuum) ⭐ 45 | 🐛 2 | 📅 2013-09-11 by ndreckshage

## Render-blocking issues detection

* [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) - Online tool that measures the performance of a page for mobile devices and desktop devices. It fetches the url twice, once with a mobile user-agent, and once with a desktop-user agent.
* [PSI](https://github.com/addyosmani/psi) ⚠️ Archived - Node module for PageSpeed Insights reporting as part of your build process. Use directly with Gulp or use [grunt-pagespeed](https://github.com/jrcryer/grunt-pagespeed) ⭐ 457 | 🐛 12 | 🌐 CoffeeScript | 📅 2022-12-07 if a Grunt user. For local testing, a write-up using this task and [ngrok](http://www.jamescryer.com/2014/06/12/grunt-pagespeed-and-ngrok-locally-testing/) is available.
* [PageSpeed Insights DevTools extension](https://chrome.google.com/webstore/detail/pagespeed-insights-by-goo/gplegfbjlmmehdoakndmohflojccocli?hl=en) - Chrome extension for running PageSpeed tests from inside the browser.
* [PageSpeed Insights Checker for mobile extension](https://chrome.google.com/webstore/detail/pagespeed-insights-checke/mkjmodmicmpjedhoekkmafdgpocdkbna?hl=en) - checks Mobile PageSpeed score for every page and gives you a handy preview.

## Supplementary tools

* [UnCSS](https://github.com/giakki/uncss) ⭐ 9,403 | 🐛 58 | 🌐 JavaScript | 📅 2024-06-18 removes unused CSS from pages, allowing you to reduce the global CSS you may need to load in for your site. Tasks are available for [Grunt](https://github.com/addyosmani/grunt-uncss) ⭐ 3,794 | 🐛 9 | 🌐 HTML | 📅 2023-07-18, [Gulp](https://github.com/ben-eb/gulp-uncss) ⚠️ Archived and [other](https://addyosmani.com/blog/removing-unused-css/) build tools.

***

> _Enhansomed by [enhansome](https://github.com/enhansome) on 2026-08-13._
