
## 合约量化框架
    异步事件驱动的高频交易系统。适合做市商、高频量化用户使用；
   ### 1、行情模块
    ws订阅orderbook、kline、tradedetail等公开行情数据，提供回调给策略使用；
   ### 2、RESTAPI模块
    火币合约的 rest API接口方法实现，供策略使用，目前已接入永续合约；
   ### 3、资产模块
    资产模块通过ws订阅account来实现资产的推送及更新，提供回调给策略使用；
   ### 4、仓位模块
    仓位模块通过ws订阅position来实现持仓的推送及更新，提供回调给策略使用；
   ### 5、订单模块
    订单模块通过ws订阅order来实现订单的推送及更新，提供回调给策略使用；
   ### 6、日志模块
    日志模块可以根据不同等级错误来记录log到文件；
   ### 7、下单模块
    集成常用下单功能接口；
   ### 8、错误处理模块
    websocket断连重连机制、心跳heartbeat机制等常见错误处理机制；
   ### 9、风控处理模块
    支持钉钉短信报警;
    
## 安装环境
    python:python 3.5.3以上版本。
    git clone
    pip install -r requirements.txt
## Demo使用示例

本示例策略简单实现了在火币永续合约(HBDM)交易所的`BTC-USD`进行卖空平空的操作。 

> NOTE: 示例策略只是简单演示本框架的使用方法，策略本身还需要进一步优化。


#### 推荐创建如下结构的文件及文件夹:
```text
ProjectName
    |----- docs
    |       |----- README.md
    |----- alpha
    |----- scripts
    |       |----- run.sh
    |----- config.json
    |----- main.py
    |----- strategy
    |      |----- strategy1.py
    |      |----- strategy2.py
    |      |----- ...
    |----- .gitignore
    |----- README.md
```

#### 策略服务配置

策略服务配置文件为 [config.json](config.json)，其中:

- ACCOUNTS `list` 策略将使用的交易平台账户配置；
- strategy `string` 策略名称
- symbol `string` 策略运行交易对
- MARKETS `list` 策略使用的行情配置

> 服务配置文件使用方式: [配置文件](/docs/config/README.md)


#### 运行

```text
python main.py config.json
```

## 功能意见征集及BUG反馈

issue区发帖提问，请务必贴上完整描述以及完整log。

## 参考
TheNextQuant

