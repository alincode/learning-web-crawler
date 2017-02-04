# 更好的寫法

* 為什麼我們要使用爬蟲框架？
* 分工更清晰，結構更清楚。
  * Spider
  * Queue
    * history
    * 暫時凍結 queue
  * error handle
    * reqeust 失敗重發
    * 控制重發次數
  * Item parse
  
```
// scrapper-config.json
{
  "article" : {
    "base": ".archive",
    "title": ".col .span_8",
    "date": ".post-date time"
  }
}
```

```
var config = JSON.parse(fs.readFileSync('scrapper-config.json', 'utf8'));
```

```
var $ = cheerio.load(html);

  $(config.article.base).each(function() {
    $(config.article.title, this).each(function(index, element) {
      console.log("Post title: %s", element.attribs.title);
    });

    $(config.article.date, this).each(function(index, element) {
      console.log("Post date: %s", element.attribs.datetime);
    });

  });
```