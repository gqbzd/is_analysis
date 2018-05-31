# 数据库设计 [首页](./README.md)

- ## USERS表（用户表）

    |字段|类型|主键，外键|可以为空|默认值|约束|说明|
    |:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
    |ID|int(10)|主键|否| | | 用户ID|
    |NAME|VARCHAR2(50 BYTE)| |否| | | 用户真实姓名|
    |PASSWORD|VARCHAR2(512 BYTE)| |是|空| | 加密存储密码，为空表示密码就是学号|
    |UPDATE_DATE|DATE| |是|空| | 信息修改日期|
    
- ## STUDENTS表（学生表）

|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
|ID|int(10)|外键|否| | | 指向users表ID|
|STUDENT_ID|int(10)|主键|否| | | 学生学号|
|CLASSNAME|VARCHAR2(50 BYTE)| |否| | | 班级|
|GITHUBNAME|VARCHAR2(512 BYTE)| |是|空| | GITHUB用户名|

- ## TEACHER表（老师表）

|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
|ID|int(10)|外键|否| | | 指向users表ID|
|TEACHER_ID|int(10)|主键|否| | | 老师工号|

- ## LESSON表（课程表）

|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
|LESSON_ID|int(10)|主键|否| | | 课程ID|
|LESSON_NAME|VARCHAR2|主键|否| | | 课程名称|

- ## STU_LESSON表（学生选课表）

|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
|ID|int(10)|主键|否| | | 记录ID|
|STU_ID|int(10)|外键|否| | | 学生学号|
|STU_NAME|VARCHAR2|外键|否| | | 学生姓名|
|LESSON_ID|int(10)|外键|否| | | 课程ID|
|LESSON_NAME|VARCHAR2|外键|否| | | 课程名称|
|A_GRADE|int(10)| | 是| | | A项评分|
|A_JUDGE|VARCHAR2| | 是| | | A项评价|
|B_GRADE|int(10)| | 是| | | B项评分|
|B_JUDGE|VARCHAR2| | 是| | | B项评价|
|C_GRADE|int(10)| | 是| | | C项评分|
|C_JUDGE|VARCHAR2| | 是| | | C项评价|
|D_GRADE|int(10)| | 是| | | D项评分|
|D_JUDGE|VARCHAR2| | 是| | | D项评价|
|ALL_GRADE|int(10)| | 是| | | 各项总和（总成绩）|
|TERM_TEST|VARCHAR2| | 是| | | 第几学期第几次实验|
|UPTIME|Date| | 是| | | 上交时间|

- ## TCH_LESSON表（老师选课表）

|字段|类型|主键，外键|可以为空|默认值|约束|说明|
|:-------:|:-------------:|:------:|:----:|:---:|:----:|:----------|
|ID|int(10)|主键|否| | | 记录ID|
|TCH_ID|int(10)|外键|否| | | 老师工呈|
|TCH_NAME|VARCHAR2|外键|否| | | 老师姓名|
|LESSON_ID|int(10)|外键|否| | | 课程ID|
|LESSON_NAME|VARCHAR2|外键|否| | | 课程名称|
|TERM_TEST|VARCHAR2| | 是| | | 第几学期第几次实验|
|RULE_TIME|Date| | 是| | | 规定上交时间|
