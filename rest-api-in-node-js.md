The fastest way to create a Rest API in Node.js
Thurs 03:50 PM
Shikhir Singh

Lookup:
#BloomEx
#Swagger

#LoopBack
  *Opensource Node.js framework
  *Built on top of Express
  *Can do everything you have learned in Express
  *Highest rest API in Node on Github
  *Fastest way to write a backend code
  *Model-based approach - Structure of an api and it will:
   - create documentation
   - write the code to write things to the database
   - get you up and running immediately
  *Sits in the middle of the API Endpoint and the Backend Resource
  ##To Use
    * Go to project: in cmd line type lb
      * Choose which model
    * in cmd line type lb model
      * Choose Persisted Model
      * Expose? yes
      * Common Server (both front and backend)
  ##Datbase
    * in cmd line type lb database
    * Can be hooked up to MySQL
    * in cmd line type lb model
  ##Relate different models (Map contacts)
    * in cmd line type lb relation
    * require through model: allows you to access through contacts
  ##ACL: Access Control List
    * User Management
    * in cmd line type lb acl
    * Deny to all, then allow access to authenticated users
      * Requires user to login to see the DB 
  ##Generate Swagger Docs in json
   * in cmd line type lb export-api-db

  ##Express Gateway (opensource)
    * Built on Express
    * Define security keys 
    * probably not the best solution for bigger apps

  ##Flaws
    * Sometimes does not give error messaging
      * Does have good Stack Overflow 
      * Potentially still worth using IBM because of better support
      
    



    

    
  