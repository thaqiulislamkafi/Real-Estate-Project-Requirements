# RealEstateHub 🏠

**"Discover, Buy & Manage Properties"**

---

## Project Overview

RealEstateHub is a full-stack real estate management platform where users can explore properties, contact agents, and manage listings. Property agents can add and manage properties, while administrators oversee the entire system and manage users and content.

The mobile client will be built using **Kotlin Jetpack (Android)** and the backend will be powered by **TypeScript Express with Prisma ORM**.

---

## Roles & Permissions

| Role             | Description                     | Key Permissions                                                 |
| ---------------- | ------------------------------- | --------------------------------------------------------------- |
| **User (Buyer)** | People searching for properties | Browse properties, view details, save favorites, contact agents |
| **Agent**        | Property sellers or brokers     | Add properties, update listings, manage property status         |
| **Admin**        | Platform manager                | Manage users, properties, reports                               |

> 💡 **Note:** Admin accounts should be seeded in the database.

---

## Tech Stack

### Mobile App

* Kotlin
* Jetpack Compose / Jetpack Components
* Retrofit / Ktor Client
* Coil (Image Loading)

### Backend

* Node.js
* Express.js
* TypeScript
* Prisma ORM
* PostgreSQL (NeonDB)

### Other Tools

* JWT Authentication
* Cloudinary (Image Upload)
* Multer

---

## Features

### Public Features

* Browse all available properties
* Filter properties by location, price, and property type
* View property details
* Search properties

### User (Buyer) Features

* Register and login
* Save properties to wishlist
* Contact with verified agents
* View saved properties
* Manage user profile

### Agent Features

* Register and login as agent
* Add new property listings
* Manage their properties (edit/update)
* Delete properties
* Upload property images
* View their listed properties

### Admin Features

* View all users
* Manage users (activate/suspend)
* Manage all properties
* Delete inappropriate listings
* Manage property categories

---

## Pages & Routes

### Public Routes

| Route             | Page             | Description         |
| ----------------- | ---------------- | ------------------- |
| `/`               | Home             | Featured properties |
| `/properties`     | Properties       | List with filters   |
| `/properties/:id` | Property Details | Full property info  |
| `/agents/:id`     | Agent Profile    | Agent details       |
| `/login`          | Login            | Login form          |
| `/register`       | Register         | Registration form   |

---

### User Routes (Private)

| Route               | Page          | Description      |
| ------------------- | ------------- | ---------------- |
| `/favorites`        | Favorites     | Saved properties |
| `/profile`          | Profile       | User information |
| `/contact/:agentId` | Contact Agent | Send message     |

---

### Agent Routes (Private)

| Route                        | Page          | Description        |
| ---------------------------- | ------------- | ------------------ |
| `/agent/dashboard`           | Dashboard     | Agent stats        |
| `/agent/properties`          | My Properties | Manage listings    |
| `/agent/properties/new`      | Add Property  | Create new listing |
| `/agent/properties/:id/edit` | Edit Property | Update listing     |

---

### Admin Routes (Private)

| Route               | Page       | Description       |
| ------------------- | ---------- | ----------------- |
| `/admin`            | Dashboard  | Platform stats    |
| `/admin/users`      | Users      | Manage users      |
| `/admin/properties` | Properties | Manage properties |
| `/admin/categories` | Categories | Manage categories |

---

## Database Tables

Design your own schema for the following tables:

* **Users** - User authentication and profile data
* **Agents** - Additional information for agents
* **Properties** - Property listings
* **Wishlist** - Saved properties by users
* **WishlistItems** - Individual items in users' wishlists
* **BookedProperty** - Properties booked by users
* **SoldProperty** - Properties sold by users
* **Reviews** - User reviews for properties

> 💡 *Think about relationships between tables when designing your schema.*

---

## API Endpoints

### Authentication

| Method | Endpoint                | Description       |
| ------ | ----------------------- | ----------------- |
| POST   | `/api/v1/auth/register` | Register new user |
| POST   | `/api/v1/auth/login`    | Login user        |
| GET    | `/api/v1/auth/me`       | Get current user  |

---

### Properties (Public)

| Method | Endpoint               | Description          |
| ------ | ---------------------- | -------------------- |
| GET    | `/api/v1/property`     | Get all properties   |
| GET    | `/api/v1/property/:id` | Get property details |


---

### Wishlist (User)

| Method | Endpoint                       | Description               |
| ------ | ------------------------------ | ------------------------- |
| POST   | `/api/v1/wishlist-item`        | Add property to wishlist  |
| GET    | `/api/v1/wishlist/:wishlistId` | Get user wishlist         |
| DELETE | `/api/v1/wishlist/:id`         | Remove item from wishlist |

---

### Agent Management

| Method | Endpoint               | Description         |
| ------ | ---------------------- | ------------------- |
| POST   | `/api/v1/property`     | Create new property |
| PUT    | `/api/v1/property/:id` | Update property     |
| DELETE | `/api/v1/property/:id` | Delete property     |

---

### Admin

| Method | Endpoint                    | Description        |
| ------ | --------------------------- | ------------------ |
| GET    | `/api/admin/users`          | Get all users      |
| PATCH  | `/api/admin/users/:id`      | Update user status |
| DELETE | `/api/admin/properties/:id` | Remove property    |

---

## Future Improvements

* Property booking system
* In-app messaging
* Map integration
* Push notifications
* Payment integration

---

## License

This project is developed for **University Academic Purposes**.
