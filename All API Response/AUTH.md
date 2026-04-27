
## Auth Management

### 1. User Sign Up

**Access:** Public  
**Description:** Register a new user account

#### Endpoint

```
POST /api/v1/auth/signup
```

#### Request Body

```json

{
  "name": "Robiul Hossain",
  "email": "robiulhossain@outlook.com",
  "password": "robiul123456",
  "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA...",
  "contactNumber": "+8801512345679",
  "address": "Chittagong, Bangladesh",
  "role": "USER"
}


