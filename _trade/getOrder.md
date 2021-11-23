---
title: Order Information
position_number: 9
type: get
description: /trade/api/v1/getOrder
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
content_markdown:
left_code_blocks:
-
    code_block: "public void getOrder() {\n\tMap<String, Object> map = new HashMap<String, Object>();\n\tmap.put(\"accesskey\", accessKey);\n\tmap.put(\"nonce\", System.currentTimeMillis());\n\tmap.put(\"market\", \"btc_usdt\");\n\tmap.put(\"id\", \"156387346384491\");\n\t// Signature\n\tString signature = HttpUtil.getSignature(map, secretKey);\n\tmap.put(\"signature\", signature);\n\t\n\tString text = HttpUtil.get(URL + \"/trade/api/v1/getOrder\", map);\n\tSystem.out.println(text);\n}"
    title: Java
    language: java
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"data\": {\r\n    \"number\": \"0.002000\",           // Order amount\r\n    \"price\": \"5000.00\",             // Order price\r\n    \"avgPrice\": \"0.00\",             // Average price\r\n    \"id\": 156293034776987,          // Order ID\r\n    \"time\": 1562930348000,          // Order time\r\n    \"type\": 1,                      // Trading type：1、buy 0、sell\r\n    \"status\": 3,                    // Status (0, submission not matched, 1, unsettled or partially completed, 2, completed, 3, cancelled, 4,matched but in the settlement)\r\n    \"completeNumber\": \"0.000000\",   // Completed Quantities\r\n    \"completeMoney\": \"0.000000\",    // Completed amount\r\n    \"entrustType\": 0,               // Order type：1、Market price 0、Limited price\r\n    \"fee\": \"0.000000\"               // Trading fees\r\n  },\r\n  \"info\": \"success\"\r\n}"
    title: Response
    language: json
---
