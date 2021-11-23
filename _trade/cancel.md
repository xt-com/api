---
title: Cancel an Order
position_number: 7
type: post
description: /trade/api/v1/cancel
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
    name: id
    type: integer
    mandatory: true
    default: N/A
    description: Order ID
    ranges:
content_markdown: Note: The API interface needs to open transaction permissions.
left_code_blocks:
-
    code_block: "public void cancel() {\n\tMap<String, Object> map = new HashMap<String, Object>();\n\tmap.put(\"accesskey\", accessKey);\n\tmap.put(\"nonce\", System.currentTimeMillis());\n\tmap.put(\"market\", \"btc_usdt\");\n\tmap.put(\"id\", \"156387346384491\");\n\t// Signature\n\tString signature = HttpUtil.getSignature(map, secretKey);\n\tmap.put(\"signature\", signature);\n\t\n\tString text = HttpUtil.post(URL + \"/trade/api/v1/cancel\", map);\n\tSystem.out.println(text);\n}"
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
