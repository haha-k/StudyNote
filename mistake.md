1. MySQL(8.0.11后)改密码
```sql
alter user 'john'@'localhost' identified with mysql_native_password by '123';
```


2. django后台加入编码错误
  `gbk codec can't decode byte 0xa6 illegal multibyte sequence`

   ![](.\pic\django后台编码错误.jpg)