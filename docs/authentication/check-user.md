---
sidebar_position: 0
---

# Check User

This API will allow an application check whether a mobile number is registered to use Mobile Banking<br/>

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
	"action": "CHECK_USER",
	"payload": {
		"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",
		"identifier_type": "MSISDN",
		"identifier": "254712345678",
		"device_identifier_type": "IMSI",
		"device _identifier": "1099200912931023"
	}
}
```

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed |
| **payload** | OBJECT | | YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be: <ol><li> ```MSISDN ```</li></ol> |
| **identifier** | STRING | 100 | YES | Mobile Banking account identifier. |
| **device_identifier_type** | STRING | 100 | YES | Device identifier tied to Mobile Banking account identifier. Values can be: <ol><li> ```IMSI ```</li><li> ```APP_ID ```</li></ol> |
| **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier. |

## Response

### Response Data Structure

```json
{
	"user_status": "SUSPENDED",
	"auth_action_valid_date": "2020-12-08 09:34:33"
}
```

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Expected** | **Description** |
| --- | --- | --- | --- | --- |
| **user_status** | STRING | 50 | YES | Specifies status of the Mobile Banking account Values can be:<ol><li> ```ACTIVE``` </li><li> ```SUSPENDED``` </li><li> ```LOCKED``` </li><li> ```INVALID_DEVICE_IDENTIFIER``` </li><li> ```NOT_FOUND``` </li><li> ```ERROR``` </li></ol> |
| **auth_action_valid_date** | DATETIME | OPTIONAL | | Specifies the date up to which the Mobile Banking account has been SUSPENDED. Should be in ISO format – ``` yyyy:MM:dd HH:mm:ss ``` |
