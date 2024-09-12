# jwt fastapi

```python
from fastapi import FastAPI, Depends, HTTPException
from fastapi_jwt_auth import AuthJWT
from fastapi_jwt_auth.exceptions import AuthJWTException
from pydantic import BaseModel
from typing import Optional

app = FastAPI()

# Configuration for JWT
class Settings(BaseModel):
    authjwt_secret_key: str = "supersecretkey"

@AuthJWT.load_config
def get_config():
    return Settings()

class User(BaseModel):
    username: str
    password: str

class Token(BaseModel):
    access_token: str
    token_type: str

# User credentials (hardcoded for simplicity, should be stored securely)
users_db = {"user1": {"username": "user1", "password": "password"}} # pragma: allowlist secret

# Login to get JWT
@app.post("/login", response_model=Token)
def login(user: User, Authorize: AuthJWT = Depends()):
    db_user = users_db.get(user.username)
    if db_user and db_user["password"] == user.password:
        # Create JWT token
        access_token = Authorize.create_access_token(subject=user.username)
        return {"access_token": access_token, "token_type": "bearer"}
    raise HTTPException(status_code=400, detail="Invalid username or password")

# Protect endpoints using JWT
@app.get("/protected")
def protected_route(Authorize: AuthJWT = Depends()):
    try:
        Authorize.jwt_required()
    except AuthJWTException as e:
        raise HTTPException(status_code=401, detail="Invalid token")

    current_user = Authorize.get_jwt_subject()
    return {"message": f"Hello {current_user}, you are authorized"}
```
