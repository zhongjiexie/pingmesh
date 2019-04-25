Pingmesh：用于数据中心网络延迟测量和分析的大规模系统
====

遇到的问题？
-
1.并发和for循环消耗时间对比<br>
20条并发->630.916396ms<br>
20条for循环->12.428980563s

2.普通ping多线程也无法达到需求<br>
30 个ip 运行时间为21s （不达标）<br>
修改为fping作为底层收集器 <br>

3.客户端  golang cannot use xx (type []string) as type string in argument to exec.Command（错误）


进度
-
1.2019-4-1客户端 1.实现并行操作 2.自动上传ip<br>
2.2019-4-2服务端 1.客户端上传的ip写入数据库 2.返回数据库中的pinglist<br>
3.2019-4-15客户端 1.使用fping，传统ping并发效果不好舍弃<br>
4.2019-4-24客户端 1.Command不能使用[]string,解决<br>
