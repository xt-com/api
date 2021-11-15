---
title: Get transaction records
position_number: 12
type: get
description: /trade/api/v1/myTrades
parameters:
-
    name: accesskey
    type: string
    mandatory: true
    default: N/A
    description: Access private key
    ranges:
-
    name: nonce
    type: integer
    mandatory: true
    default: N/A
    description: 13-bit milliseconds
    ranges:
-
    name: market
    type: string
    mandatory: true
    default: N/A
    description: Market pair
    ranges: btc_usdt, eth_usdt...
-
    name: fromId
    type: string
    mandatory: false
    default: N/A
    description: Last transaction ID, provided when turning back pages
    ranges:
-
    name: limit
    type: integer
    mandatory: false
    default: N/A
    description: The size of each page, default 200
    ranges:
-
    name: startTime
    type: integer
    mandatory: false
    default: N/A
    description: Start time, milliseconds
    ranges:
-
    name: endTime
    type: integer
    mandatory: false
    default: N/A
    description: End time, milliseconds
    ranges:
content_markdown:
left_code_blocks:
-
    code_block:
    title:
    language:
right_code_blocks:
-
    code_block: "{\r\n    \"code\": 200,\r\n    \"data\": [\r\n        {\r\n            \"id\": \"6821734611983271937\",        //Trade ID, When turning the page, provide this ID\r\n            \"orderId\": \"6821734611950127105\",\r\n            \"time\": 1626428273000,            \r\n            \"price\": \"10.3998\",\r\n            \"amount\": \"1\",\r\n            \"value\": \"10.3998\",\r\n            \"type\": 1\",                         // 0:sell 1:buy\r\n            \"entrustType\": 1,                   // 0:limit price 1:market price\r\n            \"isLever\": 0,                       // Whether to trade with leverage [1 yes; 0 no]\r\n            \"fee\": \"0.01663968\",\r\n            \"takerMaker\": \"taker\"               // [taker、maker]\r\n        }\r\n    ],\r\n    \"info\": \"success\"\r\n}"
    title: Response
    language: json
---
