# how to start

1. clone repo
2. buat file .env (PORT=..... ; MONGO_URL=.......; JWT_SECRET= .........)

## Installation


```bash
npm i
```

## Usage

```
npm run dev
```

# Routes

**News Routes:**

| Routes              | Method | Description                          |
| --------------------| ------ | ------------------------------------ |
| /news               | GET    | Find all news                        |
| /news/:id           | GET    | Find one news                        |
| /news/sl/:slug      | GET    | Find one news by slug                |
| /news               | POST   | Add new news                         |
| /news/:id           | DELETE | Delete one news with id(auth)        |
| /news/:id           | PUT    | Update news with id myNews(auth)     |
| /news/myNews        | GET    | Find all user login news             |
| /news/search        | POST   | Find news that matches the text      |

## **Find all News**
- **URL:** `/news`
- **Method:** `GET`
- **URL Params:** `None`
- **URL query:** `page=(current page)` `limit=(limit per page)`
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    {
    result:{
        Total: 2, (total data)
        next:{
            page:1, (next page)
            limit:5 (limit per page)
        },
        results:[
                {
                    "tags":["Transfer","Pemain","Yussa Nugraha","Belanda","Solo","PERSIS"],
                    "_id":"000000000000000",
                    "picture":"https://picture url.........",
                    "pictureName":"lorem-ipsum.jpg",
                    "category":"pemain",
                    "title":"Kembali ke Indonesia, Yussa Pilih Gabung PERSIS",
                    "desc":"Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. ",
                    "idUser":{"tags":[""],"_id":"000000000","username":"Tim Media PERSIS","email":"timmedia@mail.com","password":"$2a$10$R69TqqTqz7nhSZpsdwuFOeBH2p4n8Mbm9YSkheppOo.f34FcQ/tBa","__v":0},
                    "createdAt":"2021-05-24T12:28:42.652Z",
                    "updatedAt":"2021-05-24T12:28:42.652Z",
                    "slug":"kembali-ke-indonesia-yussa-pilih-gabung-persis","__v":0
                },
                {
                    "tags":["Transfer","Pemain","Yussa Nugraha","Belanda","Solo","PERSIS"],
                    "_id":"000000000000000",
                    "picture":"https://picture url.........",
                    "pictureName":"lorem-ipsum.jpg",
                    "category":"pemain",
                    "title":"Kembali ke Indonesia, Yussa Pilih Gabung PERSIS",
                    "desc":"Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. ",
                    "idUser":{"tags":[""],"_id":"000000000","username":"Tim Media PERSIS","email":"timmedia@mail.com","password":"$2a$10$R69TqqTqz7nhSZpsdwuFOeBH2p4n8Mbm9YSkheppOo.f34FcQ/tBa","__v":0},
                    "createdAt":"2021-05-24T12:28:42.652Z",
                    "updatedAt":"2021-05-24T12:28:42.652Z",
                    "slug":"kembali-ke-indonesia-yussa-pilih-gabung-persis","__v":0
                }
        ]
     }  
    }
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```

## **Find One News**
- **URL:** `/news/:id`
- **Method:** `GET`
- **URL Params:** `id`
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    {
        "tags":["Transfer","Pemain","Yussa Nugraha","Belanda","Solo","PERSIS"],
        "_id":"000000000000000",
        "picture":"https://picture url.........",
        "pictureName":"lorem-ipsum.jpg",
        "category":"pemain",
        "title":"Kembali ke Indonesia, Yussa Pilih Gabung PERSIS",
        "desc":"Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. ",
        "idUser":{"tags":[""],"_id":"000000000","username":"Tim Media PERSIS","email":"timmedia@mail.com","password":"$2a$10$R69TqqTqz7nhSZpsdwuFOeBH2p4n8Mbm9YSkheppOo.f34FcQ/tBa","__v":0},
        "createdAt":"2021-05-24T12:28:42.652Z",
        "updatedAt":"2021-05-24T12:28:42.652Z",
        "slug":"kembali-ke-indonesia-yussa-pilih-gabung-persis","__v":0
    }
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```    

## **Find One News By Slug**
- **URL:** `/news/sl/:slug`
- **Method:** `GET`
- **URL Params:** `data.slug`
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    {
        "tags":["Transfer","Pemain","Yussa Nugraha","Belanda","Solo","PERSIS"],
        "_id":"000000000000000",
        "picture":"https://picture url.........",
        "pictureName":"lorem-ipsum.jpg",
        "category":"pemain",
        "title":"Kembali ke Indonesia, Yussa Pilih Gabung PERSIS",
        "desc":"Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. ",
        "idUser":{"tags":[""],"_id":"000000000","username":"Tim Media PERSIS","email":"timmedia@mail.com","password":"$2a$10$R69TqqTqz7nhSZpsdwuFOeBH2p4n8Mbm9YSkheppOo.f34FcQ/tBa","__v":0},
        "createdAt":"2021-05-24T12:28:42.652Z",
        "updatedAt":"2021-05-24T12:28:42.652Z",
        "slug":"kembali-ke-indonesia-yussa-pilih-gabung-persis","__v":0
    }
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```      

    ## **Search News**
- **URL:** `/news/search`
- **Method:** `POST`
- **URL Params:** `none`
- **Body:** `src: 'text'`
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    [
        {
            "tags":["Transfer","Pemain","Yussa Nugraha","Belanda","Solo","PERSIS"],
            "_id":"000000000000000",
            "picture":"https://picture url.........",
            "pictureName":"lorem-ipsum.jpg",
            "category":"pemain",
            "title":"Kembali ke Indonesia, Yussa Pilih Gabung PERSIS",
            "desc":"Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. ",
            "idUser":{"tags":[""],"_id":"000000000","username":"Tim Media PERSIS","email":"timmedia@mail.com","password":"$2a$10$R69TqqTqz7nhSZpsdwuFOeBH2p4n8Mbm9YSkheppOo.f34FcQ/tBa","__v":0},
            "createdAt":"2021-05-24T12:28:42.652Z",
            "updatedAt":"2021-05-24T12:28:42.652Z",
            "slug":"kembali-ke-indonesia-yussa-pilih-gabung-persis","__v":0
        }
    ]
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```    


**Gallery Routes:**

| Routes                | Method | Description                             |
| ----------------------| ------ | --------------------------------------- |
| /gallery              | GET    | Find all photo                          |
| /gallery/kegiatan     | GET    | Find all kegiatan                       |
| /gallery/pertandingan | GET    | Find all pertandingan                   |
| /gallery/wallpaper    | GET    | Find all wallpaper                      |
| /:slug                | GET    | Find One detail kegiatan / pertandingan |

## **Find all photo**
- **URL:** `/gallery`
- **Method:** `GET`
- **URL Params:** `None`
- **URL query:** `none`
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    [ 
        { 
        "tags":["tag","tag"],
        "_id":"000000000000000",
        "name":"loremIpsum.jpg",
        "desc":"Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        "photoUrl":"https://photo url.......",
        "category":"000000000",
        "createdAt":"2021-05-24T12:32:32.659Z",
        "updatedAt":"2021-05-24T12:32:32.659Z","__v":0
        } 
    ]
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```
## **Find all kegiatan**
- **URL:** `/gallery/kegiatan`
- **Method:** `GET`
- **URL Params:** `None`
- **URL query:** `none`
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    [
        {
            "location":"solo",
            "_id":"60ab9c96856da319d5ffae03",
            "title":"Lorem ipsum",
            "date":"2021-05-23",
            "desc":"<p><span style=\"color: rgb(32, 33, 34);\">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</span></p>",
            "category":"Kegiatan",
            "photos":[{ "_id":"000000000000000",
                        "photo_id":{"tags":["tag","tag"],
                                    "_id":"000000000000",
                                    "name":"loremIpsum.jpg",
                                    "desc":" Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
                                    "photoUrl":"https://photoUrl.........",
                                    "category":"60ab9c96856da319d5ffae03",
                                    "createdAt":"2021-05-24T12:32:32.659Z",
                                    "updatedAt":"2021-05-24T12:32:32.659Z","__v":0}   }],
            "videos":[],
            "createdAt":"2021-05-24T12:31:18.316Z",
            "updatedAt":"2021-05-24T12:33:05.631Z",
            "slug":"lorem-ipsum","__v":0
        }
    ]
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```
## **Find all Pertandingan**
- **URL:** `/gallery/pertandingan`
- **Method:** `GET`
- **URL Params:** `None`
- **URL query:** `none`
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    [
        {
            "location":"solo",
            "_id":"60ab9c96856da319d5ffae03",
            "title":"Lorem ipsum",
            "date":"2021-05-23",
            "desc":"<p><span style=\"color: rgb(32, 33, 34);\">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</span></p>",
            "category":"Pertandingan",
            "photos":[{ "_id":"000000000000000",
                        "photo_id":{"tags":["tag","tag"],
                                    "_id":"000000000000",
                                    "name":"loremIpsum.jpg",
                                    "desc":" Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
                                    "photoUrl":"https://photoUrl.........",
                                    "category":"60ab9c96856da319d5ffae03",
                                    "createdAt":"2021-05-24T12:32:32.659Z",
                                    "updatedAt":"2021-05-24T12:32:32.659Z","__v":0}   }],
            "videos":[],
            "createdAt":"2021-05-24T12:31:18.316Z",
            "updatedAt":"2021-05-24T12:33:05.631Z",
            "slug":"lorem-ipsum","__v":0
        }
    ]
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```
## **Find all Wallpaper**
- **URL:** `/gallery/wallpaper`
- **Method:** `GET`
- **URL Params:** `None`
- **URL query:** `none`
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    [
        { 
        "tags":["tag","tag"],
        "_id":"000000000000000",
        "name":"loremIpsum.jpg",
        "desc":"Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        "photoUrl":"https://photo url.......",
        "wallpaper":"true",
        "createdAt":"2021-05-24T12:32:32.659Z",
        "updatedAt":"2021-05-24T12:32:32.659Z","__v":0
        },
        { 
        "tags":["tag","tag"],
        "_id":"000000000000000",
        "name":"loremIpsum.jpg",
        "desc":"Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
        "photoUrl":"https://photo url.......",
        "wallpaper":"true",
        "createdAt":"2021-05-24T12:32:32.659Z",
        "updatedAt":"2021-05-24T12:32:32.659Z","__v":0
        } 
    ]
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```
## **Find one folder detail**
- **URL:** `/gallery/:slug`
- **Method:** `GET`
- **URL Params:** `data.slug`
- **URL query:** `none`
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
        {
            "location":"solo",
            "_id":"60ab9c96856da319d5ffae03",
            "title":"Lorem ipsum",
            "date":"2021-05-23",
            "desc":"<p><span style=\"color: rgb(32, 33, 34);\">Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</span></p>",
            "category":"Pertandingan",
            "photos":[ {"_id":"000000000000000",
                        "photo_id":{"tags":["tag","tag"],
                                    "_id":"000000000000",
                                    "name":"loremIpsum.jpg",
                                    "desc":" Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
                                    "photoUrl":"https://photoUrl.........",
                                    "category":"60ab9c96856da319d5ffae03",
                                    "createdAt":"2021-05-24T12:32:32.659Z",
                                    "updatedAt":"2021-05-24T12:32:32.659Z","__v":0}   
                        },
                        {"_id":"000000000000000",
                        "photo_id":{"tags":["tag","tag"],
                                    "_id":"000000000000",
                                    "name":"loremIpsum.jpg",
                                    "desc":" Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.",
                                    "photoUrl":"https://photoUrl.........",
                                    "category":"60ab9c96856da319d5ffae03",
                                    "createdAt":"2021-05-24T12:32:32.659Z",
                                    "updatedAt":"2021-05-24T12:32:32.659Z","__v":0}   
                        },
                     ],
            "videos":[],
            "createdAt":"2021-05-24T12:31:18.316Z",
            "updatedAt":"2021-05-24T12:33:05.631Z",
            "slug":"lorem-ipsum","__v":0
        }
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```



**User Routes:**

| Routes                      | Method | Description                             |
| ----------------------------| ------ | --------------------------------------- |
| /users/customer/register    | POST   | register user and send token            |
| /users/customer/resend      | POST   | resend token                            |
| /users/customer/verify      | POST   | verify token                            |
| /users/customer/login       | POST   | login user                              |
| /users/loginGoogle          | POST   | login By google oAuth                   |

## **Register User**
- **URL:** `/users/customer/register`
- **Method:** `POST`
- **URL Params:** `None`
- **URL query:** `none`
- **Body:** 
    ```
    {
        username: 'persis solo',
        email: 'persis@mail.com',
        password: 'Password123',
        borndDate: '2-11-1923',
        city: 'city',
        phoneNumber: '123456789'
    }
    ```
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    {
    'A verification email has been sent to `Email.User`. It will be expire after one day. If you not get verification Email click on resend token.'
    }
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'Technical Issue!, Please click on resend for verify your Email.'
        ]
    ```
    - **Status:**`400`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```

## **Verify User**
- **URL:** `/users/customer/verify`
- **Method:** `POST`
- **URL Params:** `None`
- **URL query:** `none`
- **Body:** 
    ```
    {
        token: '1234',
        email: 'persis@mail.com',
    }
    ```
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    {
        "message": "register succsesfully",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjp7ImFsbEl0ZW0iOltdLCJwb2ludCI6MCwiX2lkIjoiNjBiODY1NzI1NzkxMD",
        "user": {
            "email": "persis@mail.com",
            "_id": "60b865725791044da5d",
            "username": "persis solo"
        }
    }
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`400`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```
    - **Status:**`400`**Content:**
    ```
        [
            'message' : 'Your verification link may have expired. Please click on resend for verify your Email.'
        ]
    ```    
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'The email address ' + req.body.email + ' is not associated with any account. please check and try again!'
        ]
    ```    
    - **Status:**`200`**Content:**
    ```
        [
            'message' : 'User has been already verified. Please Login'
        ]
    ``` 

## **Resend User Token**
- **URL:** `/users/customer/resend`
- **Method:** `POST`
- **URL Params:** `None`
- **URL query:** `none`
- **Body:** 
    ```
    {
        email: 'persis@mail.com',
    }
    ```
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    {
    'A verification email has been sent to `Email.User`. It will be expire after one day. If you not get verification Email click on resend token.'
    }
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'Technical Issue!, Please click on resend for verify your Email.'
        ]
    ```
    - **Status:**`400`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'The email address ' + req.body.email + ' is not associated with any account. please check and try again!'
        ]
    ```      
    - **Status:**`200`**Content:**
    ```
        [
            'message' : 'User has been already verified. Please Login'
        ]
    ``` 

## **Login User**
- **URL:** `/users/customer/login`
- **Method:** `POST`
- **URL Params:** `None`
- **URL query:** `none`
- **Body:** 
    ```
    {
        email: 'persis@mail.com',
        password: 'Password123',
    }
    ```
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    {
        "message": "login succsesfully",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjp7ImFsbEl0ZW0iOltdLCJwb2ludCI6MCwiX2lkIjoiNjBiODY1NzI1NzkxMD",
        "user": {
            "email": "persis@mail.com",
            "_id": "60b865725791044da5d",
            "username": "persis solo"
        }
    }
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`400`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'The email address ' + req.body.email + ' is not associated with any account. please check and try again!'
        ]
    ```    
    - **Status:**`401`**Content:**
    ```
        [
            'message' : 'Your Email has not been verified. Please click on resend'
        ]
    ```    
    - **Status:**`403`**Content:**
    ```
        [
            'message' : 'Wrong Password'
        ]
    ```   

    

## **Login By Google**
- **URL:** `/users/loginGoogle`
- **Method:** `POST`
- **URL Params:** `None`
- **URL query:** `none`
- **Body:** 
    ```
    {
        google_token : id_token,
        bornDate: ''
    }
    ```
- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    {
        "message": "register succsesfully",
        "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VyIjp7ImFsbEl0ZW0iOltdLCJwb2ludCI6MCwiX2lkIjoiNjBiODY1NzI1NzkxMD",
        "user": {
            "email": "persis@gmail.com",
            "_id": "60b865725791044da5d",
            "username": "persis solo"
        }
    }
    ```
- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`400`**Content:**
    ```
        [
            'message' : 'Validation Error'
        ]
    ```



**Merchandise Routes:**

| Routes                      | Method | Description                             |
| ----------------------------| ------ | --------------------------------------- |
| /item/:id                   | PUT    | after scan QRcode on item merchandise   |


## **scan QRcode**
- **URL:** `/item/:id`
- **Method:** `POST`
- **URL Params:** `id`
- **Headers:** `token:` `(token id)`
- **Body:** `None`

- **Success Respone:**
    - **Status:**`200`**Content:**
    ```
    { message: 'succsess !'}
    ```

- **Error Respone:**
    - **Status:**`500`**Content:**
    ```
        [
            'message' : 'internal server error'
        ]
    ```
    - **Status:**`404`**Content:**
    ```
        [
            'message' : 'item has updated!'
        ]
    ```
    - **Status:**`404`**Content:**
    ```
        [
            'message' : 'item not found!'
        ]
    ```    