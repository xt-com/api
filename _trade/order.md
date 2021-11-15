---
title: Place a new order
position_number: 5
type: post
description: /trade/api/v1/order
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
    name: price
    type: float
    mandatory: true
    default: N/A
    description: Order Price
    ranges:
-
    name: number
    type: float
    mandatory: true
    default: N/A
    description: Order quantity
    ranges:
-
    name: type
    type: integer
    mandatory: true
    default: N/A
    description: Trading type
    ranges: 1, buy, 0 sell
-
    name: entrustType
    type: integer
    mandatory: true
    default: N/A
    description: Order type
    ranges: 0, limit price,1 market price
content_markdown:
left_code_blocks:
-
    code_block: "public void order() {\n\tMap<String, Object> map = new HashMap<String, Object>();\n\tmap.put(\"accesskey\", accessKey);\n\tmap.put(\"nonce\", System.currentTimeMillis());\n\tmap.put(\"market\", \"btc_usdt\");\n\tmap.put(\"price\", \"10000\");\n\tmap.put(\"number\", \"1.23\");\n\tmap.put(\"type\", 1);\t\t// 0.sell 1.buy\n\tmap.put(\"entrustType\", 0);\t// 0.Limited price  1.Market price matching\n\t// Signature\n\tString signature = HttpUtil.getSignature(map, secretKey);\n\tmap.put(\"signature\", signature);\n\t// \n\tString text = HttpUtil.post(URL + \"/trade/api/v1/order\", map);\n\tSystem.out.println(text);\n}"
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
