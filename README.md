# sentimood: AFINN sentiment analyzer for the browser
A more-or-less CoffeeScript browser-compatible port of @thinkroth's [Sentimental](https://github.com/thinkroth/Sentimental), which was originally written in Node.

# usage
After you install the package via Bower (with the command `bower install sentimood`) or just add it to your HTML document's `<head>`, you can initialize Sentimood like so:
```javascript
sentiment = new Sentimood();
```
Then you can do cool things like this:
```javascript
var analyze = sentiment.analyze(),
    positivity = sentiment.positivity(),
    negativity = sentiment.negativity();

analyze("Hey you worthless scumbag"); //Score: -6, Comparative:-1.5
positivity("This is so cool"); //Score: 1, Comparative:.25
negativity("Hey you worthless scumbag"); //Score: 6, Comparative:1.5
analyze("I am happy"); //Score: 3, Comparative: 1
analyze("I am so happy"); //Score: 6, Comparative: 1.5
analyze("I am extremely happy"); //Score: 12, Comparative: 3
analyze("I am really sad"); //Score: -4, Comparative: -1
```

The difference between this project and [Sentimental](https://github.com/thinkroth/Sentimental) is the browser compatibility: Sentimental is node.js specific, which means it can only be run on the server-side. I made some minimal changes, (e.g. changed `array.forEach()` to a `for` loop) which increased performance and allowed the file to run on the client-side.
