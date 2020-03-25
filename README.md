# hmily-demo

## 项目名称

分布式事务 tcc 开源框架 Hmily

## 项目描述

Hmily 是一款高性能分布式事务 tcc 开源框架。基于java语言来开发（JDK1.8），支持 Dubbo、Spring Cloud、Motan 等 RPC 框架进行分布式事务。

## 使用说明

以 spring cloud 版为例：

#### step 1

导入 hmily-demo.sql 文件中的数据。包括三个库：tcc_account,tcc_order,tcc_stock，每个库下各自有一张表，分别为 accout,order,inventory，为别为帐户表、订单表和库存表。

#### step 2

分别启动四个工程，hmily-demo-springcloud-eureka, hmily-demo-springcloud-account, hmily-demo-springcloud-inventory, hmily-demo-springcloud-order.

#### step 3

使用 postman 工具发送 post 请求，http://0.0.0.0:8884/order/orderPay?count=1&amount=2 ，其中参数 count 代表商品数量，amount 代表金额。

#### step 4

如果调用成功的话，balance 最终会变为 9998，total_inventory 会变为 999，同时 order 表中会增加一条订单信息。其中 balance 和 total_inventory 初始值分别为 10000 和 1000，即 商品总数扣减1，帐户余额扣减2.









