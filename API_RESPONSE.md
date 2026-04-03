
# 🌐 API Response

← [Back to Main Documentation](README.md)

Complete API response of all entities with request/response specifications.

---

## Property Management

### 1. Get All Properties

**Access:** Public  
**Description:** Retrieve a list of all available properties

#### Endpoint
```
GET /api/v1/property
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Properties retrieved successfully",
    "data": [
        {
            "id": 1,
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "title": "Commercial Shop Space",
            "description": "Street-facing commercial space suitable for retail or small office setup.",
            "imageUrl": "https://example.com/images/commercial-shop.jpg",
            "location": "GEC Circle, Chattogram",
            "priceRange": "$1500-$1900",
            "propertyType": "COMMERCIAL",
            "isVerified": false,
            "isAdvertised": false,
            "isBought": false,
            "generatedAt": "2026-03-25T15:27:11.923Z",
            "updatedAt": "2026-03-25T15:27:11.923Z",
            "agent": {
                "id": "508f7879-e762-4666-869f-539c017df80a",
                "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
                "isVerified": false,
                "isFraud": false
            }
        },
        {
            "id": 2,
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "title": "Luxury Apartment in Gulshan",
            "description": "Modern fully furnished apartment with rooftop access and 24/7 security in the heart of Gulshan.",
            "imageUrl": "https://example.com/images/gulshan-apartment.jpg",
            "location": "Gulshan-2, Dhaka",
            "priceRange": "$2000-$2500",
            "propertyType": "COMMERCIAL",
            "isVerified": false,
            "isAdvertised": false,
            "isBought": false,
            "generatedAt": "2026-03-25T15:27:57.790Z",
            "updatedAt": "2026-03-25T15:27:57.790Z",
            "agent": {
                "id": "508f7879-e762-4666-869f-539c017df80a",
                "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
                "isVerified": false,
                "isFraud": false
            }
        }
    ]
}
        
```

---

### 2. Get Property Details

**Access:** Public  
**Description:** Retrieve detailed information about a specific property

#### Endpoint
```
GET /api/v1/property/:id
```
#### Success Response (201 Created)
```json
{
    "success": true,
    "message": "Property details retrieved successfully",
    "data": {
        "id": 1,
        "agentId": "508f7879-e762-4666-869f-539c017df80a",
        "title": "Commercial Shop Space",
        "description": "Street-facing commercial space suitable for retail or small office setup.",
        "imageUrl": "https://example.com/images/commercial-shop.jpg",
        "location": "GEC Circle, Chattogram",
        "priceRange": "$1500-$1900",
        "propertyType": "COMMERCIAL",
        "isVerified": false,
        "isAdvertised": false,
        "isBought": false,
        "generatedAt": "2026-03-25T15:27:11.923Z",
        "updatedAt": "2026-03-25T15:27:11.923Z",
        "agent": {
            "id": "508f7879-e762-4666-869f-539c017df80a",
            "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
            "isVerified": false,
            "isFraud": false
        }
    }
}
        
```

### 3. Add Property

**Access:** Agent  
**Description:** Add a new property to the system

#### Endpoint
```
POST /api/v1/property
```

#### Request Body

```json
{
    "agentId": "508f7879-e762-4666-869f-539c017df80a",
    "title": "Retail Shop in New Market",
    "description": "Busy retail location with high foot traffic.",
    "imageUrl": "https://example.com/images/newmarket-shop.jpg",
    "location": "New Market, Dhaka",
    "priceRange": "$2500-$3500",
    "propertyType": "COMMERCIAL"
}
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Property added successfully",
    "data": {
    "id": 1,
    "agentId": "508f7879-e762-4666-869f-539c017df80a",
    "title": "Retail Shop in New Market",
    "description": "Busy retail location with high foot traffic.",
    "imageUrl": "https://example.com/images/newmarket-shop.jpg",
    "location": "New Market, Dhaka",
    "priceRange": "$2500-$3500",
    "propertyType": "COMMERCIAL",
    "isVerified": false,
    "isAdvertised": false,
    "isBought": false,
    "generatedAt": "2026-03-25T15:27:11.923Z",
    "updatedAt": "2026-03-25T15:27:11.923Z"
    }
}
        
```

---

### 3. Update Property

**Access:** Agent  
**Description:** Update details of an existing property

#### Endpoint
```
PUT /api/v1/property/:id
```
#### Request Body

```json

{
    "title": "Updated Retail Shop in New Market",
    "description": "Updated description for the retail shop.",
    "imageUrl": "https://example.com/images/newmarket-shop-updated.jpg",
    "location": "New Market, Dhaka",
    "priceRange": "$3000-$4000",
    "propertyType": "COMMERCIAL"
}

```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Property updated successfully",
    "data": {
        "id": 3,
        "agentId": "508f7879-e762-4666-869f-539c017df80a",
        "title": "Family House",
        "description": "Cozy family house with garden, parking, and easy highway access.",
        "imageUrl": "https://example.com/images/family-house.jpg",
        "location": "Purbachal, Dhaka",
        "priceRange": "$2000-$2500",
        "propertyType": "HOUSE",
        "isVerified": false,
        "isAdvertised": false,
        "isBought": false,
        "generatedAt": "2026-03-25T15:29:13.081Z",
        "updatedAt": "2026-04-03T04:22:56.900Z"
    }
}
        
```

---

### 4. Delete Property

**Access:** Agent / Admin  
**Description:** Delete a property from the system

#### Endpoint
```
DELETE /api/v1/property/:id
```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Property deleted successfully",
    "data": {
        "id": 3,
        "agentId": "508f7879-e762-4666-869f-539c017df80a",
        "title": "Family House",
        "description": "Cozy family house with garden, parking, and easy highway access.",
        "imageUrl": "https://example.com/images/family-house.jpg",
        "location": "Purbachal, Dhaka",
        "priceRange": "$2000-$2500",
        "propertyType": "HOUSE",
        "isVerified": false,
        "isAdvertised": false,
        "isBought": false,
        "generatedAt": "2026-03-25T15:29:13.081Z",
        "updatedAt": "2026-04-03T04:22:56.900Z",
    }
}
        
```

---

### 5. Get Properties by Agent

**Access:** Agent  
**Description:** Retrieve all properties listed by a specific agent

#### Endpoint

```
GET /api/v1/property/agent/:id
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Properties retrieved successfully",
    "data": [
        {
            "id": 1,
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "title": "Commercial Shop Space",
            "description": "Street-facing commercial space suitable for retail or small office setup.",
            "imageUrl": "https://example.com/images/commercial-shop.jpg",
            "location": "GEC Circle, Chattogram",
            "priceRange": "$1500-$1900",
            "propertyType": "COMMERCIAL",
            "isVerified": false,
            "isAdvertised": false,
            "isBought": false,
            "generatedAt": "2026-03-25T15:27:11.923Z",
            "updatedAt": "2026-03-25T15:27:11.923Z",
        },
        {
            "id": 2,
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "title": "Luxury Apartment in Gulshan",
            "description": "Modern fully furnished apartment with rooftop access and 24/7 security in the heart of Gulshan.",
            "imageUrl": "https://example.com/images/gulshan-apartment.jpg",
            "location": "Gulshan-2, Dhaka",
            "priceRange": "$2000-$2500",
            "propertyType": "COMMERCIAL",
            "isVerified": false,
            "isAdvertised": false,
            "isBought": false,
            "generatedAt": "2026-03-25T15:27:57.790Z",
            "updatedAt": "2026-03-25T15:27:57.790Z",
        }
    ]
}
        
```

---

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


