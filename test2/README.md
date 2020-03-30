# 1. 图书管理系统的用例关系图
## 1.1 用例图PlantUML源码如下：

```
@startuml
left to right direction
skinparam packageStyle rectangle
actor 图书管理员
actor 读者

 图书管理员 --> (查询书籍信息)
 图书管理员 --> (更新图书信息)
 图书管理员 --> (增加图书)
 图书管理员 --> (减少图书)
 图书管理员 --> (查询读者情况)
 (查阅图书) <-- 读者
 (查阅借阅情况) <-- 读者
 (预定图书) <-- 读者
 (取消预定) <-- 读者
 (借书) <-- 读者
 (还书) <-- 读者



@enduml

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330222520305.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)


## 2.参与者说明：
### 2.1读者

主要职责是向图书馆借书，预定图书，续借图书以及在规定时间内还书功能。
### 2.2管理员
主要职责更新书籍的信息到管理系统中以及对逾期违规者处理
## 3.用例规约表：
### 3.1“读者”用例：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330231837492.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330231808619.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330232125428.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)




### 3.2“管理员”用例


![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330232214221.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)

### 读者用例流程图源码如下：


```
@startuml
start
:读者系统;
:选择业务;
split
:查询图书;
:查询借阅情况;
:借阅图书;
split again
:归还图书;
if(逾期?)then(yes)
:缴纳费用;
else(no)
:还书成功;
endif
split again
:续借;
split again
:预定;
split again
:取消预定;
end split
:退出系统;
stop
@enduml

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330225313212.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)



### 管理员用例流程图源码如下：

```
@startuml
start
:管理员;
:选择业务;
split
repeat
:更新书籍信息;
repeat while(更新是否成功?)
:更新成功;
split again
:查询用户信息;
:查询已借时间和归还时间;
if(逾期?)then(yes)
:发送逾期通知消息;
else(no)
:不用提醒;
endif

end split
:退出系统;
stop
@enduml

```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200330223256559.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3hpb25nZGF5YQ==,size_16,color_FFFFFF,t_70)
