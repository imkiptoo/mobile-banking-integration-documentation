---
sidebar_position: 2
---

# Get Accounts

This API will get accounts for a Mobile Banking user.

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
	"action": "GET_ACCOUNTS",
	"payload": {
		"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",
		"account_type": "FOSA/BOSA/WITHDRAWABLE",
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
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **account_type** | STRING | 50 | YES | Specifies the type of accounts to be retrieved. Values can be. Values can be: <ol><li>```FOSA```</li><li>```BOSA```</li><li>```WITHDRAWABLE``` NB: WITHDRAWABLE accounts is a sub set of FOSA</li></ol> |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:<ol><li>```MSISDN```</li></ol> |
| **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | 
| **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | 
| **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:<ol><li>```APP_ID```</li><li>```IMSI```</li></ol> |
| **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier |

## Response

### Response Data Structure

The following is a specification of expected response

```json
{
	"request_status": "SUCCESS/INCORRECT_PIN/ERROR",
	"accounts": [
		{
			"account_name": "Salary Account",
			"account_label": "Salary Account (41-02392-0093-01)",
			"account_number": "41-02392-0093-01",
			"account_balance": 1600.00
		},
		{
			"account_name": "Salary Account",
			"account_label": "Salary Account (41-02392-0093-01)",
			"account_number": "41-02392-0093-01",
			"account_balance": 250000.00
		}
	]
}
```

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:<ol><li>```SUCCESS```</li><li>```INCORRECT_PIN```</li><li>```ERROR```</li></ol> |
| **accounts** | LIST | | YES | Specifies the list accounts of a Mobile Banking user | 
| **account_name** | STRING | 100 | YES | Specifies the account name of the Mobile Banking user's account | 
| **account_label** | STRING | 100 | YES | Specifies the label of the account. This will be displayed to the user. | 
| **account_number** | STRING | 50 | YES | Specifies the account number of the Mobile Banking user's account | 
| **account_balance** | DOUBLE | | YES | Specifies the balance of the account |
