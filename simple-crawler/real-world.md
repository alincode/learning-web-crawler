# 真實範例

爬 MSN 新聞標題

現在讓我們牛刀小試一下，寫一個爬 MSN 新聞標題的範例，透過設定 interval 跟 maxConcurrency 即可達到前期所提的避免過度使用伺服器資源，至於 robots.txt 因為 Simple Crawler 預設就會遵守，所以就不需要再調整。

```js
var ROOT_URL = 'https://www.msn.com/';

var Crawler = require('simplecrawler');
var crawler = new Crawler(ROOT_URL);
var cheerio = require('cheerio');

// 設定每次 request 的區間
crawler.interval = 60 * 1000;

// 限制只有一個併發
crawler.maxConcurrency = 1;

crawler.on('crawlstart', function() {
  console.log('Crawl starting ', ROOT_URL);
});

// 設定抓取條件，只抓取 url 中，子路徑是 news 的網頁。
crawler.addFetchCondition(function(queueItem, referrerQueueItem) {
  return queueItem.path.indexOf('/news/') > -1
})

crawler.on('fetchcomplete', function(queueItem, responseBuffer, response) {
  if (ROOT_URL == queueItem.url) return;
  var $ = cheerio.load(responseBuffer);
  var title = $('h1').html();
  console.log('news title：', title);
});

crawler.on('complete', function() {
  console.log('Finished!', ROOT_URL);
});

crawler.start();

```

附上[原始碼](https://github.com/alincode/learning-web-crawler-30days/tree/master/ex06)