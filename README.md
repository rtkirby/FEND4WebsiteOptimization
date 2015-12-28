# Website Performance Optimization Project

### About
The objective of this project is to optimize [Cameron Pittman's portfolio](www.lin1kore.net) page for speed. The strategy was to optimize the critical rendering path, making the page render as quickly as possible, using techniques you've picked up in the [Website Performance Optimization](https://www.udacity.com/course/ud884).

### How to run
To get started, download the entire directory, `p4`, and open it in a browser locally.

### Page load speed optimization
- Image compression: images were rescaled and resized to the final layout dimensions.
- Inline critical CSS: critical above-the-fold content styles are inlined and applied to the document immediately vs. blocking loading. This was done using the methods prescribed by Google Developers (see references).
- Defer alternative media CSS: print stylesheets, although small, were deliberately chosen not to be served inline in HTML documents due to at least three different pages using it.  A media attribute was added to ensure that it would only be downloaded when printing.
- Minifying CSS/JS: all CSS and JS files were minified--but not obfuscated--to ensure faster downloading.  The formatted and indented files are still present in their respective directories, without the `.min` in their filenames.

### Frame rate optimization
- Loop optimization: unnecessary JS operations were pulled out of `for` loops where possible, in `views/js/main.js`.
- Debouncing: scroll events were 'debounced' to decouple the animations and only reflow/repaint when needed.

**Framerate timelines**: saved JSON timelines and screenshots for `pizza.html` are located in the Issue's tab, and shown below:

*Original*
![Original](https://cloud.githubusercontent.com/assets/12014930/11966687/807bf654-a8ba-11e5-86a6-a1f3303cf1ba.PNG)

*After loop optimization*
![After loop optimization](https://cloud.githubusercontent.com/assets/12014930/11966693/86767bc4-a8ba-11e5-8053-0bf713d280b5.PNG)

*After debouncing*
![After debouncing](https://cloud.githubusercontent.com/assets/12014930/11966696/8a135d10-a8ba-11e5-80e2-4e376daeb409.PNG)

*After minify*
![After minify]()

*Install Node.js and load GULP*
![After running GULP, based on nodejs, built by Fractal](https://github.com/wearefractal)

### Further improvement
- Browser caching, configured server-side, could have reduced page loading time.
- Using a CDN for Bootstrap files could have reduced page loading time as well, but was minified for the purposes of this exercise. Reduce image size
- Google Page Speed Insights from gulp

### Resources
- [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/)
- [Optimize CSS Delivery](https://developers.google.com/speed/docs/insights/OptimizeCSSDelivery)
- [Avoiding Rendering Blocking CSS](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/render-blocking-css.html "render blocking css")
- [Optimizing the Critical Rendering Path](https://developers.google.com/web/fundamentals/performance/critical-rendering-path/optimizing-critical-rendering-path.html "optimize the crp!")
- [Leaner, Animations with requestAnimationFrame](http://www.html5rocks.com/en/tutorials/speed/animations/)
- [Udacity Office Hours](https://plus.google.com/u/0/events/cqecguv492nm1uhmnqo3khr2bv4?authkey=CNG7rsiHksvtQg)
- [Youtube tutitorial by Maximilian Schmitt on GULP](https://www.youtube.com/watch?v=DkRoa2LooNM&list=PLRk95HPmOM6PN-G1xyKj9q6ap_dc9Yckm&index=1)
- [Demo of critical path plugin](https://github.com/addyosmani/critical-path-css-demo)
- [Javascript Bottleneck analyzing tool](https://developers.google.com/web/tools/chrome-devtools/profile/rendering-tools/analyze-runtime)
