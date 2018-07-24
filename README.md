项目介绍
聚合第三方支付通道并且实现零代码就能聚合收款的目的。

技术框架
* 核心框架：Spring-Boot 2.0
* 视图框架：FreeMarker 2.3.28
* 持久层框架：MyBatis 3.4.6
* 数据库连接池: Druid 1.0.15
* 日志管理：Logback 1.2.3
* JS框架：Jquery 3.2.1
* UI框架: Layui 2.2.6
* 项目管理框架: Maven 3.3.9

开发环境
* IDE: intellij idea
* DB: Mysql5.7
* JDK: JDK1.8+
* Maven: 3.3.9

运行环境
* 数据库服务器：Mysql5.7
* JAVA平台: JRE1.8+
* 操作系统：Windows、Linux等

使用说明

一：新建数据库simple_pay,并执行simple_pay.sql，修改application.yml配置文件上的数据库连接信息<br>
二：用maven编译<br>
三：直接执行java -jar -server simple-pay-0.0.1-SNAPSHOT.jar<br>
四：端口默认监听在7878上面,访问http://[域名|ip]:端口<br>
五：注册用户<br>

商户回调签名说明
收到第三方支付回调后，会转换成统一的参数，对参数进行ASCII码升序排序，取里面的值+设置到后台的Key，用MD5算一个签名<br>
具体参考类ReportMechant上的buildNotifySign方法<br>
商户收到报文之后，成功需要应答字符串“SUCCESS”，失败应答字符串 “FAILURE”
