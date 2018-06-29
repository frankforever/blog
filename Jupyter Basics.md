**Jupyter Basics**

Jupyter官网：[](https://jupyter.org)

用conda安装jupyter，方便管理，之后学一学conda管理。

Jupyter nbviewer：[](https://nbviewer.jupyter.org/)

Jupyter shortcut：

![notebook shortcut](C:\project\blog\assets\notebook_shortcuts_4_0.png)

python下使用 `？` 调取帮助

`!pwd `查看当前目录

`%history`查看调取的命令记录，`&history -n 1-5`查看最开始1-5条命令

IPython中有一些magic关键字，如果命令中包含magic关键字，则IPython自己处理，如不是，则由标准Python解释器处理。

关键字包括：

line magic:

`%alias  %alias_magic  %autocall  %automagic  %autosave  %bookmark  %cat  %cd  %clear  %colors  %config  %connect_info  %cp  %debug  %dhist  %dirs  %doctest_mode  %ed  %edit  %env  %gui  %hist  %history  %killbgscripts  %ldir  %less  %lf  %lk  %ll  %load  %load_ext  %loadpy  %logoff  %logon  %logstart  %logstate  %logstop  %ls  %lsmagic  %lx  %macro  %magic  %man  %matplotlib  %mkdir  %more  %mv  %notebook  %page  %pastebin  %pdb  %pdef  %pdoc  %pfile  %pinfo  %pinfo2  %popd  %pprint  %precision  %profile  %prun  %psearch  %psource  %pushd  %pwd  %pycat  %pylab  %qtconsole  %quickref  %recall  %rehashx  %reload_ext  %rep  %rerun  %reset  %reset_selective  %rm  %rmdir  %run  %save  %sc  %set_env  %store  %sx  %system  %tb  %time  %timeit  %unalias  %unload_ext  %who  %who_ls  %whos  %xdel  %xmode`

cell magic:

`%%!  %%HTML  %%SVG  %%bash  %%capture  %%debug  %%file  %%html  %%javascript  %%js  %%latex  %%markdown  %%perl  %%prun  %%pypy  %%python  %%python2  %%python3  %%ruby  %%script  %%sh  %%svg  %%sx  %%system  %%time  %%timeit  %%writefile`



IPython 支持多种语言输出：

`from IPython.display import (display, display_html, display_png, display_svg)`



The main idea of the first approach is that you have to implement special display methods when you define your class, one for each representation you want to use. Here is a list of the names of the special methods and the values they must return:

- `_repr_html_`: return raw HTML as a string

- `_repr_json_`: return a JSONable dict

- `_repr_jpeg_`: return raw JPEG data

- `_repr_png_`: return raw PNG data

- `_repr_svg_`: return raw SVG data as a string

- `_repr_latex_`: return LaTeX commands in a string surrounded by "$".

  

复杂输出：

```python
import json
import uuid
from IPython.display import display_javascript, display_html, display

class FlotPlot(object):
    def __init__(self, x, y):
        self.x = x
        self.y = y
        self.uuid = str(uuid.uuid4())
    
    def _ipython_display_(self):
        json_data = json.dumps(list(zip(self.x, self.y)))
        display_html('<div id="{}" style="height: 300px; width:80%;"></div>'.format(self.uuid),
            raw=True
        )
        display_javascript("""
        require(["//cdnjs.cloudflare.com/ajax/libs/flot/0.8.2/jquery.flot.min.js"], function() {
          var line = JSON.parse("%s");
          console.log(line);
          $.plot("#%s", [line]);
        });
        """ % (json_data, self.uuid), raw=True)

import numpy as np
x = np.linspace(0,10)
y = np.sin(x)
FlotPlot(x, np.sin(x))
```



命令行建立Jupyter notebook：`jupyter notebook --port 9999`

打开jupyter设置文档：`!jupyter --config-dir`

给notebook添加密码：

建立密码：

```python
from IPython.lib import passwd
password = passwd("secret")
password  #show password
```

在`ipython_notebook_config.py`中添加：

```python
# Password to use for web authentication
c = get_config()
c.NotebookApp.password = 
u'sha1:6c2164fc2b22:ed55ecf07fc0f985ab46561483c0e888e8964ae6'
```





**Something for markdown :**

for math：

$\int$

$$ \int_0^\infty f(\phi) \partial \phi$$

```python
#for python
print("hello")
```


**Something for Python**

**LibROSA**

LibROSA is a python package for music and audio analysis. It provides the building blocks necessary to create music information retrieval systems. 

[https://librosa.github.io/librosa/]()

有基于tensorflow实现的wavenet

[](https://github.com/librosa/librosa)

[](https://github.com/ibab/tensorflow-wavenet)

[](https://nbviewer.jupyter.org/github/librosa/librosa/blob/master/examples/LibROSA%20demo.ipynb)