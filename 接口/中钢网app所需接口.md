#中钢网APP二期需求所需接口

##1.获取交易明细接口


###1.1 接口名称
```
(GET)
api/Account/getTradingRecordList
```

###1.2 请求参数
| 参数名称        | 参数类型 | 描述                          |
|:----------------|:---------|:------------------------------|
| memberID        | int      | 用户ID                        |
| companyID       | int      | 企业ID                        |
| transactionType | int      | 交易类型 0-全部 1-充值 2-交易 |
| transactionTime | date     | 交易日期                      |
| pageSize        | int      | 条数                          |
| pageIndex       | int      | 页码                          |
### 1.3 响应参数
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
### 1.3.1 响应示例
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