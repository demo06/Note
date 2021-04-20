# Selenium笔记

功能介绍

- 基于浏览器自动化的模块
- 弊端:效率低
- 在使用其他库无法抓取网页时可以使用selenium

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
#当通过find系列函数进行标签定位时,如果标签处于iframe下,则会定位失败
#解决方法:使用switch_to切换到iframe后在进行定位即可
bro.switch_to.frame('frameId')
#获取到frame下的标签
div_tag=bro.find_element_by_xpath('xpath语法')
```

动作链ActionChains

- 一系列连续的动作
- 例如图片验证码滑动

导入动作链

```python
from selenium.webdriver import ActionChains
```

使用

```python
action=ActionChains(bro)
#点击且长按
action.click_and_hold(div_tag)
#拖拽
for i in range(6):
    #perform让动作链立即执行
	action.move_by_offset(10,15).perform()
action.release()#释放action
```

如何规避检测selenium

- 使用selenium接管浏览器

  1.将driver所在目录添加到环境变量中

  2.打开CMD,输入如下命令

  ```
  chrome.exe --remote-debugging-port=9222 --user-data-dir="一个空文件夹目录"
  ```

  3.执行以下代码

  ```python
  from selenium import webdriver
  from selenium.webdriver.chrome.options import Options
  
  chrome_options=Options()
  chrome_options.add_experimental_option("debuggerAddress","127.0.0.1:9222")
  #本机安装好的driver驱动程序目录
  chrome_driver="驱动目录"
  browser =webdriver.Chrome(executable_path=chrome_dricer,chrome_options=chrome_options)
  ```

无头浏览器(无可视化界面的浏览器)

- 谷歌无头浏览器
- phantomJs

```python
#无头浏览器须增加以下参数
chrome_options.add_argument('--headless')
chrome_options.add_argument('--disable-gpu')
```

webdriver截图

```
browser.save_screenshot('jietu.png')
```

其他工具

```python
from PIL import Image
```

示例:使用selenium登录12306

- 使用selenium打开登录页面

  ```python
  bro=webdriver.Chrome(executable_path='./chromedriver')
  bro.get('12306登录地址')
  ```

- 对当前页面进行截图

  ```
  bro.save_screenshot('aa.png')
  ```

- 对当前图片局部区域(验证码图片)进行裁剪

- 确定验证码图片对应左上和右下的坐标

  ```python
  #找到验证码图片
  code_img_ele=bro.find_element_by_xpath('验证码xpath')
  #验证码图片左上角坐标
  location=code_img_ele.location  
  #获取图片大小
  size=code_img_ele.size
  #验证码图片左上角和右下角坐标
  rangle=(int(location['x']),int(location['y']),int(location['x'])+size['width'],int(location['y'])+size['height'])
  #至此验证码图片区域就确定下来了
  img=Image.open('./aa.png')
  code_img_name='code.png'
  #crop根据指定区域进行图片裁剪
  frame=i.crop(rangle)
  frame.save(code_img_name)
  ```

- 使验证码图片与模拟登录验证码图片--对应

- 使用超级鹰识别验证码图片(坐标)

- 使用ActionChains对每个元素对应的x,y指定位置进行点击操作

  ```python
  #将参照物移动到要点击的element的位置
  ActionChains(bro).move_to_element_with_offset(code_img_ele,x,y).click().perform()
  ```

  

