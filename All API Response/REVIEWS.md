
## Reviews Management

### 1. Get All Reviews

**Access:** Admin  
**Description:** Retrieve a list of all reviews

#### Endpoint

```
GET /api/v1/review
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Reviews retrieved successfully",
    "data": [
        {
            "id": "9592bcc4-2ce9-42ef-9a69-5048cbf85eac",
            "propertyId": 1,
            "userId": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
            "rating": 5,
            "description": "Excellent apartment, very clean and well maintained.",
            "generatedAt": "2026-04-02T18:50:31.028Z",
            "updatedAt": "2026-04-02T18:50:31.028Z",
            "property": {
                "title": "Commercial Shop Space"
            },
            "user": {
                "name": "Nusrat Jahan"
            }
        },
        {
            "id": "e2c3c469-2e04-4514-b49a-f9dd619dd5d8",
            "propertyId": 2,
            "userId": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
            "rating": 4,
            "description": "Spacious rooms but parking was limited.",
            "generatedAt": "2026-04-02T18:50:54.367Z",
            "updatedAt": "2026-04-02T18:50:54.367Z",
            "property": {
                "title": "Luxury Apartment in Gulshan"
            },
            "user": {
                "name": "Mehedi Hasan"
            }
        } 
    ]
}
        
```

---

### Get Review Details

**Access:** User / Admin  
**Description:** Retrieve detailed information about a specific review

#### Endpoint

```
GET /api/v1/review/:id
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Review details retrieved successfully",
    "data": {
        "id": "9592bcc4-2ce9-42ef-9a69-5048cbf85eac",
        "propertyId": 1,
        "userId": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
        "rating": 5,
        "description": "Excellent apartment, very clean and well maintained.",
        "generatedAt": "2026-04-02T18:50:31.028Z",
        "updatedAt": "2026-04-02T18:50:31.028Z",
        "property": {
            "title": "Commercial Shop Space"
        },
        "user": {
            "name": "Nusrat Jahan"
        }
    }
}
        
```

---

### 3. Add Review

**Access:** User  
**Description:** Add a new review for a property

#### Endpoint

```
POST /api/v1/review
```

#### Request Body

```json

{
    "rating": 3,
    "description": "Good commercial space but limited facilities.",
    "propertyId": 8,
    "userId": "950c7e11-4af8-44b3-bd90-38ddfbefb836"
}

```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Review added successfully",
    "data": {
        "id": "e2c3c469-2e04-4514-b49a-f9dd619dd5d8",
        "propertyId": 2,
        "userId": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
        "rating": 4,
        "description": "Spacious rooms but parking was limited.",
        "generatedAt": "2026-04-02T18:50:54.367Z",
        "updatedAt": "2026-04-02T18:50:54.367Z"
    }
}
        
```

---

### 4. Update Review

**Access:** User  
**Description:** Update an existing review

#### Endpoint

```
PUT /api/v1/review/:id
```
#### Request Body

```json

{
    "rating": 4,
    "description": "Updated review: Spacious rooms and good location, but parking is still an issue."
}

```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Review updated successfully",
    "data": {
        "id": "e2c3c469-2e04-4514-b49a-f9dd619dd5d8",
        "propertyId": 2,
        "userId": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
        "rating": 4,
        "description": "Updated review: Spacious rooms and good location, but parking is still an issue.",
        "generatedAt": "2026-04-02T18:50:54.367Z",
        "updatedAt": "2026-04-03T05:00:00.000Z",
    }
}

```

---

### 5. Delete Review

**Access:** User / Admin  
**Description:** Delete a review from the system

#### Endpoint

```
DELETE /api/v1/review/:id
```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Review deleted successfully",
    "data": {
        "id": "e2c3c469-2e04-4514-b49a-f9dd619dd5d8",
        "propertyId": 2,
        "userId": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
        "rating": 4,
        "description": "Spacious rooms but parking was limited.",
        "generatedAt": "2026-04-02T18:50:54.367Z",
        "updatedAt": "2026-04-02T18:50:54.367Z",
    }
}
        
```

### 6. Get Reviews by PropertyId

**Access:** User / Admin  
**Description:** Retrieve all reviews for a specific property

#### Endpoint

```
GET /api/v1/review/property/:id
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Reviews retrieved successfully",
    "data": [
        {
            "id": "9592bcc4-2ce9-42ef-9a69-5048cbf85eac",
            "propertyId": 1,
            "userId": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
            "rating": 5,
            "description": "Excellent apartment, very clean and well maintained.",
            "generatedAt": "2026-04-02T18:50:31.028Z",
            "updatedAt": "2026-04-02T18:50:31.028Z",
            "property": {
                "title": "Commercial Shop Space"
            },
            "user": {
                "name": "Nusrat Jahan"
            }
        },
        {
            "id": "e2c3c469-2e04-4514-b49a-f9dd619dd5d8",
            "propertyId": 2,
            "userId": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
            "rating": 4,
            "description": "Spacious rooms but parking was limited.",
            "generatedAt": "2026-04-02T18:50:54.367Z",
            "updatedAt": "2026-04-02T18:50:54.367Z",
            "property": {
                "title": "Luxury Apartment in Gulshan"
            },
            "user": {
                "name": "Mehedi Hasan"
            }
        } 
    ]
}

```

---

### 7. Get Reviews by UserId

**Access:** User
**Description:** Retrieve all reviews written by a specific user

#### Endpoint

```
GET /api/v1/review/user/:id
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Reviews retrieved successfully",
    "data": [
        {
            "id": "e2c3c469-2e04-4514-b49a-f9dd619dd5d8",
            "propertyId": 2,
            "userId": "950c7e11-4af8-44b3-bd90-38ddfbefb836",
            "rating": 4,
            "description": "Spacious rooms but parking was limited.",
            "generatedAt": "2026-04-02T18:50:54.367Z",
            "updatedAt": "2026-04-02T18:50:54.367Z",
            "property": {
                "title": "Luxury Apartment in Gulshan"
            },
            "user": {
                "name": "Mehedi Hasan"
            }
        } 
    ]
}
        
```

---

← [Back to Main Documentation](README.md)
