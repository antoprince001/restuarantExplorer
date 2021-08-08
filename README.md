# restuarantExplorer

Restaurant Explorer is a PERN stack application to find nearby restaurants. 

![image](https://user-images.githubusercontent.com/47826916/128601467-0f186e33-1cc9-4a2f-a902-e92c9fb81910.png)

Reviews can be added for a restaurant and the reviews are displayed in the restaurant detail page.

![image](https://user-images.githubusercontent.com/47826916/128601486-c02ee1b0-d60b-4415-bc0f-97ff4feca555.png)

Redis is used as cache store for the restaurant details. 

Postrgres Tables : Restaurants , Reviews

## Restaurant :

    id BIGSERIAL NOT NULL PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    location VARCHAR(50) NOT NULL,
    price_range INT NOT NULL check(price_range>=1 and price_range <=5) 

![image](https://user-images.githubusercontent.com/47826916/128622187-8ebf04e1-5f25-40fa-b71b-ba696520cd07.png)

## Reviews: 

    id BIGSERIAL NOT NULL PRIMARY KEY,
    restaurant_id BIGINT NOT NULL REFERENCES restaurants(id),
    name VARCHAR(50) NOT NULL,
    review TEXT NOT NULL,
    rating INT NOT NULL check(rating>=1 and rating <=5)
    
![image](https://user-images.githubusercontent.com/47826916/128622183-21deba65-3487-4429-abca-6bfbdd55b3ab.png)



## API Endpoints :

  <b>GET /api/v1/restaurants</b> - Returns All Restuarants
  
  <b>GET /api/v1/restaurants/:id</b> - Return Restaurant For ID
  
  <b>POST /api/v1/restaurants</b> - Create Restaurant
  
  <b>PUT /api/v1/restaurants/:id</b> - Update Restaurant
  
  <b>DELETE /api/v1/restaurants/:id</b> - Delete Restaurant 
  
  <b>POST /api/v1/restaurants/:id/addReview</b> - Add Review for a Restaurant
  
  


