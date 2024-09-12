# Use encryption on sensitive data

```python
from passlib.context import CryptContext
from pydantic import BaseModel
from fastapi import FastAPI, HTTPException

app = FastAPI()

# Password hashing setup
pwd_context = CryptContext(schemes=["bcrypt"], deprecated="auto")

class User(BaseModel):
    username: str
    password: str

# In-memory database (hashed passwords for demo purposes)
users_db = {
    "user1": {"username": "user1", "hashed_password": pwd_context.hash("password")},
}

# Helper function to verify password
def verify_password(plain_password: str, hashed_password: str) -> bool:
    return pwd_context.verify(plain_password, hashed_password)

@app.post("/login")
async def login(user: User):
    db_user = users_db.get(user.username)
    if db_user and verify_password(user.password, db_user["hashed_password"]):
        return {"message": "Login successful"}
    raise HTTPException(status_code=400, detail="Invalid credentials")
```
