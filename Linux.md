1. **系统目录简介**

```
/                                       # 根目录，有且只有一个根目录
/root					# 系统管理员的目录
/home					# 存放个人数据，每个用户都有自己的用户目录(/home/用户名)
/bin					# 存放标准的linux工具，如 “ls”,“vi”等。通常来说，此目录已经包含在"path"系统环境变量里了
/etc					# 存放系统配置文件
/dev					# 存放与设备相关的文件(unix和linux系统均把设备当成文件)
/tmp					# 用于存放临时文件(即使程序运行时生成大量的临时文件，或用户对系统进行了错误的操作，文件系统的其他部分仍然是安全的)，系统会定期自动清理
/usr					# 存放软件的地方(/usr/bin存放程序,/usr/share存放共享数据,/usr/lib存放不能直接运行的但必须的函数库文件,/usr/local手动安装的软件)
/opt					# 存放可选的安装的软件(比如Beta版)
/media					# 用于挂载那些usb接口的设备


/boot					# 包含操作系统的内核和启动系统过程中所要用到的文件
/var/log				# 系统日志记录分区
/dev					# 存放设备文件
/sbin					# 存放标准系统管理文件
```

2. **GNU**

   - 编译 + 链接(一次性)

     ```shell
     gcc [文件名] -o [自定义生成文件名]
     gcc main.c -o main.out		      # 生成可执行文件可无后缀
     gcc main.c -o ./out/main.out      # 将可执行文件输出到其他目录
     ```

   - 若程序没有执行权限，可使用**sudo**命令增加权限

     ```shell
     sudo chomd 777 a.out
     ```

   - 编译(Compile)

     ```shell
     gcc -c [文件名]                     # 将main.c编译为main.o
     gcc -c [文件名] -o [目标文件名]       # 自定义目标文件名
     ```

     注 : 1. 微软编译器将生成 ".obj" 后缀的文件

     ​	   2. 通常情况下，默认的目标文件名和源文件名是一样的

   - 链接(Link)

     ```shell
     gcc [文件名]                        # 在gcc命令后面紧跟目标文件的名字
     gcc [文件名] -o [目标文件名]          # 自定义目标文件名
     ```

   - 编译流程

     + 将C语言源程序预处理，生成`.i`文件
     + 预处理后的.i文件编译成为汇编语言，生成`.s`文件
     + 将汇编语言文件经过汇编，生成目标文件`.o`文件
     + 将各个模块的`.o`文件链接起来生成一个可执行程序文件
     
   - GCC常用的编译选项

     | gcc编译选项        | 选项的意义                             |
     | ------------------ | -------------------------------------- |
     | -c                 | 编译、汇编指定的源文件，但是不进行链接 |
     | -S                 | 编译指定的源文件，但是不进行汇编       |
     | -E                 | 预处理指定的源文件，不进行编译         |
     | -o [file1] [file2] | 将文件 file2 编译成可执行文件 file1    |
     | -I directory       | 指定 include 包含文件的搜索目录        |
     | -g                 | 生成调试信息，该程序可以被调试器调试   |

     注：使用 -save-temps 选项 GCC  会正常的编译和链接，但是会把预处理器输出、汇编语言和对象文件全部存储在当前目录下

3. **解压命令**

   ```
   .tar 
   解包：tar xvf FileName.tar
   打包：tar cvf FileName.tar DirName
   （注：tar是打包，不是压缩！）
   ```
   
   ```
   .gz
   解压1：gunzip FileName.gz
   解压2：gzip -d FileName.gz
   压缩：gzip FileName
   ```

   ```
   .tar.gz 和 .tgz
   解压：tar zxvf FileName.tar.gz
   压缩：tar zcvf FileName.tar.gz DirName
   ```
   
   ```
   .bz2
   解压1：bzip2 -d FileName.bz2
   解压2：bunzip2 FileName.bz2
   压缩： bzip2 -z FileName
   ```

   ```
   .tar.bz2
   解压：tar jxvf FileName.tar.bz2
   压缩：tar jcvf FileName.tar.bz2 DirName
   ```
   
   ```
   .bz
   解压1：bzip2 -d FileName.bz
   解压2：bunzip2 FileName.bz
   压缩：未知
   ```

   ```
   .tar.bz
   解压：tar jxvf FileName.tar.bz
   压缩：未知
   ```

   ```
   .Z
   解压：uncompress FileName.Z
   压缩：compress FileName
   ```
   
   ```
   .tar.Z
   解压：tar Zxvf FileName.tar.Z
   压缩：tar Zcvf FileName.tar.Z DirName
   ```
   
   ```
   .zip
   解压：unzip FileName.zip
   压缩：zip FileName.zip DirName
   ```
   
   ```
   .rar
   解压：rar x FileName.rar
   压缩：rar a FileName.rar DirName
   ```
   
   ```
   .lha
   解压：lha -e FileName.lha
   压缩：lha -a FileName.lha FileName
   ```
   ```
   .rpm
   解包：rpm2cpio FileName.rpm | cpio -div
   ```
   
   ```
   .deb
   解包：ar p FileName.deb data.tar.gz | tar zxf -
   ```
   
   ```
   .tar .tgz .tar.gz .tar.Z .tar.bz .tar.bz2 .zip .cpio .rpm .deb .slp .arj .rar .ace .lha .lzh .lzx .lzs .arc .sda .sfx .lnx .zoo .cab .kar .cpt .pit .sit .sea
   解压：sEx x FileName.*
   压缩：sEx a FileName.* FileName
   ```

4. **Loading**