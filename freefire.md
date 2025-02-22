# API Documentation: Player ID Login

## Endpoint

-   **URL:** `https://thegioicode.com/api/v2/player_id_login`
-   **Method:** POST
-   **Header:** `Content-Type: application/json`
-   **Body:**
    ```json
    {
        "account_id": "<your_account_id>"
    }
    ```

---

## Node.js Example

### Using axios

```javascript
const axios = require('axios');

const data = {
    account_id: 'your_account_id',
};

axios
    .post('https://thegioicode.com/api/v2/player_id_login', data, {
        headers: {
            'Content-Type': 'application/json',
        },
    })
    .then((response) => {
        console.log(response.data);
    })
    .catch((error) => {
        console.error(error);
    });
```

---

## PHP Example

### Using cURL

```php
<?php

$url = 'https://thegioicode.com/api/v2/player_id_login';
$data = [
    'account_id' => 'your_account_id'
];

$ch = curl_init($url);
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, json_encode($data));
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'Content-Type: application/json'
]);

$response = curl_exec($ch);
if(curl_errno($ch)){
    echo 'Curl error: ' . curl_error($ch);
} else {
    echo $response;
}
curl_close($ch);
?>
```

---

## Python Example

### Using requests

```python
import requests
import json

url = 'https://thegioicode.com/api/v2/player_id_login'
data = {
    'account_id': 'your_account_id'
}

headers = {
    'Content-Type': 'application/json'
}

response = requests.post(url, data=json.dumps(data), headers=headers)

if response.status_code == 200:
    print(response.json())
else:
    print(f"Error: {response.status_code}", response.text)
```

---

## Notes

-   Replace `your_account_id` with the actual account ID.
-   Ensure the `Content-Type` header is set to `application/json`.
-   Check API response for error handling and validation.
