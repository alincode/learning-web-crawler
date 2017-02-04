# 爬蟲隱密技巧

### random user agent

* user_agent
* module
    * [random-ua](https://www.npmjs.com/package/random-ua): Randomly generates User-Agent strings based on actual usage statistics from Wikimedia.

### random cookie

偽裝成不同個人登入

### random IP

* IP proxy

### look like human

* 中間穿插，正常人會做的行為，偽裝成正常人。

**發送延遲 / 限制發送次數**

* 搜尋關鍵字 Throttle
* 處理並發議題，避免造成 server loading
* [throttled-request](https://www.npmjs.com/package/throttled-request)
* 例如：隨機 3 ~ 5 秒發送，而不是準確 3 秒發送。