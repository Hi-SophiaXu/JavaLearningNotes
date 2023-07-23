mybatis-config.xml核心配置文件  
约束<!DOCTYPE configuration PUBLIC "dtd">  
根标签就必须得是<configuration></configuration>  
配置连接数据库的环境：<environments>配置多个连接数据库的文件<environment>设置具体环境</environment></environments>  
引入映射文件<mappers></mappers>  



MyBatis面向接口编程的两个一致：  
1. mapper接口的全类名和映射文件的命名空间（namespace）保持一致  
2. mapper接口中方法的方法名和映射文件中编写SQL的标签的id属性保持一致  

**增删改**的返回值是固定的，是受影响的行数