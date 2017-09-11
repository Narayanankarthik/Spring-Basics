Refer the Screen.doc under database folder


Step 1: RUN THE DDL and DML in MYSQL for initial role creation.


Step 2: (Screen 2)

Method: POST

URL : http://localhost:8080/spring-course/empsignup

BODY: <RAW> <JSON(application/json)>

			{

				"firstName": "FirstName Test1",

				"lastName": "LastName Test2",

				"email": "Test1.Test1@gmail.com",

				"dateOfBirth": 979237800000,

				"yearOfExp": 2

			}


User is created in User_MASTER AND EMP_MASTER (User ID : is Email ID (Test1.Test1@gmail.com))

Default Password: password123

Step 3: (Screen 3) Generating OAUTH Token

OAuth2 testing URL

http://localhost:8080/spring-course/oauth/token?grant_type=password&username=Test1.Test1@gmail.com&password=password123


Authorization

User Name: spring-course-client

Password : spring-course

Result you will get the access token as below

{

    "access_token": "c0754368-d475-4301-b2eb-39a195c0f29a",

    "token_type": "bearer",

    "expires_in": 4913,

    "scope": "read write trust"

}

Step 4 : Screen 4( Using OAUTH Token Retriving Employee Details)


Use the same access token and hit the below URL


POST http://localhost:8080/spring-course/employee/?access_token=c0754368-d475-4301-b2eb-39a195c0f29a

  {

        "firstName": "India FirstName1",

        "lastName": "Test LastName",

        "email": "india.b@gmail.com",

        "dateOfBirth": 979237800000,

        "yearOfExp": 2

    }



