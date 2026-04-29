
## Wishlist Items Management

### 1. Get Wishlist Items by User Id

**Access:** User 
**Description:** Retrieve all wishlist items for a specific user

#### Endpoint

```
GET /api/v1/wishlist-item/user/:userId
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Wishlist items retrieved successfully",
    "data": [
        {
            "id": "8ea9ed64-79ca-4cba-8e87-fc062dad4ab4",
            "wishlistId": "4c108bca-0eeb-44cd-9ebe-16272adb923d",
            "propertyId": 7,
            "agentId": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
            "addedAt": "2026-04-29T13:36:28.530Z",
            "property": {
                "id": 7,
                "agentId": "7ff640de-a091-41d9-af5e-1a727674e398",
                "title": "Modern Apartment in Banani",
                "description": "Stylish apartment with open floor plan and balcony view.",
                "imageUrl": "https://images.pexels.com/photos/8469931/pexels-photo-8469931.jpeg",
                "location": "Banani, Dhaka",
                "priceRange": "$1800-$2200",
                "propertyType": "APARTMENT",
                "isVerified": true,
                "isAdvertised": false,
                "isBought": false,
                "generatedAt": "2026-03-25T15:32:29.714Z",
                "updatedAt": "2026-04-26T08:26:44.006Z"
            },
            "agent": {
                "id": "913fc870-beba-44de-9a0d-98b3c79ddb2c",
                "userId": "e09213da-bab4-4f99-9c46-324c329db9f0",
                "isVerified": false,
                "isFraud": true
            }
        },
        {
            "id": "2706eb7e-f02b-4deb-9bd9-316414c5a87d",
            "wishlistId": "4c108bca-0eeb-44cd-9ebe-16272adb923d",
            "propertyId": 1,
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "addedAt": "2026-04-29T13:37:34.188Z",
            "property": {
                "id": 1,
                "agentId": "508f7879-e762-4666-869f-539c017df80a",
                "title": "Commercial Shop Space",
                "description": "Street-facing commercial space suitable for retail or small office setup.",
                "imageUrl": "https://images.pexels.com/photos/209292/pexels-photo-209292.jpeg",
                "location": "GEC Circle, Chattogram",
                "priceRange": "$1500-$1900",
                "propertyType": "COMMERCIAL",
                "isVerified": true,
                "isAdvertised": false,
                "isBought": true,
                "generatedAt": "2026-03-25T15:27:11.923Z",
                "updatedAt": "2026-04-26T19:20:52.626Z"
            },
            "agent": {
                "id": "508f7879-e762-4666-869f-539c017df80a",
                "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
                "isVerified": false,
                "isFraud": true
            }
        }
    ]
}
        
```
---

### 2. Get Wishlist Item Details

**Access:** User  
**Description:** Retrieve detailed information about a specific wishlist item

#### Endpoint

```
GET /api/v1/wishlist-item/:id
```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Wishlist item retrieved successfully",
    "data": {
        "id": "680154b8-6ded-4354-986c-bf4aed10bf13",
        "wishlistId": "9171a2cb-b1a2-447d-b4be-8a8b93895d9d",
        "propertyId": 2,
        "agentId": "508f7879-e762-4666-869f-539c017df80a",
        "addedAt": "2026-04-29T14:31:20.378Z",
        "property": {
            "id": 2,
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "title": "Luxury Apartment in Gulshan",
            "description": "Modern fully furnished apartment with rooftop access and 24/7 security in the heart of Gulshan.",
            "imageUrl": "https://images.pexels.com/photos/209218/pexels-photo-209218.jpeg",
            "location": "Gulshan-2, Dhaka",
            "priceRange": "$2000-$2500",
            "propertyType": "COMMERCIAL",
            "isVerified": true,
            "isAdvertised": false,
            "isBought": true,
            "generatedAt": "2026-03-25T15:27:57.790Z",
            "updatedAt": "2026-04-27T19:05:48.900Z"
        },
        "agent": {
            "id": "508f7879-e762-4666-869f-539c017df80a",
            "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
            "isVerified": false,
            "isFraud": true
        }
    }
}
        
```

---

### 3. Add Wishlist Item

**Access:** User  
**Description:** Add a new item to the user's wishlist

#### Endpoint

```
POST /api/v1/wishlist-item/:userId
```

#### Request Body

```json

{
    "propertyId": 3,
    "agentId": "508f7879-e762-4666-869f-539c017df80a"
}

```

#### Success Response (201 Created)

```json

{
    "success": true,
    "message": "Wishlist item added successfully",
    "data": {
        "id": "b5d8eb02-2c5c-4e91-b5f9-04dd0595d930",
        "wishlistId": "9171a2cb-b1a2-447d-b4be-8a8b93895d9d",
        "propertyId": 3,
        "agentId": "508f7879-e762-4666-869f-539c017df80a",
        "addedAt": "2026-04-29T14:31:39.672Z"
    }
}
        
```
#### Note : 

*Here from client side,userId must be send as params*

---

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
        "id": "b036ded4-5ed6-4f65-9821-cd64a233a7dd",
        "wishlistId": "4c108bca-0eeb-44cd-9ebe-16272adb923d",
        "propertyId": 4,
        "agentId": "508f7879-e762-4666-869f-539c017df80a",
        "addedAt": "2026-04-29T13:38:12.307Z"
    }
}
        
```
---

## Updated Note :

* *In user dashboard, in my wishlist section, here all wishlist items must be shown, Here a delete button in each card, when user delete wishlist item , then the wishlist items removed from My wishlist section*

* *When user click the wishlist item card then he will seen about wishlist item details*

* *My wishlist section will be exist only user dashboard*

← [Back to Main Documentation](./../README.md)

