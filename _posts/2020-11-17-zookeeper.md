# zookeper

## zookeeper

参考：

https://blog.csdn.net/java_66666/article/details/81015302

https://www.cnblogs.com/sxblog/p/13564480.html

https://www.cnblogs.com/areyouready/p/10014947.html

https://developer.ibm.com/zh/tutorials/bd-zookeeper/

https://blog.csdn.net/a15835774652/article/details/80620038

下载地址（注意：3.5版本不稳定，起不来）：

http://mirror.bit.edu.cn/apache/zookeeper/zookeeper-3.4.14/

```powershell
[root@iz8vbbyuhcl6ozmfu17dziz local]# cd zookeeper-3.4.14
[root@iz8vbbyuhcl6ozmfu17dziz zookeeper-3.4.14]# ls
bin        conf        ivysettings.xml  lib          NOTICE.txt  README.md             src                   zookeeper-3.4.14.jar.asc  zookeeper-3.4.14.jar.sha1  zookeeper-contrib  zookeeper-it    zookeeper-recipes
build.xml  dist-maven  ivy.xml          LICENSE.txt  pom.xml     README_packaging.txt  zookeeper-3.4.14.jar  zookeeper-3.4.14.jar.md5  zookeeper-client           zookeeper-docs     zookeeper-jute  zookeeper-server
[root@iz8vbbyuhcl6ozmfu17dziz zookeeper-3.4.14]# cd conf/
[root@iz8vbbyuhcl6ozmfu17dziz conf]# ls
configuration.xsl  log4j.properties  zoo_sample.cfg
[root@iz8vbbyuhcl6ozmfu17dziz conf]# mv zoo_sample.cfg zoo.cfg
[root@iz8vbbyuhcl6ozmfu17dziz conf]# cd ..
[root@iz8vbbyuhcl6ozmfu17dziz zookeeper-3.4.14]# ls
bin        conf        ivysettings.xml  lib          NOTICE.txt  README.md             src                   zookeeper-3.4.14.jar.asc  zookeeper-3.4.14.jar.sha1  zookeeper-contrib  zookeeper-it    zookeeper-recipes
build.xml  dist-maven  ivy.xml          LICENSE.txt  pom.xml     README_packaging.txt  zookeeper-3.4.14.jar  zookeeper-3.4.14.jar.md5  zookeeper-client           zookeeper-docs     zookeeper-jute  zookeeper-server
[root@iz8vbbyuhcl6ozmfu17dziz zookeeper-3.4.14]# ./bin/zkServer.sh start
ZooKeeper JMX enabled by default
Using config: /usr/local/zookeeper-3.4.14/bin/../conf/zoo.cfg
Starting zookeeper ... STARTED


[root@iz8vbbyuhcl6ozmfu17dziz bin]# ./zkCli.sh 
Connecting to localhost:2181
2020-10-12 14:02:47,366 [myid:] - INFO  [main:Environment@100] - Client environment:zookeeper.version=3.4.14-4c25d480e66aadd371de8bd2fd8da255ac140bcf, built on 03/06/2019 16:18 GMT
2020-10-12 14:02:47,369 [myid:] - INFO  [main:Environment@100] - Client environment:host.name=iz8vbbyuhcl6ozmfu17dziz
2020-10-12 14:02:47,369 [myid:] - INFO  [main:Environment@100] - Client environment:java.version=1.8.0_261
2020-10-12 14:02:47,371 [myid:] - INFO  [main:Environment@100] - Client environment:java.vendor=Oracle Corporation
2020-10-12 14:02:47,371 [myid:] - INFO  [main:Environment@100] - Client environment:java.home=/usr/local/jdk1.8.0_261/jre
2020-10-12 14:02:47,371 [myid:] - INFO  [main:Environment@100] - Client environment:java.class.path=/usr/local/zookeeper-3.4.14/bin/../zookeeper-server/target/classes:/usr/local/zookeeper-3.4.14/bin/../build/classes:/usr/local/zookeeper-3.4.14/bin/../zookeeper-server/target/lib/*.jar:/usr/local/zookeeper-3.4.14/bin/../build/lib/*.jar:/usr/local/zookeeper-3.4.14/bin/../lib/slf4j-log4j12-1.7.25.jar:/usr/local/zookeeper-3.4.14/bin/../lib/slf4j-api-1.7.25.jar:/usr/local/zookeeper-3.4.14/bin/../lib/netty-3.10.6.Final.jar:/usr/local/zookeeper-3.4.14/bin/../lib/log4j-1.2.17.jar:/usr/local/zookeeper-3.4.14/bin/../lib/jline-0.9.94.jar:/usr/local/zookeeper-3.4.14/bin/../lib/audience-annotations-0.5.0.jar:/usr/local/zookeeper-3.4.14/bin/../zookeeper-3.4.14.jar:/usr/local/zookeeper-3.4.14/bin/../zookeeper-server/src/main/resources/lib/*.jar:/usr/local/zookeeper-3.4.14/bin/../conf:.:/usr/local/jdk1.8.0_261/lib:/usr/local/jdk1.8.0_261/jre/lib
2020-10-12 14:02:47,371 [myid:] - INFO  [main:Environment@100] - Client environment:java.library.path=/usr/java/packages/lib/amd64:/usr/lib64:/lib64:/lib:/usr/lib
2020-10-12 14:02:47,371 [myid:] - INFO  [main:Environment@100] - Client environment:java.io.tmpdir=/tmp
2020-10-12 14:02:47,371 [myid:] - INFO  [main:Environment@100] - Client environment:java.compiler=<NA>
2020-10-12 14:02:47,371 [myid:] - INFO  [main:Environment@100] - Client environment:os.name=Linux
2020-10-12 14:02:47,371 [myid:] - INFO  [main:Environment@100] - Client environment:os.arch=amd64
2020-10-12 14:02:47,371 [myid:] - INFO  [main:Environment@100] - Client environment:os.version=3.10.0-1127.19.1.el7.x86_64
2020-10-12 14:02:47,371 [myid:] - INFO  [main:Environment@100] - Client environment:user.name=root
2020-10-12 14:02:47,371 [myid:] - INFO  [main:Environment@100] - Client environment:user.home=/root
2020-10-12 14:02:47,371 [myid:] - INFO  [main:Environment@100] - Client environment:user.dir=/usr/local/zookeeper-3.4.14/bin
2020-10-12 14:02:47,372 [myid:] - INFO  [main:ZooKeeper@442] - Initiating client connection, connectString=localhost:2181 sessionTimeout=30000 watcher=org.apache.zookeeper.ZooKeeperMain$MyWatcher@446cdf90
Welcome to ZooKeeper!
2020-10-12 14:02:47,393 [myid:] - INFO  [main-SendThread(localhost:2181):ClientCnxn$SendThread@1025] - Opening socket connection to server localhost/127.0.0.1:2181. Will not attempt to authenticate using SASL (unknown error)
2020-10-12 14:02:47,398 [myid:] - INFO  [main-SendThread(localhost:2181):ClientCnxn$SendThread@879] - Socket connection established to localhost/127.0.0.1:2181, initiating session
JLine support is enabled
2020-10-12 14:02:47,441 [myid:] - INFO  [main-SendThread(localhost:2181):ClientCnxn$SendThread@1299] - Session establishment complete on server localhost/127.0.0.1:2181, sessionid = 0x1001faf17bc0000, negotiated timeout = 30000

WATCHER::

WatchedEvent state:SyncConnected type:None path:null
[zk: localhost:2181(CONNECTED) 0] ls /
[zookeeper]
[zk: localhost:2181(CONNECTED) 1] create /zkro     ---创建不了
[zk: localhost:2181(CONNECTED) 2] ls /        
[zookeeper]
[zk: localhost:2181(CONNECTED) 3] create /zkPro myData     ---myData是数据
Created /zkPro
[zk: localhost:2181(CONNECTED) 4] ls
[zk: localhost:2181(CONNECTED) 5] ls /
[zookeeper, zkPro]
[zk: localhost:2181(CONNECTED) 6] get /zkPro       ---查看   
myData
cZxid = 0x2
ctime = Mon Oct 12 14:09:59 CST 2020
mZxid = 0x2
mtime = Mon Oct 12 14:09:59 CST 2020
pZxid = 0x2
cversion = 0
dataVersion = 0
aclVersion = 0
ephemeralOwner = 0x0
dataLength = 6
numChildren = 0
[zk: localhost:2181(CONNECTED) 7] set /zkPro myData123     ---修改
cZxid = 0x2
ctime = Mon Oct 12 14:09:59 CST 2020
mZxid = 0x3
mtime = Mon Oct 12 14:13:19 CST 2020
pZxid = 0x2
cversion = 0
dataVersion = 1
aclVersion = 0
ephemeralOwner = 0x0
dataLength = 9
numChildren = 0
[zk: localhost:2181(CONNECTED) 8] get /zkPro         ---再次查看      
myData123
cZxid = 0x2
ctime = Mon Oct 12 14:09:59 CST 2020
mZxid = 0x3
mtime = Mon Oct 12 14:13:19 CST 2020
pZxid = 0x2
cversion = 0
dataVersion = 1
aclVersion = 0
ephemeralOwner = 0x0
dataLength = 9
numChildren = 0
[zk: localhost:2181(CONNECTED) 9] delete /zkPro
[zk: localhost:2181(CONNECTED) 10] get /zkPro        ---删除后查看不了
Node does not exist: /zkPro
```

## maven

> 这里搭建maven是为搭建zkui准备的。

https://www.ilanni.com/?p=12467

```powershell
maven：
https://www.ilanni.com/?p=12467
[root@iz8vbbyuhcl6ozmfu17dziz ~]# chown -R root:root /usr/local/jdk1.8.0_261/
[root@iz8vbbyuhcl6ozmfu17dziz ~]# wget http://mirror.bit.edu.cn/apache/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz^C
[root@iz8vbbyuhcl6ozmfu17dziz ~]# cd /usr/local/
[root@iz8vbbyuhcl6ozmfu17dziz local]# wget http://mirror.bit.edu.cn/apache/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz
--2020-10-14 10:33:22--  http://mirror.bit.edu.cn/apache/maven/maven-3/3.3.9/binaries/apache-maven-3.3.9-bin.tar.gz
正在解析主机 mirror.bit.edu.cn (mirror.bit.edu.cn)... 219.143.204.117, 202.204.80.77, 2001:da8:204:1205::22
正在连接 mirror.bit.edu.cn (mirror.bit.edu.cn)|219.143.204.117|:80... 已连接。
已发出 HTTP 请求，正在等待回应... 200 OK
长度：8491533 (8.1M) [application/octet-stream]
正在保存至: “apache-maven-3.3.9-bin.tar.gz”

100%[===========================================================================================================================================================>] 8,491,533   6.49MB/s 用时 1.2s   

2020-10-14 10:33:24 (6.49 MB/s) - 已保存 “apache-maven-3.3.9-bin.tar.gz” [8491533/8491533])

[root@iz8vbbyuhcl6ozmfu17dziz local]# tar -xf apache-maven-3.3.9-bin.tar.gz -C /usr/local/
[root@iz8vbbyuhcl6ozmfu17dziz local]# ls
apache-maven-3.3.9
[root@iz8vbbyuhcl6ozmfu17dziz local]# mv apache-maven-3.3.9 maven
[root@iz8vbbyuhcl6ozmfu17dziz local]# ls
maven
[root@iz8vbbyuhcl6ozmfu17dziz local]# vim /etc/profile
export M2_HOME=/usr/local/maven/
export PATH=$PATH:/usr/local/mysql/bin:$M2_HOME/bin
[root@iz8vbbyuhcl6ozmfu17dziz local]# mvn -v
Apache Maven 3.3.9 (bb52d8502b132ec0a5a3f4c09453c07478323dc5; 2015-11-11T00:41:47+08:00)
Maven home: /usr/local/maven
Java version: 1.8.0_261, vendor: Oracle Corporation
Java home: /usr/local/jdk1.8.0_261/jre
Default locale: zh_CN, platform encoding: UTF-8
OS name: "linux", version: "3.10.0-1127.19.1.el7.x86_64", arch: "amd64", family: "unix"
```

## 图形化界面zkui

图形化界面选型：

zkui

https://blog.csdn.net/wc1695040842/article/details/103558456

ZooViewer

https://blog.csdn.net/u010889616/article/details/80792912?utm_medium=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param

zktools

https://blog.csdn.net/rongbaojian/article/details/82078368?utm_medium=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-BlogCommendFromMachineLearnPai2-1.channel_param



zkui

https://www.ilanni.com/?p=13646

```powershell
[root@iz8vbbyuhcl6ozmfu17dziz local]# unzip ilanni-zkui-master.zip 
[root@iz8vbbyuhcl6ozmfu17dziz local]# ll
-rw-r--r--   1 root  root     444039 10月 14 11:29 ilanni-zkui-master.zip
drwxr-xr-x   5 root  root       4096 7月   7 2017 zkui
[root@iz8vbbyuhcl6ozmfu17dziz local]# cd zkui/
[root@iz8vbbyuhcl6ozmfu17dziz zkui]# ll
总用量 56
-rw-r--r-- 1 root root  2357 7月   7 2017 config.cfg
drwxr-xr-x 2 root root  4096 7月   7 2017 docker
drwxr-xr-x 2 root root  4096 7月   7 2017 images
-rw-r--r-- 1 root root 11358 7月   7 2017 LICENSE-2.0.txt
-rw-r--r-- 1 root root   416 7月   7 2017 Makefile
-rw-r--r-- 1 root root  1746 7月   7 2017 nbactions.xml
-rw-r--r-- 1 root root  5294 7月   7 2017 pom.xml
-rw-r--r-- 1 root root  6216 7月   7 2017 README.md
-rw-r--r-- 1 root root    43 7月   7 2017 run.sh
drwxr-xr-x 4 root root  4096 7月   7 2017 src
[root@iz8vbbyuhcl6ozmfu17dziz zkui]# mvn clean install
[INFO] Scanning for projects...
[INFO]                                                                         
[INFO] ------------------------------------------------------------------------
[INFO] Building zkui 2.0-SNAPSHOT
[INFO] ------------------------------------------------------------------------
Downloading: https://repo.maven.apache.org/maven2/org/apache/maven/plugins/maven-clean-plugin/2.5/maven-clean-plugin-2.5.pom
Downloaded: https://repo.maven.apache.org/maven2/org/apache/maven/plugins/maven-clean-plugin/2.5/maven-clean-plugin-2.5.pom (4 KB at 2.6 KB/sec)
。。。。。。
[INFO] 
[INFO] --- maven-clean-plugin:2.5:clean (default-clean) @ zkui ---
Downloading: https://repo.maven.apache.org/maven2/org/apache/maven/maven-plugin-api/2.0.6/maven-plugin-api-2.0.6.pom
Downloaded: https://repo.maven.apache.org/maven2/org/apache/maven/maven-plugin-api/2.0.6/maven-plugin-api-2.0.6.pom (2 KB at 4.1 KB/sec)
。。。。。。
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ zkui ---
Downloading: https://repo.maven.apache.org/maven2/org/apache/maven/maven-project/2.0.6/maven-project-2.0.6.pom
Downloaded: https://repo.maven.apache.org/maven2/org/apache/maven/maven-project/2.0.6/maven-project-2.0.6.pom (3 KB at 5.9 KB/sec)
。。。。。。
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 29 resources
[INFO] 
[INFO] --- maven-compiler-plugin:2.3.2:compile (default-compile) @ zkui ---
Downloading: https://repo.maven.apache.org/maven2/org/apache/maven/maven-toolchain/1.0/maven-toolchain-1.0.pom
Downloaded: https://repo.maven.apache.org/maven2/org/apache/maven/maven-toolchain/1.0/maven-toolchain-1.0.pom (4 KB at 7.8 KB/sec)
。。。。。。
[INFO] Compiling 20 source files to /usr/local/zkui/target/classes
[INFO] 
[INFO] >>> activejdbc-instrumentation:1.4.1:instrument (default) > process-classes @ zkui >>>
[INFO] 
[INFO] --- maven-resources-plugin:2.6:resources (default-resources) @ zkui ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] Copying 29 resources
[INFO] 
[INFO] --- maven-compiler-plugin:2.3.2:compile (default-compile) @ zkui ---
[INFO] Nothing to compile - all classes are up to date
[INFO] 
[INFO] <<< activejdbc-instrumentation:1.4.1:instrument (default) < process-classes @ zkui <<<
[INFO] 
[INFO] --- activejdbc-instrumentation:1.4.1:instrument (default) @ zkui ---
Downloading: https://repo.maven.apache.org/maven2/org/apache/maven/maven-plugin-api/2.0/maven-plugin-api-2.0.pom
Downloaded: https://repo.maven.apache.org/maven2/org/apache/maven/maven-plugin-api/2.0/maven-plugin-api-2.0.pom (601 B at 1.5 KB/sec)
。。。。。。
**************************** START INSTRUMENTATION ****************************
Directory: /usr/local/zkui/target/classes
Found model: com.deem.zkui.domain.History
Detected method: getId, skipping delegate.
Instrumented class: com.deem.zkui.domain.History in directory: /usr/local/zkui/target/classes/
**************************** END INSTRUMENTATION ****************************
[INFO] Instrumentation: directory /usr/local/zkui/target/test-classes does not exist, skipping
[INFO] 
[INFO] --- maven-resources-plugin:2.6:testResources (default-testResources) @ zkui ---
[INFO] Using 'UTF-8' encoding to copy filtered resources.
[INFO] skip non existing resourceDirectory /usr/local/zkui/src/test/resources
[INFO] 
[INFO] --- maven-compiler-plugin:2.3.2:testCompile (default-testCompile) @ zkui ---
[INFO] Compiling 1 source file to /usr/local/zkui/target/test-classes
[INFO] 
[INFO] --- maven-surefire-plugin:2.12.4:test (default-test) @ zkui ---
Downloading: https://repo.maven.apache.org/maven2/org/apache/maven/maven-plugin-api/2.0.9/maven-plugin-api-2.0.9.pom
Downloaded: https://repo.maven.apache.org/maven2/org/apache/maven/maven-plugin-api/2.0.9/maven-plugin-api-2.0.9.pom (2 KB at 1.2 KB/sec)
。。。。。。
[INFO] Surefire report directory: /usr/local/zkui/target/surefire-reports
Downloading: https://repo.maven.apache.org/maven2/org/apache/maven/surefire/surefire-junit3/2.12.4/surefire-junit3-2.12.4.pom
Downloaded: https://repo.maven.apache.org/maven2/org/apache/maven/surefire/surefire-junit3/2.12.4/surefire-junit3-2.12.4.pom (2 KB at 2.6 KB/sec)
[INFO] Surefire report directory: /usr/local/zkui/target/surefire-reports
Downloading: https://repo.maven.apache.org/maven2/org/apache/maven/surefire/surefire-junit3/2.12.4/surefire-junit3-2.12.4.pom
Downloaded: https://repo.maven.apache.org/maven2/org/apache/maven/surefire/surefire-junit3/2.12.4/surefire-junit3-2.12.4.pom (2 KB at 2.6 KB/sec)
。。。。。。
-------------------------------------------------------
 T E S T S
-------------------------------------------------------
Running com.deem.zkui.test.ZKUITest
Tests run: 0, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.001 sec

Results :

Tests run: 0, Failures: 0, Errors: 0, Skipped: 0

[INFO] 
[INFO] --- maven-jar-plugin:2.4:jar (default-jar) @ zkui ---
Downloading: https://repo.maven.apache.org/maven2/org/apache/maven/maven-archiver/2.5/maven-archiver-2.5.pom
Downloaded: https://repo.maven.apache.org/maven2/org/apache/maven/maven-archiver/2.5/maven-archiver-2.5.pom (5 KB at 2.6 KB/sec)
。。。。。。
[INFO] Building jar: /usr/local/zkui/target/zkui-2.0-SNAPSHOT.jar
[INFO] 
[INFO] --- maven-assembly-plugin:2.2-beta-5:single (make-assembly) @ zkui ---
Downloading: https://repo.maven.apache.org/maven2/org/apache/maven/shared/maven-common-artifact-filters/1.1/maven-common-artifact-filters-1.1.pom
Downloaded: https://repo.maven.apache.org/maven2/org/apache/maven/shared/maven-common-artifact-filters/1.1/maven-common-artifact-filters-1.1.pom (3 KB at 6.4 KB/sec)
。。。。。。
[INFO] META-INF/ already added, skipping
[INFO] META-INF/MANIFEST.MF already added, skipping
[INFO] META-INF/maven/ already added, skipping
[INFO] META-INF/ already added, skipping
[INFO] META-INF/MANIFEST.MF already added, skipping
[INFO] org/ already added, skipping
[INFO] org/eclipse/ already added, skipping
[INFO] org/eclipse/jetty/ already added, skipping
[INFO] about.html already added, skipping
[INFO] META-INF/maven/ already added, skipping
[INFO] META-INF/maven/org.eclipse.jetty/ already added, skipping
。。。。。。
[INFO] 
[INFO] --- maven-install-plugin:2.4:install (default-install) @ zkui ---
Downloading: https://repo.maven.apache.org/maven2/org/codehaus/plexus/plexus-utils/3.0.5/plexus-utils-3.0.5.pom
Downloaded: https://repo.maven.apache.org/maven2/org/codehaus/plexus/plexus-utils/3.0.5/plexus-utils-3.0.5.pom (3 KB at 5.1 KB/sec)
。。。。。。
[INFO] Installing /usr/local/zkui/target/zkui-2.0-SNAPSHOT.jar to /root/.m2/repository/com/deem/zkui/2.0-SNAPSHOT/zkui-2.0-SNAPSHOT.jar
[INFO] Installing /usr/local/zkui/pom.xml to /root/.m2/repository/com/deem/zkui/2.0-SNAPSHOT/zkui-2.0-SNAPSHOT.pom
[INFO] Installing /usr/local/zkui/target/zkui-2.0-SNAPSHOT-jar-with-dependencies.jar to /root/.m2/repository/com/deem/zkui/2.0-SNAPSHOT/zkui-2.0-SNAPSHOT-jar-with-dependencies.jar
[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
[INFO] Total time: 07:04 min
[INFO] Finished at: 2020-10-14T11:43:16+08:00
[INFO] Final Memory: 39M/340M
[INFO] ------------------------------------------------------------------------
[root@iz8vbbyuhcl6ozmfu17dziz zkui]# tree -L 2 target/
target/
├── archive-tmp
├── classes
│   ├── activejdbc_models.properties
│   ├── com
│   ├── db
│   ├── log4j.properties
│   └── webapp
├── generated-sources
│   ├── annotations
│   └── test-annotations
├── maven-archiver
│   └── pom.properties
├── surefire-reports
│   ├── com.deem.zkui.test.ZKUITest.txt
│   └── TEST-com.deem.zkui.test.ZKUITest.xml
├── test-classes
│   └── com
├── zkui-2.0-SNAPSHOT.jar
└── zkui-2.0-SNAPSHOT-jar-with-dependencies.jar

12 directories, 7 files
[root@iz8vbbyuhcl6ozmfu17dziz zkui]# vim config.cfg
[root@iz8vbbyuhcl6ozmfu17dziz zkui]# nohup java -jar target/zkui-2.0-SNAPSHOT-jar-with-dependencies.jar &
[1] 20726
[root@iz8vbbyuhcl6ozmfu17dziz zkui]# nohup: 忽略输入并把输出追加到"nohup.out"
[root@iz8vbbyuhcl6ozmfu17dziz zkui]# netstat -tunlp |grep 9090
tcp        0      0 0.0.0.0:9090            0.0.0.0:*               LISTEN      20726/java      
```

修改：

https://www.ilanni.com/?p=11393

```powershell
[root@iz8vbbyuhcl6ozmfu17dziz local]# mv zookeeper-3.4.14 zookeeper
[root@iz8vbbyuhcl6ozmfu17dziz local]# chown root:root -R zookeeper/
[root@iz8vbbyuhcl6ozmfu17dziz local]# vim /etc/profile
加入：
export PATH=$PATH:/usr/local/zookeeper/bin




注意：配置文件config.cfg一定要跟zkui-2.0-SNAPSHOT-jar-with-dependencies.jar在同一目录下，不然访问网页报错
[root@iz8vbbyuhcl6ozmfu17dziz local]# ls zkui-master/target/
archive-tmp  classes  config.cfg  generated-sources  maven-archiver  nohup.out  surefire-reports  test-classes  zkui-2.0-SNAPSHOT.jar  zkui-2.0-SNAPSHOT-jar-with-dependencies.jar  zkui-out.log
```



## 阿里云配置

测试环境：

![image-20201015134018250](zookeeper.assets/image-20201015134018250.png)

监听9090端口：

![image-20201015134105384](zookeeper.assets/image-20201015134105384.png)

让9090端口转发到指定后端虚拟服务器组：

![image-20201015134552037](zookeeper.assets/image-20201015134552037.png)

![image-20201015134634063](zookeeper.assets/image-20201015134634063.png)



## 访问地址

网页访问地址：http://39.99.238.52:9090/login

账号：admin

密码：admin

> 注意：这里39.99.238.52为slb的ip，实际zookeeper的ip为172.26.223.83，即请求通过slb39.99.238.52打到172.26.223.83。

开发接口访问地址：http://121.89.179.126:2181

需要开放安全组规则：

![image-20201102101243847](zookeeper.assets/image-20201102101243847.png)




