<h2><b>PDAM</b></h2>

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
	"productCode": "PDAMKABTANGERANG",
	"productPrice": 0,
	"customerID": "735711761",
	"customerPeriode": "",
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
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp desc</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp alamat</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp detail</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp biayaLain</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp denda</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp meterAkhir</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp meterAwal</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp nilaiTagihan</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp periode</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp additionalDetail</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp jatuhTempo</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp retribusi</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp tunggakanDanDenda</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp adminTutupBuka</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp jatuhTempo</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp lembarTagihan</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
</table>

<!-- | Field | Description |
| --- | --- |
|productTypeID |1: Prepaid product,<br> 2: Postpaid product |
|productPrice |Total bill/product price |
|productAdminFee |Fixed admin fee for customer |
|productMerchantFee |Sharing fee that **Service User** will received|
|alamat |Biller Address |
|biayaLain |Other fee |
|denda |Fine/penalty fee |
|meterAkhir |End of usage meter |
|meterAwal |Start of usage meter |
|nilaiTagihan |Base bill amount |
|periode |Bill periode (format : ymd) |
|jatuhTempo |Bill due date (day of month) |
|retribusi |Retribution fee |
|tunggakanDanDenda |utstanding and fine fee |
|adminTutupBuka |Open close admin fee |
|lembarTagihan |Bill count |
|tarif |Rate of usage | -->

#### Sample HTTP Raw Response (Success)
```json
{

    "responseCode": "00",
    "responseMessage": "Success",
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "DEV-220118-0000006",
    "result": {
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "DEV-220118-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "PDAM",
        "productTypeID": 2,
        "productCode": "PDAMKABTANGERANG",
        "productName": "PDAM KAB. TANGERANG",
        "productPrice": 164858,
        "productAdminFee": 2300,
        "productMerchantFee": 700,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "735711761",
        "additionalInfo": {
            "serialNumber": "",
            "billDesc": "{\"customerName\":\"IDA\",\"desc\":{\"alamat\":\"Kp.Pecinan 004 01\",\"detail\":[{\"biayaLain\":\"00000000\",\"denda\":\"15000\",\"meterAkhir\":\"60\",\"meterAwal\":\"59\",\"nilaiTagihan\":\"15800\",\"periode\":\"202008\",\"additionalDetail\":{\"jatuhTempo\":\"1 s/d 15\",\"retribusi\":\"0\",\"tuggakanDanDenda\":\"0\",\"adminTutupBuka\":\"0\"}},{\"biayaLain\":\"00000000\",\"denda\":\"15000\",\"meterAkhir\":\"61\",\"meterAwal\":\"60\",\"nilaiTagihan\":\"15800\",\"periode\":\"202009\",\"additionalDetail\":{\"jatuhTempo\":\"1 s/d 15\",\"retribusi\":\"0\",\"tuggakanDanDenda\":\"0\",\"adminTutupBuka\":\"0\"}}],\"jatuhTempo\":\"1 s/d 15\",\"lembarTagihan\":2,\"tarif\":\"1.1\"}}",
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
|partnerApprovalNo | string(64) |Unique number after **Service User** success deducting customer balance |yes |
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
        <td style="width:40%"><b>Field</b></td>
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
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp desc</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp alamat</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp detail</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp biayaLain</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp denda</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp meterAkhir</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp meterAwal</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp nilaiTagihan</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp periode</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp additionalDetail</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp jatuhTempo</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp retribusi</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp tunggakanDanDenda</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp adminTutupBuka</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp jatuhTempo</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp lembarTagihan</td>
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
    "referenceNo": "DEV-220118-0000006",
    "result": {
        "partnerApprovalNo": "ytyui876543",
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "DEV-220118-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "PDAM",
        "productTypeID": 2,
        "productCode": "PDAMKABTANGERANG",
        "productName": "PDAM KAB. TANGERANG",
        "productPrice": 164858,
        "productAdminFee": 2300,
        "productMerchantFee": 700,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "735711761",
        "additionalInfo": {
            "serialNumber": "",
            "billDesc": "{\"customerName\":\"IDA\",\"desc\":{\"alamat\":\"Kp.Pecinan 004 01\",\"detail\":[{\"biayaLain\":\"00000000\",\"denda\":\"15000\",\"meterAkhir\":\"60\",\"meterAwal\":\"59\",\"nilaiTagihan\":\"15800\",\"periode\":\"202008\",\"additionalDetail\":{\"jatuhTempo\":\"1 s/d 15\",\"retribusi\":\"0\",\"tuggakanDanDenda\":\"0\",\"adminTutupBuka\":\"0\"}},{\"biayaLain\":\"00000000\",\"denda\":\"15000\",\"meterAkhir\":\"61\",\"meterAwal\":\"60\",\"nilaiTagihan\":\"15800\",\"periode\":\"202009\",\"additionalDetail\":{\"jatuhTempo\":\"1 s/d 15\",\"retribusi\":\"0\",\"tuggakanDanDenda\":\"0\",\"adminTutupBuka\":\"0\"}}],\"jatuhTempo\":\"1 s/d 15\",\"lembarTagihan\":2,\"tarif\":\"1.1\"}}",
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
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp desc</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp alamat</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp detail</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp biayaLain</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp denda</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp meterAkhir</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp meterAwal</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp nilaiTagihan</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp periode</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp additionalDetail</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp jatuhTempo</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp retribusi</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp tunggakanDanDenda</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp adminTutupBuka</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp jatuhTempo</td>
        <td>-</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp lembarTagihan</td>
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
    "referenceNo": "DEV-220118-0000006",
    "result": {
        "partnerApprovalNo": "ytyui876543",
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "DEV-220118-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "PDAM",
        "productTypeID": 2,
        "productCode": "PDAMKABTANGERANG",
        "productName": "PDAM KAB. TANGERANG",
        "productPrice": 164858,
        "productAdminFee": 2300,
        "productMerchantFee": 700,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "735711761",
        "additionalInfo": {
			"serialNumber": "",
			"billDesc": "{\"customerName\":\"IDA\",\"desc\":{\"alamat\":\"Kp.Pecinan 004 01\",\"detail\":[{\"biayaLain\":\"00000000\",\"denda\":\"15000\",\"meterAkhir\":\"60\",\"meterAwal\":\"59\",\"nilaiTagihan\":\"15800\",\"periode\":\"202008\",\"additionalDetail\":{\"jatuhTempo\":\"1 s/d 15\",\"retribusi\":\"0\",\"tuggakanDanDenda\":\"0\",\"adminTutupBuka\":\"0\"}},{\"biayaLain\":\"00000000\",\"denda\":\"15000\",\"meterAkhir\":\"61\",\"meterAwal\":\"60\",\"nilaiTagihan\":\"15800\",\"periode\":\"202009\",\"additionalDetail\":{\"jatuhTempo\":\"1 s/d 15\",\"retribusi\":\"0\",\"tuggakanDanDenda\":\"0\",\"adminTutupBuka\":\"0\"}}],\"jatuhTempo\":\"1 s/d 15\",\"lembarTagihan\":2,\"tarif\":\"1.1\"}}",

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
    "partnerReferenceNo": "TRX-000000351",
    "referenceNo": "Callback-0000006",
    "result": {
        "partnerApprovalNo": "ytyui876543",
        "partnerReferenceNo": "TRX-000000351",
        "referenceNo": "Callback-0000006",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "PDAM",
    	"productTypeID": 2,
        "productCode": "PDAMKABTANGERANG",
        "productName": "PDAM KAB. TANGERANG",
        "productPrice": 164858,
        "productAdminFee": 2300,
        "productMerchantFee": 700,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "735711761",
        "additionalInfo": {
            "serialNumber": "",
            "billDesc": "{\"customerName\":\"IDA\",\"desc\":{\"alamat\":\"Kp.Pecinan 004 01\",\"detail\":[{\"biayaLain\":\"00000000\",\"denda\":\"15000\",\"meterAkhir\":\"60\",\"meterAwal\":\"59\",\"nilaiTagihan\":\"15800\",\"periode\":\"202008\",\"additionalDetail\":{\"jatuhTempo\":\"1 s/d 15\",\"retribusi\":\"0\",\"tuggakanDanDenda\":\"0\",\"adminTutupBuka\":\"0\"}},{\"biayaLain\":\"00000000\",\"denda\":\"15000\",\"meterAkhir\":\"61\",\"meterAwal\":\"60\",\"nilaiTagihan\":\"15800\",\"periode\":\"202009\",\"additionalDetail\":{\"jatuhTempo\":\"1 s/d 15\",\"retribusi\":\"0\",\"tuggakanDanDenda\":\"0\",\"adminTutupBuka\":\"0\"}}],\"jatuhTempo\":\"1 s/d 15\",\"lembarTagihan\":2,\"tarif\":\"1.1\"}}",
        }
    }
}
```

#### HTTP Body Response
<table>
    <tr>
        <td style="width:30%"><b>Field</b></td>
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
|productCode|customerNumber|Status|
|---|---|---|
|PDAMKABTANGERANG|735711761|- inquiry success (00) <br> - payment success (00) <br> - advice success (00)|
|PDAMKABTANGERANG|735711762|- inquiry success (00) <br> - payment pending (02) <br> - advice success (00)|
|PDAMKABTANGERANG|735711763|- inquiry success (00) <br> - payment pending (02) <br> - advice failed (96 or 18)|
|PDAMKABTANGERANG|735711764|- inquiry success (00) <br> - payment failed (96 or 18)|
|PDAMKABTANGERANG|735711765|- inquiry failed (96 or 18)|