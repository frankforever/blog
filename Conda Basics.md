# **Conda Basics**

`conda --version`

`conda update conda`

create new environment: name the environment snowflakes and install package biopython

`conda create --name snowflakes biopython`

remove environment:

`conda remove -n snowflakes --all`

activate new environment:

linux: `source activate snowflakes`

windows: `activate snowflakes`

list all environment:

`conda info --envs`

change back to default environment:

linux: `soucrce deactivate`



**Manage packages**

search package beautifulsoup4: `conda search beautifulsoup4`

install package beautifulsoup4: `conda install beautirulsoup4`

