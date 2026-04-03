
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

## Wishlist Items Management

### 1. Get All Wishlist Items

**Access:** Admin  
**Description:** Retrieve a list of all wishlist items in app

#### Endpoint

```
GET /api/v1/wishlist-item
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Wishlist items retrieved successfully",
    "data": [
        {
            "id": "f258d6c3-c9b5-4127-a6f3-0e13d039cce0",
            "wishlistId": "0d1681c0-aba2-4393-969b-293dbb070999",
            "propertyId": 1,
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "addedAt": "2026-03-26T13:49:31.779Z",
            "property": {
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
                "updatedAt": "2026-03-25T15:27:11.923Z"
            },
            "agent": {
                "id": "508f7879-e762-4666-869f-539c017df80a",
                "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
                "isVerified": false,
                "isFraud": false
            }
        },
        {
            "id": "5b96c35a-b614-4937-a443-397ce67c8fa2",
            "wishlistId": "218e5409-0056-4e65-8ba1-18deb77df79e",
            "propertyId": 3,
            "agentId": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
            "addedAt": "2026-03-26T13:50:14.230Z",
            "property": {
                "id": 3,
                "agentId": "508f7879-e762-4666-869f-539c017df80a",
                "title": "Family House",
                "description": "Amazing family house with garden, parking, and easy highway access.",
                "imageUrl": "https://example.com/images/family-house.jpg",
                "location": "Purbachal,Dhaka",
                "priceRange": "$2000-$2500",
                "propertyType": "HOUSE",
                "isVerified": false,
                "isAdvertised": false,
                "isBought": false,
                "generatedAt": "2026-03-25T15:29:13.081Z",
                "updatedAt": "2026-04-03T05:44:52.281Z"
            },
            "agent": {
                "id": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
                "userId": "e09213da-bab4-4f99-9c46-324c329db9f0",
                "isVerified": false,
                "isFraud": false
            }
        }
    ]
}
        
```

### 2. Get Wishlist Item Details

**Access:** User / Admin  
**Description:** Retrieve detailed information about a specific wishlist item

#### Endpoint

```
GET /api/v1/wishlist-item/:id
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Wishlist item details retrieved successfully",
    "data": {
        "id": "f258d6c3-c9b5-4127-a6f3-0e13d039cce0",
        "wishlistId": "0d1681c0-aba2-4393-969b-293dbb070999",
        "propertyId": 1,
        "agentId": "508f7879-e762-4666-869f-539c017df80a",
        "addedAt": "2026-03-26T13:49:31.779Z",
        "property": {
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
            "updatedAt": "2026-03-25T15:27:11.923Z"
        },
        "agent": {
            "id": "508f7879-e762-4666-869f-539c017df80a",
            "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
            "isVerified": false,
            "isFraud": false
        }
    }
}
        
```

### 3. Add Wishlist Item

**Access:** User  
**Description:** Add a new item to the user's wishlist

#### Endpoint

```
POST /api/v1/wishlist-item
```

#### Request Body

```json

{
    "wishlistId": "0fc9344d-9f92-45af-a535-a2a3c7d0a4c2",
    "propertyId": 7,
    "agentId": "913fc870-beba-44de-9a0d-98b3c79ddb2c"
}

```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Wishlist item added successfully",
    "data": {
        "id": "f258d6c3-c9b5-4127-a6f3-0e13d039cce0",
        "wishlistId": "0d1681c0-aba2-4393-969b-293dbb070999",
        "propertyId": 1,
        "agentId": "508f7879-e762-4666-869f-539c017df80a",
        "addedAt": "2026-03-26T13:49:31.779Z"
    }
}
        
```

### 4. Delete Wishlist Item

**Access:** User 
**Description:** Remove an item from the user's wishlist

#### Endpoint

```
DELETE /api/v1/wishlist-item/:id
```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Wishlist item deleted successfully",
    "data": {
        "id": "04a38f80-6ced-4542-8b52-5a9b7083ddd5",
        "wishlistId": "0fc9344d-9f92-45af-a535-a2a3c7d0a4c2",
        "propertyId": 7,
        "agentId": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
        "addedAt": "2026-04-03T18:19:26.892Z"
    }
}
        
```

### 5. Get Wishlist Items by WishlistId

**Access:** User / Admin  
**Description:** Retrieve all wishlist items for a specific wishlist

#### Endpoint

```
GET /api/v1/wishlist-item/wishlist/:wishlistId
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Wishlist items retrieved successfully",
    "data": [
        {
            "id": "8e88515a-b2aa-4040-bcbc-325a8d307fa2",
            "wishlistId": "af52b28d-8fb3-45c9-ba7b-df1880068c55",
            "propertyId": 4,
            "agentId": "bfd8fe55-a821-47b1-b645-424cc7f9889a",
            "addedAt": "2026-03-26T13:50:31.666Z",
            "property": {
                "id": 4,
                "agentId": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
                "title": "Commercial Space in Motijheel",
                "description": "Prime office space suitable for corporate headquarters.",
                "imageUrl": "https://example.com/images/motijheel-commercial.jpg",
                "location": "Motijheel, Dhaka",
                "priceRange": "$5000-$7000",
                "propertyType": "COMMERCIAL",
                "isVerified": false,
                "isAdvertised": false,
                "isBought": false,
                "generatedAt": "2026-03-25T15:31:35.728Z",
                "updatedAt": "2026-03-25T15:31:35.728Z"
            },
            "agent": {
                "id": "bfd8fe55-a821-47b1-b645-424cc7f9889a",
                "userId": "04dc6408-3d3f-48e0-b230-5d249c29811e",
                "isVerified": false,
                "isFraud": false
            }
        }
    ]
}
        
```

