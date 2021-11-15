---
title: 获取成交记录
position_number: 12
type: get
description: /trade/api/v1/myTrades
parameters:
-
    name: accesskey
    type: string
    mandatory: true
    default: N/A
    description: 访问密钥
    ranges:
-
    name: nonce
    type: integer
    mandatory: true
    default: N/A
    description: 13位毫秒数
    ranges:
-
    name: market
    type: string
    mandatory: true
    default: N/A
    description: 交易市场
    ranges: btc_usdt, eth_usdt...
-
    name: fromId
    type: string
    mandatory: false
    default: N/A
    description: 最后一笔成交ID，往后翻页时提供
    ranges:
-
    name: limit
    type: integer
    mandatory: false
    default: N/A
    description: 每页大小,默认200
    ranges:
-
    name: startTime
    type: integer
    mandatory: false
    default: N/A
    description: 开始时间，13位毫秒数
    ranges:
-
    name: endTime
    type: integer
    mandatory: false
    default: N/A
    description: 截止时间，13位毫秒数
    ranges:
content_markdown:
left_code_blocks:
-
    code_block:
    title:
    language:
right_code_blocks:
-
    code_block: "{\r\n    \"code\": 200,\r\n    \"data\": [\r\n        {\r\n            \"id\": \"6821734611983271937\",        // 成交ID，翻页时，提供此ID\r\n            \"orderId\": \"6821734611950127105\",   // 订单ID\r\n            \"time\": 1626428273000,              // 成交时间\r\n            \"price\": \"10.3998\",                 // 成交价格\r\n            \"amount\": \"1\",                      // 成交数量\r\n            \"value\": \"10.3998\",                 // 成交金额\r\n            \"type\": 1,                          // 类型[0=卖;1=买]\r\n            \"entrustType\": 1,                   // [0=现价;1=市价]\r\n            \"isLever\": 0,                       // 是否杠杆[1=是;0=否]\r\n            \"fee\": \"0.01663968\",                // 手续费\r\n            \"takerMaker\": \"taker\"               // [taker、maker]\r\n        }\r\n    ],\r\n    \"info\": \"操作成功\"\r\n}"
    title: Response
    language: json
---
