**图书管理系统的顺序图**
1. 借书用例
1.1. 借书用例PlantUML源码

```
@startuml
actor 图书管理员
activate 图书管理员
图书管理员 -> 读者: 验证读者
activate 读者
deactivate
图书管理员 -> 读者: 去读者限额
activate 读者
deactivate
图书管理员 -> 资源项: 获取资源项
activate 资源项
资源项 -> 馆藏资源品种:查找资源品种
activate 馆藏资源品种
deactivate
deactivate  资源项
图书管理员 -> 借书记录: 创建借书记录
activate 借书记录
deactivate
图书管理员 -> 资源项: 借出资源
activate 资源项
资源项 -> 馆藏资源品种:减少可借数量
activate 馆藏资源品种
deactivate
deactivate 资源项
图书管理员 -> 读者: 减少可用限额
activate 读者
deactivate
图书管理员 -> 借书记录: 打印借书清单
activate 借书记录
deactivate
deactivate 图书管理员

@enduml
```

1.2. 借书用例顺序图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200413125315687.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDAwNTEzMg==,size_16,color_FFFFFF,t_70)

1.3. 借书用例顺序图说明

```
1.验证读者：验证读者是否有借书权利
2.取读者限额：查看读者还可以借多少本书
3.取资源项：获取资源信息
4.查询资源品种：获取图书信息
5.创建借书记录：创建读者的借书记录
6.减少可借数量：从资源项中减少品种数量
7.减少可用限额：减少读者可借图书限额
8.打印借书清单：登记借书记录
9.借出资源：从资源项中借出资源
```

**2. 还书用例**
2.1. 还书用例PlantUML源码

```
@startuml
actor 图书管理员

actor 图书管理员
activate 图书管理员
图书管理员 -> 资源项: 验证读者
activate 资源项
资源项 -> 借书记录:取借书记录
activate 借书记录
deactivate
资源项 -> 馆藏资源品种:取资源记录
activate 馆藏资源品种
deactivate
deactivate
图书管理员 -> 读者: 取借阅者信息
activate 读者
deactivate
图书管理员 -> 资源项: 归还资源
activate 资源项
资源项 -> 馆藏资源品种:增加可借数量
activate 馆藏资源品种
deactivate
deactivate 资源项
图书管理员 -> 借书记录: 登记归还日期
activate 借书记录
deactivate
图书管理员 -> 逾期记录: 登记逾期记录
activate 逾期记录
deactivate
deactivate 图书管理员
@enduml
```
2.2. 还书用例顺序图

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200413125340254.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDAwNTEzMg==,size_16,color_FFFFFF,t_70)


2.3. 还书用例顺序图说明

```
1.验证读者：验证读者是否有借书权利
2取借书记录：获取读者借书记录
3.取资源记录：获取资源信息
4.取借阅者信息：获取读者信息
5.归还资源：读者还书后增加资源项
6.增加可借数量：从资源项中增加品种数量
7.登记归还日期：登记读者还书日期
8.登记逾期记录：读者如果有逾期登记逾期记录
```
