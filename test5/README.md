## 图书管理系统数据库设计与界面设计
**1.数据库表设计**
图书资源表

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020042709422456.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDAwNTEzMg==,size_16,color_FFFFFF,t_70)

图书信息表

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200427094258253.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDAwNTEzMg==,size_16,color_FFFFFF,t_70)

学生信息表

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200427095658666.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDAwNTEzMg==,size_16,color_FFFFFF,t_70)

借书记录表

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200427095738471.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDAwNTEzMg==,size_16,color_FFFFFF,t_70)


**2. 界面设计**

     [界面设计](https://white12138.github.io/is_analysis_pages/start.html)
     https://white12138.github.io/is_analysis_pages/start.htmlstart
     
2.1登陆界面

![在这里插入图片描述](https://img-blog.csdnimg.cn/20200427101643227.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDAwNTEzMg==,size_16,color_FFFFFF,t_70)

用例图参见：登录用例
类图参见：管理员类，读者类
顺序图参见：所有图的login()
API接口如下：
1.登录

功能:登录用户
请求地址：http:/api/login
请求方法：GET
请求参数：
<table>
<tr>
<td>参数名称</td>
<td>必填</td>
<td>说明</td>
</tr>
<tr>
<td>access_token</td>
<td>是</td>
<td>用于验证请求合法性的认证信息。</td>
</tr>
<tr>
<td>method</td>
<td>是</td>
<td>固定未"GET"</td>
</tr>
</table>

```
{
  "user": "username，password",
}
```



2.2[借书界面设计](https://white12138.github.io/is_analysis_pages/start.html#id=1qz6vh&p=%E5%80%9F%E4%B9%A6%E7%95%8C%E9%9D%A2)


![在这里插入图片描述](https://img-blog.csdnimg.cn/20200426170422780.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDAwNTEzMg==,size_16,color_FFFFFF,t_70)
- 类图参见：管理员类，读者类
- 顺序图参见：书籍借阅图
- API接口如下：

1.书籍借阅
- 功能:借阅
- 请求地址：http://xybbook/v1/api/book
- 请求方法：PUT
- 请求参数：
<table>
<tr>
<td>参数名称</td>
<td>必填</td>
<td>说明</td>
</tr>
<tr>
<td>access_token</td>
<td>是</td>
<td>用于验证请求合法性的认证信息。</td>
</tr>
<tr>
<td>method</td>
<td>是</td>
<td>PUT</td>
</tr>
</table>

```
{
    "info": "借阅成功",
    "ID": {
        "ID": "465854979",
      
        "ZYMC": "梦的解析",
        "author": "弗洛伊德",
        "Publisher": "北京出版社",
      },
      "XH":"201710414227",
    "borrow":{
         "XH":"201710414227", 
         "ID": "620155415",
         "ZYMC": "梦的解析"                      
     },
       
   
}
```
<table>
<tr>
<td>参数名称</td>
<td>说明</td>
</tr>
<tr>
<td>info</td>
<td>返回信息</td>
</tr>
<tr>
<td>ID</td>
<td>图书ID</td>
</tr>
<tr>
<td>XH</td>
<td>读者学号</td>
</tr>
<tr>
<td>KJSL</td>
<td>读者允许借阅图书最大数</td>
</tr>
<tr>
<td>borrow</td>
<td>生成借阅信息</td>
</tr>
</table>

2.3[还书界面设计](https://white12138.github.io/is_analysis_pages/start.html#id=rqqmy1&p=%E8%BF%98%E4%B9%A6%E7%95%8C%E9%9D%A2)
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200427103205217.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDAwNTEzMg==,size_16,color_FFFFFF,t_70)
- 类图参见：管理员类，读者类
- 顺序图参见：书籍还书图
- API接口如下：

1.书籍归还
- 功能:归还
- 请求地址：http:/api/book?id=
- 请求方法：PUT
- 请求参数：
 <table>
<tr>
<td>参数名称</td>
<td>必填</td>
<td>说明</td>
</tr>
<tr>
<td>access_token</td>
<td>是</td>
<td>用于验证请求合法性的认证信息。</td>
</tr>
<tr>
<td>method</td>
<td>是</td>
<td>PUT</td>
</tr>
</table>

```
{
    "info": "归还成功",
    "BookData": {
        "ID": "15163",
        "ZYMC": "大大大阿迪达斯",
        "author": "大",
        "Publisher": "北京出版社",
        "gjcbh": "234",
      },
      "XH":"201710414227",
      "isOutDate":"false""true",
}
```
<table>
<tr>
<td>参数名称</td>
<td>说明</td>
</tr>
<tr>
<td>info</td>
<td>返回信息</td>
</tr>
<tr>
<td>ID</td>
<td>图书ID</td>
</tr>
<tr>
<td>XH</td>
<td>读者学号</td>
</tr>
<tr>
<td>Publisher</td>
<td>出版社</td>
</tr>
<tr>
<td>isOutDate</td>
<td>是否逾期</td>
<tr>
</table>
