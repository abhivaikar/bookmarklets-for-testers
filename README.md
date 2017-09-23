# bookmarklets-for-testers
This repository documents browser bookmarklets I created using Javascript that I use daily to instantly navigate to frequently used URLs that contain variable parameters. No rocket science. Just some simple productivity hacks that help me being a quick tester.

## Ok, what are browser bookmarklets in the first place?
A bookmarklet is a bookmark stored in a web browser that contains JavaScript commands that add new features to the browser. Bookmarklets are unobtrusive JavaScripts stored as the URL of a bookmark in a web browser or as a hyperlink on a web page. Bookmarklets are usually JavaScript programs. Source: [Wikipedia.](https://en.wikipedia.org/wiki/Bookmarklet)

## How are browser bookmarklets useful for testers?
Testers use lot of tools on the web in their daily work routine (For example: Google, Stackoverflow, JIRA, GitHub many other project specific internal tools). **Context switching** leads us to frequently moving from one website/web tool to the other. Quite often the pages (URLs) that we navigate to change, based on certain parameters for example we google with a different query everytime. What about the usual browser bookmarks? Well, we cannot keep bookmarking URLs of apps/websites with variable parameters. That will be a mess.

With browser bookmarklets we can speed up our work as we eliminate unnecessary steps in opening these pages while we are working on something else!

Here are some Javascript bookmarklets that I use:
### 1. Bookmarklet to quickly open a JIRA issue/ticket given the issue number
```javascript

javascript:(function() {  var jiraBaseURL = "https://yourjiradomain.com/jira/browse/"; var issueId = prompt("Enter your JIRA issue ID"); if(issueId) {window.open(jiraBaseURL+issueId); } else return })();
```


### 2. Quick Google
```javascript

javascript:(function() {  var googleBaseURL = "https://www.google.co.in/search?q="; var query = prompt("Google what?"); if(query) {window.open(googleBaseURL+query); } else return })();
```

### 3. Questions on Stackoveflow based on tags
```javascript

javascript:(function() {  var soBaseURL = "https://stackoverflow.com/questions/tagged/"; var tag = prompt("Questions related to?"); if(query) {window.open(soBaseURL+tag); } else return })();
```

## How do I add these bookmarklets to my browser?

1. Enter the javascript code that you want to convert to a bookmarklet in any text editor
![bookmarklet in editor](https://s26.postimg.org/ez9zxnbih/bookmarklet-in-editor.png)

2. On your browser start with adding a new URL/page as a bookmark
[![adding-bookmarklet-chrome-browser-step1.png](https://s26.postimg.org/c6gsdmb61/adding-bookmarklet-chrome-browser-step1.png)](https://postimg.org/image/ol3kdy2o5/)

3. Enter name for the bookmarklet and in the URL paste the javascript code you wrote for the bookmarklet and save.
[![adding-bookmarklet-chrome-browser-step2.png](https://s26.postimg.org/3pha2p6h5/adding-bookmarklet-chrome-browser-step2.png)](https://postimg.org/image/l2rkhk1s5/)

4. Click on the bookmark and use it!
[![adding-bookmarklet-chrome-browser-step3.png](https://s26.postimg.org/w3mpmku15/adding-bookmarklet-chrome-browser-step3.png)](https://postimg.org/image/q2p0pi7et/)


## Do you use any bookmarklets to increase your work productivity? Feel free to contribute here!
