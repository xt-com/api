---
title: Signature Statement
position_number: 4
parameters:
- name:
content:
content_markdown: >-
    The request of API is likely to be tampered during the transmission through
    the Internet. In order to ensure that the request has not been changed,
    private interfaces other than public interfaces (basic information, market
    data) must use your API Key for signature verification to verify and check
    whether the parameter or parameter value has changed during the transmission.
    Each API Key needs proper permissions to access the corresponding interface.
    Every newly created API Key needs to be assigned permissions. Permission types
    are divided into: read, transaction and withdrawal. Before using the
    interface, please check the permission type of each interface and confirm that
    your API Key has the corresponding permission.


    A legitimate request consists of the following parts:
    
    
    Way to request an address: Accessing the server
    address&nbsp;**api.xt.com**&nbsp;such
    as**&nbsp;api.xt.com/trade/api/v1/order**.
    
    
    API accesskey: There is the Access Key in the API Key you applied for.
    
    
    Timestamp (nonce): The timestamp of your application's request, 13-bit
    milliseconds. XT will verify the validity of your API request based on this
    timestamp.
    
    
    Signature: A value calculated by the signature to ensure the signature is
    valid and has not been tampered. XT uses HmacSHA256.
left_code_blocks:
- code_block:
  title:
  language:
right_code_blocks:
- code_block:
  title:
  language:
---


