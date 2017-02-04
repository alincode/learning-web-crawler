# Cheer.io

從前面的範例中，我們已經知道怎麼將 html 原始碼爬出來，但是這麼繁雜的內容不容易使用，於是我們要將資料提煉出真正需要的東西，[Cheerio](https://github.com/cheeriojs/cheerio) 是一個 parser html 的模組，它是一個參照 JQuery Core 設計的模組，我們可以使用 JQuery 熟悉的語法 selector 跟 api，所以大大降低了學習門檻。

Items

```
crawler.on('fetchcomplete', function(queueItem, responseBuffer, response) {

  // parse html 轉成可以透過 cheerio 操作的格式
  var $ = cheerio.load(responseBuffer);

  // 取得值
  var title = $('h1').html();

});
```

至於更細節的部分使用說明，網路上已經有蠻豐富的文章了，在這就不重複說明，直接給傳送門吧。

**延伸閱讀**

* [cnode - 通读cheerio API](https://cnodejs.org/topic/5203a71844e76d216a727d2e)
