# Scrapy框架笔记

功能介绍

- 集成了很多功能且具有很强的通用性
- 专门用于异步爬虫的框架
- 高性能数据解析,请求发送,持久化存储,全站数据爬取,中间件,分布式等

安装

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

基础使用

- 创建一个工程:

  ```
  scrapy startproject ProName
  ```

  - 目录结构
    - spiders:爬虫文件夹
      - 必须要存放一个爬虫源文件
    - settings.py 工程配置文件





# 看到这里了

[Python爬虫小白到大神-爬虫+反爬虫（各种网站数据爬取）完整版_哔哩哔哩 (゜-゜)つロ 干杯~-bilibili](https://www.bilibili.com/video/BV15b4y1979e?p=21&spm_id_from=pageDriver)

16:40