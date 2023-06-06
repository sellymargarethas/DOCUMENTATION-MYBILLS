# Flazz BCA
## API Credential Table
<table>
<tr>
	<td>Name </td>
	<td  colspan="4">API Credential</td>
</tr>
<tr>
	<td>URL Path </td>
	<td  colspan="4">https://{host}/{version}/bca-flazz-get-credential </td>
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
	<td  rowspan="2">HTTP Body Request </td>
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
	<td>Sample HTTP Raw Request </td>
	<td  colspan="4">


```php
POST .../v2.0/bca-flazz-get-credential HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-01-18T13:50:04+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
    "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
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
    "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
    "referenceNo": "BIL-202305010002",
    "result": {
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
    	"merchantOutletName": "OUTLET ABC",
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "additionalInfo": {
            "bcaFlazzMID": "123456789012",
            "bcaFlazzTID": "123456",
            "bcaFlazzATD": "ATD029339",
            "bcaFlazzAccessCard": "12390987654323",
            "bcaFlazzAccessCardCode": "23455",
            "bcaFlazzSignature": "1234567hcdkxjcfdnfkldnkdnsl3333==",
        }
    }
}
```


</td>
</tr>
</table>

## API Inquiry Table
<table>
<tr>
	<td>Name </td>
	<td  colspan="4">API Inquiry</td>
</tr>
<tr>
	<td>URL Path </td>
	<td  colspan="4">https://{host}/{version}/bca-flazz-inquiry </td>
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
	<td  rowspan="5">HTTP Body Request </td>
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
	<td>productCode </td>
	<td>string(64) </td>
	<td>Product Code</td>
	<td>yes </td>
</tr>
<tr>
	<td>customerID </td>
	<td>string(64) </td>
	<td>Customer ID of the transaction</td>
	<td>yes </td>
</tr>
<tr>
	<td>requestData </td>
	<td>string(448) </td>
	<td>Card Data </td>
	<td>yes </td>
</tr>
<tr>
	<td>Sample HTTP Raw Request </td>
	<td  colspan="4">


```php
POST .../v2.0/bca-flazz-inquiry HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-01-18T13:50:04+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
    "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
    "productCode": "EMOFLZ20",
    "customerID": "0145200020896975",
    "requestData": "0102020020230501164540534D494B41534948455455303036333888500191467632333035303130303030303030303032697C355E654B2087871C4B0B357C4A69878E5B208E0D6534695B4B1C350D698E874B5B190B5E344B35344B5B19690B4AEEF7",
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
    "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
    "referenceNo": "BIL-230501-0024033",
    "result": {
        "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
        "referenceNo": "BIL-230501-0024033",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "ETOBC",
        "productTypeID": 1,
        "productCode": "EMOFLZ20",
        "productName": "SALDO ETOLL FLAZZ 20K",
        "productPrice": 20100,
        "productAdminFee": 0,
        "productMerchantFee": 0,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "0145200020896975",
        "additionalInfo": {
            "serialNumber": "",
            "billDesc": "{\"responseData\":\"0102020020230501164540534D494B415349484554553030363338885001914676323330353031303030303030303030326E6DB77A68B7227D53CD226ECD5DCFCDA46892CDA4CD536D6E6ED3CF5D68B0B768D368B034687AD37D7A34CDCDB768539642\"}",
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
	<td  colspan="4">https://{host}/{version}/bca-flazz-payment </td>
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
	<td  rowspan="5">HTTP Body Request </td>
	<td><b>Field</b></td>
	<td><b>Data Type</b></td>
	<td><b>Descriptions</b></td>
	<td><b>Mandatory</b></td>
</tr>
<tr>
	<td>partnerApprovalNo </td>
	<td>string(64) </td>
	<td>Unique number after <b>Service User</b> success deducting customer balance</td>
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
	<td>requestData </td>
	<td>string(448) </td>
	<td>Card Data</td>
	<td>yes </td>
</tr>
<tr>
	<td>Sample HTTP Raw Request </td>
	<td  colspan="4">


```php
POST .../v2.0/bca-flazz-payment HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-01-18T13:50:04+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
    "partnerReferenceNo": "DEV-FLAZZ-202305010002",
    "partnerApprovalNo": "DEV-FLAZZ-202305010002",
    "referenceNo": "BIL-230501-0024033",
    "requestData": "0102022401452000208969750024546600020000202305011645531704334912534D494B4153494845545530303633388850019146763233303530313030303030303030303269698E870B0D8769358E0D5B197C4A691C0D7C0D195B65875B0D351C0B207C1C655E207C4A4A341C4A34205B69690D69870B8787695E355E354A2035194A205E1C878E34651C5E0B5E8E0D0B3569355B7C4A5B208E0B69878E5B697C7C0B8E191C652087341935206587695E0D8E19655B1C69342087690B5E343519357C7C19190D3465345E5B65694B7C20344A5B1944BD36E5E6E18420B983",
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
    "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
    "referenceNo": "BIL-230501-0024033",
    "result": {
        "partnerApprovalNo": "DEV-FLAZZ-202305010002",
        "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
        "referenceNo": "BIL-230501-0024033",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "ETOBC",
        "productTypeID": 1,
        "productCode": "EMOFLZ20",
        "productName": "SALDO ETOLL FLAZZ 20K",
        "productPrice": 20100,
        "productAdminFee": 0,
        "productMerchantFee": 0,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "0145200020896975",
        "additionalInfo": {
            "serialNumber": "",
            "billDesc": "{\"responseData\":\"0124014520002089697500020000000000000028043320230501164554D3CD5D34532268A4B0B7345D22A4A47D929222B75D92CD227ACFA4927A5D5DB76DB07DB07D7A6E6DB05D3468B07DCF682268CD6E7ACD68B7D3A4B0CD7A5D536D53B7CF7AD3CF7ACD5D6E68B7D36E7AA4CF53B76E5D6DA4B7D36ED353CFA47A34D3CF7DB0B0A46E686DB77A3453A4226D68CD53B05D68CF7AB76E22226E536DB07A5D5D7DA46D22A453B734686DA422B05277\"}",
        }
    }
}
```


</td>
</tr>
</table>

## API Acknowledge Table
<table>
<tr>
	<td>Name </td>
	<td  colspan="4">API Acknowledge</td>
</tr>
<tr>
	<td>URL Path </td>
	<td  colspan="4">https://{host}/{version}/bca-flazz-ack</td>
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
	<td>partnerReferenceNo </td>
	<td>string(64) </td>
	<td>Unique Transaction Number from <b>Service User</b> </td>
	<td>yes </td>
</tr>
<tr>
	<td>referenceNo </td>
	<td>string(64) </td>
	<td>Unique Transaction Number from <b>Service Provider</b></td>
	<td>yes </td>
</tr>
<tr>
	<td>requestData </td>
	<td>string(448) </td>
	<td>Card Data</td>
	<td>yes </td>
</tr>
<tr>
	<td>Sample HTTP Raw Request </td>
	<td  colspan="4">


```php
POST https://www.partner-url.com/bca-flazz-ack HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-01-18T13:50:04+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
    "partnerReferenceNo": "DEV-FLAZZ-202305010002",
    "referenceNo": "BIL-230501-0024033",
    "requestData": "0102022401452000208969750026546600020000202305011645531704334912534D494B415349484554553030363338885001914676323330353031303030303030303030328734354B1987344A8E8E694B5E8E0B34694B4A8E204B1935198E34875B5E208E195E69207C207C1C69348E0D8E694A8E4B697C876520194A650D201C20690D19190D4B8E8E0B1987204B8734870D8E697C4A5B208E0B69878E5B697C7C0B8E194A1C200D695B8E5E4B5B34871C0D7C7C698E0B340D4A4B0B5B205E5E65354A348E690B2020204B190B19654B5B191C878E7C195B0B655B344B194B4B4A5E0D4A7C355E4B878E5B19874B5E8734655B8769205B0D1C694A4B1C7C1935205E875E44BD36E5E6E18420F644",
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
    "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
    "referenceNo": "BIL-230501-0024033",
    "result": "",
}
```


</td>
</tr>
</table>

## API Reversal Table
<table>
<tr>
	<td>Name </td>
	<td  colspan="4">API Reversal</td>
</tr>
<tr>
	<td>URL Path </td>
	<td  colspan="4">https://{host}/{version}/bca-flazz-reversal</td>
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
	<td>partnerReferenceNo </td>
	<td>string(64) </td>
	<td>Unique Transaction Number from <b>Service User</b> </td>
	<td>yes </td>
</tr>
<tr>
	<td>referenceNo </td>
	<td>string(64) </td>
	<td>Unique Transaction Number from <b>Service Provider</b></td>
	<td>yes </td>
</tr>
<tr>
	<td>requestData </td>
	<td>string(448) </td>
	<td>Card Data</td>
	<td>yes </td>
</tr>
<tr>
	<td>Sample HTTP Raw Request </td>
	<td  colspan="4">


```php
POST https://www.partner-url.com/bca-flazz-reversal HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-01-18T13:50:04+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
    "partnerReferenceNo": "DEV-FLAZZ-202305010002",
    "referenceNo": "BIL-230501-0024033",
    "requestData": "0102022401452000208969750026546600020000202305011645531704334912534D494B415349484554553030363338885001914676323330353031303030303030303030328734354B1987344A8E8E694B5E8E0B34694B4A8E204B1935198E34875B5E208E195E69207C207C1C69348E0D8E694A8E4B697C876520194A650D201C20690D19190D4B8E8E0B1987204B8734870D8E697C4A5B208E0B69878E5B697C7C0B8E194A1C200D695B8E5E4B5B34871C0D7C7C698E0B340D4A4B0B5B205E5E65354A348E690B2020204B190B19654B5B191C878E7C195B0B655B344B194B4B4A5E0D4A7C355E4B878E5B19874B5E8734655B8769205B0D1C694A4B1C7C1935205E875E44BD36E5E6E18420F644",
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
    "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
    "referenceNo": "BIL-230501-0024033",
    "result": "",
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
	<td  colspan="4">https://{host}/{version}/bca-flazz-advice</td>
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
	<td>Unique Transaction Number from <b>Service Provider</b></td>
	<td>yes </td>
</tr>
<tr>
	<td>Sample HTTP Raw Request </td>
	<td  colspan="4">


```php
POST https://www.partner-url.com/bca-flazz-advice HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-01-18T13:50:04+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
    "partnerReferenceNo": "DEV-FLAZZ-202305010002",
    "referenceNo": "BIL-230501-0024033",
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
    "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
    "referenceNo": "BIL-230501-0024033",
    "result": {
        "partnerApprovalNo": "DEV-FLAZZ-202305010002",
        "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
        "referenceNo": "BIL-230501-0024033",
        "merchantStoreName": "MERCHANT ABC",
        "merchantOutletID": 896,
        "merchantOutletName": "OUTLET ABC",
        "productReferenceCode": "ETOBC",
        "productTypeID": 1,
        "productCode": "EMOFLZ20",
        "productName": "SALDO ETOLL FLAZZ 20K",
        "productPrice": 20100,
        "productAdminFee": 0,
        "productMerchantFee": 0,
        "transactionDate": "2022-01-18T13:50:04+07:00",
        "customerID": "0145200020896975",
        "additionalInfo": {
            "serialNumber": "479382",
            "billDesc": "{\"responseData\":\"0124014520002089697500020000000000000028043320230501164554D3CD5D34532268A4B0B7345D22A4A47D929222B75D92CD227ACFA4927A5D5DB76DB07DB07D7A6E6DB05D3468B07DCF682268CD6E7ACD68B7D3A4B0CD7A5D536D53B7CF7AD3CF7ACD5D6E68B7D36E7AA4CF53B76E5D6DA4B7D36ED353CFA47A34D3CF7DB0B0A46E686DB77A3453A4226D68CD53B05D68CF7AB76E22226E536DB07A5D5D7DA46D22A453B734686DA422B05277\"}",
        }
    }
}
```


</td>
</tr>
</table>