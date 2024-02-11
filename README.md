# Film API + Docker Testing
Using 5 basic HTTP requests: GET, POST, PUT, PATCH and DELETE.

# This API allows you to receive data on all films that are available, film genre, order films or books etc.

Creating Film API requests with Film documentation using Postman tool, as part of one of the modules during my time within Software Testing bootcamp
I also decided to extend the project further by using Docker container to automate the testing using Postman and Newman, by using one of my GET collection requests. I wanted to incorporate Postman with Docker together with a previous project to further my skills in Docker, whilst also learning the importance of security and reliability when automating systems such as API calls within businesses.

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


  # Running Postman collection in Docker

  I made sure that Docker desktop was running.
  Next, I ran the CLI in Command, 'docker pull postman/newman' 



![docker newman pull](https://github.com/liaelevn/Film-Rest-API-project/assets/112964705/ec4f3499-f29a-42a2-8fc8-82d5a66cf91a)

By using the Newman command line, it allows me to use all libraries and collections within Postman so that I am able to run tests in Docker.


![docker newman url](https://github.com/liaelevn/Film-Rest-API-project/assets/112964705/b9a7c726-de0e-46d1-85ec-f1ca4a194a97)
 The 'docker run -t postman/newman' after running the CLI, will now give me a prompt to insert an URL from one of my collections within Postman 


 
![postman share](https://github.com/liaelevn/Film-Rest-API-project/assets/112964705/277aed82-c4e4-4cb8-9156-0d2aceacd564)
Within Postman, I chose the GET specific film request and clicked on the 3 dots and selected, 'Share'. This means that I can save the URL within my email to import into the command line in order for the newman cli to run.



![docker running collection](https://github.com/liaelevn/Film-Rest-API-project/assets/112964705/9ca0a0de-0274-4781-a611-a30472b4b9af)
The 'docker run -t postman/newman run "https://films-api.qaalabs.com/films?genre=action" ' command helps to officially automate the API collection. Here I am able to view any test scripts, assertions, requests and iterations. I can also view the duration of how long the the API took to run, which was 8 milliseconds with negative results.

# Summary
By automating the API request using Docker container, it made further my understanding on why this would be key for developers/testers and those working in a devOps team. As the more code there is to test and build and review, the team are able to receive quick feedback regarding the performance of API requests and update code, which is why CI/CD is key to reduce expensive mistakes and bugs before release.
