#selenium笔记

功能介绍

- 基于浏览器自动化的模块
- 弊端:效率低

安装

```python
pip install selenium 
```

导入包

``` python
from selenium import webdriver
```

基础使用

```python
#基于浏览器的驱动程序实例化一个浏览器对象
bro=webdriver.Chrome(executable='./chromedriver(驱动地址)')
#对目标网站发起请求
bro.get('https://www.baidu.com(目标网站地址)')
#标签定位
search_et=bro.find_element_by_xpath('标签xpath路径')
search_et.send_keys('录入数据')
#文字定位
tv=bro.find_element_by_link_text('文本内容')[0]
tv.click()
#文字定位
tv=bro.find_element_by_class_name('class名')[0]
tv.click()
#按钮定位
btn=bro.find_element_by_id('按钮id')
btn.click()
#当前页面向下滑动操作(执行js操作:js注入)
bro.execute_script('window.scrollTo(0,document.body.scrollHeight)') 
#获取当前页面源码数据
page_text=bro.page_soure#当前页面所有源码数据
```

动作链ActionChains

- 在使用其他库无法抓取网页时可以使用selenium
- 一系列连续的动作
- 例如图片验证码滑动

```python

```

