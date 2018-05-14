# cat
center application track
Quick Started
 1、将分支mvn-repo下的jar包复制到本机maven仓库，cat一些依赖的jar存放于mvn-repo分支

 1、git clone https://github.com/dianping/cat.git
 2、cd cat
 3、git checkout mvn-repo
 4、cp -R * ~/.m2/repository
 5、git checkout master
 6、mvn clean install -DskipTests

如果下载有问题，可以尝试翻墙后下载
2、在CAT目录下，用maven构建项目

       mvn clean install -DskipTests
3、配置CAT的运行需要配置信息

mvn cat:install

Note：

    Linux\Mac 需要对/data/appdatas/cat和/data/applogs/cat有读写权限
    Windows 则是对系统运行盘下的/data/appdatas/cat和/data/applogs/cat有读写权限,如果cat服务运行在e盘的tomcat中，则需要对e:/data/appdatas/cat和e:/data/applogs/cat有读写权限

       此步骤是配置一些cat启动需要的基本数据库配置以及配置文件
4、(Optional)如果安装了hadoop集群，需到/data/appdatas/cat/server.xml中配置对应hadoop信息。将localmode设置为false，默认情况下，CAT在开发模式（localmode=true）下工作。推荐大部分公司使用单机模式，不需要搭建hdfs，部署cat的服务端使用一个大磁盘的机器，比如1TB，这样可以省去很多事情。

================如果上述自动化程序出现问题，可以使用如下部署进行尝试，这步骤其实就是上述自动化程序做的事情==========================
5、启动的cat单机版本基本步骤

    检查下/data/appdatas/cat/ 下面需要的几个配置文件，配置文件在源码script，请修改对应的datasources.xml 以及 client.xml 里面对应的IP、PSW部分。
    在cat目录下执行 mvn install -DskipTests 。
    cat-home打包出来的war包，重新命名为cat.war, 并放入tomcat的webapps 。
    启动tomcat
    访问 http://localhost:8080/cat/r
    具体详细的还可以参考 http://unidal.org/cat/r/home?op=view&docName=deploy

6、导入eclipse发现找不到类

    请先执行mvn eclipse:eclipse 会自动生成相关的类文件
    作为普通项目导入eclipse，不要用作为maven项目导入eclipse

7、可以参考script目录下详细资料
