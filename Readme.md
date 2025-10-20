**Name:** Jephil Honasan
**Course & Block:** BSCS 4-1

# 🏨 Hotel Management API – Postman Documentation

This Postman collection provides example requests and detailed instructions for interacting with the **Hotel Management API**.
The API supports management of **rooms**, **guests**, and **bookings** through standard RESTful methods: **GET**, **POST**, and **DELETE**.

---

## 🚀 Base URL

```
http://localhost:3000/api
```

> Replace `localhost:3000` with your production or deployed server URL if applicable.

---

## 📦 API Endpoint Summary

| Resource | Method | Endpoint        | Description            |
| -------- | ------ | --------------- | ---------------------- |
| Rooms    | GET    | `/rooms`        | Get all rooms          |
| Rooms    | POST   | `/rooms`        | Create a new room      |
| Rooms    | DELETE | `/rooms/:id`    | Delete a specific room |
| Guests   | GET    | `/guests`       | Get all guest records  |
| Guests   | POST   | `/guests`       | Add a new guest        |
| Guests   | DELETE | `/guests/:id`   | Remove a guest         |
| Bookings | GET    | `/bookings`     | View all bookings      |
| Bookings | POST   | `/bookings`     | Make a new booking     |
| Bookings | DELETE | `/bookings/:id` | Cancel a booking       |

---

## 🧩 Sample API Requests

### 1. GET – Fetch All Rooms

**Endpoint:**

```
GET /rooms
```

**Description:**
Retrieves a list of all rooms, including their availability and pricing details.

**Sample Response:**

```json
[
  {
    "_id": "670f12345abc",
    "roomNumber": 101,
    "type": "Deluxe Suite",
    "status": "Available",
    "price": 4500
  },
  {
    "_id": "670f67890def",
    "roomNumber": 102,
    "type": "Standard Room",
    "status": "Occupied",
    "price": 2500
  }
]
```

---

### 2. POST – Add a New Room

**Endpoint:**

```
POST /rooms
```

**Request Body Example:**

```json
{
  "roomNumber": 105,
  "type": "Executive Room",
  "status": "Available",
  "price": 4000
}
```

**Sample Response:**

```json
{
  "message": "Room added successfully",
  "room": {
    "_id": "67100123abc",
    "roomNumber": 105,
    "type": "Executive Room",
    "status": "Available",
    "price": 4000
  }
}
```

---

### 3. DELETE – Remove a Room

**Endpoint:**

```
DELETE /rooms/:id
```

**Example Request:**

```
DELETE /rooms/67100123abc
```

**Sample Response:**

```json
{
  "message": "Room deleted successfully."
}
```

---

## 💡 Postman Testing Tips

1. **Use Environment Variables**

   * Set up a `base_url` variable in Postman (e.g., `http://localhost:5000/api`).
   * Replace hardcoded URLs with `{{base_url}}/rooms`, etc., for flexibility.

2. **Request Headers**

   * For `POST` and `DELETE` requests, include:

     ```
     Content-Type: application/json
     ```

3. **Authentication (If Required)**

   * If your API uses token-based authentication, add:

     ```
     Authorization: Bearer <your_token_here>
     ```

4. **Error Handling**

   * Error responses follow a consistent format. Example:

     ```json
     {
       "error": "Room not found"
     }
     ```

---

## 📘 Suggested Postman Folder Structure

```
Hotel Management API/
├── Rooms/
│   ├── GET All Rooms
│   ├── POST Add Room
│   └── DELETE Room by ID
├── Guests/
│   ├── GET All Guests
│   ├── POST Add Guest
│   └── DELETE Guest by ID
└── Bookings/
    ├── GET All Bookings
    ├── POST Add Booking
    └── DELETE Booking by ID
```

---

## 🧾 Version Information

* **API Version:** 1.0.0
* **Last Updated:** October 17, 2025

---

## 👨‍💻 Developer Information

* **Author:** Jephil Honasan
* **Technology Stack:** Node.js | Express | MongoDB | Postman

---

