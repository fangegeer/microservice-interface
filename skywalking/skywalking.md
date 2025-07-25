-javaagent:D:\home\skywalking\source\skywalking-java\skywalking-agent\skywalking-agent.jar -Dskywalking.agent.service_name=planner-workbench-server -Dskywalking.collector.backend_service=127.0.0.1:11800

https://www.apache.org/dyn/closer.cgi/skywalking/java-agent/9.4.0/apache-skywalking-java-agent-9.4.0.tgz
https://archive.apache.org/dist/skywalking/9.4.0/apache-skywalking-apm-9.4.0.tar.gz


https://www.apache.org/dyn/closer.cgi/skywalking/java-agent/9.4.0/apache-skywalking-java-agent-9.4.0.tgz
https://archive.apache.org/dist/skywalking/9.4.0/apache-skywalking-apm-9.4.0.tar.gz

国内agent源码：https://gitee.com/chenfang6/skywalking-java
国内apm源码：https://gitee.com/chenfang6/skywalking
github agent源码：https://github.com/apache/skywalking-java
github apm源码：https://github.com/apache/skywalking

# 指定版本打包
## 下载源码
git clone <源码地址>

## 进入目录
cd skywalking

## 切换分支
git checkout v9.1.0

## 初始化仓库目录位置
git submodule init

## 更新子模块源码，这里容易超时，注意检查，可以多试几次
git submodule update

# #maven打包
mvn clean package -DskipTests
mvnw.cmd clean package -DskipTests

打包后的agent在skywalking-agent
打包后的apm在dist

1. 运行apmq前，需要修改config/application.yml里的storage.selector
2.运行apm时，报错org.apache.skywalking.oap.server.starter.OAPServerBootstrap - 60 [main] ERROR [] - Failed to get driver instance for jdbcUrl=jdbc:mysql://
    说明缺少数据库连接jar，将mysql-connector-j-8.0.33.jar、mysql-connector-java-8.0.13.jar放到oap-libs目录下即可
