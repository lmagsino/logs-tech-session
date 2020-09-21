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
  * Server
  * Implementation on Advance/Andy
  
