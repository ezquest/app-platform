# app-platform

#### Config file 수정
<pre>
 - REDIS_HOST
 - REDIS_PORT
 - REDIS_PASSWORD
</pre>

#### Commands
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
    "command":"Auth:SignIn",
    "id": "xxxx",
    "password":"yyyy",
    "sessionId": "10bea0d1-fd4d-47dd-bf83-c557d4db6715",
    "profile": {
      "name": "testtestestst"
    }
  }
  [Response]
  {
    ...
    "sessionId": "10bea0d1-fd4d-47dd-bf83-c557d4db6715"
  }
  
  - Auth:SignOut
  - Auth:SignDrop
  
  - User:GetUserInfo
  - User:UpdateUserInfo
</pre>

#### Response
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
