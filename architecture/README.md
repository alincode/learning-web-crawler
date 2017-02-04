# 架構面

### 爬蟲框架

* Simple Crawler 或 Scrapy

### 資料庫

* MongoDB
    * Document store Database model

### 快取

* Redis
* 放置拋棄式資料，減少對 IO 的存取

### Search engine

* 全文檢索框架
* 反正規化，並不是所有塞到資料庫的資料，都需要檢索。
* Elasticsearch
    * Search engine Database model
    * A modern search and analytics engine based on Apache Lucene

**Scrapy 架構圖**

![](https://doc.scrapy.org/en/1.3/_images/scrapy_architecture_02.png)


**延伸閱讀**

* [MongoDB vs. Elasticsearch: The Quest of the Holy Performances](http://blog.quarkslab.com/mongodb-vs-elasticsearch-the-quest-of-the-holy-performances.html)
* [Elasticsearch vs. MongoDB Comparison](http://db-engines.com/en/system/Elasticsearch%3BMongoDB)
* [Architecture overview — Scrapy 1.3.0 documentation](https://doc.scrapy.org/en/1.3/topics/architecture.html)
* [原分享一下我和MongoDB与Redis那些事 - _Boz - 博客园](http://www.cnblogs.com/Bozh/p/3408765.html)
* [Memcached, Redis, MongoDB三者比較 - 壹讀](https://read01.com/GPx0GM.html)