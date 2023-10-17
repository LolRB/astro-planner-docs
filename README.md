# Astro Planner API Documentation

`const API = "https://astro-planner-server-9832.onrender.com/"`

## GET /

### Request:

```js
fetch(`${API}/`);
```

### Response:

```js
{
  "success": true,
  "message": "Welcome to Astro Planner Server!"
}
```

## GET /trips

### Request:

```js
fetch(`${API}/trips`);
```

### Response:

```js

{
  "data": {
    "success": true,
    "trip": [
      {
        "id": "7ee21c27-cbfa-45f3-b94a-ca032deac45e",
        "location": "NEW_YORK_CITY",
        "checkIn": "1970-01-01T00:00:00.000Z",
        "checkOut": "1970-01-01T00:00:00.000Z",
        "passengers": 1,
        "userId": "518ce637-db9b-45ab-880c-3c1bd8c5bb99"
      },
      {
        "id": "de317d5e-96ac-4b3f-9024-4136dab9eca0",
        "location": "CHICAGO",
        "checkIn": "2022-01-01T00:00:00.000Z",
        "checkOut": "2022-01-01T00:00:00.000Z",
        "passengers": 6,
        "userId": "4c755a15-5960-4953-9c3f-8b105432acc1"
      },
      {
        "id": "3923a1e8-0e46-4398-b67b-c28974b626d9",
        "location": "TORONTO",
        "checkIn": "1970-01-01T00:00:00.000Z",
        "checkOut": "1970-01-01T00:00:00.000Z",
        "passengers": 99,
        "userId": "470e04a7-7e6e-4f99-a272-cc47f08b9119"
      }
    ]
  }
}

```

## POST /trips

### Request:

```js
fetch(`${API}/trips`, {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
      Authorization:
      "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIzYjExZDIzMy1mZTE0LTQ2NzgtYjAwMC03YzJkNTFkYmE3MWEiLCJpYXQiOjE2OTQ1MjE5Nzl9.6qiWcCWgOA3Wvie8pjimOs1j8irhOQy6WfdVUNhUhkU",
  },
  body: JSON.stringify({
    checkIn: “2023-10-11T18:41:07.089Z”
    checkOut: “2023-10-12T18:41:07.089Z”
    location: “TORONTO”
    passengers: 4
  }),
});

```

### Response:

```js
{
  "success": true,
  "trip": {
    "id": "61467fea-8722-409e-bc3e-9e02d57e0d86",
    "location": "TORONTO",
    "checkIn": "2023-10-11T18:41:07.089Z",
    "checkOut": "2023-10-12T18:41:07.089Z",
    "passengers": 4,
    "userId": "2375167f-e85e-4901-8e9a-368e5a5f4dcd"
  }
}

```

## PUT /trips/:tripId

### Request:

```js
fetch(`${API}/trips/61467fea-8722-409e-bc3e-9e02d57e0d86`, {
  method: 'PUT',
  headers: {
    'Content-Type': 'application/json',
    Authorization:
      'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIzYjExZDIzMy1mZTE0LTQ2NzgtYjAwMC03YzJkNTFkYmE3MWEiLCJpYXQiOjE2OTQ1MjE5Nzl9.6qiWcCWgOA3Wvie8pjimOs1j8irhOQy6WfdVUNhUhkU',
  },
  body: JSON.stringify({
    location: 'CHICAGO',
    checkIn: '2023-10-11T18:41:07.089Z',
    checkOut: '2023-10-12T18:41:07.089Z',
    passengers: 6,
  }),
});
```

### Response:

```js
{
  "success": true,
  "trip": {
    "id": "61467fea-8722-409e-bc3e-9e02d57e0d86",
    "location": "CHICAGO",
    "checkIn": "2023-10-11T18:41:07.089Z",
    "checkOut": "2023-10-12T18:41:07.089Z",
    "passengers": 6,
    "userId": "2375167f-e85e-4901-8e9a-368e5a5f4dcd"
  }
}

```

## DELETE /trips/:tripId

### Request:

```js
fetch(`${API}/trips/61467fea-8722-409e-bc3e-9e02d57e0d86`, {
  method: 'DELETE',
  headers: {
    Authorization:
      'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIwM2NhMTI4MS1kZGIzLTQ0MjEtYThmNi0yMmM3NmI2YTk5YjgiLCJpYXQiOjE2OTQ0MzUxNzJ9.AbFuHRnxTB1Ztgcf2S4nwn2NjuvGmV96iUx3TJN5zFk',
  },
});
```

### Response:

```js
{
  "success": true,
  "trip": {
    "id": "61467fea-8722-409e-bc3e-9e02d57e0d86",
    "location": "CHICAGO",
    "checkIn": "2023-10-11T18:41:07.089Z",
    "checkOut": "2023-10-12T18:41:07.089Z",
    "passengers": 6,
    "userId": "2375167f-e85e-4901-8e9a-368e5a5f4dcd"
  }
}

```

## GET /reservations

### Request:

```js
fetch(`${API}//reservations/`);
```

### Response:

```js
{
  "success": true,
  "reservation": [
    {
      "id": "8e274b08-d6dd-48c2-ad2d-803ae7cafc70",
      "bookingConfirmation": null,
      "checkIn": null,
      "checkOut": null,
      "hotelName": null,
      "hotelPhone": null,
      "hotelLocation": null,
      "airlineName": null,
      "flightNumber": null,
      "departureAirport": null,
      "arrivalAirport": null,
      "departureDate": "1970-01-01T00:00:00.000Z",
      "arrivalDate": "1970-01-01T00:00:00.000Z",
      "carRentalAgency": null,
      "carType": null,
      "pickupLocation": null,
      "dropoffLocation": null,
      "tripId": "7ee21c27-cbfa-45f3-b94a-ca032deac45e",
      "userId": "518ce637-db9b-45ab-880c-3c1bd8c5bb99"
    }
  ]
}

```

## POST /reservations

### Request:

```js
fetch(`${API}/reservations`, {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    Authorization:
      'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2vySWQiOiIzYjExZDIzMy1mZTE0LTQ2NzgtYjAwMC03YzJkNTFkYmE3MWEiLCJpYXQiOjE2OTQ1MjE5Nzl9.6qiWcCWgOA3Wvie8pjimOs1j8irhOQy6WfdVUNhUhkU',
  },
  body: JSON.stringify({
    airlineName: 'Delta',
    tripId: '61467fea-8722-409e-bc3e-9e02d57e0d86',
    arrivalDate: '2023-11-10T18:41:07.089Z',
    departureDate: '2023-12-11T18:41:07.089Z',
    arrivalAirport: 'Airport1',
    departureAirport: 'Airport2',
    bookingConfirmation: null, // optional
    checkIn: null, // optional
    checkOut: null, // optional
    hotelName: null, // optional
    hotelPhone: null, // optional
    hotelLocation: null, // optional
    flightNumber: null, // optional
    carRentalAgency: null, // optional
    carType: null, // optional
    pickupLocation: null, // optional
    dropoffLocation: null, // optional
  }),
});
```

### Response:

```js
{
  "success": true,
  "reservation": {
    "id": "af0cf7e1-e33d-4d14-8b75-d48406cb1591",
    "bookingConfirmation": null,
    "checkIn": null,
    "checkOut": null,
    "hotelName": null,
    "hotelPhone": null,
    "hotelLocation": null,
    "airlineName": "Delta",
    "flightNumber": null,
    "departureAirport": "Airport2",
    "arrivalAirport": "Airport1",
    "departureDate": "2023-12-11T18:41:07.089Z",
    "arrivalDate": "2023-11-10T18:41:07.089Z",
    "carRentalAgency": null,
    "carType": null,
    "pickupLocation": null,
    "dropoffLocation": null,
    "tripId": "61467fea-8722-409e-bc3e-9e02d57e0d86",
    "userId": "2375167f-e85e-4901-8e9a-368e5a5f4dcd"
  }
}

```

## PUT /reservations/:reservationId

```js
fetch(`${API}/reservations/af0cf7e1-e33d-4d14-8b75-d48406cb1591`, {
  method: 'PUT',
  headers: {
    'Content-Type': 'application/json',
    Authorization:
      'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2vySWQiOiIzYjExZDIzMy1mZTE0LTQ2NzgtYjAwMC03YzJkNTFkYmE3MWEiLCJpYXQiOjE2OTQ1MjE5Nzl9.6qiWcCWgOA3Wvie8pjimOs1j8irhOQy6WfdVUNhUhkU',
  },
  body: JSON.stringify({
    airlineName: 'Delta',
    tripId: '61467fea-8722-409e-bc3e-9e02d57e0d86',
    arrivalDate: '2023-11-10T18:41:07.089Z',
    departureDate: '2023-12-11T18:41:07.089Z',
    arrivalAirport: 'Airport3',
    departureAirport: 'Airport4',
    bookingConfirmation: null, // optional
    checkIn: '2023-11-10T18:41:07.089Z', // optional
    checkOut: '2023-12-11T18:41:07.089Z', // optional
    hotelName: 'Chicago Hotel', // optional
    hotelPhone: '555-555-5555', // optional (enclose in quotes)
    hotelLocation: null, // optional
    flightNumber: null, // optional
    carRentalAgency: null, // optional
    carType: null, // optional
    pickupLocation: null, // optional
    dropoffLocation: null, // optional
  }),
});
```

### Response:

`````js
{
  "success": true,
  "updatedReservation": {
    "id": "af0cf7e1-e33d-4d14-8b75-d48406cb1591",
    "bookingConfirmation": null,
    "checkIn": "2023-11-10",
    "checkOut": "2023-12-11",
    "hotelName": "Chicago Hotel",
    "hotelPhone": " 555-555-5555",
    "hotelLocation": null,
    "airlineName": "Delta",
    "flightNumber": null,
    "departureAirport": "Airport2",
    "arrivalAirport": "Airport1",
    "departureDate": "2023-12-11T18:41:07.089Z",
    "arrivalDate": "2023-11-10T18:41:07.089Z",
    "carRentalAgency": null,
    "carType": null,
    "pickupLocation": null,
    "dropoffLocation": null
  }
}

`````

## DELETE /reservations/:reservationId

### Request:

````js
fetch(`${API}/reservations/af0cf7e1-e33d-4d14-8b75-d48406cb1591`, {
  method: "DELETE",
  headers: {
    Authorization:
      "Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIwM2NhMTI4MS1kZGIzLTQ0MjEtYThmNi0yMmM3NmI2YTk5YjgiLCJpYXQiOjE2OTQ0MzUxNzJ9.AbFuHRnxTB1Ztgcf2S4nwn2NjuvGmV96iUx3TJN5zFk",
  },
});

`````

### Response:

```js
{
  "success": true,
  "deletedReservation": {
    "id": "af0cf7e1-e33d-4d14-8b75-d48406cb1591",
    "bookingConfirmation": null,
    "checkIn": "2023-11-10",
    "checkOut": "2023-12-11",
    "hotelName": "Chicago Hotel",
    "hotelPhone": " 555-555-5555",
    "hotelLocation": null,
    "airlineName": "Delta",
    "flightNumber": null,
    "departureAirport": "Airport2",
    "arrivalAirport": "Airport1",
    "departureDate": "2023-12-11T18:41:07.089Z",
    "arrivalDate": "2023-11-10T18:41:07.089Z",
    "carRentalAgency": null,
    "carType": null,
    "pickupLocation": null,
    "dropoffLocation": null,
    "tripId": "61467fea-8722-409e-bc3e-9e02d57e0d86",
    "userId": "2375167f-e85e-4901-8e9a-368e5a5f4dcd"
  }
}

```

## POST /users/register

### Request:

```js
fetch(`${API}/users/register`, {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    firstName: 'austin',
    lastName: 'powers',
    email: 'austinp',
    password: '123',
  }),
});
```

### Response:

```js
{
  "success": true,
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2MDY1MjQ3Ny0yZDY1LTQzYzctYTJmMS1mMzU4ZTQyMGQxYWEiLCJpYXQiOjE2OTQ1Mjk3MDh9.a1HjJulV55JAwyKfKt8sTjpq0AKgGcahBNM1efgFE5g"
}
```

## POST /users/login

### Request:

```js
fetch(`${API}/users/login`, {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
  },
  body: JSON.stringify({
    email: 'austinp',
    password: '123',
  }),
});
```

### Response:

```js
{
  "success": true,
  "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI2MDY1MjQ3Ny0yZDY1LTQzYzctYTJmMS1mMzU4ZTQyMGQxYWEiLCJpYXQiOjE2OTQ1Mjk3MDh9.a1HjJulV55JAwyKfKt8sTjpq0AKgGcahBNM1efgFE5g"
}
```

## GET /users/token

### Request:

```js
fetch(`${API}/users/token`, {
  headers: {
    Authorization:
      'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIzYjExZDIzMy1mZTE0LTQ2NzgtYjAwMC03YzJkNTFkYmE3MWEiLCJpYXQiOjE2OTQ1MjE5Nzl9.6qiWcCWgOA3Wvie8pjimOs1j8irhOQy6WfdVUNhUhkU',
  },
});
```

### Response:

```js
{
  "success": true,
  "user": {
    "id": "03ca1281-ddb3-4421-a8f6-22c76b6a99b8",
    "email": "austinp"
  }
}
```
## GET /profile

### Request:

```js
fetch(`${API}/profile)
```

### Response:

```js

   {
    "success": true,
    "profile": [
      {
        "id": "35bf6fe0-56c2-4d33-a254-c6ae6767209b",
        "userId": "b700b2ac-4ff0-4ccd-a7c9-411903282f77",
        "picture": null,
        "firstName": "Ro",
        "lastName": "B",
        "email": "test@test.com",
        "location": null,
        "dob": null,
        "gender": "FLuid"
      }
    ]
  }
}
```

## PUT /profile/:profileId

### Request:

```js
fetch(`${API}/profile/47fd8ab5-87da-4858-bdb0-6b724b49f096`, {
  method: 'PUT',
  headers: {
    'Content-Type': 'application/json',
    Authorization:
      'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiIzYjExZDIzMy1mZTE0LTQ2NzgtYjAwMC03YzJkNTFkYmE3MWEiLCJpYXQiOjE2OTQ1MjE5Nzl9.6qiWcCWgOA3Wvie8pjimOs1j8irhOQy6WfdVUNhUhkU',
  },
  body: JSON.stringify({
  "firstName": "Rodrigo",
  "lastName": "Bueno",
  "email": "test1@test.com",
  "picture": null, //optional
  "location": "Mexico City", //optional
  "dob": null, //optional
  "gender": "Fluid" //optional
  }),
});
```

### Response:

```js
{
  "success": true,
  "profile": {
    "id": "47fd8ab5-87da-4858-bdb0-6b724b49f096",
    "userId": "85d0527e-2373-423d-8ebf-ae853c5f07a6",
    "picture": null,
    "firstName": "Rodrigo",
    "lastName": "Bueno",
    "email": "test1@test.com",
    "location": "Mexico City",
    "dob": null,
    "gender": "Fluid"
  }
}
```
