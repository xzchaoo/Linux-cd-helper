# Linux cd命令行小工具 #
## 简介 ##
用于帮助你记录 Linux 下的一些路径, 方便你在命令行下进行目录的切换
1. 在 Linux 下进行工作目录的切换是使用 cd 命令.
2. 虽然有自动补全, 但是要在多个目录切来切去还是挺麻烦的.
3. 模仿 .bash_history, 它用于保存在终端输入的历史记录
4. 在当前用户的家目录里产生一个文件, 用于保存用户收藏的工作目录列表

## 命令 ##
1. eaa : 将当前的工作目录(通过pwd命令获得) 加入到工作目录列表尾
2. ea : 列出当前的工作目录列表
3. ea n : 它会返回一个字符串, 形如 "cd /usr/local/src", n表示是第几个工作目录
4. ead n : 删除第n个工作目录

## 例子 ##
1. ea
	1. 显示空
2. cd /usr/local/src
3. eaa
	1. 将当前目录加入到目录列表
4. ea
	1. 将会显示 "1. /usr/local/src"
5. cd /home
6. eaa
	1.  将当前目录加入到目录列表
7. ea
	1. 将会显示 "1. /usr/local/src \n 2. /home"
8. ea 1
	1. 将会返回字符串 "cd /usr/local/src"
9. \`ea 1'
	1. 上面就是2个反引号
	2. 这将会使得bash执行 "cd /usr/local/src" 命令
	3. 然后工作目录就切换到了 /usr/local/src 了
10. ead 1
	1. 从列表中删除第一个工作目录 即 /usr/local/src
11. ea
	1. 显示 "1. /home"

# 安装 #
将 ea eaa ead 放入 $PATH 指定的任意一个目录中, 比如 /usr/local/bin
添加可执行权限

# LICENSE #
```
Copyright [2015] [xzchaoo(70862045@qq.com)]

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.```
See the License for the specific language governing permissions and
limitations under the License.
```