## Endpoint

-   **URL**: `https://domain.com/api/v2/garena_login`
-   **Method**: `POST`
-   **Headers**:
    -   `Content-Type: application/json`
    -   `Authorization: Bearer <Apikey của bạn>`
-   **Body**:
    ```json
    {
        "username": "<Tài khoản>",
        "password": "<Mật khẩu>"
    }
    ```

## Node.js (Use axios)

```javascript
const axios = require('axios');

const API_URL = 'https://domain.com/api/v2/garena_login';
const API_KEY = '<Apikey của bạn>';

const data = {
    username: 'mavietha999',
    password: 'Mavietha9@',
};

axios
    .post(API_URL, data, {
        headers: {
            'Content-Type': 'application/json',
            Authorization: `Bearer ${API_KEY}`,
        },
    })
    .then((response) => {
        console.log('response: ', response.data);
    })
    .catch((error) => {
        console.log('error: ', error);
    });
```

## PHP (Use cURL)

```php
<?php
$api_url = 'https://domain.com/api/v2/garena_login';
$api_key = '<Apikey của bạn>';

$data = [
    'username' => 'mavietha999',
    'password' => 'Mavietha9@',
];

$ch = curl_init($api_url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data));
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'Content-Type: application/json',
    'Authorization: Bearer ' . $api_key
]);

$response = curl_exec($ch);
if (curl_errno($ch)) {
    echo 'error: ' . curl_error($ch);
} else {
    echo 'response: ' . $response;
}
curl_close($ch);
?>
```

## Python (Use requests)

```python
import requests

API_URL = 'https://domain.com/api/v2/garena_login'
API_KEY = '<Apikey của bạn>'

data = {
    'username': 'mavietha999',
    'password': 'Mavietha9@',
}

headers = {
    'Content-Type': 'application/json',
    'Authorization': f'Bearer {API_KEY}'
}

response = requests.post(API_URL, json=data, headers=headers)

if response.status_code == 200:
    print('response: ', response.json())
else:
    print('error: ', response.status_code, response.text)
```

## cURL

```bash
curl -X POST https://domain.com/api/v2/garena_login \
-H "Content-Type: application/json" \
-H "Authorization: Bearer <Apikey của bạn>" \
-d '{"username": "mavietha999", "password": "Mavietha9@"}'
```
