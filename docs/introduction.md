<h2></b>Introduction</b></h2>

### General Information
Service User in this context is **Partner**.
<br>
Service Provider in this context is **MKP Mobile**.

### Security
#### Technical and Security Standard
The security standard is part of the Payment Standard which aims to ensure data confidentiality, data integrity, and service availability, regulate standards for authentication, authorization, and encryption to ensure data integrity and confidentiality, has a business continuity plan, as well as the implementation of a fraud detection system to mitigate potential fraud. In addition to referring to these security standards, Service Providers and Service Users must implement comprehensive control and protection of data and information from potential cyber risks to protect the system, user data, and data related to Service Providers and/or Service Users.

#### Components of Technical and Security Standard
The technical and security standards will standardize the following :
1. Architectural Type
2. Data Format
3. Character Encoding
4. Server Authentication Method
5. Encryption Standard
6. URI Path Standardization

#### Architectural API
The architecture used is Representational State Transfer (REST) API.

#### Data Format
The data format used in the request body and response body is JavaScript Object Notation (JSON).

#### Character Encoding
The standard character encoding used is UTF-8.

#### Server Authentication Method
Authorization is a method for Service Providers to grant access to API requests from Service Users. The standards used:
- Bearer token according to RFC 4648

In providing access to Service Users, Service Providers perform authentication to validate Service Users by Service Providers. The facilities used are the credentials that are exchanged during the cooperation formation process, in this context will be the client secret and the public/private key pair, which are used with certain cryptographic algorithms.

#### Encryption Standard
The communication encryption model uses Standard Symmetric Encryption Signature :
1. HMAC_SHA512 (512 bits)
2. AES-256 with client secret as the encryption key.

#### URI Path Standardization
URI resource path standardization with the following format :
```php
[domain-api]/[version]/[product-type]
```

### Credential
| Properties  | Type  | Description  |
|---|---|---|
| Secret Key  | string | *  |
| JWT Secret Key  | string | *  |
| merchantID  | float | *  |
| merchantOutletID  | float | *  |
| merchantOutletUsername  | string | *  |
| merchantOutletDeviceID  | float | ** (optional)  |
| Host  | string | https://apisandboxmkpmobile.mkpmobile.com/api/mybillsv2  |
| CallbackUrl  | string | URL provided by SERVICE USER  |

**Important Note:**
<br>

__* Secret Key will be provided separately from this document, please request by email to Service Provider.__
<br>

__** Difference for every device__

### JWT Signature
To create a JWT Signature, perform the following steps :
1. Construct a JWT header in the following format :
    ```json
    {
       "alg": "HS256",
       "typ": "JWT"
    }
    ```
2. Base64url encode the JWT header.
3. Create a JWT Payload in the following format :
    ```json
        {
           "merchantID": (int)5,
           "merchantOutletID": (int)896,
           "merchantOutletUsername": “689698832ab6462a991a721ef4d387aa”,
           "merchantOutletDeviceID": "SAMPLE DEVICE ID",
        }
    ```
4. Base64url encode the JWT payload.
5. Encode Header to Base64Url String.
6. Encode Payload to Base64Url String.
7. Create Signature Hash.
8. Encode Signature to Base64Url String.
9. Create Final JWT Signature.
10. Add Final JWT Signature result to header field Authorization as Basic Authorization in the request message.

Sample JWT Signature Code Snippet on json :
```php
    {
        # Create token header as a JSON string
        $header = json_encode(['typ' => 'JWT', 'alg' => 'HS256']);

        # Create token payload as a JSON string
        $payload = json_encode([
            'merchantID' => int(5),
            'merchantOutletID' => int(894),
            'merchantOutletUsername' => '689698832ab6462a991a721ef4d387aa',
            'merchantOutletDeviceID' => 'SAMPLE DEVICE ID',
        ]);

        # Encode Header to Base64Url String
        $base64UrlHeader = str_replace(['+', '/', '='], ['-', '_', ''], base64_encode($header));

        # Encode Payload to Base64Url String
        $base64UrlPayload = str_replace(['+', '/', '='], ['-', '_', ''], base64_encode($payload));

        # Create Signature Hash
        $signature = hash_hmac('sha256', $base64UrlHeader . "." . $base64UrlPayload, $jwtSecretKey, true);

        # Encode Signature to Base64Url String
        $base64UrlSignature = str_replace(['+', '/', '='], ['-', '_', ''], base64_encode($signature));

        # Create JWT
        $jwtSignature = $base64UrlHeader . "." . $base64UrlPayload . "." . $base64UrlSignature;

        echo $jwtSignature;
    }
```

### Digital Signature
To create a Digital Signature, perform the following steps :
1. Construct a stringToSign in the following format :
    ```php
    HTTPMethod +”:“+ EndpointUrl +”:”+ JwtSignature +”:“+ Lowercase(HexEncode(SHA256(minify(RequestBody))))+“:“+ TimeStamp
    ```
    **TimeStamp format RFC 3339 (yyyy-MM-ddTHH:mm:ss+07:00)** <br>
    *encrypt checker: https://www.devglan.com/online-tools/hmac-sha256-online
2. Sign with Symmetric Signature with algorithm **HMAC_SHA512 ([API Secret Key],stringToSign)**, which results in the following :
    ```php
    eyJ1dWlkIjoiNDI1MDlFNkQxNEI1NDk4QSIsImNsaWVudElkIjoiVE9QRUQiLCJ1bml2Q29kZSI6IjgwMDEiLCJiaWxsaW5nTnVtYmVyIjoiOTE0MTkwMTkzMTc1In0
    ```
3. Add Symmetric Signature result to header field **X-SIGNATURE** in request message

Sample Digital Signature Code Snippet on json :
```php
# Init value
$timestamp = '2022-07-15T17:11:11+07:00';

# Create body payload as a JSON string
$requestBody = json_encode([
   'key1' => 'value1',
   'key2' => 'value2',
]);

# Sha256 + HexEncode
$sha = hash('sha256', $requestBody);

# Lower
$lower = strtolower($sha);

# Create Signature Hash
$signature  = 'POST'.':'.'/end-point'.':'.$jwt.':'.$lower.':'.$timestamp;

# Create Digital Signature
$digitalSignature = base64_encode(hex2bin(hash_hmac('sha512', $signature, $secretKey)));

echo $digitalSignature;
```
