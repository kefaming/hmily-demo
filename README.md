# hmily-demo

## 项目名称

分布式事务 tcc 开源框架 Hmily

## 项目描述

Hmily 是一款高性能分布式事务 tcc 开源框架。基于java语言来开发（JDK1.8），支持 Dubbo、Spring Cloud、Motan 等 RPC 框架进行分布式事务。

## 使用说明

以 spring cloud 版为例：

step 1. 导入 hmily-demo.sql 文件中的数据。包括三个库：tcc_account,tcc_order,tcc_stock，每个库下各自有一张表，分别为 accout,order,inventory，为别为帐户表、订单表和库存表。

step 2. 分别启动四个工程，hmily-demo-springcloud-eureka,hmily-demo-springcloud-account,hmily-demo-springcloud-inventory,hmily-demo-springcloud-order.

step 3. 使用 postman 工具发送 post 请求，http://0.0.0.0:8884/order/orderPay?count=1&amount=2 ，count 代表商品数量，amount 代表商品金额。初始值：account 表中：balance: 10000, freeze_amount: 0，inventory 表中：total_inventory: 1000,lock_inventory: 0。

其中：
balance: 帐户余额
freeze_amount: 冻结金额
total_inventory: 库存数
lock_inventory: 锁定库存

如果








