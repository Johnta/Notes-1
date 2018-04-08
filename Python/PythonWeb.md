`目录 start`
 
    - [Web](#web)
        - [Django](#django)

`目录 end` |_2018-04-08_| [码云](https://gitee.com/kcp1104) | [CSDN](http://blog.csdn.net/kcp606) | [OSChina](https://my.oschina.net/kcp1104)
****************************************

## Web
### Django
`python3.5 建立虚拟环境`
- `sudo apt install python3-venv`
- 在某目录 `python3 -m venv first_env`
- 激活环境 `source first_env/bin/activate`
    - 停用环境 `deactivate`
- 安装Django `pip install Django`
- 创建项目 `django-admin.py startproject first_pro . `
    - `ls first_pro`查看到创建的默认文件
- 创建SQLite数据库 `python manage.py migrate`    
- 启动项目`python3 manage.py runserver`
