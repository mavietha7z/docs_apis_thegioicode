## Endpoint

-   **URL**: `https://thegioicode.com/api/v2/player_id_login`
-   **Method**: `POST`
-   **Headers**:
    -   `Content-Type: application/json`
    -   `Authorization: Bearer <Apikey của bạn>`
-   **Body**:
    ```json
    {
        "account_id": "ID người chơi"
    }
    ```

## Node.js (Use axios)

```javascript
const axios = require('axios');

const API_URL = 'https://thegioicode.com/api/v2/player_id_login';
const API_KEY = '<Apikey của bạn>';

const data = {
    account_id: 'ID người chơi',
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
$api_url = 'https://thegioicode.com/api/v2/player_id_login';
$api_key = '<Apikey của bạn>';

$data = [
    'account_id' => 'ID người chơi'
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

API_URL = 'https://thegioicode.com/api/v2/player_id_login'
API_KEY = '<Apikey của bạn>'

data = {
    'account_id': 'ID người chơi'
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
curl -X POST https://thegioicode.com/api/v2/player_id_login \
-H "Content-Type: application/json" \
-H "Authorization: Bearer <Apikey của bạn>" \
-d '{"account_id": "ID người chơi"}'
```
