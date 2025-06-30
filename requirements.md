# Backend Requirements Specifications for Airbnb Clone

## 1. User Authentication

- **API Endpoint:** POST `/api/register`  
  - Input: `{ "email": "user@example.com", "password": "string" }`  
  - Output: `{ "message": "User registered successfully", "userId": "123" }`  
  - Validation: Email format, password minimum 8 characters.  
  - Performance: Response within 500ms.

- **API Endpoint:** POST `/api/login`  
  - Input: `{ "email": "user@example.com", "password": "string" }`  
  - Output: `{ "token": "jwt_token_here" }`  
  - Validation: Email and password match.  
  - Performance: Response within 500ms.

## 2. Property Management

- **API Endpoint:** POST `/api/properties`  
  - Input: `{ "title": "Cozy Apartment", "location": "City", "price": 100, "description": "Nice place" }`  
  - Output: `{ "propertyId": "456", "message": "Property added" }`  
  - Validation: Required fields must not be empty, price positive number.  
  - Performance: Response within 700ms.

- **API Endpoint:** GET `/api/properties`  
  - Input: Query params (optional): `location`, `priceRange`, `availabilityDates`  
  - Output: List of properties matching criteria.

## 3. Booking System

- **API Endpoint:** POST `/api/bookings`  
  - Input: `{ "propertyId": "456", "userId": "123", "startDate": "YYYY-MM-DD", "endDate": "YYYY-MM-DD" }`  
  - Output: `{ "bookingId": "789", "message": "Booking confirmed" }`  
  - Validation: Dates availability, user and property existence.  
  - Performance: Response within 1 second.

---

# Notes:
- All endpoints require proper authentication via JWT tokens except register and login.
- All inputs should be validated both client-side and server-side.
