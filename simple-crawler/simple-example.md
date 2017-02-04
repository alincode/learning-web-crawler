# 最簡單的一個範例

```js
var Crawler = require("simplecrawler");
var crawler = new Crawler("http://127.0.0.1:1337/");

crawler.on("crawlstart", function() {
    console.log("Crawl starting");
});

crawler.on("fetchstart", function(queueItem, requestOptions) {
    console.log("fetchStart", queueItem);
});

crawler.on("fetchcomplete", function(queueItem, responseBody, responseObject) {
    console.log("fetchcomplete", queueItem);
});

crawler.on("complete", function() {
    console.log("Finished!");
});

crawler.start();
```

附上[原始碼](https://github.com/alincode/learning-web-crawler-30days/tree/master/ex05)