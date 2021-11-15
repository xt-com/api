---
title: 委托
position_number: 5
type: post
description: /trade/api/v1/order
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
    name: price
    type: float
    mandatory: true
    default: N/A
    description: 委托价格
    ranges:
-
    name: number
    type: float
    mandatory: true
    default: N/A
    description: 委托数量
    ranges:
-
    name: type
    type: integer
    mandatory: true
    default: N/A
    description: 交易类型
    ranges: 1、买 0、卖
-
    name: entrustType
    type: integer
    mandatory: true
    default: N/A
    description: 委托类型
    ranges: 0、限价，1、市价
content_markdown:
left_code_blocks:
-
    code_block: "public void order() {\r\n\tMap<String, Object> map = new HashMap<String, Object>();\r\n\tmap.put(\"accesskey\", accessKey);\r\n\tmap.put(\"nonce\", System.currentTimeMillis());\r\n\tmap.put(\"market\", \"btc_usdt\");\r\n\tmap.put(\"price\", \"10000\");\r\n\tmap.put(\"number\", \"1.23\");\r\n\tmap.put(\"type\", 1);\t\t// 0.sell 1.buy\r\n\tmap.put(\"entrustType\", 0);\t// 0.Limited price  1.Market price matching\r\n\t// 签名(en:Signature)\r\n\tString signature = HttpUtil.getSignature(map, secretKey);\r\n\tmap.put(\"signature\", signature);\r\n\t// \r\n\tString text = HttpUtil.post(URL + \"/trade/api/v1/order\", map);\r\n\tSystem.out.println(text);\r\n}"
    title: Java
    language: java
-
    code_block: "def test_order(self):\r\n    \r\n    accesskey = 'xxxxxxxxxxxxxxxxxxxx'\r\n    secretkey = 'xxxxxxxxxxxxxxxxxxxx'\r\n    sra = SignedRequestAPI(accesskey, secretkey)  \r\n    \r\n    params = {\r\n        'market': \"forth_usdt\",\r\n        'price': 4.44,\r\n        'type': 0,\r\n        'number':6,\r\n        'entrustType':0,\r\n        }\r\n    \r\n    status, data, _ = sra.palce_order(params)\r\n    \r\n    assert data.get('code') == 200\r\n    self.assertTrue(status)\r\n    self.assertTrue(isinstance(data, dict))\r\n    \r\n            \r\n    print(\"test order >>> \", data)"
    title: Python
    language: python
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"data\": {\r\n    \"id\": 156292794190713\r\n  },\r\n  \"info\": \"An order has been placed successfully\"\r\n}"
    title: Response
    language: json
---
