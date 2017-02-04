# Queue

我們辛苦的工兵，在我們執行 crawler.start() 後，首先做的事就是探索初始 url 網址的 html，然後掃瞄 html 裡面的所有 link，如果符合 fetch 條件則丟入 queue 中。

```
var initUrl = 'https://www.msn.com/';
var Crawler = require('simplecrawler');
var crawler = new Crawler(initUrl);
crawler.start();
```

接著會從 queue 中依序抓取，當抓取完成後會觸發 fetchcomplete 事件，事件中可以接收到 queuItem 這個參數跟 response，這就是它爬回來的結果了，除此之外，爬蟲會從探索到的 url 中在找出更多的 url，這就是大致上整個爬蟲的流程。

```
crawler.on('fetchcomplete', function(queueItem, responseBuffer, response) {
    // 略...
});
```

所以 queue 在爬蟲的機制其實佔很重要的位置。

### queuItem 物件常用屬性

* id：queue item 的流水號
* path: url 路徑
* url
* depth: 被爬行到的深度

### 真實 queueItem 回傳結果

```
queueItem:
 { host: 'www.msn.com',
  path: '/en-us/music/news/%E2%80%98light-years-ahead%E2%80%99-when-george-michael-toured-china-with-wham/ar-BBxzcKR?li=BBnb7Kz',
  port: '',
  protocol: 'https',
  uriPath: '/en-us/music/news/%E2%80%98light-years-ahead%E2%80%99-when-george-michael-toured-china-with-wham/ar-BBxzcKR',
  url: 'https://www.msn.com/en-us/music/news/%E2%80%98light-years-ahead%E2%80%99-when-george-michael-toured-china-with-wham/ar-BBxzcKR?li=BBnb7Kz',
  depth: 2,
  referrer: 'https://www.msn.com/en-us/',
  fetched: true,
  status: 'downloaded',
  stateData:
   { requestLatency: 258,
     requestTime: 265,
     contentLength: 20222,
     contentType: 'text/html; charset=utf-8',
     code: 200,
     headers:
      { 'cache-control': 'no-cache, no-store, no-transform',
        pragma: 'no-cache',
        'content-length': '20222',
        'content-type': 'text/html; charset=utf-8',
        'content-encoding': 'gzip',
        expires: '-1',
        vary: 'User-Agent',
        server: 'Microsoft-IIS/8.5',
        'set-cookie': [Object],
        'access-control-allow-origin': '*',
        'x-aspnetmvc-version': '5.2',
        'x-appversion': '2.0.6190.2531',
        'x-activity-id': 'de57fd1e-c82e-4f1f-b492-e3f01be16ce3',
        'x-az': '{did:5f46f41407bf434ca0465c7153fafe3d, rid: 7, sn: easia-prod-entertainment, dt: 2016-12-20T00:23:06.9965152Z, bt: 2016-12-12T01:27:25.5334005Z}',
        'strict-transport-security': 'max-age=0',
        'x-ua-compatible': 'IE=Edge;chrome=1',
        'x-content-type-options': 'nosniff',
        'x-frame-options': 'SAMEORIGIN',
        'x-powered-by': 'ASP.NET',
        'access-control-allow-methods': 'HEAD,GET,OPTIONS',
        'x-xss-protection': '1',
        'x-msedge-ref': 'Ref A: DE57FD1EC82E4F1FB492E3F01BE16CE3 Ref B: A1BB33B4FAD1528BA09DDBF4EB954AFB Ref C: Mon Dec 26 07:08:12 2016 PST',
        date: 'Mon, 26 Dec 2016 15:08:12 GMT',
        connection: 'close' },
     downloadTime: 7,
     actualDataSize: 20222,
     sentIncorrectSize: false },
  id: 1 }
  ```
