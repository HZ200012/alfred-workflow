# aflred自用workflow推荐

###  ascii码转换

**需要php+zsh**

 可以实现字符和ascii码的相互转换，直接输入ascii+空格+关键字即可,关键字可以是字符或者是字符的ascii码。

![image-20220818180641184](https://raw.fastgit.org/huangzh1229/alfred-workflow/main/image/image-20220818180641184.png)

​						**字符转ascii码**

![image-20220818180829797](https://raw.fastgit.org/huangzh1229/alfred-workflow/main/image/image-20220818180829797.png)

​						 **ascii码转字符**





### hash算法

​	这个是我改了他人的hash算法workflow后使用的，原作者的地址在这<https://github.com/willfarrell/alfred-hash-workflow> 。

具体修改如下：

1. 将所有关键字去除，只留下hash

2. 把php运行方式改为zsh运行，因为macos monterey 去除了内置的php。

    

![image-20220818181901314](https://raw.fastgit.org/huangzh1229/alfred-workflow/main/image/image-20220818181901314.png)



## 查找文件路径

  将常用的文件或文件夹路径储存起来，当我们不记得文件路径时，输入关键字即可查找，回车后自动粘贴至剪切板。

>   例如，输入path brew，查询已经存储的与brew相关的路径。

![image-20220824180813283](https://raw.fastgit.org/huangzh1229/alfred-workflow/main/image/image-20220824180813283.png)

>   例如，输入path download，查询与所有download有关的路径。

![image-20220824181535333](https://raw.fastgit.org/huangzh1229/alfred-workflow/main/image/image-20220824181535333.png)



​	将常用文件路径储存起来，输入后回车运行脚本，运行结束后将在菜单栏显示本次操作的结果。请在设置-通知与专注模式-alfred-5中，允许其通知。

>   例如，输入   path add  github项目位置,github_file,/Users/huangzhuo/githubRepo

![image-20220824182507699](https://raw.fastgit.org/huangzh1229/alfred-workflow/main/image/image-20220824182507699.png)

![image-20220824182603989](https://raw.fastgit.org/huangzh1229/alfred-workflow/main/image/image-20220824182603989.png)

​	本workflow现在只有search和add功能，后面会添加modify和delete路径功能。

### 保存路径的储存格式

>   文件夹名称，文件夹唯一标识符，文件夹路径

​	文件夹名称：自己定义

​	文件夹唯一标识符：标识文件夹的唯一标识符，字符匹配时也会用到该字段，可以组合任意的关键字来确保查询结果符合你的预期，建议使用 _ 分割各关键字。

​    文件夹路径：不用解释

>     Example:  brew软件安装位置,`brew_software_file`,/opt/homebrew/Cellar





**日后还有自用workflow会在本项目下补充**





