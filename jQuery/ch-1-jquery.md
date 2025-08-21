# jQuery

jQuery is a JavaScript library created to make it easier and faster to work with JavaScript. It is a shorter, simpler, and cross-browser way to do the same things. 

- jQuery is less essential now because modern JavaScript, frameworks (React, Vue) and browser APIs are much more powerful and standardized. 

Things jQuery simplifies:
- Manipulating HTML elements / DOM
- Manipulating CSS styles
- Handling events (like clicks, mouseovers, keypresses)
- Creating animations and visual effects
- Making AJAX requests (async calls to servers without refreshing the page)
- Extra utilities

## Versions of jQuery

Historically, there were two main version families:
**1.x** → Compatible with older browsers (like Internet Explorer 8 and below).
**2.x** → Optimized for newer browsers (IE 9+).
Then in July 2015, jQuery 3.x was released:
**jQuery 3.0** → Modern version, works with IE 9+.
jQuery Compact 3.0 → Backwards-compatible, works with IE 8.

## Downloading jQuery
Official site: jquery.com/download

Two types of files are provided:
- Uncompressed (development version) → Larger, readable code, useful for debugging.
- Compressed (minified version) → Small, optimized for production websites.
You include it in your site using the `<script>` tag with the correct path:

        <!DOCTYPE html>
        <html>
        <head>
        <title>Example</title>
        <meta charset="UTF-8">
        <script src="/js/libs/jquery/jquery.js"></script>
        </head>
        <body>
        <div>Content here</div>
        </body>
        </html>

## Using a CDN (Content Delivery Network)

Instead of downloading the file yourself, you can reference a copy of jQuery hosted on a server (CDN). This makes your site load faster and ensures users always get a cached version.
Example (using jQuery 3.x development version):
    
    <script src="https://code.jquery.com/jquery-3.0.0.js"></script>



