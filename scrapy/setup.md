# 安裝

今天換來看看 Python 界的 [Scrapy](https://scrapy.org/) 爬蟲框架，[文件](https://doc.scrapy.org/en/latest/index.html)非常的豐富。

似乎只要 `pip install scrapy` 就可以安裝完，莫非定律 Error 出現了，最後就裝了鄉民推薦的[Anaconda](https://www.continuum.io/downloads)，終於成功了。

![Imgur](http://i.imgur.com/S27lpID.png)

接著透過 conda 來裝 scrapy

```
conda install -c conda-forge scrapy=1.3.0
```

![Imgur](http://i.imgur.com/ZfNU6zF.png)

最後使用 cli 指令，建立第一個爬蟲專案。

```
scrapy startproject scrapysandbox
```