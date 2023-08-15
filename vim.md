### 1 文件内全部替换
```shell
:%s#change_cotent_before#change_content_after#g
```
### 2 文件内局部替换
把 10 行到 50 行内的 change_cotent_before 全部替换成 change_content_after
```shell
:10,50s#change_cotent_before#change_content_after#g
```
以上命令如果在g后面再加上c，则会在替换之前显示提示符给用户确认（confirm）是否需要替换。 比如
```shell
:%s#change_cotent_before#change_content_after#gc
```
