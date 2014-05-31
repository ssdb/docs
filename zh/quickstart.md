# 快速安装
强烈推荐你把 SSDB 部署在 Linux 操作系统上.

不要在生产环境中使用 Windows 操作系统来运行 SSDB 服务器. 如果你确实必须使用 Windows 操作系统, 请在上面运行一个 Linux 虚拟机, 然后再让 SSDB 运行于这个虚拟机之中.

```
$ wget --no-check-certificate https://github.com/ideawu/ssdb/archive/master.zip
$ unzip master
$ cd ssdb-master
$ make
$ # 将安装在 /usr/local/ssdb 目录下
$ sudo make install
```

# 应用示例

php API 为例子

```
<?php
require_once('SSDB.php');
$ssdb = new SimpleSSDB('127.0.0.1', 8888);
$resp = $ssdb->set('key', '123');
$resp = $ssdb->get('key');
echo $resp; // output: 123
```