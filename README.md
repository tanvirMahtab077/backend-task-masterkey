
# Project Title
Masterkey-BACKEND-TASK
## Getting Started

### Build With

- Nodejs
- Express
- MongoDb

### Dependencies

* Must be Nodejs installed ( Recomanded v20.3.0 ). 
* Must be Docker and Dcoker Compose installded.

### Project setup

* Clone the github ripository [here](https://github.com/tanvirMahtab077/backend-task-masterkey) .
- Open the project from any code editor (vscode) and open your vscode terminal
* Run the comand in the terminal:  
   ```   npm i --save   ```
   
   The node_module file will be created
* The .env file has been given in the github ripository. If you can't find it then create a file name ```.env``` in this project directory and paste the following code.
```
PORT=5000
DB_CONNECT=mongodb://localhost/movie_shows
ACCESS_TOKEN_SECRET=eyJhbGciOiJIUzI1NiJ9.eyJSb2xlIjoiQWRtaW4iLCJJc3N1ZXIiOiJJc3N1ZXIiLCJVc2VybmFtZSI6IkphdmFJblVzZSIsImV4cCI6MTY4NzI4NjQzOSwiaWF0IjoxNjg3Mjg2NDM5fQ.6jYtfvRbaePm_Icu00zVMYIlcX42EUg1L0wz5z4CwrQ
REFRESH_TOKEN_SECRET= 09b22eab53cb2de4e00f5523b3f5588d226e365149b24b026bb94404be2d36a5efc6bc2dd8ccbbdedf22aae361c56ac66d216276243cbac9b664a7a7f8f51fd4

```
- Then run ```npm start```

    The project server will start

- Create a directory name ```Docker``` outside of the projects directory (It can be anywhere of your system). Then create a file name ```docker-compose.yml``` and paste the following code and save.

```
version: "3"
services:
    mongo:
        image: mongo
        volumes:
            - "./mongo:/data/db"
        restart: always
        ports:
            - "27017:27017"
        expose:
            - 27017

```

- Open a terminal from Docker directory and run the following command :
    #### For start the docker server run ``` docker-compose up -d ```

    #### For stop the docker server run ```docker-compose down```   
    #### For checking which container is runing ```docker ps -a```   

### Recomanded Software

- Postman
- MongoDb Compass 
### Postman Documentation Link
``` https://documenter.getpostman.com/view/13231486/2s93zGzJSk ```
### Api
- #### For user Registration -
    
    route: ``` localhost:5000/api/auth/register ```

    http methode: ```POST``` 

- #### For login -  

  route: ``` localhost:5000/api/auth/login ```

    http methode: ```POST``` 

- #### For logout -  

  route: ``` localhost:5000/api/auth/logout ```

    http methode: ```POST``` 

- #### For Refresh the token -  

  route: ``` localhost:5000/api/auth/refreshToken ```

    http methode: ```GET``` 

- #### Add movie or tv Show details. only selected user can add a movie or tv show -  

  route: ``` http://localhost:5000/api/show/add ```

    http methode: ``` POST ``` 

- #### For List of movie or tv show -  

  route: ``` http://localhost:5000/api/show/all ```

    http methode: ``` GET ```


 - #### Details of a movie or tv show-  

 
    route: ``` localhost:5000/api/show/findOne ```

    http methode: ```GET```

    Query Params : ```id``` 

   


- #### For update the user role (admin, creator, basic). only admin can update the role  -  

  route: ``` localhost:5000/api/user/updateRole ```

    http methode: ```PATCH```

    Query Params : ```role``` and ```email``` 

- #### For delete an user. only admin can delete an user  -  

  route: ``` localhost:5000/api/user/delete```

    http methode: ```DELETE```

    Query Params : ```email``` 

- #### To show all user list.  -  

  route: ``` localhost:5000/api/user/list```

    http methode: ```GET```


## Security implementations are done in the project
- #### Password Hashing: 
  When an user get registered, the given password will stored in the database with hashed string form like ```$2a$10$Fn1dC5G16BpquhQRz4GFx./k6gcxkJeZXuKi7CZTuGNUyP7sFBsFS```.

- #### Access Token with jwt: 

  Access tokens are used in token-based authentication to allow an application to access an API.


- #### Refresh Token with jwt: 


  A refresh token is a special token that is used to obtain additional access tokens. This allows you to have short-lived access tokens without having to collect credentials every time one expires

- #### Store Refresh token in the HttpOnly cookie:

  An HttpOnly Cookie is a tag added to a browser cookie that prevents client-side scripts from accessing data. It provides a gate that prevents the specialized cookie from being accessed by anything other than the server.


- #### Protected Route: 


    Protected routes are routes that allow access to authorized users only. This means that users must first meet certain conditions before accessing that specific route. This is essential for securing certain routes or information.
