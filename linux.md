### 1 查看当前目录下所有文件夹的大小
```shell
du -d 1 -h
```
-d 指深度，后面加一个数值  
文件夹会逐个罗列
### 2 判断Apk是否签名
用命令：
```
jarsigner -verify -verbose -certs <apk文件>
```
如果有 Android Debug 字样就是 debug

如果已经签名: [证书的有效期为xxx至xxx]
### 3 查找
#### 3.1 递归查看当前目录下存在指定字符串的文件
```shell
grep -rn '指定字符串' *
```
#### 3.2 查看当前目录下指定文件名
```shell
find . -name '文件名'
```
### 4 查看占用端口的程序
```shell
lsof -i:8009
```
上面👆的8009指的是端口号
### 5 运行 Jekyll
```shell
bundle exec jekyll serve -w
```
### 6 清空 shell history
```shell
history -c
```
如果提示你重启 terminal 才能生效，就重新打开一个 terminal 即可