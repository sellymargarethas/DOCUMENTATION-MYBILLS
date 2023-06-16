<h2><b>Biller (General)</b></h2>

### API Inquiry Table
#### URL Path
URL Path : `https://{host}/{version}/inquiry`

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
|productPrice |integer |Product Price |no |
|customerID |string(64) |Customer ID of the transaction |yes |
|customerPeriode |string(64) |Total n month would be paid **(mandatory for specified product)** |conditional |

#### Sample HTTP Raw Request
```json
POST .../v2.0/inquiry HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-01-18T13:50:04+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
	"partnerReferenceNo": "TRX-000000351",
	"productCode": "EWOV20",
	"productPrice": 0,
	"customerID": "081284351131",
	"customerPeriode": "",
}
```

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
        <td>responseDatetime</td>
        <td>string(100)</td>
        <td>Response Date Time from Service User (yyyy-MM- dd'T'HH:mm:ss.SSS'T'Z)</td>
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
        <td>Array of object</td>
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
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp customerName</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
</table>

#### Sample HTTP Raw Response (Success)
```json
{
    "responseCode": "00",
    "responseMessage": "Success",
    "responseDatetime": "2022-01-18T13:50:04+07:00",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-220118-0000006",
    "result": {
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "Callback-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "EOVO",
        "productTypeID": 1,
        "productCode": "EWOV20",
        "productName": "SALDO OVO 20K",
        "productPrice": 20100,
        "productAdminFee": 0,
        "productMerchantFee": 0,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "081284351131",
        "additionalInfo": {
            "serialNumber": "",
            "billDesc": "{\"customerName\":\"Jh*n D*e\"}",
        }
    }
}
```

### API Payment Table
#### URL Path
URL Path : `https://{host}/{version}/payment`

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
|partnerReferenceNo | string(64) | Unique Transaction Number from **Service User** | yes |
|referenceNo |string(64) |Unique Transaction Number from **Service Provider** |yes |

#### Sample HTTP Raw Request
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
        <td>responseDatetime</td>
        <td>string(100)</td>
        <td>Response Date Time from Service User (yyyy-MM- dd'T'HH:mm:ss.SSS'T'Z)</td>
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
        <td>Array of object</td>
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
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp customerName</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
</table>

#### Sample HTTP Raw Response (Success)
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
        "productReferenceCode": "EOVO",
        "productTypeID": 1,
        "productCode": "EWOV20",
        "productName": "SALDO OVO 20K",
        "productPrice": 20100,
        "productAdminFee": 0,
        "productMerchantFee": 0,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "081284351131",
        "additionalInfo": {
            "serialNumber": "9111722123461556920",
            "billDesc": "{\"customerName\":\"Jh*n D*e\"}",
        }
    }
}
```

### API Advice Table
#### URL Path
URL Path : `https://{host}/{version}/advice`

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
        <td>responseDatetime</td>
        <td>string(100)</td>
        <td>Response Date Time from Service User (yyyy-MM- dd'T'HH:mm:ss.SSS'T'Z)</td>
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
        <td>&nbsp &nbsp &nbsp &nbsp partnerApprovalNo</td>
        <td>string(64)</td>
        <td>Unique number after Service User success deducting customer balance</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp partnerReferenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service User</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp referenceNo</td>
        <td>string(64)</td>
        <td>Unique Transaction Number from Service Provider</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp merchantStoreName</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp merchantOutletID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp merchantOutletName</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp productReferenceCode</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp productTypeID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp productCode</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp productName</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp productPrice</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp productAdminFee</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp productMerchantFee</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp transactionDate</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp customerID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp additionalInfo</td>
        <td>Array of object</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp serialNumber</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp billDesc</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp customerName</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
</table>

#### Sample HTTP Raw Response (Success)
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
        "productReferenceCode": "EOVO",
        "productTypeID": 1,
        "productCode": "EWOV20",
        "productName": "SALDO OVO 20K",
        "productPrice": 20100,
        "productAdminFee": 0,
        "productMerchantFee": 0,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "081284351131",
        "additionalInfo": {
            "serialNumber": "9111722123461556920",
        	"billDesc": "{\"customerName\":\"Jh*n D*e\"}",
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
|X-TIMESTAMP|[datetime] (yyyy-MM-ddTHH:mm:ss+07:00) |

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
        "productReferenceCode": "EOVO",
        "productTypeID": 1,
        "productCode": "EWOV20",
        "productName": "SALDO OVO 20K",
        "productPrice": 20100,
        "productAdminFee": 0,
        "productMerchantFee": 0,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "081284351131",
        "additionalInfo": {
            "serialNumber": "9111722123461556920",
            "billDesc": "{\"customerName\":\"Jh*n D*e\"}",
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
        <td>responseDatetime</td>
        <td>string(100)</td>
        <td>Response Date Time from Service User (yyyy-MM- dd'T'HH:mm:ss.SSS'T'Z)</td>
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
    "responseDatetime": "2022-01-18T13:50:04+07:00",
    "result": "",
}
```

### Scenario Test
<h4><b>E-Wallet</b></h4>

|productCode|customerNumber|Status|
|---|---|---|
|EWSP20|081284351131|- inquiry success (00) <br> - payment success (00) <br> - advice success (00)|
|EWSP20|081284351132|- inquiry success (00) <br> - payment pending (02) <br> - advice success (00)|
|EWSP20|081284351133|- inquiry success (00) <br> - payment pending (02) <br> - advice failed (96)|
|EWSP20|081284351134|- inquiry success (00) <br> - payment failed (96)|
|EWSP20|081284351135|- inquiry failed (96)|

<h4><b>Paket Data</b></h4>

|productCode|customerNumber|Status|
|---|---|---|
|DTSFL2GB|081284351121|- inquiry success (00) <br> - payment success (00) <br> - advice success (00)|
|DTSFL2GB|081284351122|- inquiry success (00) <br> - payment pending (02) <br> - advice success (00)|
|DTSFL2GB|081284351123|- inquiry success (00) <br> - payment pending (02) <br> - advice failed (96)|
|DTSFL2GB|081284351124|- inquiry success (00) <br> - payment failed (96)|
|DTSFL2GB|081284351125|- inquiry failed (96)|

<h4><b>Pulsa</b></h4>

|productCode|customerNumber|Status|
|---|---|---|
|VTS25|081284351111|- inquiry success (00) <br> - payment success (00) <br> - advice success (00)|
|VTS25|081284351112|- inquiry success (00) <br> - payment pending (02) <br> - advice success (00)|
|VTS25|081284351113|- inquiry success (00) <br> - payment pending (02) <br> - advice failed (96)|
|VTS25|081284351114|- inquiry success (00) <br> - payment failed (96)|
|VTS25|081284351115|- inquiry failed (96)|