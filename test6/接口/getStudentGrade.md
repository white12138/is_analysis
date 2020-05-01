# 接口：getStudentGrade

- 功能：
    返回一个学生的所有实验成绩和实验评价。
    
- 权限：
- 学生和老师查看成绩
    
- API请求地址： 
    接口基本地址/v1/api/getOneStudentGrade/<student_id>

- 请求方式 ：
    GET

- 请求参数说明:        

  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |student_id|学生的学号|
    
- 返回实例：

        {         
            "status": true,
            "info": null,    
            "student_id": "201510315203", 
            "github_username": "white12138", 
            "class": "软件(本)17-2", 
            "name": "张锐",
            "avgresult":90,       
            "data": [
                {
                "test_id":1,
                "grade": 90, 
                "comment":"做得很好",
                "update_date": "2020-05-01 12:00:43"
                }, 
            ] 
        }
 
- 返回参数说明：    
 
  |参数名称|说明|
  |:---------:|:--------------------------------------------------------|      
  |status|true表示正确的返回，false表示有错误|
  |info|返回结果说明信息|
  |student_id|学号|
  |github_username|学生的gitHub用户名|
  |class|班级|
  |name|姓名|   
  |avgresult|实验平均成绩|   
  |data|所有实验的成绩和评语|
  |test_id|实验编号|
  |grade|本实验成绩|
  |comment|本实验老师的评价|
  |update_date|本实验老师的批改日期|

