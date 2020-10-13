# logs-tech-session

## Requirements
  * Audit trail
  * Separated from transactional database
  * Dynamic schema

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
  
## Diagram
![existing_logging](https://user-images.githubusercontent.com/10264177/95716752-7f988480-0c9e-11eb-9a88-4cc256d86fd3.png)

![1st_level](https://user-images.githubusercontent.com/10264177/95716818-9e971680-0c9e-11eb-8626-3d10261c9284.png)

## Proposed tech stack
  * NodeJS
  * ExpressJS
  * NoSQL (MongoDB)
  
## Implemented
  * MongoDB Connection
  * Initial Project Structure (Router, Service, Model)
  * Mongoose implementation
  * Event model
  
  ```
  const Event = mongoose.model('Event', {
    type: {type: String, required: true},
    auditable_type: {type: String, required: true},
    auditable_id: {type: String, required: true},
    user_id: {type: String, required: true},
    user_type: {type: String},
    version: {type: Number, required: true},
    changes: {type: {}},
    created_at: {type: Date, required: true}
  })
  ```
  
  ```
  type : create, update, delete <system-generated>
  auditable_type : Company
  auditable_id : 1
  user_id : 1
  user_type : AdminUser
  version : 2 <system-generated>
  changes: {"city": {"old": "test", "new": "test 1"}} <system-generated>
  created_at : <current date>
  ```
  
## Endpoint
  * Save event
  * Retrieve events (by user, by type, with pagination)
  
## Pending R&D
  * Server (AWS, Google Cloud)
  * Implementation on Advance/Andy
  * Utilities
  * ELK stack
  
  
