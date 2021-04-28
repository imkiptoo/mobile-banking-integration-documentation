---
sidebar_position: 6
---

# Change PIN

This API will allow an application to facilitate change PIN for a Mobile Banking user

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
	"action": "CHANGE_PIN",
	"payload": {
        "api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",
        "identifier_type": "MSISDN",
        "identifier": "254712345678",
        "pin": "1234",
        "device_identifier_type": "IMSI/APP_ID",
        "device_identifier": "1099200912931023",
        "new_pin": "1234"
	}
}
```

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:<ol><li>```MSISDN```</li></ol> |
| **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | 
| **pin** | STRING | 50 | YES | Current Mobile Banking PIN of the member | 
| **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:<ol><li>```IMSI```</li><li>```APP_ID```</li></ol> |
| **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | 
| **new_pin** | STRING | 50 | YES | New Mobile Banking PIN of the member |

## Response

### Response Data Structure

The following is a specification of expected response

```json
{
	"change_pin_status": "SUCCESS/INVALID_ACCOUNT/INCORRECT_PIN/INVALID_NEW_PIN/ERROR",
	"change_pin_status_description": "PIN changed successfully"
}
```

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **change_pin_status** | STRING | 50 | YES | Specifies the status of the requestValues can be:<ol><li>```SUCCESS```</li><li>```INVALID_ACCOUNT```</li><li>```INCORRECT_PIN```</li><li>```INVALID_NEW_PIN```</li><li>```ERROR```</li></ol> |
| **change_pin_status_description** | STRING | 200 | YES | Specifies the status description |
