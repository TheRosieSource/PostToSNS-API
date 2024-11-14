### Node.js
```javascript
const axios = require('axios');

const API_KEY = 'your_api_key_here';  // Replace with your actual API key
const apiUrl = 'https://api.rosieapp.com/sns-post';  // Assume this is the endpoint

const postData = {
    message: "Hello, this is a post from my Node.js app!",
    // other parameters like target SNS, etc.
};

axios.post(apiUrl, postData, {
    headers: {
        'Authorization': `Bearer ${API_KEY}`,
        'Content-Type': 'application/json'
    }
})
.then(response => {
    console.log('Post successful:', response.data);
})
.catch(error => {
    console.error('Error posting to SNS:', error.response.data);
});
```
### Python
```python
import requests

API_KEY = 'your_api_key_here'  # Replace with your actual API key
api_url = 'https://api.rosieapp.com/sns-post'  # Assume this is the endpoint

data = {
    "message": "Hello, this is a post from my Python app!",
    # Add other parameters like target SNS, etc.
}

headers = {
    'Authorization': f'Bearer {API_KEY}',
    'Content-Type': 'application/json'
}

response = requests.post(api_url, json=data, headers=headers)

if response.status_code == 200:
    print('Post successful:', response.json())
else:
    print('Failed to post:', response.json())
```
