# 常用事件

### crawlstart

當爬蟲開始跟 restarted 的時候會觸發的事件

```
crawler.on("crawlstart", function() {
    console.log("Crawl starting");
});
```

### fetchstart

* 當從 queue 中取出一個 item 要開始抓取時會觸發的事件。當你使用同步化處理這個事件時，你可以修改 request options。
* request options 中有包含 headers 和 request method。

```
crawler.on("fetchstart", function(queueItem, requestOptions) {
    console.log("fetchStart", queueItem);
});
```

### fetchcomplete

抓取完成的時候會觸發的事件，responseBody 預設是 buffer，所以取值時要用 `responseBody.toString()`。

```
crawler.on("fetchcomplete", function(queueItem, responseBody, responseObject) {
    console.log("fetchcomplete", queueItem);
    console.log("body", responseBody.toString());
});
```

### fetcherror

當抓取時發生 HTTP error 的時候會觸發的事件

```
crawler.on("fetcherror", function(queueItem, responseObject) {
    console.log("fetch error!");
});
```

### complete

當爬蟲已經沒有東西可以爬，而且 queue 都做完的時候會觸發的事件。

```
crawler.on("complete", function() {
    console.log("Finished!");
});
```