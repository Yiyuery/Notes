# 常用的工具软件


## 在Linux上操作压缩文件的命令
> Linux默认自带ZIP压缩，最大支持4GB压缩，RAR的压缩比大于4GB.

### tar 归档 打包

`tar`
`这五个是独立的命令，压缩解压都要用到其中一个，可以和别的命令连用但只能用其中一个。`
- c: 打包 压缩
- x：解压
- t：查看内容 不解压
- r：向压缩归档文件末尾追加文件
- u：更新原压缩包中的文件
***
`下面的参数是根据需要在压缩或解压档案时可选的。`
- z：有gzip属性的
- j：有bz2属性的
- Z：有compress属性的
- v：显示所有过程
- O：将文件解开到标准输出
***
- `-v 可选` 将压缩或解压的过程输出
- `-f是必须的,-f: 使用档案名字，切记，这个参数是最后一个参数，后面只能接文件或目录`

***
- `tar -rf all.tar *.gif`这条命令是将所有.gif的文件增加到all.tar的包里面去。
- `tar -uf all.tar logo.gif`这条命令是更新原来tar包all.tar中logo.gif文件，
- `tar -tf all.tar` 这条命令是列出all.tar包中所有文件，
- `tar -xf all.tar` 这条命令是解出all.tar包中所有文件，
    - `-u`是表示更新文件的意思。
    - `-r`是表示增加文件的意思。
    - `-t`是列出所有文件的意思
    - `-x`是解压的意思
    - `-p` 保留绝对路径符
 
- 保留文件属性和跟随链接， -p 保留属性 -h 备份的源文件而不是链接本身
    - `tar -cphf etc.tar /etc`

********************

#### 压缩
- tar -cvf a.tar *.txt
    - z tar.gz
    - j tar.bz2
    - Z tar.Z
    - J tar.xz

- `tar -cvf jpg.tar *.jpg` //将所有jpg打包成tar.jpg 
- `tar -czf jpg.tar.gz *.jpg `  //将所有jpg打包成jpg.tar后 生成gzip压缩的包，命名为jpg.tar.gz
- `tar -cjf jpg.tar.bz2 *.jpg `//将所有jpg打包成jpg.tar后 生成bzip2压缩的包，命名为jpg.tar.bz2
- `tar -cZf jpg.tar.Z *.jpg ` //将所有jpg打包成jpg.tar后 生成umcompress压缩的包，命名为jpg.tar.Z

******

- `rar a jpg.rar *.jpg` //rar格式的压缩，需要先下载rar for linux

******

- `zip jpg.zip *.jpg` //zip格式的压缩，需要先下载zip for linux
- `zip -r file.zip code/*` 压缩code目录下所有文件
    - `-q 终端不输出` `-o 输出文件`  `-r 表示递归` `-l 兼容Windows的换行符`
    - -e 加密 

#### 解压

- `tar -xvf file.tar` //解压 tar包
- `tar -xzvf file.tar.gz` //解压tar.gz
- `tar -xjvf file.tar.bz2`   //解压 tar.bz2
- `tar -xZvf file.tar.Z `  //解压tar.Z
***
- `unrar e file.rar` //解压rar
***
- `unzip file.zip `//解压zip
    - -q 终端不输出 -d 指定目录 -l 查看不解压 -O 指定编码


#### 总结
```
    *.tar 用 tar -xvf 解压
    *.gz 用 gzip -d或者gunzip 解压
    *.tar.gz和*.tgz 用 tar -xzf 解压
    *.bz2 用 bzip2 -d或者用bunzip2 解压
    *.tar.bz2用tar -xjf 解压
    *.Z 用 uncompress 解压
    *.tar.Z 用tar -xZf 解压
    *.rar 用 unrar e解压
    *.zip 用 unzip 解压
```

*******************************************************************

## sdkman的使用 
`安装`
- 安装sdkman `curl -s "https://get.sdkman.io" | bash`
- 遇到提示zip 就是需要安装zip `sudo apt install zip` 然后重新执行命令
- 执行脚本：`source "/home/kuang/.sdkman/bin/sdkman-init.sh"` 或者重启终端就可以使用 `sdk` 了
- 查看sdkman 版本 ：`sdk version`

`使用`
> [详情见官网](http://sdkman.io/usage.html)

- 查看所有 `sdk list`
    - 查看某sdk的版本 `sdk list java ` 
- 不指定版本就是安装最新版 `sdk install java` 
- 指定默认版本 `sdk default java 8u131-zulu`
- 开始使用指定版本(for the current shell only) `sdk use scala 2.12.1`
- 查看当前版本 `sdk current java`
- 验证是否成功：`java -version`
- 移除 `sdk uninstall scala 2.11.6`

***************************
## 文本编辑器
### Kate
- [安装markdown预览插件](https://github.com/antonizoon/kate-markdown)

### sublime 
- 如果出现小bug，就直接删除 ～.config 下的 sublime文件夹注意注册证书拷出来
- 

### vi/vim
- `i` 进入编辑
- `:wq` 保存退出，注意是英文的 `:`才可以退出

### gedit
- 安装markdown预览插件 