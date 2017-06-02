## WeiBoDataMining
##### DataProcess---------数据预处理
　　　1.collectWeiboDataByKeyword---------根据微博爬虫获取原始数据集<br>
　　　　　模拟登陆----->构造URL----->爬取网页----->解析网页<br>
　　　　　解析得到的数据：用户名，发布时间，微博内容<br>
　　　　　解析的数据存储至数据库中<br>
　　　　　需注意爬取微博的速度较慢，数据需提前爬取，速度过于频繁容易造成账号被封<br>
　　　2.NLPIR----------提取爬取的微博内容进行文本预处理<br>
　　　　　提取数据----->分词----->去除停用词------>匹配情感词典<br>
　　　3.数据库<br>
　　　　　微博文本通过MongoDB进行存储<br>
　　　　　1.MongoDB配置：<br>
　　　　　　　WeiBoDB-------------->新建数据库<br>
　　　　　　　+---Collections<br>
　　　　　　　|　　　crawlerData------>用于保存原始数据<br>
　　　　　　　|　　　savaData--------->用于存储分词后的结果<br>
　　　　　2.文档示例<br>
　　　　　　　**括号内为集合中一条记录示例**<br>
 ```
　　　　　　　crawlerData:<br>
　　　　　　　{<br>
　　　　　　　　　"_id" : ObjectId("59290b0bf67345bdd477402a"),<br>
　　　　　　　　　"keyword" : "赵丽颖",<br>
　　　　　　　　　"username" : "碧瑶丶",<br>
　　　　　　　　　"date" : "2017-05-03",<br>
　　　　　　　　　"content" : "晚安，赵丽颖晚安，虫子节日快乐@赵丽颖 #赵丽颖##赵丽颖楚乔传#"<br>
　　　　　　　}<br>
```

```
　　　　　　　savaData<br>
　　　　　　　{<br>
　　　　　　　　　"_id" : ObjectId("592f803678d12435402e442d"),<br>
　　　　　　　　　"keyword" : "赵丽颖",<br>
　　　　　　　　　"words" : "快乐 向往 可爱 迷人 精灵 动听 幕后 花絮 忽视 ..... ",<br>
　　　　　　　　　"date" : ISODate("2017-06-01T02:47:18.257Z")<br>
　　　　　　　}<br>
```
　　　　　　　**注意**<br>
　　　　　　　连接mongodb，python需导入`pymongo`库，java连接需要`mongo-java-driver-3.4.2.jar`<br>
 
