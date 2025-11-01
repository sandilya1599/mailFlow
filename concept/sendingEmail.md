# Email System Design

## Protocol Overview

The email system operates using different protocols for sending and receiving:

### Sending Emails (SMTP Protocol)
- SMTP (Simple Mail Transfer Protocol) handles the sender side
- It's a "push" protocol, meaning it actively sends emails to the recipient's mailbox

### Receiving Emails (POP/IMAP Protocols)
- Two protocols handle email retrieval:
  - POP (Post Office Protocol): Downloads all emails upon server connection
  - IMAP (Internet Message Access Protocol): Downloads emails on-demand only

## System Workflow

### Sender Flow
1. User composes and sends email
   - Email is stored in database (DB Storage)
   - Email address is validated (Mail Validator)
   
2. If email is valid:
   - Content is checked for validity (Mail Content Validator - optional feature)
   - Content is scanned for malicious elements
   
3. Email Processing
   - Valid email is forwarded to SMTP server with sender details (Mail Sender)
   - SMTP server forwards to recipient's server endpoint
   - Currently supports single recipient domain (expandable to multiple)

### Receiver Flow
1. Email Reception
   - Incoming email is received
   - Email undergoes validation (Mail Validator)
   - Spam detection is performed (Spam Checker)
   
2. Storage and Delivery
   - Email is saved to database (DB Writer)
   - Client requests email updates via browser
   - Updated email list is sent to recipient (List Sender)

## Core Services

### Sending Services
- DB Writer
- Mail Validator
- Mail Content Validator
- Mail Sender

### Receiving Services
- Mail Content Validator
- Spam Checker
- DB Writer
- List Sender