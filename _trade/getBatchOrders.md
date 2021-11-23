---
title: Get a batch of Orders Information
position_number: 11
type: get
description: /trade/api/v1/getBatchOrders
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
    type: integer
    mandatory: true
    default: N/A
    description: Order data
    ranges:
content_markdown: |-
    data is a JSON array. The maximum length of the array is only 100. Anything beyond 100 will be ignored.

    The format of the array element is the order ID, such as:\[123, 456, 789\]

    After the assembly is completed, the JSON array is converted to STRING, and then Base64.encode () is the final data to be submitted.

    Please note that data is not involved in signing the JSON data itself, but STRING after Base64.decode ()
left_code_blocks:
-
    code_block: "public void getBatchOrders() {\n\tMap<String, Object> map = new HashMap<String, Object>();\n\tmap.put(\"accesskey\", accessKey);\n\tmap.put(\"nonce\", System.currentTimeMillis());\n\tmap.put(\"market\", \"btc_usdt\");\n\t\n\tJSONArray array = new JSONArray();\n\tarray.add(\"157154392122493\");\n\tarray.add(\"157154392122494\");\n\tarray.add(\"157154392122495\");\n\tarray.add(\"157154392122496\");\n\tarray.add(\"157154392122497\");\n\t\n\t// put data\n\tString data = Base64CoderC.encode(array.toJSONString());\n\t\n\tmap.put(\"data\", data);\n\t// Signature\n\tString signature = HttpUtil.getSignature(map, secretKey);\n\tmap.put(\"signature\", signature);\n\t\n\tString text = HttpUtil.get(URL + \"/trade/api/v1/getBatchOrders\", map);\n\tSystem.out.println(text);\n}"
    title: Java
    language: java
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"data\": [\r\n    {\r\n      \"number\": \"0.002000\",\r\n      \"price\": \"5000.00\",\r\n      \"avgPrice\": \"0.00\",\r\n      \"id\": 156293034074105,\r\n      \"time\": 1562930340271,\r\n      \"type\": 1,\r\n      \"status\": 1,\r\n      \"completeNumber\": \"0.000000\",\r\n      \"completeMoney\": \"0.000000\",\r\n      \"entrustType\": 0,              \r\n      \"fee\": \"0.000000\"\r\n    },\r\n    {\r\n      \"number\": \"0.001000\",\r\n      \"price\": \"5000.00\",\r\n      \"avgPrice\": \"0.00\",\r\n      \"id\": 156293034074104,\r\n      \"time\": 1562930340271,\r\n      \"type\": 1,\r\n      \"status\": 1,\r\n      \"completeNumber\": \"0.000000\",\r\n      \"completeMoney\": \"0.000000\",\r\n      \"entrustType\": 0,              \r\n      \"fee\": \"0.000000\"\r\n    }\r\n  ],\r\n  \"info\": \"success\"\r\n}"
    title: Response
    language: json
---
