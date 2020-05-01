# 接口：getStudents  
- 权限：
    学生：不能看到grade，test
    老师：可以看到grade，test

- 功能：
    返回所有学生的列表。

- API请求地址：
   接口基本地址/v1/api/getStudents

- 请求方式 ：
    GET

- 请求参数说明:
    无

- 返回实例：

        {
            "status": true,
            "info": null,
            "total": 121,
            "data": [
                {"test": "Y,Y,Y,Y,Y,N",
                "grade": "90.90,90,90,90,90,N",
                "GITHUB_USERNAME": "white12138",
                "STUDENT_ID": "201710414227",
                "CLASS": "软件(本)17-2",
                "NAME": "张锐",
                "UPDATE_DATE": "2020-05-01 13:48:01"},
            
            ]
        }

- 返回参数说明：

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|
  |status|bool类型，true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |total|返回学生人数|
  |data|所有学生的数组|
  |test|网址是否正确的汇总|
  |grade|成绩的汇总|
  |GITHUB_USERNAME|GITHUB 用户名|
  |STUDENT_ID|学号|
  |CLASS|班级|
  |NAME|姓名|
