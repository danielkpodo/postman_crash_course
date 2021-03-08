## TESTING API'S WITH POSTMAN

- Postman acts as an interface for interacting with a server that has some data
- Workspaces in postman allows you to organize your work better

### ESSENTIAL PARTS

- Overview of the interface
- Workspaces
- Request Area
- Response Area
- Collections: A list of multiple requests typicallly connected to the same api

### SELF NOTES

- Use variables to extract common parameters. e.g baseUrl
- The initial value is what people will see publicly when you share the api
- For secrets we use them in the current value (In your postman the current value is what you are using)
- Query parameters passed must be validated
- Make a comment to specify optional query parameters
- Note query parameters passed when unchecked leaves them faint, so other users can use it
- Restrict query parameter limit: (A typical error: Invalid value for query parameter 'limit', Cannot be greater than 20). This is for performance reasons
- For Fetching single Books we use what we call, path variable
- For Not Found errors: Say No book with ID -> 10
- Use 201: for post request it means -> the request has been fulfilled and resulted in a resource being created
- Instead of using a generic name token: use accessToken instead
- Note current value in variables is what being used by postman: Paste your accessToken there and put --- in initial value

### TESTING DATA WITH RANDOM DATA

- Postman has a feature where we can send random testdata to our database by just passing a variable "{{$randomFullName}}"
- When sending the request sometimes with random variables, sometimes we might not see what we sending. So we use the postman console to check the data we sending
- Make use of the the postman console
- Anything reponse status code with 200: means that everything is ok

### What not to use Postman for

- User interaction
- Performance Testing
- Security testing

NB:// Postman is good for communicating with API's

### Automation Testing with Postman

#### My First API Test

- Postman has no idea as to whether an API is correct, so to verify and check we test it by checking the response(status code)
- The most simple test that we can write is to test that the status_code is 200

### Postman Variables

- You can set global env. variables to use across board so that we do not repeat ourselves. Do this in the environment sectin

### Extracting data from the response

- You can also check if an object is received from an array

### Collection Runner

- This where the real automation thing happens
- The collection runner allows us to run the entire collection with just one click

### Request execution order

- This allows to set where the next request should go
- we use `JS postman.setNextRequest('requestName, e.g list of books')`

### Postman monitors

- Helps us to avoid manual clicks
- Helps to check if the book api is all the time running even without opening postman and also without starting the postman runner
- Once it is created you do not need to click, when something goes bad you will get a notification
- When we have created this monitor essentially we have shared this collection with postman, so we need to set accessToken in the initial value
- When something fails in the automation runner it is simply regarding something that has not being checked

### NEWMAN

- Newman is a cli tool that can take up all collection, run it and generate a report
- To get access to the collection data, you need to export collection as json or use a public link
- npm i -g newman
- After exporting json file: in terminal, `newman run books.postman_collections.json`

#### HTML REPORTS WITH NEWMAN

- We use npm i -g newman-reporter-htmlextra
- We run `newman run <link to file or public link> --reporter cli,htmlextra`
- `newman run books.postman_collection.json --reporters cli,htmlextra --reporter-htmlextra-title "Simple Books API"`

### CI/CD Overview
