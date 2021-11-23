---
title: Get Uncompleted Orders
position_number: 10
type: get
description: /trade/api/v1/getOpenOrders
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
    name: page
    type: integer
    mandatory: false
    default: '1'
    description: page number
    ranges:
-
    name: pageSize
    type: integer
    mandatory: false
    default: '10'
    description: Order quantities
    ranges: '[10-1000]'
content_markdown:
left_code_blocks:
-
    code_block: "public void getOpenOrders() {\n\tMap<String, Object> map = new HashMap<String, Object>();\n\tmap.put(\"accesskey\", accessKey);\n\tmap.put(\"nonce\", System.currentTimeMillis());\n\tmap.put(\"market\", \"btc_usdt\");\n\tmap.put(\"page\", 1);\n\tmap.put(\"pageSize\", 10);\n\t\n\t// Signature\n\tString signature = HttpUtil.getSignature(map, secretKey);\n\tmap.put(\"signature\", signature);\n\t\n\tString text = HttpUtil.get(URL + \"/trade/api/v1/getOpenOrders\", map);\n\tSystem.out.println(text);\n}"
    title: Java
    language: java
-
    code_block: "def test_opens(self):\r\n    \r\n    accesskey = 'xxxxxxxxxxxxxxxxxxxx'\r\n    secretkey = 'xxxxxxxxxxxxxxxxxxxx'\r\n    sra = SignedRequestAPI(accesskey, secretkey)  \r\n    \r\n    params = {\r\n            'market':'forth_usdt',\r\n    }\r\n    \r\n    status, data, _ = sra.get_unfinished_order(params)\r\n    \r\n    assert  data.get('code') == 200\r\n    assert data.get('data') is not None\r\n    self.assertTrue(status)\r\n    self.assertTrue(isinstance(data, dict))\r\n    \r\n    print('test opens >>> ', data)\r\n    pass"
    title: Python
    language: python
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"data\": [\r\n    {\r\n      \"number\": \"0.002000\",\r\n      \"price\": \"5000.00\",\r\n      \"avgPrice\": \"0.00\",\r\n      \"id\": 156293034074105,\r\n      \"time\": 1562930340271,\r\n      \"type\": 1,\r\n      \"status\": 1,\r\n      \"completeNumber\": \"0.000000\",\r\n      \"completeMoney\": \"0.000000\",\r\n      \"entrustType\": 0,              \r\n      \"fee\": \"0.000000\"\r\n    },\r\n    {\r\n      \"number\": \"0.001000\",\r\n      \"price\": \"5000.00\",\r\n      \"avgPrice\": \"0.00\",\r\n      \"id\": 156293034074104,\r\n      \"time\": 1562930340271,\r\n      \"type\": 1,\r\n      \"status\": 1,\r\n      \"completeNumber\": \"0.000000\",\r\n      \"completeMoney\": \"0.000000\",\r\n      \"entrustType\": 0,              \r\n      \"fee\": \"0.000000\"\r\n    }\r\n  ],\r\n  \"info\": \"success\"\r\n}"
    title: Response
    language: json
---
