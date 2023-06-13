# 创建项目
```
scrapy startproject <项目名字>

例如：
scrapy startproject myspider
```
这里会自动创建项目目录，然后会在项目目录下创建一个同名的目录，具体目录结构如下：
```
myspider/
├─── myspider
│     ├─── __init__.py
│     ├─── __pycache__
│     ├─── items.py
│     ├─── middlewares.py
│     ├─── piplines.py
│     ├─── settings.py
│     └─── spiders
│           ├─── __init__.py
│           └─── __pycache
└─── scrapy.cfg
```

# 创建爬虫
在项目目录下创建爬虫
```
scrapy genspider <爬虫名字> <允许爬取的域名>

例如：
cd myspider
scrapy genspider baidu baidu.com
```
这个命令会自动在spiders目录下创建对应名字的Python文件，目录如下：
```
myspider/
├─── myspider
│     ├─── __init__.py
│     ├─── __pycache__
│     ├─── items.py
│     ├─── middlewares.py
│     ├─── piplines.py
│     ├─── settings.py
│     └─── spiders
│           ├─── __init__.py
│           ├─── __pycache
│           └─── baidu.py
└─── scrapy.cfg
```

接下来只要修改baidu.py文件来进行相关解析操作就行了


# baidu.py中的注意事项
必须要有parse()方法，不然会报错，如果提示说xxx.parse()签名不匹配，只需要在括号里面加上", **kwargs"就可以了。
parse()方法返回必须使用 yield 返回，不能用 return
