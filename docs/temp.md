# **SYSTEM INTEGRATION DOCUMENT**

**FOR**

# **MOBILE BANKING INTERFACE**

**BY**

# **MINTEL SOLUTIONS LIMITED**

**P.O. Box 1018 – 00606 Nairobi, Kenya**

**Email: info@mintel.co.ke**

**Date: 28 April 2021**

**Document Control**

**Preparation**

| | **Name** | **Title** | **Date** |
| --- | --- | --- | --- |
| **Prepared By:** | Derek Mutende | | 28 April 2021 |
| **Reviewed By:** | Moses Magero | | 28 April 2021 |

**Distribution List**

| **Name** | **Organization** | **Title** |
| --- | --- | --- |
| **Mintel Solutions Limited Team** | Mintel Solutions Limited | |
| | | |

**Release Version**

| **Version** | **Date Released** | **Pages Affected** | **Remarks** |
| --- | --- | --- | --- |
| **0.1** | 28 April 2021 | All | 1st release for internal review |

**Contact Details**

We welcome any enquiries regarding this document, its content, structure, or scope. These should be directed to:

| **Director** | **Software Engineer** |
| --- | --- |
| **Name:** | Moses Magero | **Name:** | Derek Mutende |
| **Telephone:** | +254 721 913 958 | **Telephone:** | +254 713 000 249 |
| **Mobile:** | +254 721 913 958 | **Mobile:** | +254 713 000 249 |
| **Email:** | mosesmagero@mintel.co.ke | **Email:** | derekmutende@mintel.co.ke |

© 2009 Mintel Solutions Limited. The material contained in this document, including all attachments, is confidential and the copyright of Mintel Solutions Limited. No part may be reproduced, used or distributed for any purpose other than the purpose for which it is issued, without the prior written consent of Mintel Solutions Limited.

1.

# **Contents**

**[1.](#_Toc69687644)****DOCUMENT OVERVIEW 1**

[1.1.Intended Audience 1](#_Toc69687645)

**[2](#_Toc69687646)****Available APIs 2**

[2.1Check User 2](#_Toc69687647)

[2.1.1Request Structure 2](#_Toc69687648)

[2.1.2Request Data Definition 2](#_Toc69687649)

[2.1.3Response Structure 3](#_Toc69687650)

[2.1.4Response Data Definition 3](#_Toc69687651)

[2.2MO Check User 4](#_Toc69687652)

[2.2.1Request Structure 4](#_Toc69687653)

[2.2.2Request Data Definition 4](#_Toc69687654)

[2.2.3Response Structure 4](#_Toc69687655)

[2.2.4Response Data Definition 5](#_Toc69687656)

[2.3Login 6](#_Toc69687657)

[2.3.1Request Structure 6](#_Toc69687658)

[2.3.2Request Data Definition 6](#_Toc69687659)

[2.3.3Response Structure 7](#_Toc69687660)

[2.3.4Response Data Definition 7](#_Toc69687661)

[2.4Get Auth Security Parameters 8](#_Toc69687662)

[2.4.1Request Structure 8](#_Toc69687663)

[2.4.2Request Data Definition 8](#_Toc69687664)

[2.4.3Response Structure 9](#_Toc69687665)

[2.4.4Response Data Definition 9](#_Toc69687666)

[2.5Set Auth Security Parameters 11](#_Toc69687667)

[2.5.1Request Structure 11](#_Toc69687668)

[2.5.2Request Data Definition 11](#_Toc69687669)

[2.5.3Response Structure 12](#_Toc69687670)

[2.5.4Response Data Definition 13](#_Toc69687671)

[2.6Set PIN 14](#_Toc69687672)

[2.6.1Request Structure 14](#_Toc69687673)

[2.6.2Request Data Definition 14](#_Toc69687674)

[2.6.3Response Structure 15](#_Toc69687675)

[2.6.4Response Data Definition 15](#_Toc69687676)

[2.7Change PIN 16](#_Toc69687677)

[2.7.1Request Structure 16](#_Toc69687678)

[2.7.2Request Data Definition 16](#_Toc69687679)

[2.7.3Response Structure 17](#_Toc69687680)

[2.7.4Response Data Definition 17](#_Toc69687681)

[2.8Activate Mobile App 18](#_Toc69687682)

[2.8.1Request Structure 18](#_Toc69687683)

[2.8.2Response Data Definition 18](#_Toc69687684)

[2.8.3Response Structure 19](#_Toc69687685)

[2.8.4Response Data Definition 19](#_Toc69687686)

[2.9Deactivate Mobile App 20](#_Toc69687687)

[2.9.1Request Structure 20](#_Toc69687688)

[2.9.2Response Data Definition 20](#_Toc69687689)

[2.9.3Response Structure 21](#_Toc69687690)

[2.9.4Response Data Definition 21](#_Toc69687691)

[2.10Get User Details 22](#_Toc69687692)

[2.10.1Request Structure 22](#_Toc69687693)

[2.10.2Request Data Definition 22](#_Toc69687694)

[2.10.3Response Structure 23](#_Toc69687695)

[2.10.4Response Data Definition 23](#_Toc69687696)

[2.11Get Accounts 25](#_Toc69687697)

[2.11.1Request Structure 25](#_Toc69687698)

[2.11.2Request Data Definition 25](#_Toc69687699)

[2.11.3Response Structure 26](#_Toc69687700)

[2.11.4Response Data Definition 26](#_Toc69687701)

[2.12Account Balance Enquiry 28](#_Toc69687702)

[2.12.1Request Structure 28](#_Toc69687703)

[2.12.2Request Data Definition 28](#_Toc69687704)

[2.12.3Response Structure 29](#_Toc69687705)

[2.12.4Response Data Definition 29](#_Toc69687706)

[2.13MO Account Balance Enquiry 31](#_Toc69687707)

[2.13.1Request Structure 31](#_Toc69687708)

[2.13.2Request Data Definition 31](#_Toc69687709)

[2.13.3Response Structure 32](#_Toc69687710)

[2.13.4Response Data Definition 32](#_Toc69687711)

[2.14Account Statement 33](#_Toc69687712)

[2.14.1Request Structure 33](#_Toc69687713)

[2.14.2Request Data Definition 33](#_Toc69687714)

[2.14.3Response Structure 35](#_Toc69687715)

[2.14.4Response Data Definition 35](#_Toc69687716)

[2.15Withdrawal 37](#_Toc69687717)

[2.15.1Request Structure 37](#_Toc69687718)

[2.15.2Request Data Definition 38](#_Toc69687719)

[2.15.3Response Structure 39](#_Toc69687720)

[2.15.4Response Data Definition 39](#_Toc69687721)

[2.16Withdrawal Result 40](#_Toc69687722)

[2.16.1Request Structure 40](#_Toc69687723)

[2.16.2Request Data Definition 40](#_Toc69687724)

[2.16.3Response Structure 41](#_Toc69687725)

[2.16.4Response Data Definition 41](#_Toc69687726)

[2.17Internal Funds Transfer 43](#_Toc69687727)

[2.17.1Request Structure 43](#_Toc69687728)

[2.17.2Request Data Definition 43](#_Toc69687729)

[2.17.3Response Structure 44](#_Toc69687730)

[2.17.4Response Data Definition 45](#_Toc69687731)

[2.18Deposit 46](#_Toc69687732)

[2.18.1Request Structure 46](#_Toc69687733)

[2.18.2Request Data Definition 46](#_Toc69687734)

[2.18.3Response Structure 47](#_Toc69687735)

[2.18.4Response Data Definition 47](#_Toc69687736)

[2.19Get Loan Types 49](#_Toc69687737)

[2.19.1Request Structure 49](#_Toc69687738)

[2.19.2Request Data Definition 49](#_Toc69687739)

[2.19.3Response Structure 50](#_Toc69687740)

[2.19.4Response Data Definition 50](#_Toc69687741)

[2.20Check Loan Limit 51](#_Toc69687742)

[2.20.1Request Structure 51](#_Toc69687743)

[2.20.2Request Data Definition 51](#_Toc69687744)

[2.20.3Response Structure 52](#_Toc69687745)

[2.20.4Response Data Definition 52](#_Toc69687746)

[2.21Loan Application 53](#_Toc69687747)

[2.21.1Request Structure 53](#_Toc69687748)

[2.21.2Request Data Definition 53](#_Toc69687749)

[2.21.3Response Structure 54](#_Toc69687750)

[2.21.4Response Data Definition 54](#_Toc69687751)

[2.22Loans in Service 56](#_Toc69687752)

[2.22.1Request Structure 56](#_Toc69687753)

[2.22.2Request Data Definition 56](#_Toc69687754)

[2.22.3Response Structure 57](#_Toc69687755)

[2.22.4Response Data Definition 57](#_Toc69687756)

[2.23Loan Statement 59](#_Toc69687757)

[2.23.1Request Structure 59](#_Toc69687758)

[2.23.2Request Data Definition 59](#_Toc69687759)

[2.23.3Response Structure 61](#_Toc69687760)

[2.23.4Response Data Definition 61](#_Toc69687761)

[2.24Get Loan Guarantors 63](#_Toc69687762)

[2.24.1Request Structure 63](#_Toc69687763)

[2.24.2Request Data Definition 63](#_Toc69687764)

[2.24.3Response Structure 64](#_Toc69687765)

[2.24.4Response Data Definition 64](#_Toc69687766)

[2.25Get Loans Guaranteed 66](#_Toc69687767)

[2.25.1Request Structure 66](#_Toc69687768)

[2.25.2Request Data Definition 66](#_Toc69687769)

[2.25.3Response Structure 67](#_Toc69687770)

[2.25.4Response Data Definition 68](#_Toc69687771)

[2.26Add Loan Guarantor 70](#_Toc69687772)

[2.26.1Request Structure 70](#_Toc69687773)

[2.26.2Request Data Definition 70](#_Toc69687774)

[2.26.3Response Structure 72](#_Toc69687775)

[2.26.4Response Data Definition 72](#_Toc69687776)

[2.27Get Loan Guarantorship Requests 73](#_Toc69687777)

[2.27.1Request Structure 73](#_Toc69687778)

[2.27.2Request Data Definition 73](#_Toc69687779)

[2.27.3Response Structure 74](#_Toc69687780)

[2.27.4Response Data Definition 74](#_Toc69687781)

[2.28Accept/Reject Loan Guarantorship Request 76](#_Toc69687782)

[2.28.1Request Structure 76](#_Toc69687783)

[2.28.2Request Data Definition 76](#_Toc69687784)

[2.28.3Response Structure 77](#_Toc69687785)

[2.28.4Response Data Definition 77](#_Toc69687786)

**[3](#_Toc69687787)****NOTES 78**

[3.1Authentication 78](#_Toc69687788)

[3.2CBS Generated Messages 83](#_Toc69687789)

**[4](#_Toc69687790)****APPENDIX 84**

[4.1Auth Parameters XML Snippet 84](#_Toc69687791)

1.

# DOCUMENT OVERVIEW

This document specifies the Xtreme Mobile Banking API. The following are covered on this document:

1. Check User
2. MO Check User
3. Login
4. Get Auth Security Parameters
5. Set Auth Security Parameters
6. Set PIN
7. Change PIN
8. Activate Mobile App
9. Deactivate Mobile App
10. Get User Details
11. Get Accounts
12. Account Balance Enquiry
13. MO Account Balance Enquiry
14. Account Statement
15. Withdrawal
16. Withdrawal Result
17. Internal Funds Transfer
18. Deposit
19. Get Loan Types
20. Check Loan Limit
21. Loan Application
22. Loans in Service
23. Loan Statement
24. Get Loan Guarantors
25. Get Loans Guaranteed
26. Add Loan Guarantor
27. Get Loan Guarantorship Requests
28. Accept/Reject Loan Guarantorship Request

1.

## Intended Audience

The intended audience is any organization provided access to the Xtreme Mobile Banking API.

1.

# Available APIs

1.

## Check User

This API will allow an application check whether a mobile number is registered to use Mobile Banking

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

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
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. IMSI
2. APP_ID | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier |

```json
{
   "user_status": "SUSPENDED",
   "auth_action_valid_date": "2020-12-08 09:34:33"
}
```
Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Expected** | **Description** |
| --- | --- | --- | --- | --- |
| **user_status** | STRING | 50 | YES | Specifies status of the Mobile Banking accountValues can be:

1. ACTIVE
2. SUSPENDED
3. LOCKED
4. INVALID_DEVICE_IDENTIFIER
5. NOT_FOUND
6. ERROR | | **auth_action_valid_date** | DATETIME | | OPTIONAL | Specifies the date up to which the Mobile Banking account has been SUSPENDED. Should be in ISO format – yyyy:MM:dd HH:mm:ss |


## MO Check User

This API will allow an application check whether a mobile number is registered to use Mobile Banking

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "MO_CHECK_USER",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. |

    1.

        1. {
        2. "user_status": "FOUND/NOT_FOUND"
        3. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Expected** | **Description** |
| --- | --- | --- | --- | --- |
| **user_status** | STRING | 50 | YES | Specifies status of the Mobile Banking accountValues can be:

1. FOUND
2. NOT_FOUND |

1.

## Login

This API will allow an application check authenticate a Mobile Banking user

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

          1. {
          2. "action": "LOGIN",
          3. "payload": {
          4. "api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",
          5. "identifier_type": "MSISDN",
          6. "identifier": "254712345678",
          7. "pin": "1234",
          8. "device_identifier_type": "IMSI/APP_ID",
          9. "device_identifier": "1099200912931023"
          10. }
          11. }

Request Structure

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. IMSI

1. APP_ID | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier |

    1.

        1. {
        2. "login_status": "SUSPENDED",
        3. "auth_action_valid_date": "2020-12-08 09:34:33",
        4. "login_attempts": 15
        5. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **login_status** | STRING | 50 | YES | Login status. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. INVALID_DEVICE_IDENTIFIER
4. MOBILE_APP_INACTIVE
5. SET_PIN
6. SUSPENDED
7. LOCKED | | **auth_action_valid_date** | DATETIME | | OPTIONAL | Specifies the date up to which the Mobile Banking account has been SUSPENDED. Should be in ISO format – yyyy:MM:dd HH:mm:ss | | **login_attempts** | INTEGER | 10 | YES | Number of times the Mobile Banking user has tried logging in | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user |

1.

## Get Auth Security Parameters

This API will allow an application get Login Security Parameters tied to a Mobile Banking user

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "GET_AUTH_SECURITY_PARAMETERS",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023",

"auth_security_type": "PASSWORD/OTP"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. IMSI

1. APP_ID | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **auth_security_type** | STRING | 50 | YES | Specifies the type of Auth Security parameters are needed.Values can be:
1. PASSWORD
2. OTP |

    1.

### Response Structure

{

"request_status": "SUCCESS/INCORRECT_PIN/ERROR",

"auth_security_type": " PASSWORD/OTP",

"auth_action": "SUSPEND",

"auth_action_valid_date": "2020-12-08 09:34:33",

"auth_flag": "SECOND_SUSPENSION",

"auth_attempts": 15

}

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. ERROR | | **auth_security_type** | STRING | 50 | YES | Specifies the type of Auth Security parameters are needed.Values can be:
1. PASSWORD
2. OTP | | **auth_action** | STRING | 50 | YES | Specifies the current auth action set. Values can be:
1. NONE
2. WARN
3. SUSPEND
4. LOCK | | **auth_action_valid_date** | DATETIME | | OPTIONAL | Specifies the date up to which the Mobile Banking account has been SUSPENDED. Should be in ISO format – yyyy:MM:dd HH:mm:ss | | **auth_flag** | STRING | 100 | YES | Specifies the current auth flag set. The auth_flag is the NAME of the Auth Attempt that has been violated/triggered. This is as per the Auth Security XML. See sample in Appendix section of the document. | | **auth_attempts** | INTEGER | 10 | YES | Number of times the Mobile Banking user has tried logging in or entering OTP. This depends on the auth_security_type |

1.

## Set Auth Security Parameters

This API will allow an application set Login Security Parameters tied to a Mobile Banking user

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

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

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. IMSI

1. APP_ID | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **auth_security_type** | STRING | 50 | YES | Specifies the type of Auth Security parameters are needed.Values can be:
1. PASSWORD
2. OTP | | **auth_action** | STRING | 50 | YES | Specifies the current auth action to be set. Values can be:
1. NONE
2. WARN
3. SUSPEND
4. LOCK | | **auth_action_valid_date** | DATETIME | | OPTIONAL | Specifies the date up to which the Mobile Banking account has been SUSPENDED. Should be in ISO format – yyyy:MM:dd HH:mm:ss | | **auth_flag** | STRING | 100 | YES | Specifies the current auth flag to be set. The auth_flag is the NAME of the Auth Attempt that has been violated/triggered. This is as per the Auth Security XML. See sample in Appendix section of the document. | | **auth_attempts** | INTEGER | 10 | YES | Number of times the Mobile Banking user has tried logging in or entering OTP. This depends on the auth_security_type | | **date_time** | DATETIME | | YES | Specifies the date the set parameters request was initiated. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

    1.

        1. {
        2. "set_auth_security_parameters_status": "SUCCESS ",
        3. "set_auth_security_parameters_status_description": "Auth Status Parameters set successfully",
        4. "date_time": "2020-12-08 09:34:33"
        5. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **set_auth_security_parameters_status** | STRING | 50 | YES | Specifies the status of the requestValues can be:

1. SUCCESS
2. INCORRECT_PIN
3. ERROR | | **set_auth_security_parameters_status_description** | STRING | 200 | YES | Specifies the status description | | **date_time** | DATETIME | | YES | Specifies the date the set parameters response was initiated. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

1.

## Set PIN

This API will allow an application do KYC and set the New PIN for a Mobile Banking user

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "SET_PIN",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023",

"new_pin": "1234",

"identity_type": "NATIONAL_ID",

"identity": "23994857"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Current MBanking PIN of the member | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. IMSI
2. APP_ID | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **new_pin** | STRING | 50 | YES | New MBanking PIN of the member | | **identity_type** | STRING | 50 | YES | Specifies the Identity type used by the member:
1. NATIONAL_ID
2. PASSPORT_NO
3. DRIVING_LICENSE | | **identity** | STRING | 50 | YES | Specifies the actual identity of the member |

    1.

        1. {
        2. "set_pin_status": "SUCCESS/INVALID_ACCOUNT/INCORRECT_PIN/INVALID_NEW_PIN/ERROR",
        3. "set_pin_status_description": "PIN set successfully"
        4. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **set_pin_status** | STRING | 50 | YES | Specifies the status of the requestValues can be:

1. SUCCESS
2. INVALID_ACCOUNT
3. INCORRECT_PIN
4. INVALID_NEW_PIN
5. ERROR | | **set_pin_status_description** | STRING | 200 | YES | Specifies the status description |

1.

## Change PIN

This API will allow an application to facilitate change PIN for a Mobile Banking user

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

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

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Current Mobile Banking PIN of the member | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. IMSI
2. APP_ID | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **new_pin** | STRING | 50 | YES | New Mobile Banking PIN of the member |

    1.

### Response Structure

{

"change_pin_status": "SUCCESS/INVALID_ACCOUNT/INCORRECT_PIN/INVALID_NEW_PIN/ERROR",

"change_pin_status_description": "PIN changed successfully"

}

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **change_pin_status** | STRING | 50 | YES | Specifies the status of the requestValues can be:

1. SUCCESS
2. INVALID_ACCOUNT
3. INCORRECT_PIN
4. INVALID_NEW_PIN
5. ERROR | | **change_pin_status_description** | STRING | 200 | YES | Specifies the status description |

1.

## Activate Mobile App

This API will allow an application to facilitate Activation of Mobile App for a Mobile Banking user.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

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

}`

}

Request Data Definition

Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. Values can be:

1. ACTIVATE_MOBILE_APP | | **payload** | OBJECT | | YES | Contains the payload data | | **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. | | **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:
1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **app_id** | STRING | 100 | YES | Specifies the App ID to be activated. | | **activate_with_kyc** | STRING | 10 | OPTIONAL | Specify whether Mobile App activation requires KYC. Values can be:
1. YES
2. NO | | **identity_type** | STRING | 50 | OPTIONAL | Specifies the Identity type used by the member. Should be specified if activate_with_kyc is YES. Values can be:
1. NATIONAL_ID
2. PASSPORT_NO
3. DRIVING_LICENSE | | **identity** | STRING | 50 | OPTIONAL | Specifies the actual identity of the member. Should be specified if activate_with_kyc is YES. |

    1.

        1. {
        2. "mobile_app_activation_status": "SUCCESS ",
        3. "mobile_app_activation_status_description": "Mobile App Activated successfully"
        4. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **mobile_app_activation_status** | STRING | 50 | YES | Specifies the status of the requestValues can be:

1. SUCCESS
2. INCORRECT_PIN
3. INVALID_ACCOUNT
4. ERROR | | **mobile_app_activation_status_description** | STRING | 200 | YES | Specifies the status description |

1.

## Deactivate Mobile App

This API will allow an application to facilitate Deactivation of Mobile App for a Mobile Banking user.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

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

Request Data Definition

Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. Values can be:

1. DEACTIVATE_MOBILE_APP | | **payload** | OBJECT | | YES | Contains the payload data | | **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. | | **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:
1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. IMSI
2. APP_ID | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier

|

    1.

          1. {
          2. "mobile_app_activation_status": "SUCCESS ",
          3. "mobile_app_activation_status_description": "Mobile App Deactivated successfully"
          4. }

Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **mobile_app_activation_status** | STRING | 50 | YES | Specifies the status of the requestValues can be:

1. SUCCESS
2. INCORRECT_PIN
3. INVALID_ACCOUNT
4. ERROR | | **mobile_app_activation_status_description** | STRING | 200 | YES | Specifies the status description |

1.

## Get User Details

This API will get details for a Mobile Banking user.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

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

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **user_identifier_type** | STRING | 50 | YES | Mobile Banking account user identifier type. Values can be:
1. MEMBER_NUMBER
2. MSISDN
3. NATIONAL_ID
4. ACCOUNT_NUMBER
5. PASSPORT_NO
6. DRIVING_LICENSE | | **user_identifier** | STRING | 50 | YES | Mobile Banking account user identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier |

    1.

### Response Structure

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

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:

1. SUCCESS
2. USER_NOT_FOUND
3. INCORRECT_PIN
4. ERROR | | **member_number** | STRING | 50 | YES | Specifies the member umber of the Mobile Banking user | | **full_name** | STRING | 100 | YES | Specifies the full name of the Mobile Banking user | | **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:
1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **identity_type** | STRING | 50 | YES | Specifies the Identity type used by the member:
1. NATIONAL_ID
2. PASSPORT_NO
3. DRIVING_LICENSE | | **identity** | STRING | 50 | YES | Specifies the actual identity of the member | | **ift_dest_accounts** | LIST | | YES | Specifies the list accounts that can allow for Internal Funds Transfer | | **account_name** | STRING | 100 | YES | Specifies the account name of the Mobile Banking user's account | | **account_label** | STRING | 100 | YES | Specifies the label of the account. This will be displayed to the user. | | **account_number** | STRING | 50 | YES | Specifies the account number of the Mobile Banking user's account |

1.

## Get Accounts

This API will get accounts for a Mobile Banking user.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

          1. {
          2. "action": "GET_ACCOUNTS",
          3. "payload": {
          4. "api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",
          5. "account_type": "FOSA/BOSA/WITHDRAWABLE",
          6. "identifier_type": "MSISDN",
          7. "identifier": "254712345678",
          8. "pin": "1234",
          9. "device_identifier_type": "IMSI/APP_ID",
          10. "device_identifier": "1099200912931023"
          11. }
          12. }

Request Structure

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **account_type** | STRING | 50 | YES | Specifies the type of accounts to be retrieved. Values can be. Values can be:

1. FOSA
2. BOSA
3. WITHDRAWABLE NB: WITHDRAWABLE accounts is a sub set of FOSA | | **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:
1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier |

    1.

### Response Structure

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

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. ERROR | | **accounts** | LIST | | YES | Specifies the list accounts of a Mobile Banking user | | **account_name** | STRING | 100 | YES | Specifies the account name of the Mobile Banking user's account | | **account_label** | STRING | 100 | YES | Specifies the label of the account. This will be displayed to the user. | | **account_number** | STRING | 50 | YES | Specifies the account number of the Mobile Banking user's account | | **account_balance** | DOUBLE | | YES | Specifies the balance of the account |

1.

## Account Balance Enquiry

This API will get account balances for a Mobile Banking user.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "ACCOUNT_BALANCE_ENQUIRY",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023",

"account_type": "FOSA"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

      1. MSISDN

|
| **identifier** | STRING | 50 | YES | Mobile Banking account identifier. |
| **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user |
| **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:

      1. APP_ID
      2. IMSI

|
| **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier |
| **account_type** | STRING | 50 | YES | Specifies account type. Values can be:

      1. FOSA
      2. BOSA
      3. LOAN
      4. ALL

|

    2.

### Response Structure

{

"request_status": "SUCCESS/INCORRECT_PIN/ERROR",

"account_balances": [

{

"account_type": "BOSA",

"account_name": "Bosa Deposit",

"account_label": " Bosa Deposit A/C(001)"

"account_number": "001",

"account_balance": 1200000.00

},

{

"account_type": "FOSA",

"account_name": "Salary Account",

"account_label": " Salary A/C(5-02-00009-00)"

"account_number": "5-02-00009-00",

"account_balance": 3300.00

}

]

}

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. ERROR | | **account_balances** | LIST | | YES | Specifies the list account balances of a Mobile Banking user | | **account_type** | STRING | 50 | YES | Specifies the type of account. Values can be. Values can be:
1. FOSA
2. BOSA | | **account_name** | STRING | 100 | YES | Specifies the account name of the Mobile Banking user's account | | **account_label** | STRING | 100 | YES | Specifies the label of the account. This will be displayed to the user. | | **account_number** | STRING | 50 | YES | Specifies the account number of the Mobile Banking user's account | | **account_balance** | DOUBLE | | YES | Specifies the account balance of the Mobile Banking user's account |

1.

## MO Account Balance Enquiry

This API will get account balances for a Mobile Banking user.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "MO_ACCOUNT_BALANCE_ENQUIRY",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. |

    1.

### Response Structure

{

"request_status": "SUCCESS/ERROR",

"account_balances": [

{

"account_type": "BOSA",

"account_name": "Bosa Deposit",

"account_label": " Salary A/C(001)"

"account_number": "001",

"account_balance": 1200000.00

},

{

"account_type": "FOSA",

"account_name": "Salary Account",

"account_label": " Salary A/C(5-02-00009-00)"

"account_number": "5-02-00009-00",

"account_balance": 3300.00

}

]

}

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:

1. SUCCESS
2. ERROR | | **account_balances** | LIST | | YES | Specifies the list account balances of a Mobile Banking user | | **account_type** | STRING | 50 | YES | Specifies the type of account. Values can be. Values can be:
1. FOSA
2. BOSA | | **account_name** | STRING | 100 | YES | Specifies the account name of the Mobile Banking user's account | | **account_label** | STRING | 100 | YES | Specifies the label of the account. This will be displayed to the user. | | **account_number** | STRING | 50 | YES | Specifies the account number of the Mobile Banking user's account | | **account_balance** | DOUBLE | | YES | Specifies the account balance of the Mobile Banking user's account |

1.

## Account Statement

This API will get account statement for a Mobile Banking user.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

          1. {
          2. "action": "ACCOUNT_STATEMENT",
          3. "payload": {
          4. "api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",
          5. "identifier_type": "MSISDN",
          6. "identifier": "254712345678",
          7. "pin": "1234",
          8. "device_identifier_type": "IMSI/APP_ID",
          9. "device_identifier": "1099200912931023",
          10. "statement_type": "MINI_STATEMENT/FULL_STATEMENT",
          11. "max_number_of_transactions": 100,
          12. "start_date": "2021-01-01 20:00:00",
          13. "end_date": "2021-01-03 20:00:00",
          14. "account_type": "FOSA/BOSA",
          15. "account_number": "41-02392-0093-01"
          16. }
          17. }

Request Structure

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **statement_type** | STRING | 50 | YES | Specifies the type of Account Statement to get. Values can be:
1. MINI_STATEMENT
2. FULL_STATEMENT | | **max_number_of_transactions** | INTEGER | | YES | Specifies the maximum number of transactions to get | | **start_date** | DATETIME | | OPTIONAL | Specifies the start date for getting transactions. Should be specified when statement type is FULL_STATEMENT. Should be in ISO format – yyyy:MM:dd HH:mm:ss | | **end_date** | DATETIME | | OPTIONAL | Specifies the end date for getting transactions. Should be specified when statement type is FULL_STATEMENT. Should be in ISO format – yyyy:MM:dd HH:mm:ss | | **account_type** | STRING | 50 | YES | Specifies the type of account. Values can be. Values can be:
1. FOSA
2. BOSA | | **account_number** | STRING | 50 | YES | Specifies the account number of the Mobile Banking user's account |

    1.

### Response Structure

{

"request_status": "SUCCESS/INCORRECT_PIN/ERROR",

"account_type": "FOSA/BOSA",

"account_name": "Salary Account",

"account_number": "41-02392-0093-01",

"available_balance": 3300.00,

"transactions": [

{

"transaction_reference": "OH50CRUHJK",

"transaction_date": "2021-01-02",

"transaction_time": "13:00:00",

"transaction_amount": -3500.00,

"running_balance": 15350.00,

"transaction_description": "M-PESA Withdrawal from A/C 41-02392-0093-01 to 254724763290",

"other_details": "Withdrawal via Mobile Banking"

},

{

"transaction_reference": "XTREME:9225-40A8F0293DCC",

"transaction_date": "2021-01-03",

"transaction_time": "11:00:00",

"transaction_amount": -10300.00,

"running_balance": 5050.00,

"transaction_description": "ATM Withdrawal from A/C 41-02392-0093-01",

"other_details": "Withdrawal via ATM - Nyahururu Terminal"

}

]

}

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. ERROR | | **account_type** | STRING | 50 | YES | Specifies the type of account. Values can be. Values can be:
1. FOSA
2. BOSA | | **account_name** | STRING | 100 | YES | Specifies the account name of the Mobile Banking user's account | | **account_number** | STRING | 50 | YES | Specifies the account number of the Mobile Banking user's account | | **available_balance** | DOUBLE | | YES | Specifies the account available balance of the Mobile Banking user's account | | **transactions** | LIST | | YES | Specifies the list of transactions of a Mobile Banking user | | **transaction_reference** | STRING | 200 | YES | Specifies the reference of the transaction | | **transaction_date** | DATE | | YES | Specifies the date of the transaction. Should be in ISO format – yyyy-MM-dd | | **transaction_time** | TIME | | YES | Specifies the time of the transaction. Should be in ISO format – HH:mm:ss | | **transaction_amount** | DOUBLE | | YES | Specifies the amount of the transaction | | **running_balance** | DOUBLE | | YES | Specifies the running balance after the transaction | | **
   transaction_description** | STRING | 250 | OPTIONAL | Specifies the description of the transaction | | **other_details** | STRING | 250 | OPTIONAL | Specifies other details of the transaction like location etc. |

1.

## Withdrawal

This API will facilitate withdrawal from a Mobile Banking user's account.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action":"WITHDRAWAL",

"payload":{

"api_request_id":"df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type":"MSISDN",

"identifier":"254712345678",

"pin":"1234",

"device_identifier_type":"IMSI/APP_ID",

"device_identifier":"1099200912931023",

"transaction_reference":"ef6582cc-b972-457a-998f-7fb6fa932167",

"transaction_beneficiary_details":{

"identifier_type":"MSISDN",

"identifier":"254712345678",

"name":"John Doe Omolo",

"other_details":""

},

"account_number":"41-02392-0093-01",

"amount":1500.00,

"category":"MPESA_WITHDRAWAL",

"transaction_description":"Cash Withdrawal by John Doe Omolo (254712345678) to 254712345678",

"source_reference":"USSD_36027106_8",

"request_application":"MAPP",

"source_application":"MBANKING",

"transaction_date_time":"2020-01-02 12:34:45"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **transaction_reference** | STRING | 150 | YES | Specifies the unique transaction identifier for correlation | | **account_number** | STRING | 50 | YES | Specifies the account to be debited | | **transaction_beneficiary_details** | OBJECT | | YES | Contains beneficiary details as per the Mobile Money service provider. | | **identifier_type** | STRING | 50 | YES | Specifies the identifier type of the beneficiary. Values can be:
1. MSISDN
2. ACCOUNT_NO | | **identifier** | STRING | 50 | YES | Specifies the identifier of the beneficiary | | **name** | STRING | 50 | YES | Specifies the name of the beneficiary | | **other_details** | STRING | 2000 | NO | Contains other details of the beneficiary if present. **NB:** The details are as an XML String | | **amount** | DOUBLE | | YES | Specifies the amount to be debited | | **category** | STRING | 50 | YES | Specifies the category. Values can be:
1. MPESA_WITHDRAWAL
2. BILL_PAYMENT
3. BANK_TRANSFER
4. AIRTIME_PURCHASE | | **transaction_description** | STRING | 250 | YES | Specifies the transaction description/remark | | **source_reference** | STRING | 150 | YES | Specifies the reference of the source of the transaction for correlation | | **request_application** | STRING | 50 | YES | Specifies the request application | | **source_application** | STRING | 50 | YES | Specifies the source application | | **transaction_date_time** | DATETIME | | YES | Specifies the date and time the transaction was initiated. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

    1.

        1. {
        2. "transaction_status": "SUCCESS ",
        3. "transaction_status_description": "Withdrawal processed successfully",
        4. "transaction_date_time": "2020-01-02 12:34:46"
        5. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **transaction_status** | STRING | 50 | YES | Specifies the status of the transaction. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. INSUFFICIENT_BAL
4. TRANSACTION_EXISTS
5. ACCOUNT_NOT_ACTIVE
6. BLOCKED
7. INVALID_ACCOUNT
8. WITHDRAWWAL_LIMIT_VIOLATION
9. ERROR | | **transaction_status_description** | STRING | 200 | YES | Specifies the status description | | **transaction_status_date_time** | DATETIME | | YES | Specifies the date and time of the transaction status. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

1.

## Withdrawal Result

This API will facilitate completing/reversing a withdrawal transaction.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "WITHDRAWAL_RESULT",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"transaction_reference": "ef6582cc-b972-457a-998f-7fb6fa932167",

"transaction_status": "CONFIRMED/REVERSE_CONFIRMED",

"transaction_status_description": "Transaction Completed Successfully",

"transaction_beneficiary_details": {

"identifier_type": "MSISDN",

"identifier":"254712345678",

"name": "JOHN DOE",

"other_details": ""

},

"destination_reference": "OH50CRUHJK",

"transaction_date_time": "2020-01-02 12:34:45"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **transaction_reference** | STRING | 150 | YES | Specifies the unique transaction identifier for correlation |
| **transaction_status** | STRING | 50 | YES | Specifies status of the transaction. Values can be:

1. CONFIRMED
2. REVERSE_CONFIRMED | | **transaction_status_description** | STRING | 250 | YES | Specifies status description of the transaction | | **transaction_beneficiary_details** | OBJECT | | YES | Contains beneficiary details as per the Mobile Money service provider. | | **identifier_type** | STRING | 50 | YES | Specifies the identifier type of the beneficiary | | **identifier** | STRING | 50 | YES | Specifies the identifier of the beneficiary | | **name** | STRING | 50 | YES | Specifies the name of the beneficiary as per the Mobile Money service provider. | | **other_details** | STRING | 2000 | NO | Contains other details of the beneficiary if present. **NB:** The details are as an XML String | | **destination_reference** | STRING | 150 | YES | Specifies the reference of the destination of the transaction for correlation | | **transaction_date_time** | DATETIME | | YES | Specifies the date and time the transaction was initiated. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

    1.

### Response Structure

{

"transaction_status": "SUCCESS/TRANSACTION_DOES_NOT_EXIST/ERROR",

"transaction_status_description": "Result processed successfully",

"transaction_status_date_time": "2020-01-02 12:34:46"

}

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **transaction_status** | STRING | 50 | YES | Specifies the status of the transaction. Values can be:

1. SUCCESS
2. TRANSACTION_DOES_NOT_EXIST
3. ERROR | | **transaction_status_description** | STRING | 200 | YES | Specifies the status description | | **transaction_status_date_time** | DATETIME | | YES | Specifies the date and time of the transaction status. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

1.

## Internal Funds Transfer

This API will facilitate transfer of funds from a member's account to their own account or another member's account. Within the SACCO. It will also facilitate loan repayment.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "IFT_ACCOUNT_TO_ACCOUNT",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023",

"transaction_reference": "ef6582cc-b972-457a-998f-7fb6fa932167",

"source_account": "41-02392-0093-01",

"destination_account": "U:203813:03:2020",

"amount": 35000.00,

"source_reference": "USSD_36027106_8",

"request_application": "USSD",

"source_application": "MBANKING",

"transaction_description": "Loan Repayment Internal Funds Transfer. Source A/C: 41-02392-0093-01 - Destination A/C: U:203813:03:2020",

"transaction_date_time": "2020-01-02 12:34:45"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. Values can be:

1. IFT_ACCOUNT_TO_ACCOUNT
2. IFT_LOAN_REPAYMENT
3. IFT_SCHEMES_DEPOSIT | | **payload** | OBJECT | | YES | Contains the payload data | | **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. | | **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:
1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **transaction_reference** | STRING | 150 | YES | Specifies the unique transaction identifier for correlation | | **source_account** | STRING | 50 | YES | Specifies the FOSA account where the funds will be debited | | **destination_account** | STRING | 50 | YES | For action IFT_ACCOUNT_TO_ACCOUNT - Specifies the FOSA account where the funds will be credited.For action IFT_LOAN_REPAYMENT – Specifies the loan identifier that is being fundedFor action IFT_SCHEMES_DEPOSIT – Specifies the scheme code being deposited | | **amount** | DOUBLE | | YES | Specifies the amount to be transferred | | **source_reference** | STRING | 150 | YES | Specifies the reference of the source of the transaction for correlation | | **request_application** | STRING | 50 | YES | Specifies the request application | | **source_application** | STRING | 50 | YES | Specifies the source
   application | | **transaction_date_time** | DATETIME | | YES | Specifies the date and time the transaction was initiated. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

    1.

### Response Structure

{

"request_status": "SUCCESS ",

"request_status_description": "Internal Funds Transfer request received successfully"

}

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the transaction. Values can be:

1. SUCCESS
2. INVALID_PIN
3. INSUFFICIENT_BAL
4. IFT_REQUEST_EXISTS
5. DEST_ACCOUNT_NOT_ACTIVE
6. ACCOUNT_NOT_FOUND
7. INVALID_SCHEME_CODE
8. ERROR | | **request_status_description** | STRING | 200 | YES | Specifies the status description |

1.

## Deposit

This API will facilitate deposits by a member either to their FOSA/BOSA accounts or repayment of loans.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "FOSA_DEPOSIT/BOSA_DEPOSIT/LOAN_REPAYMENT_DEPOSIT/OTHER_DEPOSIT",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"sender_name": "John Doe Omolo",

"transaction_reference": "PAB9IMA0FJ",

"beneficiary_account": "41-02392-0093-01",

"amount": 2500.00,

"transaction_description": "Pay Bill (1234567) From 254712345678",

"source_reference": "PAB9IMA0FJ",

"request_application": "MPESA_BROKER",

"source_application": "MPESA_BROKER",

"transaction_date_time": "2020-01-02 12:34:45"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. Values can be:

1. FOSA_DEPOSIT
2. BOSA_DEPOSIT
3. LOAN_REPAYMENT_DEPOSIT
4. OTHER_DEPOSIT | | **payload** | OBJECT | | YES | Contains the payload data | | **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. | | **identifier_type** | STRING | 50 | YES | Specifies the sender type doing the deposit. Values can be:
1. MSISDN | | **identifier** | STRING | 50 | YES | Specifies the actual sender identifier of the person doing the deposit | | **sender_name** | STRING | 50 | YES | Specifies the sender name doing the deposit | | **transaction_reference** | STRING | 150 | YES | Specifies the unique transaction identifier for correlation | | **beneficiary_account** | STRING | 50 | YES | For action FOSA_DEPOSIT - Specifies FOSA account to be credited.For action BOSA_DEPOSIT – Specifies BOSA Account to be creditedFor action LOAN_REPAYMENT_DEPOSIT – Specifies Loan Identifier of the loan that is being funded | | **amount** | DOUBLE | | YES | Specifies the amount to be debited | | **transaction_description** | STRING | 250 | YES | Specifies the transaction description/remark | | **source_reference** | STRING | 150 | YES | Specifies the reference of the source of the transaction for correlation | | **request_application** | STRING | 50 | YES | Specifies the request application | | **source_application** |
   STRING | 50 | YES | Specifies the source application | | **transaction_date_time** | DATETIME | | YES | Specifies the date and time the transaction was initiated. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

    1.

        1. {
        2. "transaction_status": "SUCCESS ",
        3. "transaction_status_description": "Deposit processed successfully",
        4. "transaction_destination_reference": "2fc5e950-769b-4942-a748",
        5. "transaction_date_time": "2020-01-02 12:34:46"
        6. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **transaction_status** | STRING | 50 | YES | Specifies the status of the transaction. Values can be:

1. SUCCESS
2. TRANSACTION_EXISTS
3. ERROR | | **transaction_status_description** | STRING | 200 | YES | Specifies the status description | | **transaction_destination_reference** | STRING | 250 | YES | Specifies destination reference of the transaction. This value is from the CBS and helps in correlation. | | **transaction_status_date_time** | DATETIME | | YES | Specifies the date and time of the transaction status. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

1.

## Get Loan Types

This API will get loan types available to a Mobile Banking user.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": " GET_LOAN_TYPES_MOBILE",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier |

    1.

### Response Structure

{

"request_status": "SUCCESS/INCORRECT_PIN/ERROR",

"loan_types": [

{

"loan_type_id": "N",

"loan_type_name": "NORMAL LOAN",

"loan_type_min_ussd_amount": 100.00,

"loan_type_max_ussd_amount": 9999999.00

},

{

"loan_type_id": "R",

"loan_type_name": "SUPA LOAN",

"loan_type_min_ussd_amount": 100.00,

"loan_type_max_ussd_amount": 9999999.00

}

]

}

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:

      1. SUCCESS
      2. INCORRECT_PIN
      3. ERROR

|
| **loan _types** | LIST |
|
| List of loan types supported for Mobile Banking |
| **loan_type_id** | STRING | 50 | YES | Specifies the unique loan type identifier |
| **loan_type_name** | STRING | 100 | YES | Specifies the loan type name |
| **loan_type_min_ussd_amount** | DOUBLE |
| YES | Specifies the minimum amount a member can borrow for the loan type |
| **loan_type_max_ussd_amount** | DOUBLE |
| YES | Specifies the maximum amount a member can borrow for the loan type |

1.

## Check Loan Limit

This API will do appraisal and check loan limit for a Mobile Banking user's account.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "CHECK_LOAN_LIMIT",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023",

"transaction_reference": "ef6582cc-b972-457a-998f-7fb6fa932167",

"loan_name": "SUPA LOAN",

"loan_type_id": "T"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **transaction_reference** | STRING | 150 | YES | Specifies the unique transaction identifier for correlation | | **loan_name** | STRING | 50 | YES | Specifies the loan name | | **loan_type** | STRING | 50 | YES | Specifies the loan type |

    1.

        1. {
        2. "request_status": "SUCCESS/INCORRECT_PIN/ERROR",
        3. "request_status_description": "Check loan limit request received successfully"
        4. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the transaction. Values can be:

1. SUCCESS
2. INVALID_PIN
3. ERROR | | **request_status_description** | STRING | 200 | YES | Specifies the status description |

1.

## Loan Application

This API will facilitate Mobile Banking loan application by a member.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "LOAN_APPLICATION",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023",

"transaction_reference": "ef6582cc-b972-457a-998f-7fb6fa932167",

"loan_type_id": "N",

"amount": 120000.00,

"source_reference": "USSD_36027106_8",

"request_application": "USSD",

"source_application": "MBANKING",

"transaction_date_time": "2020-01-02 12:34:45"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **transaction_reference** | STRING | 150 | YES | Specifies the unique transaction identifier for correlation | | **loan_type_id** | STRING | 50 | YES | Specifies the loan type id of loan being applied | | **amount** | DOUBLE | | YES | Specifies the amount being applied | | **source_reference** | STRING | 150 | YES | Specifies the reference of the source of the transaction for correlation | | **request_application** | STRING | 50 | YES | Specifies the request application | | **source_application** | STRING | 50 | YES | Specifies the source application | | **transaction_date_time** | DATETIME | | YES | Specifies the date and time the transaction was initiated. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

    1.

### Response Structure

{

"request_status": "SUCCESS/INCORRECT_PIN/LOAN_APPLICATION_EXISTS/ERROR",

"request_status_description": "Loan application request received successfully"

}

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the transaction. Values can be:

1. SUCCESS
2. INVALID_PIN
3. LOAN_APPLICATION_EXISTS
4. LOAN_APPLICATION_AMOUNT_LIMIT_VIOLATION
5. TRANSACTION_EXISTS
6. ERROR | | **request_status_description** | STRING | 200 | YES | Specifies the status description |

1.

## Loans in Service

This API will get active Mobile Banking loans tied to a member.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "GET_LOANS_IN_SERVICE",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier |

    1.

### Response Structure

{

"request_status": "SUCCESS/INCORRECT_PIN/ERROR",

"loans": [

{

"loan_id": "N:203813:03:2020",

"loan_type_id": "N",

"loan_type_name": "NORMAL LOAN",

"loan_amount": 120000.00,

"loan_balance": 35000.00,

"installment_amount ": 10000.00,

"loan_defaulted_amount": 0.00,

"loan_issued_date": "2021-01-03 08:45:15",

"loan_end_date": "2021-10-03 08:45:15",

"loan_performance": "PERFORMING/NOT_PERFORMING",

"loan_performance_description": "Loan is performing"

},

{

"loan_id": "U:203813:03:2020",

"loan_type_id": "U",

"loan_type_name": "SUPA LOAN",

"loan_amount": 500000.00,

"loan_balance": 120000.00,

"installment_amount ": 10000.00,

"loan_defaulted_amount": 0.00,

"loan_issued_date": "2021-01-03 08:45:15",

"loan_end_date": "2021-10-03 08:45:15",

"loan_performance": "PERFORMING/NOT_PERFORMING",

"loan_performance_description": "Loan is performing"

}

]

}

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. ERROR | | **loans** | LIST | | | List of a member's Mobile Banking loans | | **loan_id** | STRING | 50 | YES | Specifies the unique loan identifier | | **loan_type_id** | STRING | 50 | YES | Specifies the unique loan type identifier | | **loan_type_name** | STRING | 100 | YES | Specifies the loan type name | | **loan_amount** | DOUBLE | | YES | Specifies the amount a member borrowed | | **loan_balance** | DOUBLE | | YES | Specifies the loan balance | | **installment_amount** | DOUBLE | | OPTIONAL | Specifies the amount due as payment for funding the load, for the current month. i.e. Principal + Interest | | **loan_defaulted_amount** | DOUBLE | | OPTIONAL | Specifies the loan defaulted amount | | **loan_issued_date** | DATETIME | | OPTIONAL | Specifies the date the loan was issued | | **loan_end_date** | DATETIME | | OPTIONAL | Specifies the date the loan is supposed to end or be fully paid | | **loan_performance** | STRING | 50 | OPTIONAL | Specifies the loan is performing.
   Values can be:
1. PERFORMING
2. NOT_PERFORMING | | **loan_performance_description** | STRING | 250 | OPTIONAL | Specifies loan performance description |

1.

## Loan Statement

This API will get loan statement for a member.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "LOAN_STATEMENT",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023",

"statement_type": "MINI_STATEMENT/FULL_STATEMENT",

"max_number_of_transactions": 100,

"start_date": "2021-01-01 20:00:00",

"end_date": "2021-01-03 20:00:00",

"loan_id": "U:203813:03:2020"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **statement_type** | STRING | 50 | YES | Specifies the type of Account Statement to get. Values can be:
1. MINI_STATEMENT
2. FULL_STATEMENT | | **max_number_of_transactions** | INTEGER | | YES | Specifies the maximum number of transactions to get | | **start_date** | DATETIME | | OPTIONAL | Specifies the start date for getting transactions. Should be specified when statement type is FULL_STATEMENT. Should be in ISO format – yyyy:MM:dd HH:mm:ss | | **end_date** | DATETIME | | OPTIONAL | Specifies the end date for getting transactions. Should be specified when statement type is FULL_STATEMENT. Should be in ISO format – yyyy:MM:dd HH:mm:ss | | **loan_id** | STRING | 50 | YES | Specifies the Loan ID |

    1.

        1. {
        2. "request_status": "SUCCESS/INCORRECT_PIN/ERROR",
        3. "loan_id": "N:203813:03:2020",
        4. "loan_type_id": "N",
        5. "loan_type_name": "NORMAL LOAN",
        6. "loan_amount": 120000.00,
        7. "loan_balance": 15000.00,
        8. "transactions": [
        9. {
        10. "transaction_reference": "OH50CRUHJK",
        11. "transaction_date": "2021-01-02",
        12. "transaction_time": "13:00:00",
        13. "transaction_amount": 5000.00,
        14. "running_balance": 30000.00,
        15. "transaction_description": "M-PESA Loan Repayment from 254724763290 to Loan ID: N:203813:03:2020",
        16. "other_details": "Loan Repayment via Mobile Banking"
        17. },
        18. {
        19. "transaction_reference": "XTREME:9225-40A8F0293DCC",
        20. "transaction_date": "2021-01-03",
        21. "transaction_time": "11:00:00",
        22. "transaction_amount": 15000.00,
        23. "running_balance": 15000.00,
        24. "transaction_description": "IFT Loan Repayment from A/C 41-02392-0093-01 to Loan ID: N:203813:03:2020",
        25. "other_details": "Loan Repayment via IFT"
        26. }
        27. ]
        28. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. ERROR | | **loan_id** | STRING | 50 | YES | Specifies the Loan ID | | **loan_type_id** | STRING | 50 | YES | Specifies the Loan Type ID | | **loan_type_name** | STRING | 50 | YES | Specifies the Loan Type Name | | **loan_amount** | DOUBLE | | YES | Specifies the original loan amount granted | | **loan_balance** | DOUBLE | | YES | Specifies the current loan balance | | **transactions** | LIST | | YES | Specifies the list of transactions of a Mobile Banking user | | **transaction_reference** | STRING | 200 | YES | Specifies the reference of the transaction | | **transaction_date** | DATE | | YES | Specifies the date of the transaction. Should be in ISO format – yyyy-MM-dd | | **transaction_time** | TIME | | YES | Specifies the time of the transaction. Should be in ISO format – HH:mm:ss | | **transaction_amount** | DOUBLE | | YES | Specifies the amount of the transaction | | **running_balance** | DOUBLE | | YES | Specifies the running balance after the transaction | | **
   transaction_description** | STRING | 250 | OPTIONAL | Specifies the description of the transaction | | **other_details** | STRING | 250 | OPTIONAL | Specifies other details of the transaction like location etc. |

1.

## Get Loan Guarantors

This API will get the guarantors of a member's loan.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

          1. {
          2. "action": "GET_LOAN_GUARANTORS",
          3. "payload": {
          4. "api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",
          5. "identifier_type": "MSISDN",
          6. "identifier": "254712345678",
          7. "pin": "1234",
          8. "device_identifier_type": "IMSI/APP_ID",
          9. "device_identifier": "1099200912931023",
          10. "loan_id": "U:203813:03:2020"
          11. }
          12. }

Request Structure

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **loan_id** | STRING | 50 | YES | Specifies the Loan ID |

    1.

        1. {
        2. "request_status": "SUCCESS/INCORRECT_PIN/ERROR",
        3. "loan_id": "N:203813:03:2020",
        4. "loan_type_id": "N",
        5. "loan_type_name": "NORMAL LOAN",
        6. "loan_amount": 120000.00,
        7. "loan_balance": 15000.00,
        8. "guarantors": [
        9. {
        10. "full_name": "John Doe Omollo",
        11. "identifier_type": "MSISDN",
        12. "identifier": "254712345678",
        13. "amount_guaranteed": 5000.00,
        14. "guarantorship_status": "ACCEPTED",
        15. "guarantorship_status_date": "2021-01-02 13:45:15"
        16. },
        17. {
        18. "full_name": "Mary Jane Mwangi",
        19. "identifier_type": "MSISDN",
        20. "identifier": "254712345679",
        21. "amount_guaranteed": 15000.00,
        22. "guarantorship_status": "ACCEPTED",
        23. "guarantorship_status_date": "2021-01-02 13:45:15"
        24. }
        25. ]
        26. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. ERROR | | **loan_id** | STRING | 50 | YES | Specifies the Loan ID | | **loan_type_id** | STRING | 50 | YES | Specifies the Loan Type ID | | **loan_type_name** | STRING | 50 | YES | Specifies the Loan Type Name | | **loan_amount** | DOUBLE | | YES | Specifies the original loan amount granted | | **loan_balance** | DOUBLE | | YES | Specifies the current loan balance | | **guarantors** | LIST | | YES | Specifies the list of loan guarantors | | **full_name** | STRING | 150 | YES | Specifies the full name of the guarantor | | **identifier_type** | STRING | 50 | YES | Specifies the identifier type of the guarantor Values can be:
1. MSISDN | | **identifier** | STRING | 50 | YES | Specifies the identifier of the guarantor. | | **amount_guaranteed** | DOUBLE | | YES | Specifies the amount guaranteed | | **guarantorship_status** | STRING | 50 | YES | Specifies the guarantorship status. Values can be:
1. PENDING
2. ACCEPTED
3. REJECTED | | **guarantorship_status_date** | DATETIME | | YES | Specifies the guarantorship status date of the guarantor. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

1.

## Get Loans Guaranteed

This API will get the loans a member has guaranteed.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "GET_LOANS_GUARANTEED",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier |

    1.

### Response Structure

{

"request_status": "SUCCESS/INCORRECT_PIN/ERROR",

"loans_guaranteed": [

{

"loan_id": "N:203813:03:2020",

"loan_type_id": "N",

"loan_type_name": "NORMAL LOAN",

"guaranteed_full_name": "Mary Jane Mwangi",

"guaranteed_identifier_type": "MSISDN",

"guaranteed_identifier": "254712345679",

"amount_guaranteed": 5000.00,

"loan_amount": 120000.00,

"loan_balance": 15000.00,

"loan_defaulted_amount": 0.00,

"loan_issued_date": "2021-01-03 08:45:15",

"loan_end_date": "2021-10-03 08:45:15",

"loan_performance": "PERFORMING/NOT_PERFORMING",

"loan_performance_description": "Loan is performing",

"guarantorship_status": "ACCEPTED",

"guarantorship_status_date": "2021-01-02 13:45:15"

},

{

"loan_id": "U:203813:03:2020",

"loan_type_id": "U",

"loan_type_name": "SUPA LOAN",

"guaranteed_full_name": "John Doe Omollo",

"guaranteed_identifier_type": "MSISDN",

"guaranteed_identifier": "254712345678",

"amount_guaranteed": 15000.00,

"loan_amount": 120000.00,

"loan_balance": 15000.00,

"loan_defaulted_amount": 0.00,

"loan_issued_date": "2021-01-03 08:45:15",

"loan_end_date": "2021-10-03 08:45:15",

"loan_performance": "PERFORMING/NOT_PERFORMING",

"loan_performance_description": "Loan is performing",

"guarantorship_status": "ACCEPTED",

"guarantorship_status_date": "2021-01-02 13:45:15"

}

]

}

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. ERROR | | **loans_guaranteed** | LIST | | YES | Specifies the list of loan guaranteed | | **loan_id** | STRING | 50 | YES | Specifies the Loan ID | | **loan_type_id** | STRING | 50 | YES | Specifies the Loan Type ID | | **loan_type_name** | STRING | 50 | YES | Specifies the Loan Type Name | | **guaranteed_full_name** | STRING | 150 | YES | Specifies the full name of the guaranteed member | | **guaranteed_identifier_type** | STRING | 50 | YES | Specifies the identifier type of the guaranteed member. Values can be:
1. MEMBER_NUMBER
2. MSISDN
3. NATIONAL_ID
4. PASSPORT_NO
5. DRIVING_LICENSE | | **guaranteed_identifier** | STRING | 50 | YES | Specifies the identifier of the guaranteed member. | | **amount_guaranteed** | DOUBLE | | YES | Specifies the amount guaranteed | | **loan_amount** | DOUBLE | | YES | Specifies the amount a member borrowed | | **loan_balance** | DOUBLE | | YES | Specifies the loan balance | | **loan_defaulted_amount** | DOUBLE | | OPTIONAL | Specifies the loan defaulted amount | | **loan_issued_date** | DATETIME | | OPTIONAL | Specifies the date the loan was issued | | **loan_end_date** | DATETIME | | OPTIONAL | Specifies the date the loan is supposed to end or be fully paid | | **loan_performance** | STRING | 50 | OPTIONAL | Specifies the loan is performing. Values can be:
1. PERFORMING
2. NOT_PERFORMING | | **loan_performance_description** | STRING | 250 | OPTIONAL | Specifies loan performance description | | **guarantorship_status** | STRING | 50 | YES | Specifies the guarantorship status. Values can be:1. PENDING2. ACCEPTED3. REJECTED | | **guarantorship_status_date** | DATETIME | | YES | Specifies the guarantorship status date of the guarantor. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

1.

## Add Loan Guarantor

This API will allow a member to add/request other members to guarantee their loan.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "ADD_LOAN_GUARANTOR",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023",

"guarantor_identifier_type": "MSISDN",

"guarantor_identifier": "254712345678",

"loan_id": "U:203813:03:2020",

"proposed_amount_to_guarantee": 15000.00,

"request_date_time": "2021-01-04 10:15:35"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **guarantor_identifier_type** | STRING | 50 | YES | Specifies the identifier type of the guaranteed member. Values can be:
1. MEMBER_NUMBER
2. MSISDN
3. NATIONAL_ID
4. PASSPORT_NO
5. DRIVING_LICENSE | | **guarantor_identifier** | STRING | 50 | YES | Specifies the identifier of the guaranteed member. | | **loan_id** | STRING | 50 | YES | Specifies the Loan ID | | **proposed_amount_to_guarantee** | DOUBLE | | OPTIONAL | Proposed amount to guarantee | | **request_date_time** | DATETIME | | YES | Specifies the date and time of the guarantorship request. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

    1.

        1. {
        2. "request_status": "SUCCESS/INCORRECT_PIN/ERROR",
        3. "request_status_description": "Loan Guarantor added successfully"
        4. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the transaction. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. ERROR | | **request_status_description** | STRING | 200 | YES | Specifies the status description |

1.

## Get Loan Guarantorship Requests

This API will allow a member to get their guarantorship request.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "GET_GUARANTORSHIP_REQUESTS",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier |

    1.

        1. {
        2. "request_status": "SUCCESS/INCORRECT_PIN/ERROR",
        3. "guarantorship_requests": [
        4. {
        5. "loan_id": "N:203813:03:2020",
        6. "loan_type_id": "N",
        7. "loan_type_name": "NORMAL LOAN",
        8. "requester_full_name": "Mary Jane Mwangi",
        9. "requester_identifier_type": "MSISDN",
        10. "requester_identifier": "254712345679",
        11. "loan_amount": 120000.00,
        12. "proposed_amount_to_guarantee": 5000.00,
        13. "guarantorship_status": "PENDING",
        14. "guarantorship_status_date": "2021-01-02 13:45:15"
        15. },
        16. {
        17. "loan_id": "U:203813:03:2020",
        18. "loan_type_id": "U",
        19. "loan_type_name": "SUPA LOAN",
        20. "guaranteed_full_name": "John Doe Omollo",
        21. "guaranteed_identifier_type": "MSISDN",
        22. "guaranteed_identifier": "254712345678",
        23. "loan_amount": 120000.00,
        24. "proposed_amount_to_guarantee": 5000.00,
        25. "guarantorship_status": "PENDING",
        26. "guarantorship_status_date": "2021-01-02 13:45:15"
        27. }
        28. ]
        29. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the request. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. ERROR | | **guarantorship_requests** | LIST | | YES | Specifies the list of loan guarantorship requests | | **loan_id** | STRING | 50 | YES | Specifies the Loan ID | | **loan_type_id** | STRING | 50 | YES | Specifies the Loan Type ID | | **loan_type_name** | STRING | 50 | YES | Specifies the Loan Type Name | | **requester_full_name** | STRING | 150 | YES | Specifies the full name of the member requesting to be guaranteed | | **requester_identifier_type** | STRING | 50 | YES | Specifies the identifier type of the guaranteed member. Values can be:
1. MEMBER_NUMBER
2. MSISDN
3. NATIONAL_ID
4. PASSPORT_NO
5. DRIVING_LICENSE | | **requester_identifier** | STRING | 50 | YES | Specifies the identifier of the guaranteed member. | | **amount_guaranteed** | DOUBLE | | YES | Specifies the amount guaranteed | | **loan_amount** | DOUBLE | | YES | Specifies the amount a member borrowed | | **loan_balance** | DOUBLE | | YES | Specifies the loan balance | | **loan_defaulted_amount** | DOUBLE | | OPTIONAL | Specifies the loan defaulted amount | | **loan_issued_date** | DATETIME | | OPTIONAL | Specifies the date the loan was issued | | **loan_end_date** | DATETIME | | OPTIONAL | Specifies the date the loan is supposed to end or be fully paid | | **loan_performance** | STRING | 50 | OPTIONAL | Specifies the loan is performing. Values can be:
1. PERFORMING
2. NOT_PERFORMING | | **loan_performance_description** | STRING | 250 | OPTIONAL | Specifies loan performance description | | **guarantorship_status** | STRING | 50 | YES | Specifies the guarantorship status. Values can be:1. PENDING2. ACCEPTED3. REJECTED | | **guarantorship_status_date** | DATETIME | | YES | Specifies the guarantorship status date of the guarantor. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

1.

## Accept/Reject Loan Guarantorship Request

This API will allow a member to accept/reject a guarantorship request.

**API Access Method:** HTTP(S) POST

**URL &amp; Credentials:** To be provided separately

**Request Headers:**

| **HEADER** | **Value** |
| --- | --- |
| **Content-Type** | application/json |
| **Accept** | application/json |

    1.

### Request Structure

{

"action": "UPDATE_GUARANTORSHIP_STATUS",

"payload": {

"api_request_id": "df3e7cf5-1e4b-41ef-a22f-e755be665432",

"identifier_type": "MSISDN",

"identifier": "254712345678",

"pin": "1234",

"device_identifier_type": "IMSI/APP_ID",

"device_identifier": "1099200912931023",

"loan_id": "U:203813:03:2020",

"amount_guaranteed": 15000.00,

"guarantorship_status": "ACCEPTED/REJECTED",

"guarantorship_status_date": "2021-01-02 13:45:15"

}

}

    1.

### Request Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **action** | STRING | 50 | YES | Specifies action to be performed. |
| **payload** | OBJECT |
| YES | Contains the payload data |
| **api_request_id** | STRING | 150 | YES | Specifies the unique request reference for a particular API call request. |
| **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:

1. MSISDN | | **identifier** | STRING | 50 | YES | Mobile Banking account identifier. | | **pin** | STRING | 50 | YES | Secret phrase/PIN for the Mobile Banking user | | **device_identifier_type** | STRING | 30 | YES | Device identifier tied to Mobile Banking account identifier. Values can be:
1. APP_ID
2. IMSI | | **device_identifier** | STRING | 100 | YES | Actual Device identifier tied to Mobile Banking account identifier | | **identifier_type** | STRING | 50 | YES | Mobile Banking account identifier type. Values can be:
1. MSISDN | | **loan_id** | STRING | 50 | YES | Specifies the Loan ID | | **amount_guaranteed** | DOUBLE | | YES | Amount guaranteed | | **guarantorship_status** | STRING | 50 | YES | Specifies the guarantorship status. Values can be:
1. PENDING
2. ACCEPTED
3. REJECTED | | **guarantorship_status_date** | DATETIME | | YES | Specifies the date and time of the guarantorship request. Should be in ISO format – yyyy:MM:dd HH:mm:ss |

    1.

        1. {
        2. "request_status": "SUCCESS/INCORRECT_PIN/ERROR",
        3. "request_status_description": "Loan Guarantorship status updated successfully"
        4. } Response Structure

    1.

### Response Data Definition

| **Field** | **Data Type** | **Size** | **Required** | **Description** |
| --- | --- | --- | --- | --- |
| **request_status** | STRING | 50 | YES | Specifies the status of the transaction. Values can be:

1. SUCCESS
2. INCORRECT_PIN
3. ERROR | | **request_status_description** | STRING | 200 | YES | Specifies the status description |

1.

# NOTES

1.

## Authentication

      1.

#### Check User

Scenario 1: NOT_FOUND

CBS to return **NOT_FOUND** only when the following conditions have been met:

1. The **identifier** does NOT exist OR **not** active OR **not** registered to use MBanking services.

Action to be taken:

1. No further action needed.

Scenario 2: INVALID_DEVICE_IDENTIFIER

CBS to return **INVALID_DEVICE_IDENTIFIER** only when the following conditions have been met:

1. The **device_identifier** is stored in the CBS and does **NOT** match the **device_identifier** provided in the request data.

Action to be taken:

1. No further action needed.

Scenario 3: LOCKED

CBS to return **LOCKED** only when the following conditions have been met:

1. The **auth_action** is LOCK.

Action to be taken:

1. No further action needed.

Scenario 4: SUSPENDED

CBS to return **SUSPENDED** only when the following conditions have been met:

1. The **auth_action** is SUSPEND AND the **auth_action_valid_date** is still in the future.

Action to be taken:

1. No further action needed.

Scenario 5: ACTIVE

CBS to return **ACTIVE** only when the following conditions have been met:

1. The **identifier** is valid, active and registered to use MBanking services.
2. The **device_identifier** stored in the CBS matches the device identifier provided in the request data. OR. If the device identifier is NULL or EMPTY in the CBS.
3. The **auth_action** is **NONE.** OR. If the **auth_action** is **SUSPEND** AND **auth_action_valid_date** is in the PAST.

Action to be taken:

1. No further action needed.

    1.

#### Login

Scenario 1: INVALID_DEVICE_IDENTIFIER

CBS to return **INVALID_DEVICE_IDENTIFIER** only when the following conditions have been met:

1. The **device_identifier** is stored in the CBS and does **NOT** match the **device_identifier** provided in the request data.

Action to be taken:

1. No further action needed.

Scenario 2: LOCKED

CBS to return **LOCKED** only when the following conditions have been met:

1. The **auth_action** is LOCK.

Action to be taken:

1. No further action needed.

Scenario 3: SUSPENDED

CBS to return **SUSPENDED** only when the following conditions have been met:

1. The **auth_action** is SUSPEND AND the **auth_action_valid_date** is still in the future.

Action to be taken:

1. No further action needed.

Scenario 4: INCORRECT_PIN

CBS to return **INCORRECT_PIN** only when the following conditions have been met:

1. The **identifier** is valid, active and registered to use MBanking services.
2. The **pin** provided in the request does NOT match the **pin** stored in the CBS for the **identifier** in subject.

Actions to be taken:

1. Increment **auth_attempts** by 1
2. Return the new value of **auth_attempts** in the response body.

Scenario 5: SET_PIN

CBS to return **SET_PIN** only when the following conditions have been met:

1. The **identifier** exists, is active and registered to use MBanking services.
2. The **pin** provided in the request matches the **pin** stored in the CBS for the **identifier** in subject.
3. The **has_pin_been_set** Field is 'NO'

Action to be taken:

1. No further action needed.

Scenario 6: MOBILE_APP_INACTIVE

CBS to return MOBILE_APP_INACTIVE only when the following conditions have been met:

1. The request is a Mobile APP request.
2. The **identifier** is valid, active and registered to use MBanking services.
3. The **pin** provided in the request does NOT match the **pin** stored in the CBS for the **identifier** in subject.
4. The **device_identifier** (**app_id)** Field in the CBS is NULL or EMPTY

Action to be taken:

1. No further action needed.

Scenario 7: SUCCESS

CBS to return **SUCCESS** only when the following conditions have been met:

1. The **identifier** is valid, active and registered to use MBanking services.
2. The **pin** provided in the request matches the **pin** stored in the CBS for the **identifier** in subject.
3. The **device_identifier** stored in the CBS matches the **device_identifier** provided in the request data.
4. The **auth_action** is NONE. OR. If **auth_action** is SUSPEND AND the **auth_action_valid_date** is in the PAST

Action to be taken:

1. Set the **auth_attempts** to 0
2. Set **auth_action** to NONE
3. Set **auth_flag** to NONE
4. Set **auth_action_valid_date** to NULL
5. Return **auth_attempts** as 0 in response body

    1.

#### General Authentication Notes

- When AuthAction is **WARN** , all APIs should work as normal.
- When AuthAction is **SUSPEND** / **LOCK** , no API should work except:

1. Check User
2. Login
3. Get/Set Auth Parameters
4. Withdrawal Result
5. Deposit APIs

- When Making MAPP **GET_AUTH_SECURITY_**** PARAMETERS **and** SET_AUTH_SECURITY_ ****PARAMETERS** Request, **APP_ID** is **NOT** checked.

    1.

## CBS Generated Messages

- The CBS will generate messages for the following actions (but **ONLY** for **USSD** Requests. For **Mobile App** , the CBS will **NOT** generate messages:
    1. ACCOUNT_BALANCE_ENQUIRY
    2. ACCOUNT_STATEMENT
    3. LOAN_STATEMENT

1.

# APPENDIX

1.

    1. \&lt;ATTEMPTS NAME='DEFAULT_SUSPEND' ACTION='SUSPEND' STEP='2' DURATION='30' UNIT='DAY' NOTIFY='YES' \&gt;
    2. \&lt;!-- \&lt;ATTEMPTS NAME='DEFAULT_SUSPEND/DEFAULT_WARN/DEFAULT_LOCK' ACTION='SUSPEND/WARN/LOCK' STEP='3' DURATION='24' UNIT='HOUR' NOTIFY='YES' \&gt; --\&gt;
    3. \&lt;!--\&lt;ATTEMPT ACTION='NONE/WARN/SUSPEND/LOCK' NOTIFY='YES/NO'\&gt;3\&lt;/ATTEMPT\&gt;--\&gt;
    4. \&lt;ATTEMPT NAME='FIRST_WARNING' ACTION='WARN' NOTIFY='NO'\&gt;2\&lt;/ATTEMPT\&gt;
    5. \&lt;ATTEMPT NAME='FIRST_SUSPENSION' ACTION='SUSPEND' DURATION='60' UNIT='MINUTE' NOTIFY='YES'\&gt;4\&lt;/ATTEMPT\&gt; \&lt;!-- UNIT='SECOND/MINUTE/HOUR/DAY' --\&gt;
    6. \&lt;ATTEMPT NAME='SECOND_WARNING' ACTION='WARN' NOTIFY='NO'\&gt;5\&lt;/ATTEMPT\&gt;
    7. \&lt;ATTEMPT NAME='SECOND_SUSPENSION' ACTION='SUSPEND' DURATION='24' UNIT='HOUR' NOTIFY='NO'\&gt;6\&lt;/ATTEMPT\&gt;
    8. \&lt;ATTEMPT NAME='THIRD_WARNING' ACTION='WARN' NOTIFY='NO'\&gt;7\&lt;/ATTEMPT\&gt;
    9. \&lt;/ATTEMPTS\&gt; Auth Parameters XML Snippet
