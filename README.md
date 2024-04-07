For this enhancement, I enhanced the database by creating CRUD methods that can be used on the Angular admin SPA to modify the "Rooms" data that appears on the customer facing Express page. Additionally I tested these methods, and added security measures to ensure only authorized users are able to make changes to the database. This enhancement ties together the previous two enhancements and we are finally able to see how everything integrates. 
<br/>
See images below for a brief testing overview of the newly created functionalities: 

**ADD ROOM** 
<br/>
Admins are now able to add rooms to the database as shown in the example below : 
<br/>
<img width="468" alt="Picture1" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/62ec2f4c-2043-453c-873a-fd0da9b2cb04">
<br/> 

After pressing save you can see the new “Test Room” now renders on the admin page and on the customer facing page:
<br/>

**ADMIN SIDE** 
<br/>
<img width="468" alt="Picture2" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/dd958827-696f-4fb4-b0f9-2cf8f4420be3">
<br/> 
<br/> 
<br/>
**CUSTOMER SIDE**
<br/> 

<img width="468" alt="Picture3" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/94b68a95-e583-494f-a823-85eb03ae3cd9">
<br/>
<br/>
As you can see in the images above, the room that was created on the admin page was successfully added to the database. 
<br/> 
<br/> 

**EDIT ROOM** 
<br/>
To test edit room, I changed the image from rooms.png to first-class.jpg as below 
<br/>

<img width="468" alt="Picture4" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/57df09e3-b99a-4eb2-86fb-900603b458c4">
<br/> 
After pressing SAVE , you can see in the images below that the image used for our Test Room was successfully updated on both the admin page and the customer facing page. 
<br/> 

**ADMIN SIDE**
<br/>

<img width="468" alt="Picture5" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/d6663f45-99a2-457c-9e23-279402cc1b94">
<br/>
<br/>

**CUSTOMER SIDE**
<br/>

<img width="468" alt="Picture6" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/90b9f88f-c3cf-4289-90c4-bb02d4b1c515">
<br/>
<br/> 
<br/> 

**DELETE ROOM** 
<br/>
To test delete room, I simply pressed the DELETE button at the bottom of our test trip  on the admin-page 
<br/>

<img width="265" alt="Picture7" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/49bce927-30ee-4e6d-94a0-e8a4e1f807d2">
<br/>
<br/>
After pressing DELETE the following page renders on the admin site : 
<br/> 
<img width="468" alt="Picture8" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/6ac8c14d-5a7e-4685-acd6-63e56487ee97">
<br/> 
To further verify the test room was successfully removed from the database, see images below where TEST ROOM is no longer rendered in our rooms-list. 
<br/> 
<br/> 

**ADMIN SIDE** 
<br/>
<img width="468" alt="Picture9" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/ffc67f34-c3b0-4191-b5ea-080a05becfcd">

<br/> 
<br/> 
<br/> 

**CUSTOMER SIDE**
<br/> 
<img width="468" alt="Picture10" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/0fa83ed9-74eb-4e7b-9cb7-7a41db41e302">
<br/> 
<br/> 



**SECURITY MEASURES** 
<br/> 
Along with implementing and testing the CRUD methods for ROOMS in this enhancement, I also implemented security measures as shown below: 
<br/> 
I previously configured the application to use Express passport for username and password authentication using JSON web tokens (JWT). The **passport.js** file can be seen below: 
<br/> 
<img width="468" alt="Picture11" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/0de18990-b676-4766-9a11-4c9fbf88b51b">
<br/> 
<br/> 
I used the same configuration and applied it to our "ROOMS" functions. An example of this can be seen in the **\travlr\app_api\routes\rooms.js** file shown below. Specifically notice the "AUTH" requirement listed for post, put, and delete functions (Lines 10,11, and 12). 
<br/> 

<img width="468" alt="Picture12" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/efc586b0-6700-4994-a8c2-05d8db2e966b">
<br/> 
<br/> 
Further security measures were placed by coding the ADD ROOM, EDIT ROOM, or DELETE ROOM options to only appear on the admin-page when an authorized user is logged in. See below what happens when a user redners ROOMS on the admin-page without being logged in. Notice that the ADD ROOM, EDIT ROOM, and DELETE ROOM options are no longer there. 
<br/> 

<img width="468" alt="Picture13" src="https://github.com/JessicaDuft/Database_Enhancement/assets/130928718/4b3ee077-3563-414f-986d-78f6c6f9f074">

<br/> 
<br/> 
<br/> 
For this enhancement the following files were added or modified : 
<br/> 

**travlr\app_api\controllers\rooms.js - added roomsAddRoom,roomsUpdateRoom, and roomsDeleteRoom functions**
<br/>

**\travlr\app_api\routes\rooms.js - added lines 10-12 and added auth requirements to each function**
<br/>

**\travlr\travlr-admin\src\app\add-room\add-room.component.ts - completed the add room component on the travlr-admin page**
<br/>

**\travlr\travlr-admin\src\app\edit-room - completed the edit room component on the travlr-admin page**
<br/>

**\travlr\travlr-admin\src\app\delete-room - completed the delete room component on the travlr-admin page**


<br/>
<br/>
<br/>

[**Return to Main Repository**](https://github.com/JessicaDuft/CS499-Capstone)









