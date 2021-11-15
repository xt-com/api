---
title: 撤单
position_number: 7
type: post
description: /trade/api/v1/cancel
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
    code_block: "public void cancel() {\r\n\tMap<String, Object> map = new HashMap<String, Object>();\r\n\tmap.put(\"accesskey\", accessKey);\r\n\tmap.put(\"nonce\", System.currentTimeMillis());\r\n\tmap.put(\"market\", \"btc_usdt\");\r\n\tmap.put(\"id\", \"156387346384491\");\r\n\t// 签名(en:Signature)\r\n\tString signature = HttpUtil.getSignature(map, secretKey);\r\n\tmap.put(\"signature\", signature);\r\n\t\r\n\tString text = HttpUtil.post(URL + \"/trade/api/v1/cancel\", map);\r\n\tSystem.out.println(text);\r\n}"
    title: Java
    language: java
-
    code_block: "def test_cancel(self):\r\n    \r\n    accesskey = 'xxxxxxxxxxxxxxxxxxxx'\r\n    secretkey = 'xxxxxxxxxxxxxxxxxxxx'\r\n    sra = SignedRequestAPI(accesskey, secretkey)  \r\n    \r\n    params = {\r\n            'market':'forth_usdt',\r\n            'id':'6823168236830742528'\r\n    }\r\n    \r\n    status, data, _ = sra.palce_order(params)\r\n    \r\n    assert  data.get('code') == 200\r\n    assert data.get('data') is not None\r\n    self.assertTrue(status)\r\n    self.assertTrue(isinstance(data, dict))\r\n    \r\n    print('test cancel >>> ', data)"
    title: Python
    language: python
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"info\": \"The order has been canceled successfully\"\r\n}"
    title: Response
    language: json
---
