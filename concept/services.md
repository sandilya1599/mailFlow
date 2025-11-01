## Core Services

A consolidated list of services grouped by responsibility.

## Storage
- Mail Storage 
  - Persistent storage for sent and received emails
  - Responsible for saving, retrieving and indexing mail records
  - shared between sending and receiving mails
- User Storage
  - adds user into database 

## Validation & Sanitization
- Data Cleaner
  - Normalizes and sanitizes user inputs (email, password, etc.).
  - used in signup, login.
- Mail Validator
  - Verifies email address format and existence.
  - reused between sending mails, login and signup
- Mail Content Validator (optional)
  - Scans email body and attachments for malicious content or policy violations.
- Login Validator
  - Verifies credentials and validates login attempts (works with Data Cleaner).
- Signup Validator
  - Validates username, password and email matches requirements.

## Sending & Delivery
- Mail Sender
  - Forwards validated outbound emails to the SMTP server or recipient endpoints.
- Mail List Sender
  - Delivers lists/updates of stored messages to clients (e.g., for inbox views).

## Receiving, Filtering & Security
- Spam Checker
  - Detects and flags spam or suspicious messages.
- (Mail Content Validator from Validation & Sanitization is also applied on receive)

## Authentication & Access
- Authentication Service (composed of Data Cleaner + Mail Validator + Login Validator)
  - Handles user sign-in validation and access checks.