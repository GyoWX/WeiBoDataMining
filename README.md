## WeiBoDataMining
##### 1.DataProcess---------数据预处理
###### 功能介绍
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
 
　　　　　　　　crawlerData:<br>
　　　　　　　　{<br>
　　　　　　　　　　"_id" : ObjectId("59290b0bf67345bdd477402a"),<br>
　　　　　　　　　　"keyword" : "赵丽颖",<br>
　　　　　　　　　　"username" : "碧瑶丶",<br>
　　　　　　　　　　"date" : "2017-05-03",<br>
　　　　　　　　　　"content" : "晚安，赵丽颖晚安，虫子节日快乐@赵丽颖 #赵丽颖##赵丽颖楚乔传#"<br>
　　　　　　　　}<br>
 
　　　　　　　　savaData<br>
　　　　　　　　{<br>
　　　　　　　　　　"_id" : ObjectId("592f803678d12435402e442d"),<br>
　　　　　　　　　　"keyword" : "赵丽颖",<br>
　　　　　　　　　　"words" : "快乐 向往 可爱 迷人 精灵 动听 幕后 花絮 忽视 ..... ",<br>
　　　　　　　　　　"date" : ISODate("2017-06-01T02:47:18.257Z")<br>
　　　　　　　　}<br>
 
　　　　　　　　**注意**<br>
　　　　　　　　连接mongodb，python需导入pymongo库，java需要mongo-java-driver-3.4.2<br>
 
 
  
**------------------DataProcess目录结构------------------**<br>

collectWeiboDataByKeyword-------------------------->python微博爬虫获取网络数据<br>
|   <br>
+---collectWeiboDataByKeyword.py----------->根据关键词收集微博，数据收集类<br>
+---login.py----------->模拟登陆新浪微博<br>
+---mymain.py----------->程序入口<br>
|<br>
NLPIR------------------->java数据预处理<br>
|<br>
.project<br>
.classpath<br>
+---bin<br>
|   ...<br>
|<br>
+---Data-->NLPIR系统核心词库<br>
|   |   BIG2GBK.map<br>
|   |   BIG5.pdat<br>
|   |   BIG5.wordlist<br>
|   |   BiWord.big<br>
|   |   charset.type<br>
|   |   Configure.xml<br>
|   |   CoreDict.pdat<br>
|   |   CoreDict.pos<br>
|   |   CoreDict.unig<br>
|   |   DocExtractor.user<br>
|   |   FieldDict.pdat<br>
|   |   FieldDict.pos<br>
|   |   GBK.pdat<br>
|   |   GBK.wordlist<br>
|   |   GBK2BIG.map<br>
|   |   GBK2GBKC.map<br>
|   |   GBK2UTF.map<br>
|   |   GBKA.pdat<br>
|   |   GBKA.wordlist<br>
|   |   GBKA2UTF.map<br>
|   |   GBKC.pdat<br>
|   |   GBKC.wordlist<br>
|   |   GBKC2GBK.map<br>
|   |   GranDict.pdat<br>
|   |   GranDict.pos<br>
|   |   ICTPOS.map<br>
|   |   location.map<br>
|   |   location.pdat<br>
|   |   location.wordlist<br>
|   |   NewWord.lst<br>
|   |   NLPIR.ctx<br>
|   |   NLPIR.user<br>
|   |   NLPIR_First.map<br>
|   |   nr.ctx<br>
|   |   nr.fsa<br>
|   |   nr.role<br>
|   |   PKU.map<br>
|   |   PKU_First.map<br>
|   |   sentiment.pdat<br>
|   |   sentiment.ung<br>
|   |   UserDict.pdat<br>
|   |   UTF2GBK.map<br>
|   |   UTF2GBKA.map<br>
|   |   UTF8.pdat<br>
|   |   UTF8.wordlist<br>
|   |   <br>
|   \---English-->英文处理的支持知识库，如果不需要英文处理的功能，可以不加载本库。<br>
|           English.pdat<br>
|           English.pos<br>
|           English.ung<br>
|           English.wordlist<br>
|           Irrel2regular.map<br>
|           ne.pdat<br>
|           ne.pos<br>
|           ne.wordlist<br>
|<br>
+---dict-------->用户词典<br>
|   |   emotion.txt 情感词典<br>
|   |   expression.txt 表情符号及网络词典，已导入<br>
|   |   user_dict.txt 测试使用字典<br>
|   |   <br>
|   \---table-->停用词表和情感词表<br>
|           StopWordTable.txt<br>
|           EmotionWordTable.txt<br>
|<br>
+---dll-------->NLPIR 不同环境下的支撑库<br>
|   +---linux32-->Linux 32bit操作系统下的支持库<br>
|   |       NLPIR.so<br>
|   |       <br>
|   +---linux64-->Linux 64bit操作系统下的支持库<br>
|   |       NLPIR.so<br>
|   |       <br>
|   +---win32-->Win 32bit操作系统下的支持库<br>
|   |       NLPIR.dll<br>
|   |       <br>
|   \---win64-->Win 64bit操作系统下的支持库<br>
|           NLPIR.dll<br>
|<br>
+---lib-------->所需jar包<br>
|   ...<br>
|<br>
+---src-------->主要代码<br>
|   +---com.nlpir<br>
|   |   +---demo<br>
|   |   |       NlpirLib.java<br>
|   |   |       NlpirMethod.java<br>
|   |   +---test<br>
|   |   |       NlpirTest.java<br>
|   |   +---util<br>
|   |   |       OSInfo.java<br>
|   |   \---Impl<br>
|   |           SegmentImpl.java------>调用nlpir接口进行分词处理<br>
|<br>
<br>
**------------------------------------------------------**<br>
