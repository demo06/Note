# Scrapy框架笔记

## 功能介绍

- 集成了很多功能且具有很强的通用性
- 专门用于异步爬虫的框架
- 高性能数据解析,请求发送,持久化存储,全站数据爬取,中间件,分布式等

## 安装

 1.mac,linux

```
pip install scrapy
```

2.windows

​	1.安装wheel

```python
pip install wheel
```

​	2.下载twisted文件

> twisted是一个异步框架,scrapy框架用来做异步请求 

```html
https://www.lfd.uci.edu/~gohlke/pythonlibs/#twisted
```

​	3.进入下载目录执行

```python
pip install Twisted‑20.3.0‑cp39‑cp39‑win_amd64.whl
```

​	4.安装pywin32

```python
pip3 install pywin32
```

​	5.安装scrapy

```python
pip3 install scrapy
```

cmd中输入scrapy按下回车,如果没有报错说明安装成功

## 基础使用

- 创建一个工程:

  ```
  scrapy startproject ProName
  ```

  - 目录结构
    - spiders:爬虫文件夹
      - 必须要存放一个爬虫源文件
    - settings.py 工程配置文件

- 根据提示内容 进入到项目目录  cd projectName

  > 命令行操作

- 创建爬虫文件

  > scrapy genspider spiderName www.xxx.com(随便跟一个Url,后面可以改)

  - 编写爬虫文件

- 执行工程

  > scrapy crawl spiderName(爬虫名称)

  - 执行工程后,默认输出工程所有日志信息
  - 指定类型日志的输出
    - 修改项目目录下settings.py文件下:
      - LOG_LEVEL ='ERROR' 	#设置日志输出级别

- 生成的爬虫文件描述

  ```python
  import scrapy
  
  class LearnscrapySpider(scrapy.Spider):
      #爬虫文件名称:当前源文件的唯一标识
      name = 'learnScrapy'
      #允许的域名,相当于白名单,一般不用
      allowed_domains = ['example.com']
      #起始的URL列表:只可以存储url
      #作用:列表中存储的url都会被进行get请求的发送
      start_urls = ['http://example.com/']
  
      #数据解析
      #parse方法调用的次数完全取决于请求的次数
      #response: 表示的就是服务器返回的响应对象
      def parse(self, response):
        pass
  ```
  

- 数据解析(接上面)

  ```python
     def parse(self, response):
    		div_list=response.xpath('xpath路径')
          for div in div_list:
              #xpath 解析出来的是Selector对象,所需数据保存在该对象的data属性中
              title =div.xpath('./div[1]/h1/a/text()')[0]
              content =div.xpath('./div[2]/p/a/text()')[0]
              #将Selector对象 data属性值取出使用 extract(),但是一般不用
              title =div.xpath('./div[1]/h1/a/text()')[0].extract()
              content =div.xpath('./div[2]/p/a/text()')[0].extract()
               #下面方法取出来的是个数组
              title =div.xpath('./div[1]/h1/a/text()').extract()
              content =div.xpath('./div[2]/p/a/text()').extract()
              #一般用这个
              title =div.xpath('./div[1]/h1/a/text()').extract_first()
              content =div.xpath('./div[2]/p/a/text()').extract_first()
  ```

  