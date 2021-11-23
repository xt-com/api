---
title: Bulk Orders
position_number: 6
type: post
description: /trade/api/v1/batchOrder
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
    name: data
    type: string
    mandatory: true
    default: N/A
    description: Order data
    ranges:
content_markdown: |-
    Only limit orders are supported. One transaction will either succeed or failed.

    Data is a JSON array. The maximum length of the array is only 100. Anything beyond 100 will be ignored. The format of the array element is as following:

    \{ "price": 1000,&nbsp; "amount": 1, &nbsp;"type" : 1&nbsp; // 1, buy, 0 sell\}

    After the assembly is completed, the JSON array is converted to STRING, and then Base64.encode () is the final data to be submitted.

    Please note that data is not involved in signing the JSON data itself, but STRING after Base64.decode ()

    Note：The API interface needs to open transaction permissions.

left_code_blocks:
-
    code_block: "public void batchOrder() {\n\tMap<String, Object> map = new HashMap<String, Object>();\n\tmap.put(\"accesskey\", accessKey);\n\tmap.put(\"nonce\", System.currentTimeMillis());\n\tmap.put(\"market\", \"btc_usdt\");\n\t\n\tJSONArray array = new JSONArray();\n\tfor(int i = 0; i < 10; i++) {\n\t\tJSONObject bid = new JSONObject();\n\t\tbid.put(\"price\", \"10000.123\");\n\t\tbid.put(\"amount\", \"0.1\");\n\t\tbid.put(\"type\", 1);\n\t\tarray.add(bid);\n\t\tJSONObject ask = new JSONObject();\n\t\task.put(\"price\", \"10001.123\");\n\t\task.put(\"amount\", \"0.1\");\n\t\task.put(\"type\", 0);\n\t\tarray.add(ask);\n\t}\n\t// put data\n\tString data = Base64CoderC.encode(array.toJSONString());\n\t\n\tmap.put(\"data\", data);\n\t\n\t// Signature\n\tString signature = HttpUtil.getSignature(map, secretKey);\n\tmap.put(\"signature\", signature);\n\t// \n\tString text = HttpUtil.post(URL + \"/trade/api/v1/batchOrder\", map);\n\tSystem.out.println(text);\n}"
    title: Java
    language: java
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"data\": [\r\n    {\r\n      \"amount\": 0.0010,\r\n      \"price\": 5000.0000,\r\n      \"id\": 156292972664756,\r\n      \"type\": 1\r\n    },\r\n    {\r\n      \"amount\": 0.0020,\r\n      \"price\": 5000.0000,\r\n      \"id\": 156292972664757,\r\n      \"type\": 1\r\n    }\r\n  ],\r\n  \"info\": \"An order has been placed successfully\"\r\n}"
    title: Response
    language: json
---
