# bookmarklets-for-testers
This repository documents browser bookmarklets I created using Javascript that I use daily to instantly navigate to frequently used URLs that contain variable parameters. No rocket science. Just some simple productivity hacks that help me being a quick tester.

## Ok, what are browser bookmarklets in the first place?
A bookmarklet is a bookmark stored in a web browser that contains JavaScript commands that add new features to the browser. Bookmarklets are unobtrusive JavaScripts stored as the URL of a bookmark in a web browser or as a hyperlink on a web page. Bookmarklets are usually JavaScript programs. Source: [Wikipedia.](https://en.wikipedia.org/wiki/Bookmarklet)

## How are browser bookmarklets useful for testers?
### Use 1 - Navigating to different websites where URLs are keyword driven

Testers use lot of tools on the web in their daily work routine (For example: Google, Stackoverflow, JIRA, GitHub many other project specific internal tools). **Context switching** leads us to frequently moving from one website/web tool to the other. Quite often the pages (URLs) that we navigate to change, based on certain parameters for example we google with a different query everytime. What about the usual browser bookmarks? Well, we cannot keep bookmarking URLs of apps/websites with variable parameters. That will be a mess.

With browser bookmarklets we can speed up our work as we eliminate unnecessary steps in opening these pages while we are working on something else!

Here are some Javascript bookmarklets that I use:
#### 1. Bookmarklet to quickly open a JIRA issue/ticket given the issue number
```javascript

javascript:(function() {  var jiraBaseURL = "https://yourjiradomain.com/jira/browse/"; var issueId = prompt("Enter your JIRA issue ID"); if(issueId) {window.open(jiraBaseURL+issueId); } else return })();
```


#### 2. Quick Google
```javascript

javascript:(function() {  var googleBaseURL = "https://www.google.co.in/search?q="; var query = prompt("Google what?"); if(query) {window.open(googleBaseURL+query); } else return })();
```

#### 3. Questions on Stackoveflow based on tags
```javascript

javascript:(function() {  var soBaseURL = "https://stackoverflow.com/questions/tagged/"; var tag = prompt("Questions related to?"); if(query) {window.open(soBaseURL+tag); } else return })();
```

### Use 2 — Retrieving useful information of a website/webapp that you test
Let’s say that you want to retrieve performance metrics of a webpage that you are testing, specifically page load time and page render time. We can make use of browsers’ [performance](https://developer.mozilla.org/en-US/docs/Web/API/Navigation_timing_API) APIs to calculate page load time and page render time using Javascript.

```javascript
var perfData = window.performance.timing;
var pageLoadTime = perfData.loadEventEnd - perfData.navigationStart;
var pageRenderTime = perfData.domComplete - perfData.domLoading;
//Above code can be executed in the browser's console to retrieve results
```

Now what if we convert this code into a bookmarklet and display page load time and render time on a popup just with a click? Wouldn’t that be convenient?

```javascript
javascript:(function() {
var perfData = window.performance.timing; 
var pageLoadTime = perfData.loadEventEnd - perfData.navigationStart;
var pageRenderTime = perfData.domComplete - perfData.domLoading;
alert("Load time of this page is: " + pageLoadTime + " milliseconds\n" + "Render time of this page is: " + pageRenderTime + " milli-seconds")
})();
```
[![page-performance-bookmarklet.png](https://s26.postimg.org/m57rni1ah/page-performance-bookmarklet.png)](https://postimg.org/image/4f632gnph/)

Apart from displaying page performance data, testers can make use of browser’s JavaScript window and document objects to fetch any information that they want based on the context of their tests and convert them to bookmarklets to test quickly.
For example:
* Checking if there are any anchor elements with no href
* Checking cookies saved for the current page
* Checking local storage and session storage key values stored for the current page

Ofcourse above usecase requires some decent JavaScript coding skills but it should not be that difficult if you already know programming.

## How do I add these bookmarklets to my browser?

1. Enter the javascript code that you want to convert to a bookmarklet in any text editor
![bookmarklet in editor](https://s26.postimg.org/ez9zxnbih/bookmarklet-in-editor.png)

2. On your browser start with adding a new URL/page as a bookmark
[![adding-bookmarklet-chrome-browser-step1.png](https://s26.postimg.org/c6gsdmb61/adding-bookmarklet-chrome-browser-step1.png)](https://postimg.org/image/ol3kdy2o5/)

3. Enter name for the bookmarklet and in the URL paste the javascript code you wrote for the bookmarklet and save.
[![adding-bookmarklet-chrome-browser-step2.png](https://s26.postimg.org/3pha2p6h5/adding-bookmarklet-chrome-browser-step2.png)](https://postimg.org/image/l2rkhk1s5/)

4. Click on the bookmark and use it!
[![adding-bookmarklet-chrome-browser-step3.png](https://s26.postimg.org/w3mpmku15/adding-bookmarklet-chrome-browser-step3.png)](https://postimg.org/image/q2p0pi7et/)


### Javascript in the bookmarklet runs in the context of the current tab open on your browser. So I am sure there are many other ways we can exploit the power of this small nifty feature of browsers. Do you use bookmarklets to increase your work productivity or make testing easier? Feel free to contribute here!
