# Audit Logs

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

## Stack
  * NodeJS
  * ExpressJS
  * NoSQL (MongoDB)
  * Mongoose
  * Oauth
  * GCP App Engine
  * Mongodb Atlas
  * Robo3T

## Setup MongoDB
  * Install and setup MongoDB: https://zellwk.com/blog/install-mongodb/
  * Create advance-log database
  * Import dump of advance transactional database using mongorestore

## Migration
  * Convert postgresql data to json
  * Import to MongoDB using mongoimport: mongoimport --db advance-log --collection audits --type json --file /temp.json --jsonArray
  
## Tech Consideration
  * ELK stack
  * Server (AWS)
  * GCP Firestore


  
  
