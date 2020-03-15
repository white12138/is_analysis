```
@startuml|教务处|start:安排考试;:考试安排表;|#AntiqueWhite|教师|:出卷;fork :A、B试卷forkagain:打印审批表;|系主任|:审批签字;:打印审批表;end fork|教务处|:打印试卷;:试卷;|#AntiqueWhite|学生|:参加考试;:答卷;|#AntiqueWhite|教师|:阅卷出成绩;fork:成绩单;|教务处|if(有不合格？)then(yes)
endif:安排补考;:补考安排表;fork again|#AntiqueWhite|教师|:答卷;:装订存档;end fork:期末流程结束;stop
@enduml
-

```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200316000353263.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDAwNTEzMg==,size_16,color_FFFFFF,t_70)


```
@startuml|客户|start:申请服务;|#AntiqueWhite|业务经理|if(是新客户)then(是):登记客户信息;else(不是)endif:上门勘察;:制定方案;|客户|if(满意吗？)then(否)stopelse(是):签到服务合同;endif|#AntiqueWhite|业务经理|fork:安排工人;fork again:安排材料;end fork:填写派工单;|工人|:领取材料;:上门服务;|客户|:验收并填写反馈意见;|#AntiqueWhite|业务经理|:交回派工单;|#AntiqueWhite|财务人员|:结算验收;stop@enduml

```

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020031600020864.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80NDAwNTEzMg==,size_16,color_FFFFFF,t_70)

