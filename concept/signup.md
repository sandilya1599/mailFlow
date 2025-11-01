# Email System Design

## Signup

### Signup - System Workflow

User
- enters username, email and password
- confirms password (all are validated at client level)
- clicks signup

Backend flow
- Data is sent to login end point upon clicking on Login -> handled by front-end
- Data is cleaned (for protection against injection attacks) -> Data Cleaner (small service?)
- Check if email exists first -> Mail Validator
- If mail exists, say mail exists to user (can be made better in future)
- If not, perform validations on password, account, user name -> Signup validator
- add user to database -> User Storage
- send response

### Services

- Data Cleaner - cleans user's email , password inputs
- Mail Validator - checks if email exists or not
- Signup Validator - validates that password, username and email meets requirements
- User Storage - adds user details to Database

