# 選擇框架

非常幸運的在 Google 的茫茫大海中找到了 [awesome crawler repo](https://github.com/BruceDone/awesome-crawler)，從列表就可以很清楚知道 Python 的爬蟲庫資源，遠遠甩開其他語言。

### [Scrapy](https://scrapy.org/)

![Scrapy](https://scrapy.org/img/scrapylogo.png)

* 建構在 Python 程式語言
* 誕生於 2008 / 06
* 在 Github 上有一萬多顆星星
* 文件及學習資源非常完整
* 架構完整，雖然寫一個簡單範例不難，但見樹不見林，之後的擴充學習門檻高。

### [Simple Crawler](https://github.com/cgiffard/node-simplecrawler)

* 建構在 Node.JS 程式語言
* 特色是提供非常彈性的事件導向 Crawler
* 誕生於 2011 / 12
* 在 Github 上有一千多顆星星
* 文件完整度僅次於 Scrapy 框架，但優於其他框架很多。
* 架構不大，雖然功能沒有包山包海，但該有的都有了，容易與其他 module 搭配做擴充，學習門檻低。

### 題外話

對岸某位開發者，自產了一個用 Go 語言寫的 Crawler 框架叫 [Pholcus](https://github.com/henrylee2cn/pholcus)，雖然不可能採用這個框架，但框架提供的功能跟[文件](https://pholcus.gitbooks.io/docs/content/)完整度，真的非常的驚人。

雖然看似 Scrapy 完勝，但是由於我完全不會 Python 語言，對我是一個兩難的決定，或許現在採用 Scrapy 依附在它生態系之下把資料爬回來會比較簡單，但是爬回來之後的處理及後續跟其他架構的銜接，還是得要一些對 Python 語言的熟悉度，如果我採用 Scrapy，勢必得花很多時間學 Python，若採用 Simple Crawler 是熟悉的程式語言，但可能會遇到 Crawler 架構不完整，需自行在擴充實作的部分。