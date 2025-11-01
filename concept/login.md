# Email System Design

## Login


### Login - System Workflow
User 
- lands on website -> Landing URL (frontend)
- enters email and password -> Client side validation
- clicks login
- if invalid, proper message is shown to user.


Backend flow
- Data is sent to login end point upon clicking on Login -> handled by front-end
- Data is cleaned (for protection against injection attacks) -> Data Cleaner (small service?)
- Check if email exists first -> Mail Validator (see sendingEmail.md)
- if mail exists, check if password matches -> Validator
- send response


### Services

- Data Cleaner - cleans user's email , password inputs
- Mail Validator - checks if email exists or not
- Login Validator - checks if email and password match / validates login