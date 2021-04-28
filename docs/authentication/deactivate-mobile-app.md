---
sidebar_position: 8
---

# DeActivate Mobile App

This API will allow an application to facilitate Deactivation of Mobile App for a Mobile Banking user.

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
	"action": "DEACTIVATE_MOBILE_APP",
	"payload": {
		"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",
		"identifier_type": "MSISDN",
		"identifier": "254712345678",
		"pin": "1234",
		"device_identifier_type": "IMSI/APP_ID",
		"device_identifier": "1099200912931023"
	}
}
```

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. Values can be:<ol><li>```DEACTIVATE_MOBILE_APP```</li></ol> |
| **payload** | OBJECT | | YES | Contains the payload data | 
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. | 
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:<ol><li>```MSISDN```</li></ol> |
| **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | 
| **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | 
| **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:<ol><li>```IMSI```</li><li>```APP_ID```</li></ol> |
| **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier

## Response

### Response Data Structure

The following is a specification of expected response

```json
{
	"mobile_app_activation_status": "SUCCESS ",
	"mobile_app_activation_status_description": "Mobile App Deactivated successfully"
}
```

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **mobile_app_activation_status** | STRING | 50 | YES | Specifies the status of the requestValues can be:<ol><li>```SUCCESS```</li><li>```INCORRECT_PIN```</li><li>```INVALID_ACCOUNT```</li><li>```ERROR```</li></ol> |
| **mobile_app_activation_status_description** | STRING | 200 | YES | Specifies the status description |
