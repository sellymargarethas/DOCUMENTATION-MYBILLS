# Disbursement
## API Inquiry Table
<table>
<tr>
	<td>Name </td>
	<td  colspan="4">API Inquiry</td>
</tr>
<tr>
	<td>URL Path </td>
	<td  colspan="4">https://{host}/{version}/disbursement-inquiry </td>
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
	<td  rowspan="7">HTTP Body Request </td>
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
	<td>remarks </td>
	<td>string(64) </td>
	<td>Remark/transaction description,<br>*recommended to use a unique value </td>
	<td>yes </td>
</tr>
<tr>
	<td>beneficiaryBankCode </td>
	<td>string(64) </td>
	<td>Beneficiary Bank Code</td>
	<td>yes </td>
</tr>
<tr>
	<td>beneficiaryAccountNo </td>
	<td>string(64) </td>
	<td>Beneficiary Account Number</td>
	<td>yes </td>
</tr>
<tr>
	<td>Sample HTTP Raw Request </td>
	<td  colspan="4">


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
	<td  colspan="4">https://{host}/{version}/disbursement-payment </td>
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
	<td  colspan="4">https://{host}/{version}/disbursement-advice </td>
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
    "referenceNo": "DEV-221121-0000006",
    "result": "",
}
```


</td>
</tr>
</table>