
This application is built as a server side part of a Web Of Things project.
## Usage

mongod --auth --bind_ip 127.0.0.1 

Make sure you have mongodb installed into your own machine and running;
Get the project and run: `npm install`

Run `npm start`. It will initialize the server at port 8443.

## Test

POST https://localhost:8443/users

{"firstName":"Hamadi-Rabie","lastName":"Alum","email":"hamadi.rabie@xyz.com","password":"Min$09ou2!","permissionLevel":2049}

201 Created

{
    "id": "5bcc712b50ace7ebfaaf82ac"
}


GET https://localhost:8443/users/5bcc712b50ace7ebfaaf82ac

401 Unauthorized

POST https://localhost:8443/auth

201 Created

{"email":"hamadi.rabie@xyz.com","password":"Min$09ou2!"}

{
    "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI1YmNjNzEyYjUwYWNlN2ViZmFhZjgyYWMiLCJlbWFpbCI6Imd0X2FtaW5lQHlhaG9vLmZyIiwicGVybWlzc2lvbkxldmVsIjoxLCJwcm92aWRlciI6ImVtYWlsIiwibmFtZSI6Ik1vaGFtZWQtQW1pbmUgR3VldGFyaSIsInJlZnJlc2hLZXkiOiI2L1gyendwckRJMWF2VTNYSVMwcWVBPT0iLCJpYXQiOjE1NDAxMjU1NDJ9.oHf4kSVmziEy6pbpmpgYzmUc_WpZa0kuyWbXfTH6b1o",
    "refreshToken": "QkM2MlNTSHRaM3NlMzhRNWViOFpMelEvUXd1Y00xV0dZSlNBSHpkeGF6TVBOK1c1cERFb3lQeWppaVJvTGVmOEpnNDlvSElrZGM4K0xGenpLTVNySGc9PQ=="
}

GET https://localhost:8443/users/5bcc712b50ace7ebfaaf82ac

authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJ1c2VySWQiOiI1YmNjNzEyYjUwYWNlN2ViZmFhZjgyYWMiLCJlbWFpbCI6Imd0X2FtaW5lQHlhaG9vLmZyIiwicGVybWlzc2lvbkxldmVsIjoxLCJwcm92aWRlciI6ImVtYWlsIiwibmFtZSI6Ik1vaGFtZWQtQW1pbmUgR3VldGFyaSIsInJlZnJlc2hLZXkiOiI2L1gyendwckRJMWF2VTNYSVMwcWVBPT0iLCJpYXQiOjE1NDAxMjU1NDJ9.oHf4kSVmziEy6pbpmpgYzmUc_WpZa0kuyWbXfTH6b1o

200 OK

{
    "firstName": "Hamadi-Rabie",
    "lastName": "Alum",
    "email": "hamadi.rabie@xyz.com",
    "password": "aSptMBJUtcjA81T8gsn8Lg==$klzw7dDgRkSp9xlPEGe1RpVZCrdCFjDikAQqWTMvcYPXVywR9HdBzXmsRA8pFQnEatokusQ8pA5/QbCaT3mdrw==",
    "permissionLevel": 1,
    "id": "5bcc712b50ace7ebfaaf82ac"
}
