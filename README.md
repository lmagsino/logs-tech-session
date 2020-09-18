# logs-tech-session

## Requirements
  * Audit logs
  * Separated from transactional database
  * Dynamic column

## Existing Implementation
  * Audited gem
  * Used transactional database
  * Changes are being saved to a single (text) column
  
  ```
  ---
  state:
  - pending
  - deducted
  ```

## Proposed tech stack
  * NodeJS
  * ExpressJS
  * NoSQL (MongoDB)
  
## Implemented
  * MongoDB Connection
  * Initial Project Structure (Router, Service, Model)
  * Mongoose implementation
  * Event model
  
## Pending R&D
  * Server
  * Implementation on Advance/Andy
  
