---
sidebar_position: 1
---

# MO Check User

This API will allow an application check whether a mobile number is registered to use Mobile Banking

__API Access Method__: HTTP(S) POST<br/>

__URL & Credentials__: To be provided separately<br/>

__Request Headers__:<br/>

|  Header    |  Value     | 
| :----- | :---------- |
|  __Content-Type__     |  ```application/json``` |
|  __Accept__     |  ```application/json``` |

## Request

### Request Data Structure

```json
{
	"action": "MO_CHECK_USER",
	"payload": {
		"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",
		"identifier_type": "MSISDN",
		"identifier": "254712345678"
	}
}
```

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed |
| **payload** | OBJECT | | YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:<br/> <ol><li>```MSISDN``` </li></ol>|
| **identifier** | STRING | 50 | YES | Mobile Banking account identifier. |

## Response

### Response Data Structure

The following is a specification of expected response

```json
{
	"user_status": "FOUND/NOT_FOUND"
}
```

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Expected** | **Description** |
| --- | --- | --- | --- | --- |
| **user_status** | STRING | 50 | YES | Specifies status of the Mobile Banking account<br/>Values can be:<br/> <ol><li>```FOUND``` </li><li>```NOT_FOUND``` </li></ol>|
