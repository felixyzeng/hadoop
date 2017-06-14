# hadoop
hadoop study
今天开始实际在阿里云的EMC上操作hadoop，下面在这个文件里面记录一下遇到的问题
1.关于hadoop里的操作如创建文件夹 很多网上教程和百度回答都是 hadoop fs -mkdir XXX，但是实际操作时可能由于hadoop版本原因一直没能成功
后来发现是因为少了一个/，需要hadoop fs -mkdir /XXX。
2.还有就是用阿里云的EMC时，包括hadoop命令在内的好些命令都会提示SLF4J: Class path contains multiple SLF4J bindings.
百度了后，大家都是是path变量多个导致，目前没有实质性的影响，暂时不管
