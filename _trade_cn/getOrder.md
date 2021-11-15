---
title: 订单信息
position_number: 9
type: get
description: /trade/api/v1/getOrder
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
    name: id
    type: integer
    mandatory: true
    default: N/A
    description: 订单ID
    ranges:
content_markdown:
left_code_blocks:
-
    code_block: "public void getOrder() {\r\n\tMap<String, Object> map = new HashMap<String, Object>();\r\n\tmap.put(\"accesskey\", accessKey);\r\n\tmap.put(\"nonce\", System.currentTimeMillis());\r\n\tmap.put(\"market\", \"btc_usdt\");\r\n\tmap.put(\"id\", \"156387346384491\");\r\n\t// 签名 (en:Signature)\r\n\tString signature = HttpUtil.getSignature(map, secretKey);\r\n\tmap.put(\"signature\", signature);\r\n\t\r\n\tString text = HttpUtil.get(URL + \"/trade/api/v1/getOrder\", map);\r\n\tSystem.out.println(text);\r\n}"
    title: Java
    language: java
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"data\": {\r\n    \"number\": \"0.002000\",           // 委托数量\r\n    \"price\": \"5000.00\",             // 委托价格\r\n    \"avgPrice\": \"0.00\",             // 成交均价\r\n    \"id\": 156293034776987,          // 订单ID\r\n    \"time\": 1562930348000,          // 委托时间\r\n    \"type\": 1,                      // 交易类型：1、买 0、卖\r\n    \"status\": 3,                    // 状态  (0、提交未撮合，1、未成交或部份成交，2、已完成，3、已取消，4、撮合完成结算中)\r\n    \"completeNumber\": \"0.000000\",   // 完成数量\r\n    \"completeMoney\": \"0.000000\",    // 完成金额\r\n    \"entrustType\": 0,               // 订单类型：1、市价 0、限价\r\n    \"fee\": \"0.000000\"               // 交易手续费\r\n  },\r\n  \"info\": \"success\"\r\n}"
    title: Response
    language: json
---
