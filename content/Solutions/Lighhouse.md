## What
[Lighthouse](https://github.com/GoogleChrome/lighthouse) is an [[Open Source]], automated tool for improving the quality of web pages. You can run it against any web page, public or requiring authentication. It has audits for performance, accessibility, progressive web apps, [[SEO]], and more.

## How
#### 4 Ways running
1.  Since it is included in Google Chrome, you can run it directly from the browser. Click on **More tools** > **Developer Tools** and open the Lighthouse tab.
2.  If you have Node installed, you can run npm install -g lighthouse and run the tool in the command line like this: lighthouse {{Website URL}}
3.  You can include it in your code as a Node package.
4.  And finally, Lighthouse has a [CI version](https://github.com/GoogleChrome/lighthouse-ci) you can run in your [continuous integration](https://semaphoreci.com/continuous-integration). We’ll use this method to schedule periodical benchmarks.

#### Measuring Page Speed with Lighthouse and [[CICD]]
[Tutorial](https://semaphoreci.com/blog/lighthouse-page-speed)


