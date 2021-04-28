---
sidebar_position: 1
---

# Get User Details

This API will get details for a Mobile Banking user.

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
	"action": "GET_USER_DETAILS",
	"payload": {
		"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",
		"identifier_type": "MSISDN",
		"identifier": "254712345678",
		"pin": "1234",
		"device_identifier_type": "IMSI/APP_ID",
		"device_identifier": "1099200912931023",
		"user_identifier_type": "MSISDN",
		"user_identifier": "254712345678"
	}
}
```

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT | | YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:<ol><li>```MSISDN```</li></ol> |
| **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | 
| **user_identifier_type** | STRING | 50 | YES | Mobile Banking account user identifier type. Values can be:<ol><li>```MEMBER_NUMBER```</li><li>```MSISDN```</li><li>```NATIONAL_ID```</li><li>```ACCOUNT_NUMBER```</li><li>```PASSPORT_NO```</li><li>```DRIVING_LICENSE```</li></ol> |
| **user_identifier** | STRING | 50 | YES | Mobile Banking account user identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:<ol><li>```APP_ID```</li><li>```IMSI```</li></ol> |
| **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier |

## Response

### Response Data Structure

The following is a specification of expected response

```json
{
	"request_status": "SUCCESS/USER_NOT_FOUND/INCORRECT_PIN/ERROR",
	"member_number": "012939",
	"full_name": "John Doe",
	"identifier_type": "MSISDN",
	"identifier": "254712345678",
	"identity_type": "NATIONAL_ID/PASSPORT_NO/DRIVING_LICENSE",
	"identity": "23994857",
	"ift_dest_accounts": [
		{
			"account_name": "Salary Account",
			"account_label": "Salary Account (41-02392-0093-01)",
			"account_number": "41-02392-0093-01"
		},
		{
			"account_name": "Salary Account",
			"account_label": "Salary Account (41-02392-0093-01)",
			"account_number": "41-02392-0093-01"
		}
	]
}
```

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:<ol><li>```SUCCESS```</li><li>```USER_NOT_FOUND```</li><li>```INCORRECT_PIN```</li><li>```ERROR```</li></ol> |    
| **member_number** | STRING | 50 | YES | Specifies the member umber of the Mobile Banking user | 
| **full_name** | STRING | 100 | YES | Specifies the full name of the Mobile Banking user | 
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:<ol><li>```MSISDN```</li></ol> |
| **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | 
| **identity_type** | STRING | 50 | YES | Specifies the Identity type used by the member:<ol><li>```NATIONAL_ID```</li><li>```PASSPORT_NO```</li><li>```DRIVING_LICENSE```</li></ol> |
| **identity** | STRING | 50 | YES | Specifies the actual identity of the member | 
| **ift_dest_accounts** | LIST | | YES | Specifies the list accounts that can allow for Internal Funds Transfer | 
| **account_name** | STRING | 100 | YES | Specifies the account name of the Mobile Banking user's account | 
| **account_label** | STRING | 100 | YES | Specifies the label of the account. This will be displayed to the user. | 
| **account_number** | STRING | 50 | YES | Specifies the account number of the Mobile Banking user's account |
