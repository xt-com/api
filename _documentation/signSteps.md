---
title: Signing steps
position_number: 5
parameters:
- name:
content:
content_markdown: >-
    Standardize the request to calculate signature. When HMAC is used for signature calculation, the calculation result using different content will be completely different. Therefore, before performing signature calculation, please standardize the request. The following takes the query of an order details request as an example:


    https://api.xt.com/trade/api/v1/getOrder?accesskey=\{AccessKey\}&market=\{Market\}&nonce=\{Timestamp\}&id=\{OrderId\}&signature=\{Signature\}


    Sort the parameter names according to the order of ASCII codes, and concatenate each parameter with the character "&".


    accesskey=myAccessKey&id=123&market=btc\_usdt&nonce=1562919832183


    Note that the value of nonce is a 13-bit millisecond number.


    Use the Secret Key obtained from the website to sign the HmacSHA256 parameter string generated above.

    For example, the signature of the above parameters results:


    97b7b71741ca0aec6e0404a5b1c7cb2a78e7bd6c2a8088dbd84a20129dee4fe7


    Finally, the signature is assigned to the parameter name signature and submitted to the server. 
left_code_blocks:
- code_block:
  title:
  language:
right_code_blocks:
- code_block:
  title:
  language:
---
