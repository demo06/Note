# APP三合一物流宝功能梳理



## 模块

### 1. 登录模块

####  1.1 验证码登录

接口地址

```
https://wlbservicet.zgw.com/api/User/LoginByValidateCode
```

 - 获取验证码

   ```
   https://wlbservicet.zgw.com/api/User/SendVcode
   ```

#### 1.2 密码登录

```
https://wlbservicet.zgw.com/api/User/Login
```

#### 1.3 忘记密码

````
https://wlbservicet.zgw.com/api/User/FindPassword
````



#### 1.4 用户协议以及隐私协议

### 2. 货源模块

####  2.1 基础运单展示

```
https://wlbservicet.zgw.com/api/Statistics/Index
```

- 累计运单
- 累计路线
- 累计车辆
- 累计吨位

#### 2.2 物流宝使用手册

#### 2.3 弹窗

##### 2.3.1 发货地弹窗

```
https://wlbservicet.zgw.com/api/Company/GetProvince
```

##### 2.3.2收货地弹窗

```
https://wlbservicet.zgw.com/GetHistoryAddress
```

##### 2.3.3 筛选弹窗

- 车型

```
https://wlbservicet.zgw.com/GetVehicleType
```

- 装货时间

```
https://wlbservicet.zgw.com/GetSearchDate
```

- 车长

```
https://wlbservicet.zgw.com/GetVehicleLength
```

##### 2.3.4常跑路线弹窗

```
https://wlbservicet.zgw.com/GetRegularRouteListByUserId
```

##### 2.3.5 订单类型弹窗

##### 2.3.6 发布时间弹窗

#### 2.4 货源信息列表

接口地址

```
https://wlbservicet.zgw.com/GetOrderHallCompeleListNewForSelect
```

##### 2.4.1报价货源

- 物流单详情

  ```
  https://wlbservicet.zgw.com/GetGrabDetail
  ```

  - 物流单信息
    - 单号
    - 状态
    - 物流服务人
    - 联系方式
    
  - 运输信息
    - 发货地->收货地,重量,类型,车辆最低要求,运费付款方式,结算依据,装货时间,发布日期
    
  - 地址信息
    - 发货地
    
    - 收货地
    
  - 货物信息
    - 货主要求(走高速,需雨布,时效要求,司机五证齐全,装卸服务等)
    
  - 报价弹窗

    ```
    https://wlbservicet.zgw.com/UserQuoteInfo
    ```

    - 单价
    - 总价
    - 备注

##### 2.4.2 抢单货源

- 同上

### 3. 运单模块

#### 3.1 抢单管理

```
 https://wlbservicet.zgw.com/GetOrderHallAllist
```

 - 查看运输合同

```
https://wlbservicet.zgw.com/api/System/GetAgreeMentURL
```

 - 查看订单详情

```
https://wlbservicet.zgw.com/GetInfoCompeleByTaskIdAndUserId
```

#### 3.2 竞价管理

> 与抢单管理相同type=1

```
 https://wlbservicet.zgw.com/GetOrderHallAllist
```

##### 3.2.1再次报价

- 获取再次报价订单信息

```	
 https://wlbservicet.zgw.com/GetGrabDetail
```

- 提交报价

```
https://wlbservicet.zgw.com/UserQuoteInfo
```

##### 3.2.2 删除报价

```
https://wlbservicet.zgw.com/DeleteUserQuoteInfo
```

##### 3.2.3 指派车辆

```
https://wlbservicet.zgw.com/DeliveryTask
```

##### 3.2.4 物流单详情

  - 基本信息

```
https://wlbservicet.zgw.com/QuoteGetGrabDetail
```

  - 车辆信息列表

```
https://wlbservicet.zgw.com/GetDriverAndVehicleInfoList
```

  - 货物运输规范

####  3.3 搜索运单

``` 
https://wlbservicet.zgw.com/GetOrderHallAllist
```

##### 3.3.1 地区选择框(控件)

##### 3.3.2 时间选择框(控件)

### 4. 消息模块

- 获取消息列表

```
https://wlbservicet.zgw.com/api/PushMessages/PushMessagesList
```

#### 4.1 系统消息

> 消息类型 0

```
https://wlbservicet.zgw.com/api/PushMessages/PushMessagesList?PageIndex=1&PageSize=10&UserId=847&MessageType=0
```

-  全部标记已读
- 批量删除

#### 4.2 新订单发布消息

> 接口同上类型为9 MessageType=9

- 同上

#### 4.3 运单消息

> 接口同上类型为MessageType=45678

- 运单提醒消息列表(成功/失败/失效)

#### 4.4 审核消息

> 接口同上类型为MessageType=123

- 审核消息列表

### 5. 个人中心

#### 5.1 车主认证

- 基本信息
  - 个人姓名
  - 身份证号
- 实名认证
  - 身份证头像
  - 身份证国徽
  - 手持身份证

接口地址

```
https://wlbservicet.zgw.com/api/Certify/GetCertifyDetail?UserId=847
```

- 上传图片

```
https://wlbservicet.zgw.com/api/Company/UploadImage
```

- 提交认证

```
https://wlbservicet.zgw.com/api/Certify/ManageCertify
```

#### 5.2 车辆管理

##### 5.2.1 车辆信息列表

接口地址

```
https://wlbservicet.zgw.com/GetVehicleListByUserId
```

- 解绑驾驶员

  ```
  https://wlbservicet.zgw.com/DeleteBindDriverVehicle
  ```

- 删除车辆

  ```
  https://wlbservicet.zgw.com/DelVehicle
  ```

- 绑定驾驶员

  ```
  https://wlbservicet.zgw.com/BindDriverVehicle
  ```

- 查看车辆信息

  ```
  https://wlbservicet.zgw.com/VehicleDetailNew
  ```

##### 5.2.2 添加车辆基本信息

- 证件照上传
  - 行驶证主页(ORC识别)
  - 行驶证副页
  - 人车合影
  - 保险证照片
  
- 车辆信息
  - 车牌号码
  
  - 车长类型
  
    ```
    https://wlbservicet.zgw.com/GetVehicleLength
    ```
  
  - 车牌颜色
  
  - 能源类型
  
  - 环保标准
  
    ```
    https://wlbservicet.zgw.com/api/Company/GetTypeCodeList?CodeTypeId=10
    ```
  
  - 设置默认车辆
  
  - 运费收款账号
  
  - 车辆所有人(ORC)
  
  - 使用性质
  
  - 发证机关
  
  - 发证日期
  
  - 注册日期
  
  - 核定载重
  
  - 车辆总重量
  
  - 车架号
  
  - 提交信息
  
  ```
  https://wlbservicet.zgw.com/MangeVehicle
  ```
  
  

##### 5.2.3 搜索车辆信息

接口地址

> 建议与列表接口区分开

```
https://wlbservicet.zgw.com/GetVehicleListByUserId?UserId=847&PageIndex=1&PageSize=10&VehicleCondition=
```

####  5.3 司机管理

#### 5.3.1 司机信息搜索

> 搜索与列表接口相同建议区分开来

```
https://wlbservicet.zgw.com/DriverList?UserId=847&PageIndex=1&PageSize=10&DriveCondition=11
```

#### 5.3.2 司机信息列表

```
https://wlbservicet.zgw.com/DriverList
```

#### 5.3.3 添加司机信息

 - 证件照上传

    ```
   https://wlbservicet.zgw.com/ManageDriver
   ```
   
   - 驾驶证主页

   ```
   https://wlbservicet.zgw.com/api/Company/UploadImage
   ```
   
    - 驾驶证副页
    - 身份证人像照
    - 身份证国徽照
    - 上传手持身份证
    - 联系电话
    - 从业资格证号
    - 司机姓名(ORC识别)
    - 身份证号
    - 准驾车型(车型弹窗)
    - 发证机关
    - 有效期始(日期选择框)
   	- 有效期至(日期选择框)

#### 5.4 运费收款

#####  5.4.1 银行卡管理列表

- 银行卡列表

```
https://wlbservicet.zgw.com/WalletIndex
```

##### 5.4.2 编辑银行卡

- 获取银行代码列表

```
https://wlbservicet.zgw.com/api/Company/GetTypeCodeList
```

- 开户姓名
- 卡号
  - ORC识别拍照
- 银行卡(根据ORC自动识别银行)
- 身份证号
- 预留手机号
- 是否默认使用此卡
- 删除此卡

```
https://wlbservicet.zgw.com/DeleteWallet
```

- 提交审核

##### 5.4.3 添加银行卡

```
https://wlbservicet.zgw.com/ManageWallet
```

#### 5.5 常跑路线

- 常跑路线列表

```
https://wlbservicet.zgw.com/GetRegularRouteListByUserId
```

- 添加路线

  ```
  https://wlbservicet.zgw.com/MangeRegularRoute
  ```

  - 获取城市

  ```
  https://wlbservicet.zgw.com/api/Company/GetArea
  ```

  - 出发地弹窗
  - 目的地弹窗

- 删除路线

```
https://wlbservicet.zgw.com/DeleteRegularRoute
```

#### 5.6 客户服务

##### 5.6.1 客户服务热线

- 客户热线 0371-22-22988

#### 5.7 常见问题

#### 5.8 使用手册

#### 5.9 设置

- 设置密码

```
https://wlbservicet.zgw.com/api/User/SetUpPassword
```

- 检查更新
  - Bugly更新
- 清除缓存
- 隐私协议
- 关于
- 退出登录

#### 5.10 获取个人信息

接口地址

```html
https://wlbservicet.zgw.com/api/User/GetUserInfoById?UserId=847
```

#### 5.11 获取推送消息列表

接口地址

```
https://wlbservicet.zgw.com/api/PushMessages/PushMessagesList
```

### 6. 其他

#### 6.1 启动页

```
https://wlbservicet.zgw.com/api/System/LoadingImgList
```

