---
title: Get specific account assets
position_number: 4
type: get
description: /trade/api/v1/getFunds
parameters:
-
    name: accesskey
    type: string
    mandatory: true
    default: N/A
    description: Access private key
    ranges:
-
    name: account
    type: integer
    mandatory: true
    default: N/A
    description: account ID
    ranges: Refer to getAccounts interface
-
    name: nonce
    type: integer
    mandatory: true
    default: N/A
    description: 13-bit milliseconds
    ranges:
content_markdown:
left_code_blocks:
-
    code_block: "public void getFunds() {\n\tMap<String, Object> map = new HashMap<String, Object>();\n\tmap.put(\"accesskey\", accessKey);\n\tmap.put(\"account\", 2);\t// Spot account\n\tmap.put(\"nonce\", System.currentTimeMillis());\n\t// Signature\n\tString signature = HttpUtil.getSignature(map, secretKey);\n\tmap.put(\"signature\", signature);\n\tString text = HttpUtil.get(URL + \"/trade/api/v1/getFunds\", map);\n\tSystem.out.println(text);\n}"
    title: Java
    language: java
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"data\": {\r\n    \"btc\": {\r\n      \"freeze\": \"0.00\",     // freeze\r\n      \"available\": \"0.00\"   // available\r\n    },\r\n    \"eth\": {\r\n      \"freeze\": \"0.00\",\r\n      \"available\": \"0.00\"\r\n    },\r\n    \"usdt\": {\r\n      \"freeze\": \"3062.17437341\",\r\n      \"available\": \"3867.43650012\"\r\n    },\r\n    \"ltc\": {\r\n      \"freeze\": \"0.00\",\r\n      \"available\": \"0.00\"\r\n    }\r\n  },\r\n  \"info\": \"success\"\r\n}"
    title: Response
    language: json
---
