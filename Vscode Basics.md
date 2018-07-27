# **Vscode Basics**

shift + alt + f: format document

ctrl + shift + b: build

[gcc编译指令](https://blog.csdn.net/zhuxiaoyang2000/article/details/5575194)

[task说明](https://code.visualstudio.com/docs/editor/tasks#vscode)

[debug说明](https://github.com/Microsoft/vscode-cpptools/blob/master/launch.md)

${workspaceRoot} 当前打开的文件夹的绝对路径+文件夹的名字

${workspaceRootFolderName}   当前打开的文件夹的名字

${file} 当前打开正在编辑的文件名，包括绝对路径，文件名，文件后缀名

${relativeFile} 从当前打开的文件夹到当前打开的文件的路径 

如 当前打开的是test文件夹，当前的打开的是main.c，并有test / first / second / main.c

那么此变量代表的是  first / second / main.c

${fileBasename}  当前打开的文件名+后缀名，不包括路径

${fileBasenameNoExtension} 当前打开的文件的文件名，不包括路径和后缀名

${fileDirname} 当前打开的文件所在的绝对路径，不包括文件名

${fileExtname} 当前打开的文件的后缀名

${cwd} the task runner's current working directory on startup

不知道怎么描述，这是原文解释，

跟 cmd 里面的 cwd 是一样的

${lineNumber}  当前打开的文件，光标所在的行数