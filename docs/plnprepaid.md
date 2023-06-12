# PLN PREPAID
## API Inquiry Table
### URL Path
URL Path : https://{host}/{version}/inquiry

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
|productPrice |integer |Product Price |no |
|customerID |string(64) |Customer ID of the transaction |yes |
|customerPeriode |string(64) |Total n month would be paid **(mandatory for specified product)** |conditional |

### Sample HTTP Raw R
```json
POST .../v2.0/inquiry HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-01-18T13:50:04+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
	"partnerReferenceNo": "TRX-000000351",
	"productCode": "PLNPR20",
	"productPrice": 20500,
	"customerID": "86034655976",
	"customerPeriode": "",
}
```

### Sample HTTP Raw Response (Success)
```json
{
    "responseCode": "00",
    "responseMessage": "Success",
    "responseDatetime": "2022-01-18T13:50:04+07:00",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-220118-0000006",
    "result": {
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "DEV-220118-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "PLNPREPAIDV2",
        "productTypeID": 1,
        "productCode": "PLNPR20",
        "productName": "PLN PREPAID 20",
        "productPrice": 20500,
        "productAdminFee": 0,
        "productMerchantFee": 0,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "86034655976",
        "additionalInfo": {
            "serialNumber": "",
            "billDesc": "{\"customerName\":\"JOHN DOE\",\"idPelanggan\":\"520061321123\",\"nomorMeter\":\"86034655976\",\"tarifDaya\":\"R1/450VA\"}",
        }
    }
}
```


## API Payment Table
### URL Path
URL Path : https://{host}/{version}/payment

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
|partnerApprovalNo | string(64) |Unique number after **Service User** success deducting customer balance |yes |
|partnerReferenceNo | string(64) | Unique Transaction Number from **Service User** | yes |
|referenceNo |string(64) |Unique Transaction Number from **Service Provider** |yes |

### Sample HTTP Raw Request
```json
POST .../v2.0/payment HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-01-18T13:50:04+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
    "partnerApprovalNo": "ytyui876543",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-220118-0000006",
}
```

### Sample HTTP Raw Response (Success)
```json
{
    "responseCode": "00",
    "responseMessage": "Success",
    "responseDatetime": "2022-01-18T13:50:04+07:00",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-220118-0000006",
    "result": {
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "DEV-220118-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "PLNPREPAIDV2",
        "productTypeID": 1,
        "productCode": "PLNPR20",
        "productName": "PLN PREPAID 20",
        "productPrice": 20500,
        "productAdminFee": 0,
        "productMerchantFee": 0,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "86034655976",
        "additionalInfo": {
            "serialNumber": "",
            "billDesc": "{\"customerName\":\"JOHN DOE\",\"idPelanggan\":\"312100087994\",\"nomorMeter\":\"45052452799\",\" noRef\":\"0UAK211100048431C8F5\",\"jumlahKwh\":\"13,50\",\"tarifDaya\":\"R1M/900VA\",\"angsuran\":\"0,00\",\"materai\":\"0,00\",\"stroomToken\":\"6156-0790-0556-6477-7418\",\"rpStroomToken\":\"RP18.181,00\",\"ppj\":\"1819,00\",\"ppn\":\"0,00\"}",
        }
    }
}
```

## API Advice Table
### URL Path
URL Path : https://{host}/{version}/advice

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
```json
POST .../v2.0/payment HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-01-18T13:50:04+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-220118-0000006",
}
```
### Sample HTTP Raw Response (Success)
```json
{
    "responseCode": "00",
    "responseMessage": "Success",
    "responseDatetime": "2022-01-18T13:50:04+07:00",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-220118-0000006",
    "result": {
        "partnerApprovalNo": "ytyui876543",
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "DEV-220118-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "PLNPREPAIDV2",
        "productTypeID": 1,
        "productCode": "PLNPR20",
        "productName": "PLN PREPAID 20",
        "productPrice": 20500,
        "productAdminFee": 0,
        "productMerchantFee": 0,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "86034655976",
        "additionalInfo": {
            "serialNumber": "9111722123461556920",
        	"billDesc": "{\"customerName\":\"JOHN DOE\",\"idPelanggan\":\"312100087994\",\"nomorMeter\":\"45052452799\",\" noRef\":\"0UAK211100048431C8F5\",\"jumlahKwh\":\"13,50\",\"tarifDaya\":\"R1M/900VA\",\"angsuran\":\"0,00\",\"materai\":\"0,00\",\"stroomToken\":\"6156-0790-0556-6477-7418\",\"rpStroomToken\":\"RP18.181,00\",\"ppj\":\"1819,00\",\"ppn\":\"0,00\"}",
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
|X-TIMESTAMP|[datetime] (yyyy-MM-ddTHH:mm:ss+07:00) |

### HTTP Body Payload
|Field | Data Type | Descriptions | Mandatory |
| --- | --- | --- | --- |
|partnerReferenceNo | string(64) | Unique Transaction Number from **Service User** | yes |
|responseCode |string(2) |Response Code from **Service User** [00 or 03] |yes |
|responseMessage |string(64) |Response Message from **Service User** [00 = Success, 03 = Failed or other message] |yes |
|referenceNo |string(64) |Unique Transaction Number from **Service Provider** |yes |

### Sample HTTP Raw Request
```json
POST https://www.partner-url.com/ HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-01-18T13:50:04+07:00

{
    "responseCode": "00",
    "responseMessage": "Success",
    "responseDateTime": "2022-01-18T13:50:04+07:00",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "Callback-0000006",
    "result": {
        "partnerApprovalNo": "ytyui876543",
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "DEV-220118-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "PLNPREPAIDV2",
        "productTypeID": 1,
        "productCode": "PLNPR20",
        "productName": "PLN PREPAID 20",
        "productPrice": 20500,
        "productAdminFee": 0,
        "productMerchantFee": 0,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "86034655976",
        "additionalInfo": {
            "serialNumber": "9111722123461556920",
            "billDesc": "{\"customerName\":\"JOHN DOE\",\"idPelanggan\":\"312100087994\",\"nomorMeter\":\"45052452799\",\" noRef\":\"0UAK211100048431C8F5\",\"jumlahKwh\":\"13,50\",\"tarifDaya\":\"R1M/900VA\",\"angsuran\":\"0,00\",\"materai\":\"0,00\",\"stroomToken\":\"6156-0790-0556-6477-7418\",\"rpStroomToken\":\"RP18.181,00\",\"ppj\":\"1819,00\",\"ppn\":\"0,00\"}",
    	}
    }
}
```
### Sample HTTP Raw Response (Success)
```json
{
    "responseCode": "00",
    "responseMessage": "Success",
    "responseDatetime": "2022-01-18T13:50:04+07:00",
    "result": "",
}
```