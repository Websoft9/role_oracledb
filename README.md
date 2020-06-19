Ansible Role: oracle
=========

本 Role 在CentOS或者oraclelinux服务器上安装和配置 oracle。

## Requirements

运行本 Role，请确认符合如下的必要条件：

| **Items**      | **Details** |
| ------------------| ------------------|
| Operating system | CentOS7.x OracleLinux7.x|
| Python 版本 | Python2  |
| Python 组件 |    |
| Runtime |  |


## Related roles

本 Role 在语法上不依赖其他 role 的变量，但程序运行时需要确保已经运行：common。以 oracle 为例：

```
  roles:
   - {role: role_common, tags: "role_common"}   
   - {role: role_cloud, tags: "role_cloud"}
   - {role: role_oracle, tags: "role_oracle"}
```


## Variables

本 Role 主要变量以及使用方法如下：

| **Items**      | **Details** | **Format**  | **是否初始化** |
| ------------------| ------------------|-----|-----|
| oracle_version | [ 18c, 19c ] | 字符串 |是|
| oracle_password | [ "123456"] | 字符串 |是|


注意：
1. mysql_version, oracle_password  的值在 mysql.yml 中由用户选择输入；

## Example

```
#1 create database wordpress and user wordpress
mysql_databases:
 - name: wordpress
   encoding: utf8
 
mysql_users:
 - name: wordpress
   host: localhost
   priv: 'wordpress.*:ALL'

#2 create database wordpress,joomla and user wordpress,joomla
mysql_databases:
 - name: wordpress
   encoding: utf8
 - name: joomla
   encoding: utf8
 
mysql_users:
 - name: wordpress
   host: localhost
   priv: 'wordpress.*:ALL'
 - name: joomla
   host: localhost
   priv: 'joomla.*:ALL'
```
## FAQ
