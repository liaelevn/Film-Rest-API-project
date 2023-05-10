# Film API
Using 5 basic HTTP requests: GET, POST, PUT, PATCH and DELETE.

# This API allows you to receive data on all films that are available, film genre, order films or books etc.

# Creating Film API requests with Film documentation using Postman tool, as part of one of the modules during my time within Software Testing bootcamp

Writing simple tests/scripts using variables and JSON.

# ENDPOINTS

# Status

GET /films
Returns list of films.

# Genre of films
GET /genre of film

Optional query parameters:

-type: action/thriller/horror

# Get specific film

GET /films/200

Retrieve detailed information about film

# Register new customer

POST /registrations
Allows you to register your details and requires authentication.
The request body has to be in JSON/raw format and type below:

Example

POST /registrations/
Authorization: Bearer <YOUR TOKEN>

{
   "name": "Jane",
   "creditCardNumber":"5555333311112222"
}

The response body will contain the Order Id.
  
# Order a film
 
  POST /orders
  
  Allows you to order a film and requires Bearer token number in 'Auth'

 {
  "filmId":200,
  "format":"SD"
}

 
 # Get my orders
  
  POST /orders
Requires same Bearer Token with 'Auth', allowing you to view an existing order

{
  "filmId": 700,
  "format": "SD"
}
  
# Get specific order
  
  POST /orders/orderID
  
# Update an order
  
  Allows you to update your film order, using same Bearer Token in 'Auth' and JSON format
  
  PATCH /orders/orderID
  
  {
 "format": "SD"
  }
  
  # Delete an order
  
  Delete your order, including the same Bearer Token and ID number within url.
  
  DEL /orders/orderID
  
  
  


