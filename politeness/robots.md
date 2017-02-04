# robots.txt

> robots.txt（統一小寫）是一種存放於網站根目錄下的 ASCII 編碼的文字檔案，它通常告訴網路搜尋引擎的漫遊器（又稱網路蜘蛛），此網站中的哪些內容是不應被搜尋引擎的漫遊器取得的，哪些是可以被漫遊器取得的。 >>> [Wiki - Robots.txt](https://zh.wikipedia.org/wiki/Robots.txt)

### 常見屬性

**User-agent**

定義誰需遵守遊戲規則

* 所有機器人 `User-agent: *`
* Google 機器人 `User-agent: Googlebot`

**Disallow**

不允許抓取得規則

**Allow**

允許抓取的規則

**Crawl-delay**

* 每次抓取需間隔10秒 `Crawl-delay: 10`

### 實際範例

以 Yahoo 的 robots.txt 為範例，我們可以得知 Yahoo 不允許我們使用機器人訪問以下的目錄及檔案。

https://tw.yahoo.com/robots.txt

```
User-agent: *
Disallow: /p/
Disallow: /r/
Disallow: /bin/
Disallow: /includes/
Disallow: /blank.html
Disallow: /_td_api
Disallow: /_tdpp_api
Disallow: /_remote
Disallow: /_multiremote
Disallow: /_tdhl_api
Disallow: /_td_remote
Disallow: /_tdpp_remote
```

針對一個網頁寫一個爬蟲很簡單，但針對一個網站或一群網站寫爬蟲，就是一門學問了。從上一篇 robots.txt 的探討，不知道你有沒有注意到 `crawl-delay:20` 設個值，它告訴我們的是我們允許你**合理**的來我家抓東西，但每次頻率要間隔 20 秒，否則就...

通常人家這麼好心地告訴你，也代表著它勢必有針對過度的撈取有一些防護措施，如果你不照著規則走，下一步就是把你的 IP 列入黑名單，成為列入拒絕往來戶。

所以在學會寫爬蟲之前，必須怎麼不照成對方是伺服器太大的負擔，基本上針對兩項原則做控管。

**延伸閱讀**

* [瞭解robots.txt 檔案- Search Console說明](https://support.google.com/webmasters/answer/6062608?hl=zh-Hant)
