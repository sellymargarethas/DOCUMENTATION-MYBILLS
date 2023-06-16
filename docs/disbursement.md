<h2><b>Disbursement</b></h2>

### API Inquiry Table
#### URL Path
URL Path : `https://{host}/{version}/disbursement-inquiry`

#### HTTP Method
HTTP Method : `POST`

#### HTTP Header
|Header Name | Header Value |
| --- | --- |
|Content-Type | application/json |
|X-TIMESTAMP|[datetime] (yyyy-MM-ddTHH:mm:ss+07:00) |
|X-SIGNATURE|**[Digital Signature]** |
|Authorization|Basic **[JWT Token]**|

#### HTTP Body Request
|Field | Data Type | Descriptions | Mandatory |
| --- | --- | --- | --- |
|partnerReferenceNo | string(64) | Unique Transaction Number from **Service User** | yes |
|productCode |string(64) |Product Code |yes |
|productPrice |string(64) |Product Price |no |
|remarks |string(64) |Remark/transaction description,<br>*recommended to use a unique value |yes |
|beneficiaryBankCode |string(64) |Beneficiary Bank Code |yes |
|beneficiaryAccountNo |string(64) |Beneficiary Account Number |yes |

#### Sample HTTP Raw Request
```json
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

#### HTTP Body Response
<!-- |Field | Data Type | Descriptions |
| --- | --- | --- |
|responseCode | string(2) | Response Code from **Service User** [00 or 03] |
|responseMessage | string(64) | Response Message from **Service User** [00 = Success, 03 = Failed or other message] |
|partnerReferenceNo | string(64) | Unique Transaction Number from **Service User** |
|referenceNo | string(64) | Unique Transaction Number from **Service Provider** |
|result |Array of objects |List of objects <br> `{"partnerReferenceNo": <partnerReferenceNo>, "referenceNo": <referenceNo>, "merchantStoreName": <merchantStoreName>, "merchantOutletID": <merchantOutletID>, "merchantOutletName": <merchantOutletName>, "productReferenceCode": <productReferenceCode>, "productTypeID": <productTypeID>, "productCode": <productCode>, "productName": <productName>, "productPrice": <productPrice>, "productAdminFee": <productAdminFee>, "productMerchantFee": <productMerchantFee>, "transactionDate": <transactionDate>, "customerID": <customerID>, "additionalInfo": {"serialNumber": <serialNumber>, "billDesc": <billDesc>,}}` <br> - `partnerReferenceNo` : Unique Transaction Number from Service User <br> - `referenceNo` : Unique Transaction Number from Service Provider <br> - `merchantStoreName` : lorem ipsum <br> - `merchantOutletID` : lorem ipsum <br> - `merchantOutletName` : lorem ipsum <br> - `productReferenceCode` : lorem ipsum <br> - `productTypeID` : lorem ipsum <br> - `productCode` : lorem ipsum <br> - `productName` : lorem ipsum <br> - `productPrice` : lorem ipsum <br> - `productAdminFee` : lorem ipsum <br> - `productMerchantFee` : lorem ipsum <br> - `transactionDate` : lorem ipsum <br> - `customerID` : lorem ipsum <br> - `serialNumber` : lorem ipsum <br> - `billDesc` : lorem ipsum| -->
<table>
    <tr>
        <td><b>Field</b></td>
        <td><b>Data Type</b></td>
        <td><b>Descriptions</b></td>
    </tr>
    <tr>
        <td>responseCode</td>
        <td>string(2)</td>
        <td>Response Code from Service User [00 or 03]</td>
    </tr>
    <tr>
        <td>responseMessage</td>
        <td>string(64)</td>
        <td>Response Message from Service User [00 = Success, 03 = Failed or other message]</td>
    </tr>
    <tr>
        <td>partnerReferenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service User</td>
    </tr>
    <tr>
        <td>referenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service Provider</td>
    </tr>
    <tr>
        <td>result</td>
        <td>Array of object</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp partnerReferenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service User</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp referenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service Provider</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp merchantStoreName</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp merchantOutletID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp merchantOutletName</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productReferenceCode</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productTypeID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productCode</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productName</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productPrice</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productAdminFee</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productMerchantFee</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp transactionDate</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp customerID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp additionalInfo</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp serialNumber</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp billDesc</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp beneficiaryBankCode</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp beneficiaryBankName</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp beneficiaryAccountNo</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp beneficiaryAccountName</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp remarks</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
</table>

#### Sample HTTP Raw Response (Success)
```json
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


### API Payment Table
#### URL Path
URL Path : `https://{host}/{version}/disbursement-payment`

#### HTTP Method
HTTP Method : `POST`

#### HTTP Header
|Header Name | Header Value |
| --- | --- |
|Content-Type | application/json |
|X-TIMESTAMP|[datetime] (yyyy-MM-ddTHH:mm:ss+07:00) |
|X-SIGNATURE|**[Digital Signature]** |
|Authorization|Basic **[JWT Token]**|

#### HTTP Body Request
|Field | Data Type | Descriptions | Mandatory |
| --- | --- | --- | --- |
|partnerApprovalNo | string(64) | Unique number after **Service User** success deducting customer balance | yes |
|partnerReferenceNo |string(64) |Unique Transaction Number from **Service User** |yes |
|referenceNo |string(64) |Unique Transaction Number from **Service Provider** |yes |

#### Sample HTTP Raw Request
```json
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

#### HTTP Body Response
<table>
    <tr>
        <td><b>Field</b></td>
        <td><b>Data Type</b></td>
        <td><b>Descriptions</b></td>
    </tr>
    <tr>
        <td>responseCode</td>
        <td>string(2)</td>
        <td>Response Code from Service User [00 or 03]</td>
    </tr>
    <tr>
        <td>responseMessage</td>
        <td>string(64)</td>
        <td>Response Message from Service User [00 = Success, 03 = Failed or other message]</td>
    </tr>
    <tr>
        <td>partnerReferenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service User</td>
    </tr>
    <tr>
        <td>referenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service Provider</td>
    </tr>
    <tr>
        <td>result</td>
        <td>Array of object</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp partnerApprovalNo</td>
        <td>string(64)</td>
        <td>Unique number after Service User success deducting customer balance</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp partnerReferenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service User</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp referenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service Provider</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp merchantStoreName</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp merchantOutletID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp merchantOutletName</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productReferenceCode</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productTypeID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productCode</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productName</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productPrice</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productAdminFee</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productMerchantFee</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp transactionDate</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp customerID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp additionalInfo</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp serialNumber</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp billDesc</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp beneficiaryBankCode</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp beneficiaryBankName</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp beneficiaryAccountNo</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp beneficiaryAccountName</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp remarks</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
</table>

#### Sample HTTP Raw Response (Success)
```json
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


### API Advice Table
#### URL Path
URL Path : `https://{host}/{version}/disbursement-advice`

#### HTTP Method
HTTP Method : `POST`

#### HTTP Header
|Header Name | Header Value |
| --- | --- |
|Content-Type | application/json |
|X-TIMESTAMP|[datetime] (yyyy-MM-ddTHH:mm:ss+07:00) |
|X-SIGNATURE|**[Digital Signature]** |
|Authorization|Basic **[JWT Token]**|

#### HTTP Body Request
|Field | Data Type | Descriptions | Mandatory |
| --- | --- | --- | --- |
|partnerReferenceNo | string(64) | Unique Transaction Number from **Service User** | yes |
|referenceNo |string(64) |Unique Transaction Number from **Service Provider** |yes |

#### Sample HTTP Raw Request
```json
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

#### HTTP Body Response
<table>
    <tr>
        <td><b>Field</b></td>
        <td><b>Data Type</b></td>
        <td><b>Descriptions</b></td>
    </tr>
    <tr>
        <td>responseCode</td>
        <td>string(2)</td>
        <td>Response Code from Service User [00 or 03]</td>
    </tr>
    <tr>
        <td>responseMessage</td>
        <td>string(64)</td>
        <td>Response Message from Service User [00 = Success, 03 = Failed or other message]</td>
    </tr>
    <tr>
        <td>partnerReferenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service User</td>
    </tr>
    <tr>
        <td>referenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service Provider</td>
    </tr>
    <tr>
        <td>result</td>
        <td>Array of object</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp partnerApprovalNo</td>
        <td>string(64)</td>
        <td>Unique number after Service User success deducting customer balance</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp partnerReferenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service User</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp referenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service Provider</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp merchantStoreName</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp merchantOutletID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp merchantOutletName</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productReferenceCode</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productTypeID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productCode</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productName</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productPrice</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productAdminFee</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp productMerchantFee</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp transactionDate</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp customerID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp additionalInfo</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp serialNumber</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp billDesc</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp beneficiaryBankCode</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp beneficiaryBankName</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp beneficiaryAccountNo</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp beneficiaryAccountName</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp remarks</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
</table>

#### Sample HTTP Raw Response (Success)
```json
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


### API Callback Table
#### URL Path
URL Path : `{CallbackURL}`

#### HTTP Method
HTTP Method : `POST`

#### HTTP Header
|Header Name | Header Value |
| --- | --- |
|Content-Type | application/json |
|Authorization|Basic **[JWT Token]**|

#### HTTP Body Payload
|Field | Data Type | Descriptions | Mandatory |
| --- | --- | --- | --- |
|partnerReferenceNo | string(64) | Unique Transaction Number from **Service User** | yes |
|responseCode |string(2) |Response Code from **Service User** [00 or 03] |yes |
|responseMessage |string(64) |Response Message from **Service User** [00 = Success, 03 = Failed or other message] |yes |
|referenceNo |string(64) |Unique Transaction Number from **Service Provider** |yes |

#### Sample HTTP Raw Request
```json
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

#### HTTP Body Response
<table>
    <tr>
        <td><b>Field</b></td>
        <td><b>Data Type</b></td>
        <td><b>Descriptions</b></td>
    </tr>
    <tr>
        <td>responseCode</td>
        <td>string(2)</td>
        <td>Response Code from Service User [00 or 03]</td>
    </tr>
    <tr>
        <td>responseMessage</td>
        <td>string(64)</td>
        <td>Response Message from Service User [00 = Success, 03 = Failed or other message]</td>
    </tr>
    <tr>
        <td>partnerReferenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service User</td>
    </tr>
    <tr>
        <td>referenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service Provider</td>
    </tr>
    <tr>
        <td>result</td>
        <td>Array of object</td>
        <td>Lorem ipsum</td>
    </tr>
</table>

#### Sample HTTP Raw Response (Success)
```json
{
    "responseCode": "00",
    "responseMessage": "Success",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-221121-0000006",
    "result": "",
}
```

### Scenario Test
|productCode|customerNumber|Status|
|---|---|---|
|DBSFL|1234567891|- inquiry success (00) <br> - payment success (00) <br> - advice success (00)|
|DBSFL|1234567892|- inquiry success (00) <br> - payment pending (02) <br> - advice success (00)|
|DBSFL|1234567893|- inquiry success (00) <br> - payment pending (02) <br> - advice failed (96)|
|DBSFL|1234567894|- inquiry success (00), <br> - payment failed (17)|
|DBSFL|1234567895|- inquiry failed (96)|