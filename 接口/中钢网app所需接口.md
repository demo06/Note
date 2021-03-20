# 中钢网APP二期需求所需接口

## 1.接口列表
+ [**获取交易列表接口**](#2.获取交易列表接口)

+ [**获取交易详情接口**](#3.获取交易详情接口)


## 2.获取交易列表接口


### 2.1 接口名称
```
(GET)
api/Account/getTradingRecordList
```

### 2.2 请求参数
| 参数名称        | 参数类型 | 描述                          |
|:----------------|:---------|:------------------------------|
| memberID        | int      | 用户ID                        |
| companyID       | int      | 企业ID                        |
| transactionType | int      | 交易类型 0-全部 1-充值 2-交易 |
| transactionTime | date     | 交易日期                      |
| pageSize        | int      | 条数                          |
| pageIndex       | int      | 页码                          |
### 2.3 响应参数
| 参数名称        | 参数类型 | 描述                    |
|:----------------|:---------|:------------------------|
| tradingMonth    | date     | 交易月份                |
| incomeAmount    | double   | 收入                    |
| payAmount       | double   | 支出                    |
| transactionlist | list     | 交易列表                |
| --- id          | int      | 交易列表                |
| ---dealTime     | String   | 成交时间                |
| ---dealType     | int      | 交易类型  0-充值 1-交易 |
| ---amount       | String   | 金额                    |
### 2.3.1 响应示例
```
{
  "statuscode": 200,
  "result": 0,
  "msg": "获取成功",
  "data": {
      "tradingMonth":2020-08
      "incomeAmount":5553.65,
      "payAmount":1000.23,
      "transactionlist": [
                {
                    "id":1001
                    "dealtime":2020-08-12 11:15:03,
                    "dealType":0,
                    "amount":"+1000.00",
                },
                {
                    "id":1002
                    "dealtime":2020-08-12 11:15:03,
                    "dealType":1,
                    "amount":"-1000.00",
                },
              ]
        
          }
}
```

## 3.获取交易详情接口


### 3.1 接口名称
```
(GET)
api/Account/getTradingDetail
```

### 3.2 请求参数
| 参数名称      | 参数类型 | 描述   |
|:--------------|:---------|:-------|
| memberID      | int      | 用户ID |
| transactionID | int      | 交易ID |
### 3.3 响应参数
| 参数名称    | 参数类型 | 描述                        |
|:------------|:---------|:----------------------------|
| dealType    | int      | 交易类型      0-充值 1-交易 |
| dealDate    | date     | 交易时间                    |
| dealAmount  | String   | 成交金额                    |
| dealState   | String   | 交易状态                    |
| productName | String   | 产品名称                    |
| supperlier  | String   | 供应商名称                  |
| payment     | String   | 支付方式                    |
| dealOrderId | int      | 交易单号                    |
### 3.3.1 响应示例
```
{
  "statuscode": 200,
  "result": 0,
  "msg": "获取成功",
  "data": {
      "dealType":1
      "dealDate":2021-03-07 09:43:36,
      "dealAmount":"-50400.00",
      "dealState":"付款完成",
      "productName":"螺纹钢、盘螺",
      "supperlier":"中钢网自营官方旗舰店",
      "payment":"余额支付",
      "dealOrderId":20212226700028,
}
```