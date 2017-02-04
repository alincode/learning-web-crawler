# 抓取條件

當你只需要抓特定規則的頁面並非全部時，可以設定要抓取的條件，且條件可以有多個。

### 新增抓取條件

Spider

```
var conditionID = crawler.addFetchCondition(function(queueItem, referrerQueueItem) {
  return queueItem.path.indexOf('/news/') > -1
});
```

或

```
function condition(queueItem, referrerQueueItem) {
  return queueItem.path.indexOf('/news/') > -1
}

var conditionID = crawler.addFetchCondition(condition);
```

### 移除抓取條件

```
crawler.removeFetchCondition(conditionID);
```

或

```
crawler.removeFetchCondition(condition);
```
