## Spark 用户 Session 分析项目简介

### 项目环境搭建

- CentOS7
- Hadoop-2.7.6
- Hive-1.2.2
- Zookeeper-3.4.10
- Kafka-2.11-2.1.0
- Flume-1.9.0
- Spark-2.3.1
- Mongodb-linux-2.4.9
- Scala-2.11.8
- Jdk1.8.0_191
- MySQL

### 编程语言

#### Java / Scala

### 项目架构搭建

- 配置管理组件
- JDBC辅助组件 (内置数据库连接池)
- 工具类
- 模拟数据生成
- 单元测试
- Domain 和 DAO

### 项目开发流程

- 数据分析（数据来源分析）
- 需求分析（基于数据，要实现的功能和需求）
- 技术方案设计（根据数据和需求，设计方案实现功能）
- 数据库设计（设计数据库表）
- 编码实现（基于掌握的Spark技术，编码实现）
- 功能测试（本地测试，单元测试，spark的client和cluster说明）
- 性能调优（spark core，spark sql，spark streaming，troubleshooting< 项目上线后，要及时解决出现的线上故障与报错 >，数据倾斜< 后期维护过程中，可能出现严重的性能问题 >）

### 项目模块

- **用户访问session分析**
  - session粒度聚合，按筛选条件进行过滤
  - session聚合统计：统计出访问时长和访问步长，各个区间范围的session数量，占总session数量的比例
  - session随机抽取：按时间比例，随机抽取出10个session
  - top10热门品类：获取通过筛选条件的session，点击，下单和支付次数最多的10个品类。
  - top10活跃session：获取top10热门品类中，每个品类点击次数最多的10个session。
  - 自定义Accumulator
  - 按时间比例随机抽取算法
  - 二次排序
  - 分组取topN
- **页面单跳转化率**
  - 页面单跳转化率计算业务
  - 页面切片生成以及页面流匹配算法

### 技术点

- 项目架构（公共组件封装，包的划分）
- 复杂的分析需求（纯Spark作业）
- Spark core 算子的综合实战：map，reduce，count，group
- 高级技术：自定义Accumulator，按时间比例随机抽取算法，二次排序，分组取topN算法

### 生成环境测试

- hive 表
