# Max retries and jail

```python
from fastapi import FastAPI, Depends, HTTPException, status
from pydantic import BaseModel
from typing import Dict
from time import time

app = FastAPI()

# In-memory retry count and lockout time (for demo purposes, use a real database in production)
login_attempts: Dict[str, int] = {}
lockout_time: Dict[str, float] = {}

class User(BaseModel):
    username: str
    password: str

# Rate limit settings
MAX_ATTEMPTS = 5
LOCKOUT_DURATION = 60  # in seconds

# Dummy user data
users_db = {"user1": {"username": "user1", "password": "password"}} # pragma: allowlist secret

# Rate limit and retry check
def check_retry(user: User):
    now = time()
    if lockout_time.get(user.username, 0) > now:
        raise HTTPException(status_code=status.HTTP_429_TOO_MANY_REQUESTS, detail="Too many failed attempts, try again later")

    if login_attempts.get(user.username, 0) >= MAX_ATTEMPTS:
        lockout_time[user.username] = now + LOCKOUT_DURATION
        login_attempts[user.username] = 0
        raise HTTPException(status_code=status.HTTP_429_TOO_MANY_REQUESTS, detail="Too many failed attempts, try again later")

@app.post("/login")
async def login(user: User, retry_check: None = Depends(check_retry)):
    db_user = users_db.get(user.username)
    if db_user and db_user["password"] == user.password:
        # Successful login, reset login attempts
        login_attempts[user.username] = 0
        return {"message": "Login successful"}

    # Increment login attempts for failed login
    login_attempts[user.username] = login_attempts.get(user.username, 0) + 1
    raise HTTPException(status_code=401, detail="Invalid username or password")
```
