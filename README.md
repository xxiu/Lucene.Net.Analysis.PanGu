Lucene.Net.Analysis.PanGu
=========================

盘古分词(http://pangusegment.codeplex.com/ )，由于老版本不支持最新Lucene.Net 3.0.3，对其进行了升级，可以支持最新的Lucene.Net 3.0.3。可以直接NuGet安装。另外把词库打包到dll文件里面了，无需拷贝词库。

使用说明
=========================

Lucene.Net：https://github.com/apache/lucene.net
盘古分词：http://pangusegment.codeplex.com/ 


修改平台(mono)兼容性问题
============================

+ StrConv这个函数没有检查通过，作者使用了 Microsoft.VisualBasic.Strings.StrConv 这个类库来处理简体和繁体转换的问题，这个类用到了windows平台的特性,用一个简单的简体繁体转换替换.

+ 是一个Marshal.GetHRForException 用来做io处理出错的时候判断的,代码如下大概是出现了ERR_PROCESS_CANNOT_ACCESS_FILE错误时让线程稍等,这个错误用到了COM.mono不能使用,注释掉这部分判断.


