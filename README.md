![image](https://github.com/user-attachments/assets/8199e872-9957-4c94-8935-5d2db7433cb3)
# 用于学习Github 使用（记录数据开发相关知识）
此存储库（repository）用于练习 Cypher语句
## Cypher语言教程
1. (nodes)-[:ARE_CONNECTED_TO]->(otherNodes)
*  <https://bboyjing.github.io/2016/07/08/Neo4j%E5%AD%A6%E4%B9%A0%E7%AC%94%E8%AE%B0%E4%BA%94%E3%80%90%E6%9F%A5%E8%AF%A2%E8%AF%AD%E8%A8%80Cypher%E3%80%91/>
2. 结构
*  start–查找图形中的起始节点
*  match–匹配图形模式，可以定位感兴趣数据的子图形
*  where–基于某些标准过滤数据
*  return–返回感兴趣的结果
3. 代码块
``` //遍历出John的朋友看过，John也看过的电影
``` // 遍历出John的朋友看过，John也看过的电影
```//由此可以看出Cypher查询中的多个模式使用逗号分隔，相当与关系型数据库的AND语句
```start john = node(0)
```match (john)-[:IS_FRIEND_OF]->()-[:HAS_SEEN]->(movie),
```     (john)-[:HAS_SEEN]->(movie)
```return movie;
```//通过where条件过滤john看过的电影，与关系型数据库的where语句类似
```start john = node(0)
```match (john)-[:IS_FRIEND_OF]->()-[:HAS_SEEN]->(movie)
```where NOT (john)-[:HAS_SEEN]->(movie)
```return movie;
```
4. neo4j 数据写入官网教学地址
   *  https://neo4j.com/docs/spark/current/gds/
     ![image](https://github.com/user-attachments/assets/76935090-1dfd-4707-b2f9-8c7b58762af2)


