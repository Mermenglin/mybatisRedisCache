# mybatisRedisCache

创建了两种 redis缓存做法

一种config目录，基于在方法上添加注解实现。  
  优点，可以自定义配置key，value等，更加灵活。  
  缺点，在方法上添加注解，需要配置的地方就很多，代码量增加


一种在 util目录，在 Mapper中添加开启二级缓存。  
  优点，mybatis框架支持，简单，代码量少。  
  缺点是不够灵活，测试中发现，当delete执行后，会将reids中该mapper缓存的数据都删除掉，主要原因是因为二级缓存flush整个DB，导致不需要失效的缓存也给失效掉了。  

