# Disbursement
## API Inquiry Table
### URL Path
URL Path : https://{host}/{version}/disbursement-inquiry

### HTTP Method
HTTP Method : POST

### HTTP Header
|Header Name | Header Value |
| --- | --- |
|Content-Type | application/json |
|X-TIMESTAMP|[datetime] (yyyy-MM-ddTHH:mm:ss+07:00) |
|X-SIGNATURE|**[Digital Signature]** |
|Authorization|Basic **[JWT Token]**|

### HTTP Body Request
|Field | Data Type | Descriptions | Mandatory |
| --- | --- | --- | --- |
|partnerReferenceNo | string(64) | Unique Transaction Number from **Service User** | yes |
|productCode |string(64) |Product Code |yes |
|productPrice |string(64) |Product Price |no |
|remarks |string(64) |Remark/transaction description,<br>*recommended to use a unique value |yes |
|beneficiaryBankCode |string(64) |Beneficiary Bank Code |yes |
|beneficiaryAccountNo |string(64) |Beneficiary Account Number |yes |

### Sample HTTP Raw Request
```php
POST .../v2.0/disbursement-inquiry HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-07-14T14:35:06+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
    "partnerReferenceNo": "TRX-000000351",
    "productCode": "DBSFL",
    "productPrice": 10000,
    "remarks": "Test Remarks",
    "beneficiaryBankCode": "BRI",
    "beneficiaryAccountNo": "123457890",
}
```

### Sample HTTP Raw Response (Success)
```php
{
    "responseCode": "00",
    "responseMessage": "Success",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-221121-0000006",
    "result": {
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "Callback-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "DBSFL",
        "productTypeID": 2,
        "productCode": "DBSFL",
        "productName": "DISBURSEMENT FL",
        "productPrice": 10000,
        "productAdminFee": 10000,
        "productMerchantFee": 2000,
        "transactionDate": "2022-07-14T14:35:06+07:00",
        "customerID": "123457890",
        "additionalInfo": {
            "serialNumber": "",
            "billDesc": "{\"beneficiaryBankCode\":\"BRI\",\"beneficiaryBankName\":\"BANK RAKYAT INDONESIA\",\"beneficiaryAccountNo\":\"123457890\",\"beneficiaryAccountName\":\"John Doe\",\"remarks\":\"Test Remaks\"}",
        }
    }
}
```


## API Payment Table
### URL Path
URL Path : https://{host}/{version}/disbursement-payment

### HTTP Method
HTTP Method : POST

### HTTP Header
|Header Name | Header Value |
| --- | --- |
|Content-Type | application/json |
|X-TIMESTAMP|[datetime] (yyyy-MM-ddTHH:mm:ss+07:00) |
|X-SIGNATURE|**[Digital Signature]** |
|Authorization|Basic **[JWT Token]**|

### HTTP Body Request
|Field | Data Type | Descriptions | Mandatory |
| --- | --- | --- | --- |
|partnerApprovalNo | string(64) | Unique number after **Service User** success deducting customer balance | yes |
|partnerReferenceNo |string(64) |Unique Transaction Number from **Service User** |yes |
|referenceNo |string(64) |Unique Transaction Number from **Service Provider** |yes |

### Sample HTTP Raw Request
```php
POST .../v2.0/disbursement-payment HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-07-14T14:35:06+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
    "partnerApprovalNo": "ytyui876543",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-221121-0000006",
}
```

### Sample HTTP Raw Response (Success)
```php
{
    "responseCode": "00",
    "responseMessage": "Success",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-221121-0000006",
    "result": {
        "partnerApprovalNo": "ytyui876543",
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "DEV-221121-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "DBSFL",
        "productTypeID": 2,
        "productCode": "DBSFL",
        "productName": "DISBURSEMENT FL",
        "productPrice": 10000,
        "productAdminFee": 10000,
        "productMerchantFee": 2000,
        "transactionDate": "2022-07-14T14:35:06+07:00",
        "customerID": "123457890",
        "additionalInfo": {
            "serialNumber": "",
            "billDesc": "{\"beneficiaryBankCode\":\"BRI\",\"beneficiaryBankName\":\"BANK RAKYAT INDONESIA\",\"beneficiaryAccountNo\":\"123457890\",\"beneficiaryAccountName\":\"John Doe\",\"remarks\":\"Test Remaks\"}",
        }
    }
}
```


## API Advice Table
### URL Path
URL Path : https://{host}/{version}/disbursement-advice

### HTTP Method
HTTP Method : POST

### HTTP Header
|Header Name | Header Value |
| --- | --- |
|Content-Type | application/json |
|X-TIMESTAMP|[datetime] (yyyy-MM-ddTHH:mm:ss+07:00) |
|X-SIGNATURE|**[Digital Signature]** |
|Authorization|Basic **[JWT Token]**|

### HTTP Body Request
|Field | Data Type | Descriptions | Mandatory |
| --- | --- | --- | --- |
|partnerReferenceNo | string(64) | Unique Transaction Number from **Service User** | yes |
|referenceNo |string(64) |Unique Transaction Number from **Service Provider** |yes |

### Sample HTTP Raw Request
```php
POST .../v2.0/disbursement-advice HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-06-17T13:50:04+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-221121-0000006",
}
```

### Sample HTTP Raw Response (Success)
```php
{
    "responseCode": "00",
    "responseMessage": "Success",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-221121-0000006",
    "result": {
        "partnerApprovalNo": "ytyui876543",
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "DEV-221121-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "DBSFL",
        "productTypeID": 2,
        "productCode": "DBSFL",
        "productName": "DISBURSEMENT FL",
        "productPrice": 10000,
        "productAdminFee": 10000,
        "productMerchantFee": 2000,
        "transactionDate": "2022-07-14T14:35:06+07:00",
        "customerID": "123457890",
        "additionalInfo": {
            "serialNumber": "",
            "billDesc": "{\"beneficiaryBankCode\":\"BRI\",\"beneficiaryBankName\":\"BANK RAKYAT INDONESIA\",\"beneficiaryAccountNo\":\"123457890\",\"beneficiaryAccountName\":\"John Doe\",\"remarks\":\"Test Remaks\"}",
        }
    }
}
```


## API Callback Table
### URL Path
URL Path : {CallbackURL}

### HTTP Method
HTTP Method : POST

### HTTP Header
|Header Name | Header Value |
| --- | --- |
|Content-Type | application/json |
|Authorization|Basic **[JWT Token]**|

### HTTP Body Payload
|Field | Data Type | Descriptions | Mandatory |
| --- | --- | --- | --- |
|partnerReferenceNo | string(64) | Unique Transaction Number from **Service User** | yes |
|responseCode |string(2) |Response Code from **Service User** [00 or 03] |yes |
|responseMessage |string(64) |Response Message from **Service User** [00 = Success, 03 = Failed or other message] |yes |
|referenceNo |string(64) |Unique Transaction Number from **Service Provider** |yes |

### Sample HTTP Raw Request
```php
POST https://www.partner-url.com/ HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-06-17T13:50:04+07:00

{
    "responseCode": "00",
    "responseMessage": "Success",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "Callback-0000006",
    "result": {
        "partnerApprovalNo": "ytyui876543",
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "DEV-220118-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "DBSFL",
        "productTypeID": 2,
        "productCode": "DBSFL",
        "productName": "DISBURSEMENT FL",
        "productPrice": 10000,
        "productAdminFee": 10000,
        "productMerchantFee": 2000,
        "transactionDate": "2022-07-14T14:35:06+07:00",
        "customerID": "123457890",
        "additionalInfo": {
            "serialNumber": "",
            "billDesc": "{\"beneficiaryBankCode\":\"BRI\",\"beneficiaryBankName\":\"BANK RAKYAT INDONESIA\",\"beneficiaryAccountNo\":\"123457890\",\"beneficiaryAccountName\":\"John Doe\",\"remarks\":\"Test Remaks\"}",
        }
    }
}
```

### Sample HTTP Raw Response (Success)
```php
{
    "responseCode": "00",
    "responseMessage": "Success",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-221121-0000006",
    "result": "",
}
```