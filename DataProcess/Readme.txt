**------------------DataProcessĿ¼�ṹ------------------**

collectWeiboDataByKeyword------------------>python΢�������ȡ��������
|   
+---collectWeiboDataByKeyword.py----------->���ݹؼ����ռ�΢���������ռ���
+---login.py----------->ģ���½����΢��
+---mymain.py----------->�������
|
NLPIR------------------->java����Ԥ����
|
.project
.classpath
+---bin
|   ...
|
+---Data-->NLPIRϵͳ���Ĵʿ�
|   |   BIG2GBK.map
|   |   BIG5.pdat
|   |   BIG5.wordlist
|   |   BiWord.big
|   |   charset.type
|   |   Configure.xml
|   |   CoreDict.pdat
|   |   CoreDict.pos
|   |   CoreDict.unig
|   |   DocExtractor.user
|   |   FieldDict.pdat
|   |   FieldDict.pos
|   |   GBK.pdat
|   |   GBK.wordlist
|   |   GBK2BIG.map
|   |   GBK2GBKC.map
|   |   GBK2UTF.map
|   |   GBKA.pdat
|   |   GBKA.wordlist
|   |   GBKA2UTF.map
|   |   GBKC.pdat
|   |   GBKC.wordlist
|   |   GBKC2GBK.map
|   |   GranDict.pdat
|   |   GranDict.pos
|   |   ICTPOS.map
|   |   location.map
|   |   location.pdat
|   |   location.wordlist
|   |   NewWord.lst
|   |   NLPIR.ctx
|   |   NLPIR.user
|   |   NLPIR_First.map
|   |   nr.ctx
|   |   nr.fsa
|   |   nr.role
|   |   PKU.map
|   |   PKU_First.map
|   |   sentiment.pdat
|   |   sentiment.ung
|   |   UserDict.pdat
|   |   UTF2GBK.map
|   |   UTF2GBKA.map
|   |   UTF8.pdat
|   |   UTF8.wordlist
|   |   
|   \---English-->Ӣ�Ĵ����֧��֪ʶ�⣬�������ҪӢ�Ĵ���Ĺ��ܣ����Բ����ر��⡣
|           English.pdat
|           English.pos
|           English.ung
|           English.wordlist
|           Irrel2regular.map
|           ne.pdat
|           ne.pos
|           ne.wordlist
|
+---dict-------->�û��ʵ�
|   |   emotion.txt ��дʵ�
|   |   expression.txt ������ż�����ʵ䣬�ѵ���
|   |   user_dict.txt ����ʹ���ֵ�
|   |   
|   \---table-->ͣ�ôʱ����дʱ�
|           StopWordTable.txt
|           EmotionWordTable.txt
|
+---dll-------->NLPIR ��ͬ�����µ�֧�ſ�
|   +---linux32-->Linux 32bit����ϵͳ�µ�֧�ֿ�
|   |       NLPIR.so
|   |       
|   +---linux64-->Linux 64bit����ϵͳ�µ�֧�ֿ�
|   |       NLPIR.so
|   |       
|   +---win32-->Win 32bit����ϵͳ�µ�֧�ֿ�
|   |       NLPIR.dll
|   |       
|   \---win64-->Win 64bit����ϵͳ�µ�֧�ֿ�
|           NLPIR.dll
|
+---lib-------->����jar��
|   ...
|
+---src-------->��Ҫ����
|   +---com.nlpir
|   |   +---demo
|   |   |       NlpirLib.java
|   |   |       NlpirMethod.java
|   |   +---test
|   |   |       NlpirTest.java
|   |   +---util
|   |   |       OSInfo.java
|   |   \---Impl
|   |           SegmentImpl.java------>����nlpir�ӿڽ��зִʴ���
|

**------------------------------------------------------**
