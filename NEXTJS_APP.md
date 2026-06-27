# 🌐 Next.js Web Application

# RealEstateHub Web Application Documentation

The **RealEstateHub Web Application** is built with **Next.js (App Router)** and **TypeScript**. It provides a modern, responsive, and interactive interface for buyers, property agents, and administrators to manage every aspect of the platform.

The application follows a **role-based architecture**, where each authenticated user only has access to the pages and features permitted for their role.

---

# Tech Stack

| Technology         | Purpose                 |
| ------------------ | ----------------------- |
| Next.js latest     | React Framework         |
| TypeScript         | Type Safety             |
| Tailwind CSS       | UI Styling              |
| TanStack Query     | Server State Management |
| TanStack Table     | Data Tables             |
| TanStack Form      | Form Management         |
| Axios              | API Requests            |
| Zod                | Validation              |
| Framer Motion      | Animations              |
| Imgbb              | Image Upload            |
| JWT Authentication | Authentication          |

---

# Folder Structure

```
src
│
├── app
│   ├── (public)
│   ├── (auth)
│   ├── dashboard
├── components
│
├── features
│
├── hooks
│
├── providers
│
├── lib
│   └── api
├── types
│
├── constants
│
└── utils
```

The project follows a scalable feature-based architecture to keep business logic separated from UI components.

---

# Route Structure

The application consists of four major sections.

- Public Pages
- Authentication Pages
- User Dashboard
- Agent Dashboard
- Admin Dashboard

---

# Public Pages

These pages are accessible without authentication.

---

## Home

Route

```
/
```

### Purpose

The landing page of the application.

### Features

- Hero Section
- Featured Properties
- Property Categories
- Latest Properties
- Why Choose Us
- Customer Reviews
- Statistics
- Call To Action
- Footer

---

## Properties

Route

```
/properties
```

### Purpose

Browse every available property.

### Features

- Grid View
- Pagination
- Property Cards
- Property Search
- Property Type Filter
- Price Filter
- Location Filter
- Bedrooms Filter
- Bathrooms Filter
- Sorting

---

## Property Details

Route

```
/properties/[id]
```

### Purpose

Shows detailed information about a property.

### Features

- Property Images
- Property Information
- Amenities
- Property Description
- Agent Information
- Reviews
- Wishlist Button
- Contact Agent Button

---

## Agents

Route

```
/agents
```

### Features

- Browse Verified Agents
- Search Agents
- View Agent Profile

---

## Agent Details

Route

```
/agents/[id]
```

### Features

- Agent Information
- Listed Properties
- Contact Details
- Reviews

---

## About

Route

```
/about
```

Contains

- Company Information
- Mission
- Vision
- Team
- Statistics

---

## Contact

Route

```
/contact
```

Contains

- Contact Form
- Office Information
- Email
- Phone Number
- Google Map

---

# Authentication Pages

---

## Login

Route

```
/login
```

Features

- Email Login
- Password Login
- Remember Me
- Forgot Password
- Validation

---

## Register

Route

```
/register
```

Features

- Register as Buyer
- Register as Agent
- Email Verification
- Password Validation
- Image Upload

---

## Verify OTP

Route

```
/verify-otp
```

Features

- OTP Verification
- Resend OTP

---

# Protected Routes

Authenticated users can access dashboard pages depending on their role.

---

# Dashboard

Route

```
/dashboard
```

After login, users are redirected to the dashboard according to their role.

---

# Buyer Dashboard(USER)

```
/dashboard/user-dashboard
```

---

## Dashboard Overview

```
/dashboard/user-dashboard
```

Displays

- Total Saved Properties
- Total Booked Properties
- Notifications
- Recent Activity

---

## My Profile

```
/dashboard/user-dashboard/my-profile
```

Features

- Update Personal Information
- Upload Profile Image
- Change Password
- Address Information

---

## Wishlist

```
/dashboard/user-dashboard/wishlist
```

Features

- View Saved Properties
- Remove Property
- View Details

---

## Booked Properties

```
/dashboard/user-dashboard/booked-properties
```

Features

- View Booked Properties
- Booking Status

---

## Notifications

```
/dashboard/user-dashboard/my-notifications
```

Features

- Property Updates
- Booking Updates
- Admin Notifications

---

# Agent Dashboard

---

## Dashboard

```
/dashboard/agent-dashboard
```

Displays

- Total Listings
- Total Sold
- Total Active Listings
- Revenue Overview

---

## Add Property

```
/dashboard/agent-dashboard/add-property
```

Features

- Upload Images
- Property Details
- Amenities
- Pricing
- Address
- Publish Property

---

## My Properties

```
/dashboard/agent-dashboard/my-properties
```

Features

- View Listings
- Edit Property
- Delete Property
- Update Status

---


## My Notifications

```
/dashboard/agent-dashboard/my-notifications
```

Features

- All Notifications

---

# Admin Dashboard

---

## Dashboard(Static)

```
/dashboard/admin-dashboard
```

Displays

- Total Users
- Total Agents
- Total Properties
- Total Reviews

---

## Manage Users

```
/dashboard/admin-dashboard/all-users
```

Features

- View Users
- Update User
- Delete User

---

## Manage Agents

```
/dashboard/admin-dashboard/all-agents
```

Features

- View Agents
- Update Agent
- Delete Agent

---

## Manage Properties

```
/dashboard/admin-dashboard/manage-properties
```

Features

- View All Properties
- Delete Listings
- Update Status
- Moderate Content

---

## Manage Reviews

```
/dashboard/admin-dashboard/all-reviews
```

Features

- View Reviews
- Update Reviews
- Delete Reviews
  

---

# Shared Components

The application uses reusable UI components across multiple pages.

Examples

- Navbar
- Footer
- Sidebar
- Property Card
- Property Grid
- Search Bar
- Filter Sidebar
- Pagination
- Review Card
- Agent Card
- Notification Card
- Empty State
- Loading Skeleton
- Error Boundary
- Confirmation Dialog

---

# Authentication & Authorization

The application uses JWT Authentication.

Supported Roles

- Buyer
- Agent
- Admin

Protected routes are handled using middleware and role-based access control (RBAC).

---

# State Management

The project uses

- TanStack Query
- React Context
- Custom Hooks

TanStack Query is responsible for

- Fetching API data
- Caching
- Pagination
- Infinite Queries
- Mutations
- Optimistic Updates

---

# Form Validation

Forms are validated using

- TanStack Form
- Zod

Validation includes

- Required Fields
- Email Validation
- Password Validation
- File Validation
- Number Validation

---

# Image Upload

Property images and profile pictures are uploaded to Cloudinary.

Supported formats

- JPG
- PNG
- WEBP

---

# Responsive Design

The application is fully responsive.

Supported devices

- Mobile
- Tablet
- Laptop
- Desktop

---

# Performance Optimizations

The application uses various Next.js performance features.

- Server Components
- Client Components where necessary
- Dynamic Imports
- Image Optimization
- Route-based Code Splitting
- Lazy Loading
- Memoization
- Suspense
- API Caching

---

# Error Handling

The application provides user-friendly error handling.

Examples

- 404 Page
- Unauthorized Page
- Forbidden Page
- Network Error
- API Error Messages
- Form Validation Errors

---

# Future Enhancements

- Dark Mode
- Real-time Chat
- Property Comparison
- AI Property Recommendation
- Interactive Maps
- Mortgage Calculator
- Payment Gateway
- Push Notifications
- Multi-language Support
- PWA Support

---

# User Flow

```
Visitor
    │
    ▼
Browse Properties
    │
    ▼
Register / Login
    │
    ▼
Buyer Dashboard
    │
    ├──────────────► Save Wishlist
    │
    ├──────────────► Contact Agent
    │
    └──────────────► Book Property


Agent
    │
    ▼
Login
    │
    ▼
Dashboard
    │
    ├──────────────► Add Property
    │
    ├──────────────► Edit Property
    │
    └──────────────► Manage Listings


Admin
    │
    ▼
Login
    │
    ▼
Dashboard
    │
    ├──────────────► Manage Users
    │
    ├──────────────► Manage Properties
    │
    ├──────────────► Manage Agents
    │
    └──────────────► View Notifications
```

---

# Conclusion

The RealEstateHub Next.js application is designed with scalability, maintainability, and user experience in mind. By following a feature-based architecture, reusable component design, and role-based access control, the project provides a robust foundation for a modern real estate management platform.