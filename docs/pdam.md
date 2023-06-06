# PDAM
## API Inquiry Table
<table>
<tr>
	<td>Name </td>
	<td  colspan="4">API Inquiry</td>
</tr>
<tr>
	<td>URL Path </td>
	<td  colspan="4">https://{host}/{version}/inquiry </td>
</tr>
<tr>
	<td>HTTP Method </td>
	<td  colspan="4">POST </td>
</tr>
<tr>
	<td  rowspan="5">HTTP Header </td>
	<td  colspan="2"><b>Header Name</b></td>
	<td  colspan="2"><b>Header Value</b></td>
</tr>
<tr>
	<td  colspan="2">Content-Type </td>
	<td  colspan="2">application/json </td>
</tr>
<tr>
	<td  colspan="2">X-TIMESTAMP </td>
	<td  colspan="2">[datetime] (yyyy-MM-ddTHH:mm:ss+07:00) </td>
</tr>
<tr>
	<td  colspan="2">X-SIGNATURE </td>
	<td  colspan="2"><b>[Digital Signature]</b></td>
</tr>
<tr>
	<td  colspan="2">Authorization </td>
	<td  colspan="2">Basic <b>[JWT Token]</b>  </td>
</tr>
<tr>
	<td  rowspan="6">HTTP Body Request </td>
	<td><b>Field</b></td>
	<td><b>Data Type</b></td>
	<td><b>Descriptions</b></td>
	<td><b>Mandatory</b></td>
</tr>
<tr>
	<td>partnerReferenceNo </td>
	<td>string(64) </td>
	<td>Unique Transaction Number from <b>Service User</b></td>
	<td>yes </td>
</tr>
<tr>
	<td>productCode </td>
	<td>string(64) </td>
	<td>Product Code </td>
	<td>yes </td>
</tr>
<tr>
	<td>productPrice </td>
	<td>integer </td>
	<td>Product Price </td>
	<td>no </td>
</tr>
<tr>
	<td>customerID </td>
	<td>string(64) </td>
	<td>Customer ID of the transaction </td>
	<td>yes </td>
</tr>
<tr>
	<td>customerPeriode </td>
	<td>string(64) </td>
	<td>Total n month would be paid <b>(mandatory for specified product)</b></td>
	<td>conditional </td>
</tr>
<tr>
	<td>Sample HTTP Raw Request </td>
	<td  colspan="4">


```php
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


</td>
</tr>
<tr>
	<td  rowspan="18">HTTP Body Response </td>
	<td  colspan="2"><b>Field</b></td>
	<td  colspan="2"><b>Descriptions</b></td>
</tr>
<tr>
	<td  colspan="2">productTypeID </td>
	<td  colspan="2">1: Prepaid product,<br> 2: Postpaid product</td>
</tr>
<tr>
	<td  colspan="2">productPrice </td>
	<td  colspan="2">Total bill/product price </td>
</tr>
<tr>
	<td  colspan="2">productAdminFee </td>
	<td  colspan="2">Fixed admin fee for customer </td>
</tr>
<tr>
	<td  colspan="2">productMerchantFee </td>
	<td  colspan="2">Sharing fee that <b>Service User</b> will received </td>
</tr>
<tr>
	<td  colspan="2">alamat </td>
	<td  colspan="2">Biller Address </td>
</tr>
<tr>
	<td  colspan="2">biayaLain </td>
	<td  colspan="2">Other fee </td>
</tr>
<tr>
	<td  colspan="2">denda </td>
	<td  colspan="2">Fine/penalty fee </td>
</tr>
<tr>
	<td  colspan="2">meterAkhir </td>
	<td  colspan="2">End of usage meter </td>
</tr>
<tr>
	<td  colspan="2">meterAwal </td>
	<td  colspan="2">Start of usage meter </td>
</tr>
<tr>
	<td  colspan="2">nilaiTagihan </td>
	<td  colspan="2">Base bill amount </td>
</tr>
<tr>
	<td  colspan="2">periode </td>
	<td  colspan="2">Bill period (format : ymd) </td>
</tr>
<tr>
	<td  colspan="2">jatuhTempo </td>
	<td  colspan="2">Bill due date (day of month) </td>
</tr>
<tr>
	<td  colspan="2">retribusi </td>
	<td  colspan="2">Retribution fee </td>
</tr>
<tr>
	<td  colspan="2">tunggakanDanDenda </td>
	<td  colspan="2">Outstanding and fine fee </td>
</tr>
<tr>
	<td  colspan="2">adminTutupBuka </td>
	<td  colspan="2">Open close admin fee </td>
</tr>
<tr>
	<td  colspan="2">lembarTagihan </td>
	<td  colspan="2">Bill count </td>
</tr>
<tr>
	<td  colspan="2">tarif </td>
	<td  colspan="2">Rate of usage </td>
</tr>
<tr>
	<td>Sample HTTP Raw Response (Success) </td>
	<td  colspan="4">


```php
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


</td>
</tr>
</table>

## API Payment Table
<table>
<tr>
	<td>Name </td>
	<td  colspan="4">API Payment</td>
</tr>
<tr>
	<td>URL Path </td>
	<td  colspan="4">https://{host}/{version}/payment </td>
</tr>
<tr>
	<td>HTTP Method </td>
	<td  colspan="4">POST </td>
</tr>
<tr>
	<td  rowspan="5">HTTP Header </td>
	<td  colspan="2"><b>Header Name</b></td>
	<td  colspan="2"><b>Header Value</b></td>
</tr>
<tr>
	<td  colspan="2">Content-Type </td>
	<td  colspan="2">application/json </td>
</tr>
<tr>
	<td  colspan="2">X-TIMESTAMP </td>
	<td  colspan="2">[datetime] (yyyy-MM-ddTHH:mm:ss+07:00) </td>
</tr>
<tr>
	<td  colspan="2">X-SIGNATURE </td>
	<td  colspan="2"><b>[Digital Signature]</b></td>
</tr>
<tr>
	<td  colspan="2">Authorization </td>
	<td  colspan="2">Basic <b>[JWT Token]</b>  </td>
</tr>
<tr>
	<td  rowspan="4">HTTP Body Request </td>
	<td><b>Field</b></td>
	<td><b>Data Type</b></td>
	<td><b>Descriptions</b></td>
	<td><b>Mandatory</b></td>
</tr>
<tr>
	<td>partnerApprovalNo </td>
	<td>string(64) </td>
	<td>Unique number after <b>Service User</b> success deducting customer balance</b></td>
	<td>yes </td>
</tr>
<tr>
	<td>partnerReferenceNo </td>
	<td>string(64) </td>
	<td>Unique Transaction Number from <b>Service User</b> </td>
	<td>yes </td>
</tr>
<tr>
	<td>referenceNo </td>
	<td>string(64) </td>
	<td>Unique Transaction Number from <b>Service Provider</b> </td>
	<td>yes </td>
</tr>
<tr>
	<td>Sample HTTP Raw Request </td>
	<td  colspan="4">


```php
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


</td>
</tr>
<tr>
		<td>Sample HTTP Raw Response (Success) </td>
		<td  colspan="4">


```php
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


</td>
</tr>
</table>

## API Advice Table
<table>
<tr>
	<td>Name </td>
	<td  colspan="4">API Advice</td>
</tr>
<tr>
	<td>URL Path </td>
	<td  colspan="4">https://{host}/{version}/advice </td>
</tr>
<tr>
	<td>HTTP Method </td>
	<td  colspan="4">POST </td>
</tr>
<tr>
	<td  rowspan="5">HTTP Header </td>
	<td  colspan="2"><b>Header Name</b></td>
	<td  colspan="2"><b>Header Value</b></td>
</tr>
<tr>
	<td  colspan="2">Content-Type </td>
	<td  colspan="2">application/json </td>
</tr>
<tr>
	<td  colspan="2">X-TIMESTAMP </td>
	<td  colspan="2">[datetime] (yyyy-MM-ddTHH:mm:ss+07:00) </td>
</tr>
<tr>
	<td  colspan="2">X-SIGNATURE </td>
	<td  colspan="2"><b>[Digital Signature]</b></td>
</tr>
<tr>
	<td  colspan="2">Authorization </td>
	<td  colspan="2">Basic <b>[JWT Token]</b>  </td>
</tr>
<tr>
	<td  rowspan="3">HTTP Body Request </td>
	<td><b>Field</b></td>
	<td><b>Data Type</b></td>
	<td><b>Descriptions</b></td>
	<td><b>Mandatory</b></td>
</tr>
<tr>
	<td>partnerReferenceNo </td>
	<td>string(64) </td>
	<td>Unique Transaction Number from <b>Service User</b> </td>
	<td>yes </td>
</tr>
<tr>
	<td>referenceNo </td>
	<td>string(64) </td>
	<td>Unique Transaction Number from <b>Service Provider</b> </td>
	<td>yes </td>
</tr>
<tr>
	<td>Sample HTTP Raw Request </td>
	<td  colspan="4">


```php
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


</td>
</tr>
<tr>
	<td>Sample HTTP Raw Response (Success) </td>
	<td  colspan="4">


```php
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


</td>
</tr>
</table>

## API Callback Table
<table>
<tr>
	<td>Name </td>
	<td  colspan="4">API Callback</td>
</tr>
<tr>
	<td>URL Path </td>
	<td  colspan="4">{CallbackUrl}</td>
</tr>
<tr>
	<td>HTTP Method </td>
	<td  colspan="4">POST </td>
</tr>
<tr>
	<td  rowspan="3">HTTP Header </td>
	<td  colspan="2"><b>Header Name</b></td>
	<td  colspan="2"><b>Header Value</b></td>
</tr>
<tr>
	<td  colspan="2">Content-Type </td>
	<td  colspan="2">application/json </td>
</tr>
<tr>
	<td  colspan="2">X-TIMESTAMP </td>
	<td  colspan="2">[datetime] (yyyy-MM-ddTHH:mm:ss+07:00) </td>
</tr>
<tr>
	<td  rowspan="5">HTTP Body Payload </td>
	<td><b>Field</b></td>
	<td><b>Data Type</b></td>
	<td><b>Descriptions</b></td>
	<td><b>Mandatory</b></td>
</tr>
<tr>
	<td>partnerReferenceNo </td>
	<td>string(64) </td>
	<td>Unique Transaction Number from <b>Service User</b> </td>
	<td>yes </td>
</tr>
<tr>
	<td>responseCode </td>
	<td>string(2) </td>
	<td>Response Code from <b>Service User</b> [00 or 03] </td>
	<td>yes </td>
</tr>
<tr>
	<td>responseMessage </td>
	<td>string(64) </td>
	<td>Response Message from <b>Service User</b> [00 = Success, 03 = Failed or other message] </td>
	<td>yes </td>
</tr>
<tr>
	<td>referenceNo </td>
	<td>string(64) </td>
	<td>Unique Transaction Number from <b>Service Provider</b> </td>
	<td>yes </td>
</tr>
<tr>
	<td>Sample HTTP Raw Request </td>
	<td  colspan="4">


```php
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


</td>
</tr>
<tr>
	<td>Sample HTTP Raw Response (Success) </td>
	<td  colspan="4">


```php
{
    "responseCode": "00",
    "responseMessage": "Success",
    "responseDatetime": "2022-01-18T13:50:04+07:00",
    "result": "",
}
```


</td>
</tr>
</table>