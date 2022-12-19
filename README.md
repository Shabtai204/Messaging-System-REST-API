# Messaging System REST API
## About
The task is to write a simple rest API backend system that is responsible for handling messages between users.
A message contains:
* sender (owner)
* Receiver
* Message
* Subject
* creation date

The rest API should contains:

  ```POST``` **/dj-rest-auth/registration/**

  * **Target**: User registration

  * **Usage**: Requires body request with the following fields: 
    - **username** (String)
    - **password1** (String)
    - **password2** (String)

  * **Example**:
    {
      "username": "Liron",
      "password1": "1q2w3e1q2w3e",
      "password2": "1q2w3e1q2w3e"
    }
    
     -------------------------------------------------------------- 

  ```POST``` **/dj-rest-auth/login/**

  * **Target**: User login

  * **Usage**: Requires body request with the following fields: 
    - **username** (String)
    - **password** (String)

  * **Example**:
    {
      "username": "Liron",
      "password": "1q2w3e1q2w3e"
    }
    
    * **Response**: Getting user token key for authorization e.g: {"key": "caf1d7c5dda16f4214b4875f499f3a05269b6768"}.
    
     -------------------------------------------------------------- 
     
  ```POST``` **/dj-rest-auth/logout/**

  * **Target**: User logout

  * **Usage**: No requires body request.

     -------------------------------------------------------------- 
     
  ```GET``` **/users/**

  * **Target**: Get all users.
 
  * **Usage**: Requires **Key = Authorization** and **value = token {key}**
   
     -------------------------------------------------------------- 
  
  ```GET``` **/users/{user_id}/**

  * **Target**: Get user with the given id.
  
  * **Usage**: Requires **Key = Authorization** and **value = token {key}**

     -------------------------------------------------------------- 

  ```GET``` **/messages/**

  * **Target**: Get all messages

     -------------------------------------------------------------- 

  ```POST``` **/messages/**

  * **Target**: Create a message

  * **Usage**: Requires body request with the following fields: 
    - **sender** (id of existed user)
    - **receiver** (id of existed user)
    - **subject** (String)
    - **message** (String)
          
  * **Example**:
    {
      "sender": 1,
      "receiver": 2,
      "subject": "For Shiran",
      "message": "Hey Shiran, How are you?"
     }
     
       -------------------------------------------------------------- 

  ```GET``` **/specific-message/{message_id}/**

  * **Target**: Get a specific message with the given id (read message). An authenticated user can only see his own messages (as the message receiver).
  
  * **Usage**: Requires **Key = Authorization** and **value = token {key}**

       -------------------------------------------------------------- 

  ```DELETE``` **/specific-message/{message_id}/**

  * **Target**: Delete a message with the given id. An authenticated user can only delete messages as owner or as receive.
  
  * **Usage**: Requires **Key = Authorization** and **value = token {key}**
  
       -------------------------------------------------------------- 
    
  ```GET``` **/all-messages/{user_id}/**

  * **Target**: Get all the messages that were sent for the user with the given id.
  
  * **Usage**: Requires **Key = Authorization** and **value = token {key}**
  
       -------------------------------------------------------------- 

```GET``` **/all-unread-messages/{user_id}/**

  * **Target**: Get all the unread messages that were sent for the user with the given id.
  
  * **Usage**: Requires **Key = Authorization** and **value = token {key}**

