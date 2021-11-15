---
title: 获取多个订单信息
position_number: 11
type: get
description: /trade/api/v1/getBatchOrders
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
    name: data
    type: integer
    mandatory: true
    default: N/A
    description: 订单数据
    ranges:
content_markdown: |-
    data 是一个JSON数组，数组长度最大只支持100个，超出100的会被忽略100个以外的元素，数组元素格式为订单ID，如

    \[123, 456, 789\]

    组装完成之后，把JSON数组转为STRING，再进行Base64.encode()才是最终要提交的数据

    请注意，data参与签名的不是JSON数据本身，而是Base64.decode()之后的STRING
left_code_blocks:
-
    code_block: "public void getBatchOrders() {\r\n\tMap<String, Object> map = new HashMap<String, Object>();\r\n\tmap.put(\"accesskey\", accessKey);\r\n\tmap.put(\"nonce\", System.currentTimeMillis());\r\n\tmap.put(\"market\", \"btc_usdt\");\r\n\t\r\n\tJSONArray array = new JSONArray();\r\n\tarray.add(\"157154392122493\");\r\n\tarray.add(\"157154392122494\");\r\n\tarray.add(\"157154392122495\");\r\n\tarray.add(\"157154392122496\");\r\n\tarray.add(\"157154392122497\");\r\n\t\r\n\t// put data\r\n\tString data = Base64CoderC.encode(array.toJSONString());\r\n\t\r\n\tmap.put(\"data\", data);\r\n\t// 签名 (en:Signature)\r\n\tString signature = HttpUtil.getSignature(map, secretKey);\r\n\tmap.put(\"signature\", signature);\r\n\t\r\n\tString text = HttpUtil.get(URL + \"/trade/api/v1/getBatchOrders\", map);\r\n\tSystem.out.println(text);\r\n}"
    title: Java
    language: java
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"data\": [\r\n    {\r\n      \"number\": \"0.002000\",\r\n      \"price\": \"5000.00\",\r\n      \"avgPrice\": \"0.00\",\r\n      \"id\": 156293034074105,\r\n      \"time\": 1562930340271,\r\n      \"type\": 1,\r\n      \"status\": 1,\r\n      \"completeNumber\": \"0.000000\",\r\n      \"completeMoney\": \"0.000000\",\r\n      \"entrustType\": 0,              \r\n      \"fee\": \"0.000000\"\r\n    },\r\n    {\r\n      \"number\": \"0.001000\",\r\n      \"price\": \"5000.00\",\r\n      \"avgPrice\": \"0.00\",\r\n      \"id\": 156293034074104,\r\n      \"time\": 1562930340271,\r\n      \"type\": 1,\r\n      \"status\": 1,\r\n      \"completeNumber\": \"0.000000\",\r\n      \"completeMoney\": \"0.000000\",\r\n      \"entrustType\": 0,              \r\n      \"fee\": \"0.000000\"\r\n    }\r\n  ],\r\n  \"info\": \"success\"\r\n}"
    title: Response
    language: json
---
