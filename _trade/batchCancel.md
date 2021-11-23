---
title: Cancel the Bulk Orders
position_number: 8
type: post
description: /trade/api/v1/batchCancel
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
    Data is a JSON array. The maximum length of the array is only 100. Anything beyond 100 will be ignored. The format of the array element is the order ID, such as:
    
    \[123, 456, 789\]

    After the assembly is completed, the JSON array is converted to STRING, and then Base64.encode () is the final data to be submitted.
  
    Please note that data is not involved in signing the JSON data itself, but STRING after Base64.decode ()

    Note：The API interface needs to open transaction permissions.

left_code_blocks:
-
    code_block: "public void batchCancel() {\n\tMap<String, Object> map = new HashMap<String, Object>();\n\tmap.put(\"accesskey\", accessKey);\n\tmap.put(\"nonce\", System.currentTimeMillis());\n\tmap.put(\"market\", \"btc_usdt\");\n\t\n\tJSONArray array = new JSONArray();\n\tarray.add(\"157154392122493\");\n\tarray.add(\"157154392122494\");\n\tarray.add(\"157154392122495\");\n\tarray.add(\"157154392122496\");\n\tarray.add(\"157154392122497\");\n\t\n\t// put data\n\tString data = Base64CoderC.encode(array.toJSONString());\n\t\n\tmap.put(\"data\", data);\n\t\n\t// Signature\n\tString signature = HttpUtil.getSignature(map, secretKey);\n\tmap.put(\"signature\", signature);\n\t// \n\tString text = HttpUtil.post(URL + \"/trade/api/v1/batchCancel\", map);\n\tSystem.out.println(text);\n}"
    title: Java
    language: java
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"data\": [\r\n    {\r\n      \"msg\": \"The order has been canceled successfully\",\r\n      \"code\": 120,\r\n      \"id\": 156293034776986\r\n    },\r\n    {\r\n      \"msg\": \"The order has been canceled successfully\",\r\n      \"code\": 120,\r\n      \"id\": 156293034776987\r\n    },\r\n    {\r\n      \"msg\": \"Failed to cancel the order since it does not exist or has been canceled\",\r\n      \"code\": 121,\r\n      \"id\": 156293034776988\r\n    }\r\n  ],\r\n  \"info\": \"The order has been canceled successfully\"\r\n}"
    title: Response
    language: json
---
