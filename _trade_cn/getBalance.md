---
title: 获取交易(现货)账户资产
position_number: 2
type: get
description: /trade/api/v1/getBalance
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
    description: "13位毫秒数\t"
    ranges:
content_markdown:
left_code_blocks:
-
    code_block: "public void getBalance() {\n\tMap<String, Object> map = new HashMap<String, Object>();\n\tmap.put(\"accesskey\", accessKey);\n\tmap.put(\"nonce\", System.currentTimeMillis());\n\t// 签名(en:Signature)\n\tString signature = HttpUtil.getSignature(map, secretKey);\n\tmap.put(\"signature\", signature);\n\t\n\tString text = HttpUtil.get(URL + \"/trade/api/v1/getBalance\", map);\n\tSystem.out.println(text);\n}"
    title: Java
    language: java
-
    code_block: "def test_balance(self):\r\n    \r\n    accesskey = 'xxxxxxxxxxxxxxxxxxxx'\r\n    secretkey = 'xxxxxxxxxxxxxxxxxxxx'\r\n    sra = SignedRequestAPI(accesskey, secretkey)\r\n    \r\n    status, data, _ = sra.get_balance()\r\n    self.assertTrue(status)\r\n    self.assertTrue(isinstance(data, dict))\r\n    \r\n    assert data.get('info') == \"Success\"\r\n    assert len(data.get('data')) > 0\r\n    \"\"\" ¡®Forth¡¯ is my test account, if not ¡®Forth¡¯ account please switch   \"\"\"\r\n    assert data['data'].get('forth') and data['data'].get('usdt')\r\n    \r\n    print(\"test balance >>> \", data)"
    title: Python
    language: python
right_code_blocks:
-
    code_block: "{\r\n  \"code\": 200,\r\n  \"data\": {\r\n    \"btc\": {\r\n      \"freeze\": \"0.00\",     // 冻结\r\n      \"available\": \"0.00\"   // 可用\r\n    },\r\n    \"eth\": {\r\n      \"freeze\": \"0.00\",\r\n      \"available\": \"0.00\"\r\n    },\r\n    \"usdt\": {\r\n      \"freeze\": \"3062.17437341\",\r\n      \"available\": \"3867.43650012\"\r\n    },\r\n    \"ltc\": {\r\n      \"freeze\": \"0.00\",\r\n      \"available\": \"0.00\"\r\n    }\r\n    ...\r\n  },\r\n  \"info\": \"success\"\r\n}"
    title: Response
    language: json
---


