gologer
————
##简介 
gologer 是一个C语言版nginx/apache日志分析工具，

##安装
Centos

```
  yum install gcc.x86_64 glib2-devel.x86_64
  gcc -o gologer gologer.c  -I/usr/include/glib-2.0 -I/usr/lib64/glib-2.0/include   -lglib-2.0
```
Ubuntu

```
sudo apt-get install libglib2.0-dev
  gcc -o gologer gologer.c  -I/usr/include/glib-2.0 -I/usr/lib64/glib-2.0/include   -lglib-2.0
````


valgrind --tool=memcheck --leak-check=yes --leak-check=full --show-reachable=yes -v  ./gologer t.log 

## 使用方法

``` 
  ./gologer log_file 
  cat log_file | ./gologer 

  The following options can also be supplied to the command:

      -f <argument>  log_format, such as: %h %^ %^ [%d %^] \"%r\" %s %b \"%R\" \"%^\" \"%^\" %t
      -d <argument> - date_format, such as: %Y-%m-%d or %d/%b/%Y:%H:%M:%S 
      -u <argument>   S or M or H .
      -t <argument>   html
      -h              html
      ./gologer [ -f log_format][ -d date_format ][ -u time_unit ] [-t html] log_file 

  Output:
      result_20130705_114714.txt or result_20130705_114714.html
```