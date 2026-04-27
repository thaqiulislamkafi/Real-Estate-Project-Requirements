
## Sold Property Management

### 1. Get All Sold Properties
**Access:** Admin  
**Description:** Retrieve a list of all sold properties in the app

#### Endpoint

```
GET /api/v1/sold-property
```
#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Sold properties retrieved successfully",
    "data": [
        {
            "id": 2,
            "bookedPropertyId": 1,
            "propertyId": 1,
            "userId": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "amount": "$950",
            "soldAt": "2026-03-28T16:58:57.961Z",
            "updatedAt": "2026-03-28T16:58:57.961Z",
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
            },
            "user": {
                "id": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
                "name": "Nusrat Jahan",
                "email": "nusrat.jahan@example.com",
                "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA..."
            }
        },
        {
            "id": 4,
            "bookedPropertyId": 2,
            "propertyId": 2,
            "userId": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "amount": "$1200",
            "soldAt": "2026-04-09T15:45:11.407Z",
            "updatedAt": "2026-04-09T15:45:11.407Z",
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
                "updatedAt": "2026-04-26T19:20:59.580Z"
            },
            "agent": {
                "id": "508f7879-e762-4666-869f-539c017df80a",
                "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
                "isVerified": false,
                "isFraud": true
            },
            "user": {
                "id": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
                "name": "Nusrat Jahan",
                "email": "nusrat.jahan@example.com",
                "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA..."
            }
        },
        {
            "id": 5,
            "bookedPropertyId": 2,
            "propertyId": 2,
            "userId": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "amount": "$1200",
            "soldAt": "2026-04-26T16:53:20.203Z",
            "updatedAt": "2026-04-26T16:53:20.203Z",
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
                "updatedAt": "2026-04-26T19:20:59.580Z"
            },
            "agent": {
                "id": "508f7879-e762-4666-869f-539c017df80a",
                "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
                "isVerified": false,
                "isFraud": true
            },
            "user": {
                "id": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
                "name": "Nusrat Jahan",
                "email": "nusrat.jahan@example.com",
                "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA..."
            }
        }
    ]
}
        
```

### 2. Get Sold Property Details

**Access:** Admin / User / Agent  
**Description:** Retrieve detailed information about a specific sold property

#### Endpoint

```
GET /api/v1/sold-property/:id
```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Sold property details retrieved successfully",
    "data": {
            "id": 2,
            "bookedPropertyId": 1,
            "propertyId": 1,
            "userId": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "amount": "$950",
            "soldAt": "2026-03-28T16:58:57.961Z",
            "updatedAt": "2026-03-28T16:58:57.961Z",
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
            },
            "user": {
                "id": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
                "name": "Nusrat Jahan",
                "email": "nusrat.jahan@example.com",
                "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA..."
            }
        }
}
        
```

### 3. Get Buy Properties by User

**Access:** User  
**Description:** Retrieve a list of all properties bought by a specific user

#### Endpoint

```
GET /api/v1/sold-property/user/:userId
```

#### Success Response (200 OK)

```json

{
    "success": true,
    "message": "Sold properties retrieved successfully",
    "data": [
        {
            "id": 4,
            "bookedPropertyId": 2,
            "propertyId": 2,
            "userId": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "amount": "$1200",
            "soldAt": "2026-04-09T15:45:11.407Z",
            "updatedAt": "2026-04-09T15:45:11.407Z",
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
                "updatedAt": "2026-04-26T19:20:59.580Z"
            },
            "agent": {
                "id": "508f7879-e762-4666-869f-539c017df80a",
                "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
                "isVerified": false,
                "isFraud": true
            },
            "user": {
                "id": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
                "name": "Nusrat Jahan",
                "email": "nusrat.jahan@example.com",
                "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA..."
            }
        },
        {
            "id": 5,
            "bookedPropertyId": 2,
            "propertyId": 2,
            "userId": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
            "agentId": "508f7879-e762-4666-869f-539c017df80a",
            "amount": "$1200",
            "soldAt": "2026-04-26T16:53:20.203Z",
            "updatedAt": "2026-04-26T16:53:20.203Z",
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
                "updatedAt": "2026-04-26T19:20:59.580Z"
            },
            "agent": {
                "id": "508f7879-e762-4666-869f-539c017df80a",
                "userId": "b6747d21-d5b8-48c9-babd-8487f58eb92f",
                "isVerified": false,
                "isFraud": true
            },
            "user": {
                "id": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
                "name": "Nusrat Jahan",
                "email": "nusrat.jahan@example.com",
                "image": "data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAUA..."
            }
        }
    ]
}

```

### 4. Add Sold Property

**Access:** User
**Description:** Mark a booked property as sold by accepting the proposed amount from the agent

#### Endpoint

```
POST /api/v1/sold-property
```

#### Request Body

```json
{
    "bookedPropertyId": 2,
    "propertyId": 2,
    "userId": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
    "agentId": "508f7879-e762-4666-869f-539c017df80a",
    "amount": "$1200"
}

```

#### Success Response (201 Created)

```json
{
    "success": true,
    "message": "Sold property added successfully",
    "data": {
        "id": 5,
        "bookedPropertyId": 2,
        "propertyId": 2,
        "userId": "3c1d61d6-25e7-4e03-83dc-a61d90e4e38e",
        "agentId": "508f7879-e762-4666-869f-539c017df80a",
        "amount": "$1200",
        "soldAt": "2026-04-26T16:53:20.203Z",
        "updatedAt": "2026-04-26T16:53:20.203Z"
    }
}

```

### Note :

*In Admin Dashboard, in All Sold Properties Section,here admin see all Sold properties and see specific sold property details*
*In User Dashboard, in My Buy Properties Section, here user see all his/her Buy properties*