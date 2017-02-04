# 常用配置

### maxDepth

設定爬行的深度

> “六度空間”理論又稱作六度分隔（Six Degrees of Separation）理論。簡單地說：“你和任何一個陌生人之間所間隔的人不會超過五個，也就是說，最多通過五個中間人你就能夠認識任何一個陌生人。” >>>[MBA lib 六度空間](http://wiki.mbalib.com/zh-tw/%E5%85%AD%E5%BA%A6%E7%A9%BA%E9%97%B4%E7%90%86%E8%AE%BA)

```
crawler.maxDepth = 3;
```

### interval

設定每一次 request 需間隔的時間長度，單位是毫秒。

```
crawler.interval = 250;
```

### maxConcurrency

最大限制的 Concurrency，預設是 5

```
crawler.maxConcurrency = 5;
```

### userAgent

爬蟲會留下的足跡，如果沒特別設定的話，會帶下面那組 userAgent，但也可以更改它。

```
crawler.userAgent="Node/simplecrawler <version> (https://github.com/cgiffard/node-simplecrawler)"
```
