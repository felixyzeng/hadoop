# hadoop
hadoop study
今天开始实际在阿里云的EMC上操作hadoop，下面在这个文件里面记录一下遇到的问题
1.关于hadoop里的操作如创建文件夹 很多网上教程和百度回答都是 hadoop fs -mkdir XXX，但是实际操作时可能由于hadoop版本原因一直没能成功
后来发现是因为少了一个/，需要hadoop fs -mkdir /XXX。
2.还有就是用阿里云的EMC时，包括hadoop命令在内的好些命令都会提示SLF4J: Class path contains multiple SLF4J bindings.
百度了后，大家都说是path变量多个导致，目前没有实质性的影响，暂时不管
3.直接复制windows电脑上的.py文件到linux电脑上，不能直接运行，以后要注意



下面是阿里云EMC上操作word count的步骤
1.找STEAMING文件  根目录下执行  find ./ -type f -name "*streaming*"   然后设置为一个变量
2.写mapper.py和reducer.py 并用chmod +x的方式给程序加可执行权限
3.下载几个文件放到hdfs中
4.执行hadoop jar $STREAM  \
-files ./mapper.py,./reducer.py \
-mapper ./mapper.py \
-reducer ./reducer.py \
-input /user/$(whoami)/input/pg5000.txt,/user/$(whoami)/input/pg4300.txt,/user/$(whoami)/input/pg20417.txt\
 -output /user/$(whoami)/output
5.查看结果


下次学习：
1.从Github中get源码
2.自己写mapper.py和reducer.py
3.找一个很大的文件来mapreduce，测一下速度到底有多快
