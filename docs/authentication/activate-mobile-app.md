---
sidebar_position: 7
---

# Activate Mobile App

This API will allow an application do KYC and set the New PIN for a Mobile Banking user

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
	"action": "ACTIVATE_MOBILE_APP ",
	"payload": {
		"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",
		"identifier_type": "MSISDN",
		"identifier": "254712345678",
		"pin": "1234",
		"app_id": "1099200912931023",
		"activate_with_kyc": "YES/NO",
		"identity_type": "NATIONAL_ID",
		"identity": "23994857"
	}
}
```

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. Values can be:<ol><li>```ACTIVATE_MOBILE_APP```</li></ol> |
| **payload** | OBJECT | | YES | Contains the payload data | 
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. | | **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:<ol><li>```MSISDN```</li></ol> |
| **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | 
| **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | 
| **app_id** | STRING | 100 | YES | Specifies the App ID to be activated. | 
| **activate_with_kyc** | STRING | 10 | OPTIONAL | Specify whether Mobile App activation requires KYC. Values can be:<ol><li>```YES```</li><li>```NO```</li></ol> |
| **identity_type** | STRING | 50 | OPTIONAL | Specifies the Identity type used by the member. Should be specified if ```activate_with_kyc``` is ```YES```. Values can be:<ol><li>```NATIONAL_ID```</li><li>```PASSPORT_NO```</li><li>```DRIVING_LICENSE```</li></ol> |
| **identity** | STRING | 50 | OPTIONAL | Specifies the actual identity of the member. Should be specified if ```activate_with_kyc``` is ```YES```. |

## Response

### Response Data Structure

The following is a specification of expected response

```json
{
	"mobile_app_activation_status": "SUCCESS ",
	"mobile_app_activation_status_description": "Mobile App Activated successfully"
}
```

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **mobile_app_activation_status** | STRING | 50 | YES | Specifies the status of the requestValues can be:<ol><li>```SUCCESS```</li><li>```INCORRECT_PIN```</li><li>```INVALID_ACCOUNT```</li><li>```ERROR```</li></ol> |
| **mobile_app_activation_status_description** | STRING | 200 | YES | Specifies the status description |
