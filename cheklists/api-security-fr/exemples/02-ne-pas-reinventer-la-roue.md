# Do not reinvent the wheel

```python
from fastapi import Depends, FastAPI, HTTPException
from fastapi.security import OAuth2PasswordBearer
from pydantic import BaseModel
from typing import Optional

app = FastAPI()

oauth2_scheme = OAuth2PasswordBearer(tokenUrl="token")

class User(BaseModel):
    username: str
    password: str

class TokenData(BaseModel):
    username: Optional[str] = None

# Example of using OAuth2PasswordBearer
@app.post("/token")
async def login(user: User):
    # Here you'd authenticate with a real system like a database
    if user.username == "user1" and user.password == "password": # pragma: allowlist secret
        return {"access_token": user.username, "token_type": "bearer"}
    raise HTTPException(status_code=401, detail="Invalid credentials")

@app.get("/users/me")
async def read_users_me(token: str = Depends(oauth2_scheme)):
    return {"token": token}
```
