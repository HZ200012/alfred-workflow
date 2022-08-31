[toc]

# aflred自用workflow推荐

##  ascii码转换

**需要php+zsh**

 可以实现字符和ascii码的相互转换，直接输入ascii+空格+关键字即可,关键字可以是字符或者是字符的ascii码。

![image-20220818180641184](https://raw.fastgit.org/huangzh1229/alfred-workflow/main/image/image-20220818180641184.png)

​																		字符转ascii码

![image-20220818180829797](https://raw.fastgit.org/huangzh1229/alfred-workflow/main/image/image-20220818180829797.png)

​																		ascii码转字符





## hash算法

​	这个是我改了他人的hash算法workflow后使用的，原作者的地址在这<https://github.com/willfarrell/alfred-hash-workflow> 。

具体修改如下：

1. 将所有关键字去除，只留下hash

2. 把php运行方式改为zsh运行，因为macos monterey 去除了内置的php。

    

![image-20220818181901314](https://raw.fastgit.org/huangzh1229/alfred-workflow/main/image/image-20220818181901314.png)



## 查找常用路径

  将常用的各类路径储存起来，包括文件，文件夹，甚至网络路径，当我们不记得路径时，输入关键字即可查找，回车后自动粘贴至剪切板。

​	除了查找之外，通过输入path open key，将查找出来的路径直接在finder中打开。

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

以文件夹为例：

>   文件夹名称，文件夹唯一标识符，文件夹路径

​	文件夹名称：自己定义

​	文件夹唯一标识符：标识文件夹的唯一标识符，字符匹配时也会用到该字段，可以组合任意的关键字来确保查询结果符合你的预期，建议使用 _ 分割各关键字。

​    文件夹路径：不用解释

>     Example:  brew软件安装位置,brew_software_file,/opt/homebrew/Cellar



​	这个workflow并不与alfred本身的文件查找和spotlight的查找冲突，有些常用的东西并不能直接通过路径查找出来，需要我们进行记录，就像上面的brew中的软件安装地址一样。这个workflow可以很好的与alfred互补使用，除了存储路径之外，还可以储存其他内容（暂时没想到）。如果有其他建议，请与我联系。



## 常用快捷键记录

 又来写workflow了，这次的workflow主要记录常用的快捷键，可以将任何常用的快捷键记录进去并查看。这次和以后都不放截图了，太麻烦了，介绍用法和信息。

1. 文件

	> shorcutKey:快捷键文件，以json字符形式储存。config为配置信息，配置信息可以自行修改，但是格式必须按照**{"配置内容":"True/False","comment":"配置内容解释"}**的格式编写，配置内容的value值只能为True或者False。icon为快捷键和图标映射，剩下的就是存放各个软件甚至某一方面的常用快捷键。

	```json
	{
	    "config": [
	        {"isIcon": "False", 
	         "comment": "是否在显示时用图标替换快捷键，默认不开启"
	        }],
	    "icon": 
	    	{"control": "⌃", 
	         "command": "⌘ ", 
	         "option": "⌥ ", 
	         "delete": "⌫ ", 
	         "enter": "⏎", 
	         "shift": "⇧ "}, 
	    "idea": 
	        {"复制": "command+C", 
	         "粘贴": "command+V", 
	        }, 
	    "mac": 
	        {"mac表情": "control+command+space"
	        }
	}
	```

2. > main.py:查询快捷键的文件。 
	>
	> showConfig.py:显示配置信息。
	>
	> config.py：进行配置。
	>
	> add.py: 新增或修改快捷键。
	>
	> log:把每一次新增或修改记录成日志

2. 使用<br> 输入key 软件名称，查询某个软件的所有常用快捷键，如key idea 查询与idea相关的所有常用快捷键。如果要查看某一类比如与查找有关的快捷键，可以输入key idea，查找<br>

	输入key config，显示所有的配置信息，方向键选择其中一个回车就可以改变其配置，因为配置只有true或者false，所以配置内容只能二选一。

	输入 key add 软件名，快捷键名称，快捷键，即可新增常用快捷键或者修改已有的快捷键，每一次都会被记录到日志中。 比如： key add mac,全屏截图,shift+command+3

3. 其他
	+ 还有一些需要完善的地方，比如检测输入的键位是否正确如shift打成shirt，config文件也需要修改，可以改成name:配置内容，value：值，comment：注释的格式，这样配置就能更多样化。还有一些没想到，这些想到了的暂时不弄，麻烦。

​			



**日后还有自用workflow会在本项目下补充，联系邮箱：huangzh1229@163.com**





