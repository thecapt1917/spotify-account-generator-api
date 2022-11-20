# SPOTIFY ACCOUNT GENERATOR API (SPOGENTIFY)
Spogentify is an API for create an spotify account

# HTTP API
- Endpoint: https://spogentify.vercel.app/api/v1
- Method: GET
- Parameters:
  - name
  - email
  - password
  - proxy ***(optional)***
  
 ## Example
  - GET https://spogentify.vercel.app/api/v1?name=YOUR_NAME&email=YOUR_VALID_EMAIL&password=YOUR_PASSWORD

 ## Response
  Success ✅
  ```json
  {
    "status": true,
    "message": "Spotify account created successfully",
    "data": {
        "username": "31x7hyduk3gsvvttdhqq4cp36jqi",
        "email": "john.doead9123@gmail.com",
        "password": "johndoe1990"
    }
  }
  ```
  
  Failed ❌
  ```json
  {
    "status": false,
    "message": "Spotify account failed to create",
    "errors": {
        "email": "That email is already registered to an account."
    }
  }
  ```
  
 ## Proxy *(Optional)*
  This API need to use proxy to bypass spotify `'You seem to be using a proxy service. ....'`
  - This is example response if proxy detected by spotify
  ```json
  {
    "status": false,
    "message": "Spotify account failed to create",
    "errors": {
        "generic_error": "You seem to be using a proxy service. Please turn off these services and try again. For more help, please contact customer service."
    }
  }
  ```
  So, you've to fill the `proxy` parameter with your own proxy or you can report to me (create new issues)
  - Example:

  **GET** https://spogentify.vercel.app/api/v1?name=john%20doe&email=john.doe123@gmail.com&password=johndoe1990&proxy=111.68.26.237:8080
