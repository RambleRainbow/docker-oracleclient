# docker-oracleclient
基于centos:7安装的ORACLE客户端程序(12.2.0.1.0版)
集成了
* **基础包**(oracle-instantclient12.2-basic-12.2.0.1.0-1.x86_64.rpm)
* **sqlplus**(oracle-instantclient12.2-sqlplus-12.2.0.1.0-1.x86_64.rpm)
* **data dump**(oracle-instantclient12.2-tools-12.2.0.1.0-1.x86_64.rpm)

## 使用说明
oracle的安装路径为/usr/lib/oracle/12.2/client64

### 构建新镜像，复制你自己的tnsname.ora
```
FROM warmworm/docker-oracleclient:7-12.2
COPY </your/path/to/tnsname.ora> /usr/lib/oracle/12.2/client64/lib/newwork/admin/tnsname.ora
```

### 运行容器

1. 独立运行
```
$~ docker run -it --rm warmworm/docker-oracleclient
$~ sqlplus <username>/<passwd>@<tns>
```
2. 直接运行
```
$~ docker run -it --rm warmworm/docker-oracleclient sqlplus <username>/<passwd>@<tns>
```
