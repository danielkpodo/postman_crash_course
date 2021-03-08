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
