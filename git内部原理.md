### .git目录结构
1. objects/  
存储所有数据内容
1. index  
保存了暂存区域信息
1. refs/  
存储指向数据 (分支) 的提交对象的指针
1. HEAD  
文件指向当前分支
1. config  
项目特有的配置选项
1. description  
仅供 GitWeb 程序使用
1. branches/  
新版本不再使用
1. hooks/  
保存了客户端或服务端钩子脚本
1. info/  
保存了一份不希望在 .gitignore 文件中管理的忽略模式 (ignored patterns) 的全局可执行文件

### objects文件夹
1. 存储所有数据内容，即需要版本控制的内容。
1. 共三种object类型：
    1. blob类型，对应普通文件  
       git-cat-file -p输出文件内容
    1. tree类型，对应文件夹  
       git-cat-file -p输出该tree对象包含的其他tree对象和blob对象，具体信息有：权限模式，对象类型，hash地址，文件名
    1. commit类型，对应一次提交  
       git-cat-file -p输出对应快照的顶层tree对象的hash地址，以及作者／提交者信息，时间戳信息，提交注释信息  
       除了第一次提交，后续提交还会包含一个parent commit的地址，从而形成历史记录
1. 头部信息格式
    1. content = "what is up, doc?"  
       原始内容
    1. header = "blob #{content.length}\0"  
       头部信息格式
    1. store = header + content  
       实际存储的内容
    1. sha1 = Digest::SHA1.hexdigest(store)  
       计算hash地址
    1. zlib_content = Zlib::Deflate.deflate(store)  
       压缩存储数据

1. echo 'test content' | git hash-object -w --stdin  
-w 表示存储数据，默认是只返回hash串  
--stdin 表示从标准输入接受数据，否则必须提供一个文件路径  
这条命令返回40个字符的校验和（存储的内容和一些头部信息）
1. git hash-object -w /tmp/hello.txt  
存储一个文件
1. find .git/objects -type f  
查看objects目录，此时应该可以找到一个文件
1. git cat-file -p `hash`  
查看内容
1. git cat-file -t `hash`  
查看类型：blob，tree，commit

### index文件
1. git ls-files --stage  
显示index文件内容  
100644 da0f8ed91a8f2f0f067b3bdf26265d5ca48cf82c 0	a.txt  
100644 c9c6af7f78bc47490dbf3e822cf2f3c24d4b9061 0	b.txt  

### refs文件夹
1. 创建或更新引用，其实就是hash的别名，这也是分支的概念  
git update-ref refs/heads/master hash  
echo hash > .git/refs/heads/master  

### HEAD文件
1. cat .git/HEAD  
输出：`ref: refs/heads/master`
1. git checkout test  
再次查看HEAD文件：`ref: refs/heads/test`
1. git symbolic-ref HEAD  
查看当前HEAD：`refs/heads/test`
1. git symbolic-ref HEAD refs/heads/master  
设置HEAD为新的地址

### 命令解释
1. git add
1. git commit
1. git checkout
1. git reset
1. git reset --soft
1. git reset --hard
1. git log
1. git rebase
1. git merge


find .git/objects
find .git/objects -type f
echo 'test content' | git hash-object -w --stdin
git hash-object -w test.txt
git cat-file -p d670460b4b4aece5915caf5c68d12f560a9fe3e4
git cat-file -t 1f7a7a472abf3dd9643fd615f6da379c4acb3e3a
