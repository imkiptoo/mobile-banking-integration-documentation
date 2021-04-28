---
sidebar_position: 3
---

# Set Auth Security Parameters

This API will allow an application get Login Security Parameters tied to a Mobile Banking user

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
	"action": "SET_AUTH_SECURITY_PARAMETERS",
	"payload": {
		"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",
		"identifier_type": "MSISDN",
		"identifier": "254712345678",
		"pin": "1234",
		"device_identifier_type": "IMSI/APP_ID",
		"device_identifier": "1099200912931023",
		"auth_security_type": " PASSWORD/OTP",
		"auth_action": "SUSPEND",
		"auth_action_valid_date": "2020-12-08 09:34:33",
		"auth_flag": "SECOND_SUSPENSION",
		"auth_attempts": 16,
		"date_time": "2020-12-08 09:34:33"
	}
}
```

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed |
| **payload** | OBJECT | | YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:<ol><li>```MSISDN```</li></ol> | 
| **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | 
| **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | 
| **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:<ol><li>```IMSI```</li><li>```APP_ID```</li></ol> |
| **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | 
| **auth_security_type** | STRING | 50 | YES | Specifies the type of Auth Security parameters are needed.Values can be: <ol><li>```PASSWORD```</li><li>```OTP```</li></ol> |
| **auth_action** | STRING | 50 | YES | Specifies the current auth action to be set. Values can be:<ol><li>```NONE```</li><li>```WARN```</li><li>```SUSPEND```</li><li>```LOCK```</li></ol> |
| **auth_action_valid_date** | DATETIME | | OPTIONAL | Specifies the date up to which the Mobile Banking account has been SUSPENDED. Should be in ISO format – ```yyyy:MM:dd HH:mm:ss``` | 
| **auth_flag** | STRING | 100 | YES | Specifies the current auth flag to be set. The auth_flag is the NAME of the Auth Attempt that has been violated/triggered. This is as per the Auth Security XML. See sample in Appendix section of the document. | 
| **auth_attempts** | INTEGER | 10 | YES | Number of times the Mobile Banking user has tried logging in or entering OTP. This depends on the auth_security_type | 
| **date_time** | DATETIME | | YES | Specifies the date the set parameters request was initiated. Should be in ISO format – ```yyyy:MM:dd HH:mm:ss``` |

## Response

### Response Data Structure

The following is a specification of expected response

```json
 {
	"set_auth_security_parameters_status": "SUCCESS ",
	"set_auth_security_parameters_status_description": "Auth Status Parameters set successfully",
	"date_time": "2020-12-08 09:34:33"
}
```

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Expected** | **Description** |
| --- | --- | --- | --- | --- |
| **set_auth_security_parameters_status** | STRING | 50 | YES | Specifies the status of the requestValues can be:<ol><li>```SUCCESS```</li><li>```INCORRECT_PIN```</li><li>```ERROR```</li></ol> |
| **set_auth_security_parameters_status_description** | STRING | 200 | YES | Specifies the status description | | **date_time** | DATETIME | | YES | Specifies the date the set parameters response was initiated. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

