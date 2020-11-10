# FoodLooks
FoodLooks is an recipe app that can search for items to cook and users will get recipes , pictures  or videos back from search. 
# Group 5 

## Table of Contents
1. [Overview](#Overview)
1. [Product Spec](#Product-Spec)
1. [Wireframes](#Wireframes)
1. [Schema](#Schema)

## Overview
### Description


- **Category:** Social Networking / Food
- **Mobile:** This app would be primarily developed for mobile but would perhaps be just as viable on a computer, such as tinder or other similar apps. Functionality wouldn't be limited to mobile devices, however mobile version could potentially have more features.
- **Story:** Analyzes users food choices, and connects them to other users with similar choices. The user can search for a particular item to eat or creat anf the searches becomes avalibale to them. 

. User Stories (Required and Optional)

















2. Screen Archetypes
Login
Register - User signs up or logs into their account

...
Feed Screen - Allow users to see diffrent recipies 

Profile Screen
Allows user to upload recipies , along with pictures.

Save Screen
Allows User to save and edit recipies 




## Schema 
### Models
#### Post

   | Property      | Type     | Description |
   | ------------- | -------- | ------------|
   | objectId      | String   | unique id for the user post (default field) |
   | author        | Pointer to User| image author |
   | image         | File     | image that user posts |
   | caption       | String   | image caption by author |
   | commentsCount | Number   | number of comments that has been posted to an image |

### Networking
#### List of network requests by screen
      <<<<<<< patch-1
   - Home screen
      - (Read/GET) Query recipes 
    
                =======
   - Home recipe Screen
      - (Read/GET) Query all posts where user is author
                >>>>>>> main
         ```swift
         let query = PFQuery(className:"Post")
         query.whereKey("author", equalTo: currentUser)
         query.order(byDescending: "createdAt")
         query.findObjectsInBackground { (posts: [PFObject]?, error: Error?) in
            if let error = error { 
               print(error.localizedDescription)
    <<<<<<< patch-1
           // TODO: Do something with posts...
            }
         }
         ```
      - (Create/POST) Create a new comment on a post
      - (Delete) Delete existing comment
   - Create Post Screen
      - (Create/POST) Create a new post object
   - Profile Screen
      - (Read/GET) Query logged in user object
      - (Update/PUT) Update user profile image
=======
            } else if let posts = posts {
               print("Successfully retrieved \(posts.count) posts.")
           
            }
         }
         ```
      - (Create/POST) Create a new like on a post
      - (Delete) Delete existing like
      - (Create/POST) Create a new comment on a post
      - (Delete) Delete existing comment
>>>>>>> main
<img src="FoodLooksApp.gif" width=250><br>
