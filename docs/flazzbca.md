<h2><b>Flazz BCA</b></h2>

### API Credential Table
#### URL Path
URL Path : https://{host}/{version}/bca-flazz-get-credential

#### HTTP Method
HTTP Method : POST

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

#### Sample HTTP Raw Request
```json
POST .../v2.0/bca-flazz-get-credential HTTP/1.2
Content-type: application/json
X-TIMESTAMP: 2022-01-18T13:50:04+07:00
X-SIGNATURE: 85be817c55b2c135157c7e89f52499bf0c25ad6eeebe04a986e8c862561b19a5
Authorization: Bearer gp9HjjEj813Y9JGoqwOeOPWbnt4CUpvIJbU1mMU4a11MNDZ7Sg5u9a

{
    "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
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
        <td>&nbsp &nbsp &nbsp &nbsp transactionDate</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp additionalInfo</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp bcaFlazzMID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp bcaFlazzTID</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp bcaFlazzATD</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp bcaFlazzAccessCard</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp bcaFlazzAccessCardCode</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp bcaFlazzSignature</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
</table>

#### Sample HTTP Raw Response (Success)
```json
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

### API Inquiry Table
#### URL Path
URL Path : https://{host}/{version}/bca-flazz-inquiry

#### HTTP Method
HTTP Method : POST

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
|customerID |string(64) |Customer ID of the transaction |yes |
|requestData |string(448) |Card Data |yes |

#### Sample HTTP Raw Request
```json
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
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp serialNumber</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp billDesc</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
</table>

#### Sample HTTP Raw Response (Success)
```json
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

### API Payment Table
#### URL Path
URL Path : https://{host}/{version}/bca-flazz-payment

#### HTTP Method
HTTP Method : POST

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
|requestData |string(448) |Card Data |yes |

#### Sample HTTP Raw Request
```json
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
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp serialNumber</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp billDesc</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
</table>

#### Sample HTTP Raw Response (Success)
```json
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


### API Acknowledge Table
#### URL Path
URL Path: https://{host}/{version}/bca-flazz-ack

#### HTTP Method
HTTP Method: POST

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
|referenceNo | string(64) |Unique Transaction Number from **Service Provider** |yes |
|requestData |string(448) |Card Data |yes |

#### Sample HTTP Raw Request
```json
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
    "responseDatetime": "2022-01-18T13:50:04+07:00",
    "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
    "referenceNo": "BIL-230501-0024033",
    "result": "",
}
```


### API Reversal Table
#### URL Path
URL Path : https://{host}/{version}/bca-flazz-reversal

#### HTTP Method
HTTP Method : POST

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
|requestData |string(448) |Card Data |yes |

#### Sample HTTP Raw Request
```json
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
    "responseDatetime": "2022-01-18T13:50:04+07:00",
    "partnerReferenceNo": "DEV-FLAZZ-A-202305010002",
    "referenceNo": "BIL-230501-0024033",
    "result": "",
}
```


### API Advice Table
#### URL Path
URL Path : https://{host}/{version}/bca-flazz-advice

#### HTTP Method
HTTP Method : POST

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
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp serialNumber</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
    <tr>
        <td>&nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp &nbsp billDesc</td>
        <td>string(64)</td>
        <td>Lorem ipsum</td>
    </tr>
</table>

#### Sample HTTP Raw Response (Success)
```json
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

### Scenario Test
|productCode|Status|
|---|---|
|EMOFLZ20|- inquiry success (00) <br> - payment success (00) <br> - acknowledge success (00)|
|EMOFLZ20|- inquiry success (00) <br> - payment pending (02) <br> - reversal success (00)|
|EMOFLZ20|- inquiry success (00) <br> - payment failed (96 or other)|
|EMOFLZ20|- inquiry failed (96 or other)|