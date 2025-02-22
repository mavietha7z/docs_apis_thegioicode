# API Documentation: player_id_login

## Endpoint

-   **URL**: `https://thegioicode.com/api/v2/player_id_login`
-   **Method**: `POST`
-   **Headers**:
    -   `Content-Type: application/json`
    -   `Authorization: Bearer <Apikey>`
-   **Body**:
    ```json
    {
        "account_id": "your_account_id"
    }
    ```

## Node.js Example (using axios)

```javascript
const axios = require('axios');

const API_URL = 'https://thegioicode.com/api/v2/player_id_login';
const API_KEY = '<Apikey>'; // Replace with your API key

const data = {
    account_id: 'your_account_id', // Replace with actual account_id
};

axios
    .post(API_URL, data, {
        headers: {
            'Content-Type': 'application/json',
            Authorization: `Bearer ${API_KEY}`,
        },
    })
    .then((response) => {
        console.log('Response:', response.data);
    })
    .catch((error) => {
        console.error('Error:', error.response ? error.response.data : error.message);
    });
```

## PHP Example (using cURL)

```php
<?php
$api_url = 'https://thegioicode.com/api/v2/player_id_login';
$api_key = '<Apikey>'; // Replace with your API key

$data = [
    'account_id' => 'your_account_id' // Replace with actual account_id
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
    echo 'Error: ' . curl_error($ch);
} else {
    echo 'Response: ' . $response;
}
curl_close($ch);
?>
```

## Python Example (using requests)

```python
import requests

API_URL = 'https://thegioicode.com/api/v2/player_id_login'
API_KEY = '<Apikey>'  # Replace with your API key

data = {
    'account_id': 'your_account_id'  # Replace with actual account_id
}

headers = {
    'Content-Type': 'application/json',
    'Authorization': f'Bearer {API_KEY}'
}

response = requests.post(API_URL, json=data, headers=headers)

if response.status_code == 200:
    print('Response:', response.json())
else:
    print('Error:', response.status_code, response.text)
```

## cURL Example

```bash
curl -X POST https://thegioicode.com/api/v2/player_id_login \
-H "Content-Type: application/json" \
-H "Authorization: Bearer <Apikey>" \
-d '{"account_id": "your_account_id"}'
```
