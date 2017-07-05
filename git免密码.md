问题：在使用git代码仓库时，使用git clone 获取代码时，如果使用的是https协议，则在每次push时需要输入账号密码。

相关文档：文档一，文档二

验证了文档一种的方法二可用，记录一下

创建文件存储GIT用户名和密码， 在当前用户的根目录中文件名为.Git-credentials,* 用vim编辑此文件，输入内容格式：
vim .git-credentials
https://{username}:{password}@github.com
1
2
ps：（*windows一般为C:\users\Administrator，也可以是你自己创建的系统用户名目录，反正都在C:\users\中（Linux/mac在~/）。*）
    （由于在Window中不允许直接创建以”.”开头的文件，所以需要借助git bash进行，打开git bash客户端，进行%HOME%目录，然后用touch创建文件 .git-credentials,*）
1.2 添加Git Config 内容

输入如下命令（win中可以进入git bash终端）：

git config --global credential.helper store
1
–global 为全局属性，也可以不添加全局，相关配置说明 
执行完后查看用户目录下 .gitconfig文件，会多了一项：

$ cat ~/.gitconfig

[credential]
        helper = store
1
2
3
4
git push时不用再输入用户名和密码（如果还需要，可以重新开启git bash，或者重新打开ssh链接）

注：当用户名为邮箱时，需要把用户名的@转义为%40

ps：在写这篇博文的时候，又找到了官方的关于设置的文章（每一个工具或者技术，果然官方的文档才是最全的） 链接：

（中文） https://git-scm.com/book/zh/v2/Git-%E5%B7%A5%E5%85%B7-%E5%87%AD%E8%AF%81%E5%AD%98%E5%82%A8#_credential_caching
（英文）https://git-scm.com/book/en/v2/Git-Tools-Credential-Storage