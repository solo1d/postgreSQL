## 安装

apt 管理的 linux 服务器

```bash
# 安装
sudo apt install postgresql
# 让其保持运行
sudo systemctl start postgresql.service
```

## 初始化数据库

```bash
#切换到 postgres 用户, 并连接到数据库
sudo -u postgres psql

# 在 postgres 用户下的命令行进行登录数据库
psql postgres

# 终端会变成 postgres=# 开头的样式
# 添加一个用户 myusers  并设置密码 userpassword
postgres=# CREATE USER myusers WITH ENCRYPTED PASSWORD 'userpassword';

# 新建一个库 mydb 并属于 myusers 用户
postgres=# CREATE DATABASE mydb OWNER myusers;

# 将库 mydb 给与用户权限
postgres=# GRANT ALL PRIVILEGES ON DATABASE mydb TO myusers;

# 退出即可完成配置
postgres=# \q
```



### 连接数据库命令

```bash
 # 用户 myusers ，数据库 mydb ，本地数据库
 psql -U myusers -d mydb -h localhost
```









