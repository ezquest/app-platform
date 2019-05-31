# app-platform

#### [Android]
 * source: CouponBook_hw12.zip
 * Config file 수정 필요
 ```
 > SERVER_URL은 본인의 서버주소로 변경
 > API_KEY는 본인의 key로 변경
 ```
 
------------------------------------------------------
#### [Server]
 - source: yonsei.app_1.0.6.zip
 - jar: yonsei.app-1.0.6-fat.jar
 - Config file 수정
 ```
 > REDIS_HOST
 > REDIS_PORT
 > REDIS_PASSWORD
```
#### [Json Commands]
<pre>
  - Auth:SignUp
  [Request]
  {
    "command":"Auth:SignUp",
    "id": "xxxx",
    "password":"yyyy",
    "profile": {
      "name": "zzzz"
    }
  }
  
  - Auth:SignIn
  [Request]
  {
    "command":"Auth:SignUp",
    "id": "xxxx",
    "password":"yyyy"
  }
  [Response]
  {
    ...
    "sessionId": "X-Y-Z"
  }
  
  - Auth:SignOut
  [Request]
  {
    "command":"Auth:SignOut",
    "sessionId": "X-Y-Z"
  }
  
  - Auth:SignDrop
  [Request]
  {
    "command":"Auth:SignDrop",
    "sessionId": "X-Y-Z"
  }
  
  - User:GetUserInfo
  [Request]
  {
    "command":"User:GetUserInfo",
    "sessionId": "X-Y-Z"
  }
  [Response]
  {
    ...
    "profile": {
      "name": "zzz"
    }
  }
  
  - User:UpdateUserInfo
  [Request]
  {
    "command":"User:UpdateUserInfo",
    "sessionId": "X-Y-Z"
    "profile": {
      "name": "ZZZZ"
    }
  }  
</pre>

#### [Response(statusCode, message)]
<pre>
  - SUCCESS(200, "The request is successful")
  - BAD_REQUEST(400, "Bad request")
  - UNAUTHORIZED(403, "Unauthorized")
  - INTERNAL_ERROR(500, "Interval server error")

  - SIGN_UP_SUCCESS(200, "Account successfully created.")
  - SIGN_UP_ERROR(400, "Invalid user ID and Password.")
  - SIGN_UP_EXIST(409, "Account already exists.")

  - SIGN_IN_SUCCESS(200, "You have successfully signed in.")
  - SIGN_IN_FAILED(401, "Incorrect user ID or Password.")
</pre>
