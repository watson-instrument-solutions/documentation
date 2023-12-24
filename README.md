# Watson Instrument Solutions - Documentation

### Trello board : https://trello.com/b/HYZPSzNc/wissite

---


## Purpose

The aim of this project is to create a site that delivers a professional web portal for the current customer base of WIS.

Currently, they take hire bookings via email and phone call only so having an online booking system will save their customers time, and enable them more efficient project planning by being able to see equipment availability immediately without having to wait for a returned email or phone call.

Additionally, the site will enable them to grow their customer base by having another avenue for promotion and have potential new customers find them via web searches. 



## Functionality & Features

### Customer Users

#### Customer Account Creation

Customers can create a user account by providing an email and password.

#### Customer Log in

Customers can then log in using their email and password for verification and provide further details and start making hire bookings.

#### Account / Profile page

Once logged in customers will be able to see and edit their current user information such as email, password, contact phone number, address as well as view any current bookings.

#### Log out

Customers will be able to logout of their account so their data is secure.

### Admin Users

#### Admin Creation

Admin accounts will be able to create other admin, and non admin accounts, the business owners frequently hire their own equipment to themselves for another side of their business, so being able to create their own bookings is a requirement. 

#### CRUD all bookings / users

Admin accounts will be able to view and edit / delete all current bookings from all users. They will also be able to view, create, and delete all users if necessary.

#### CRUD all equipment

Admin accounts will have full control over all the equipment and its pricing listed on the site. They will be able to add new items or remove them if they are out for service.

### Browsing

Anyone will be able to browse equipment, each item will have an image and description as well as a dynamic calendar to show its availability. This way any potential new customers will be able to quickly see if the equipment they need is available without going through a sign up process.

### Booking System

Customer users will be able to create a booking, then be prompted to give the required dates, and then the equipment they need (multiple items). They will be shown an alert if one of the pieces is unavailable. Then they will navigate to a confirmation page with all details of items that were successfully added to their cart. If they confirm they will have an invoice auto generated and sent to their user email address.

If once a booking is created, it needs to be updated or deleted they will need to contact one of the business owners directly via details provided on the contact page. This is subject to change depending on the business cancellation policy.

## Target Audience

The target audience for WIS are professional acoustician businesses only. It is very unlikely for anyone outside of the industry to need to hire this kind of equipment without at least using a subcontractor who has the expertise to use it. Therefore it is assumed that most users will be technical and already have a strong grasp of the products they need to hire, so the focus will be be on providing efficient presentation of data and clear ease of navigation to save time and provide an easy transactional experience. 

## Tech Stack

### Front-end:

- REACT
- Bootstrap

### Back-end:

- Express
- Node.js
- MongoDB
- Email.js
- easyinvoice (npm package)

### Design:

- Figma
- draw.io

### Deployment:

- Netlify
- Mongo Could Atlas
- Heroku

## Data Flow Diagram

![Image](./docs/WIS_dataflow.drawio_V2.png)

### Models Draft

```js 
User {
    "id": Number, unique, required = true,
    "first name": String, required = true,
    "last name": String, required = true,
    "business name": String, required = true,
    "telephone": Number, required = true,
    "email": String, required = true,
    "password": hash, required = true,
    "address line": String, required = true,
    "city/town": String, required = true
    "postcode": Number, required = true
}

Booking {
    "id": Number, unique, required = true,
    "equipment id": Number, unique, required = true,
    "user id": Number, unique, required = true,
    "start date": Date, required = true,
    "end date": Date, required = true
}

Equipment {
    "id": Number, unique, required = true,
    "item name": String, unique, required = true,
    "description": String,
    "price per day": Number, required = true,
    "price per week": Number, required = true,
    "price per month": Number, required = true,
    "supply cost": Number,
    "stock": Number
}
```

## Application Architecture Diagram

![Image](./docs/WIS%20App%20architecture%20diagram.drawio.png)

## User Stories

### 1 - Richard Whitely (Customer User)

Richard (39) is a certified acoustician operating as a sole trader in Brisbane. He works via contract drafting acoustic reports for new or upgrading buildings. To gather data for his reports he needs to use specialised acoustic monitoring equipment and chooses to hire it on a per contract basis as its more cost effective. 

Richard has a strong technical knowledge base and frequently used WIS for hiring as he is familiar with their catalog and they are local to him. He has developed a good working and personal relationship with the owners, however he occasionally hires from other companies when the specific tools he requires are not available for the dates he needs them.

#### Revised user requirements for Richard

Richard is known to have slightly chaotic organisation skills and often forgets his passwords. An option would be to grant JWT tokens a long validation period of 30days or more, however, there is no guarantee he will use the service that frequently. It would be best I think to implement a 'forgot password?' feature to the site that can send the user a secure link to their registered email address that enables them to change their password. I have marked this as a nice to have for the project assessment deadline, but will endeavor to implement it before the site goes live. 

### 2 - Annika Rice (Customer User)

Annika (42) works for a larger Acoustics company with offices in Melbourne, Adelaide, and Sydney. Her company commonly takes large contracts to provide acoustic reports to government buildings, airports, and new large buildings of many types. Often her companies own resources are stretched beyond their capacity so they will use WIS to supplement them so they can fulfill more concurrent projects across different states. 

Annika does not have first hand experience of using the equipment that she books but is familiar enough to be able to identify them by model names/numbers. Annika has a good professional relationship with the owners but expects a fast turnaround on her queries and requests.

### - Carol Vordemon (Customer User)

Carol (59) runs a mid size acoustics company in Perth. Her business generally operates on the west coast getting contract work from local government and mining corporations. Carols usual go to hire company in Perth has fallen through at the last minute with an equipment failure and she is in desperate need of a replacement, having no other local hire companies to go to she looks on the web and comes across WIS.

Carol has a strong technical knowledge but is distrustful of giving her personal details over to a random website and prefers to speak to someone directly on the phone. She navigates to the contact page and calls Kate, one of the business owners.

### - Kate O'Sullivan (Admin User)

Kate (35) is the principal owner / operator of WIS. She handles all the booking, shipping, servicing, admin, and the majority of the client contact. She prefers bookings to come in via the website as its less admin work for her but she still takes some bookings over the phone from customers who don't like to use the web service. Her admin account is able to create new customer users and make bookings for them (as in Carols case).

Her partner, Craig, is an acoustician and often hires their equipment for his own contracts. Kate is able to make bookings under her own admin account, or create a user account for that purpose.

#### Revised user requirements for Kate

After further discussions with Kate, it became apparent that she would like to have a notification system implemented such that when a new booking is created she is alerted automatically. The easiest way to do this should be to use a package like email.js. I will mark it as a nice to have for the deadline of assessment but will implement it before the site goes live.

## Wireframes 

### Desktop Frames / Pageflow

![Image](./docs/WIS_Pageflow_3crop.png)

## Consultation Notes & Further Amendments

During the design process I have been in ongoing consultation with the business owner (Kate) about various aspects of the business requirements. I've decided to scrap the auto invoice generation and email feature as shes advised me that she generally invoices after the return of the gear as often hire periods are extended on the job. To cover that on the booking side, Kate will use her admin portal to amend the booking period to ensure theres no danger of double ups.

We have also decided to leave the 'About Us' page out, Kate thinks it is unnecessary so we have agreed to park it for now and perhaps revisit when the final site is completed.

She and Craig have both signed off on the initial design as of 21/11, their one note was to make sure there are some images and explanation of the equipment. I was planning including this on the 'hire equipment' page which they happy with. They will provide some images to use. 

### Mobile frames

![Image](./docs/WIS_ALL_mobile.png)

### Design Notes

In implementing the design I took a look at the current competitors websites or inspiration and make sure my design would be appropriate. Most of the designs are very functional and leave very little room for any creative visual components. I feel like this makes sense for the clientele of the business, its a very technical field and there is no need for salesmanship of any sort. Businesses come to hire equipment they need for a contract and generally want to be efficient and perfunctory about it. Therefore, Ive kept the design as minimal and as clear as I can. WIS already have some logo material so I have used those in the header component and built up from there. I based my colour and font choices on fitting with their logo design.


## Trello

here: https://trello.com/b/HYZPSzNc/wissite


I've opted for a simple 4 column approach of Brainstorm, ToDo, Doing, and Done. This helps me easily keep track of where I am, see how much has to be done, and not feel too overwhelmed. Putting things in the done column also helps motivation levels by giving me a sense of progression. 


Below are some screenshots of my trello board as I moved through the project up until now. 

![Image](./docs/Screenshot%202023-11-21%20133105.png)
![Image](./docs/Screenshot%202023-11-21%20162018.png)
![Image](./docs/Screenshot%202023-11-22%20214223.png)
![Image](./docs/Screenshot%202023-11-23%20213442.png)
![Image](./docs/Screenshot%202023-11-27%20221307.png)
![Image](./docs/Screenshot%202023-11-29%20210441.png)
![Image](./docs/Screenshot%202023-11-30%20204747.png)

I will continue to take daily screenshots to document the project progress as it moves forward.

# PART B

Deployed site: https://subtle-rolypoly-42ba7c.netlify.app/

Deployed server: https://wis-api-2q17.onrender.com/

## General development notes

The app is largely complete as serves the purpose as described in the part A documentation. Working as a solo dev, time constraints have impeded where I'd like the deployed app to be at this stage.

Having a little more time I would have liked to make the design and UX better, the site feels a little clunky to use and could be improved on with a better design of the homepage, the use of professional images for the equipment, more loading animations and custom alert messages etc. The mobile view of some pages is also not resolved correctly.

I'd also have implemented some of the features outlined as nice to haves (email notifications for new bookings, forgot password etc), as well as some small issues detailed in the client testing section below.

However, overall I'm very happy with what I've managed to achieve in the time Ive had to do it. With some more consultation and revisions with the business owners, I hope it'll be live and helping them out early in the new year.


## Deviations from the part A planning

- Editing forms are now (almost) all edit in place forms, I changed this aspect of the design after receiving some feedback from the part A designs. This change helps the save space on the page and is in line with the minimalist design choice.

- With edit in place forms saving space I decided to do away with the booking update page and keep that function on the admin portal. This makes things much more understandable and straightforward for the user.

- Ive also decided not to use a calendar on the hire page. I initially tried to do this but quickly felt it was going to be a lot of work and time to get working and the UI would be unnecessarily complex. I instead opted for a simple bootstrap date form which has a dropdown date picker, this feels much more intuitive to me. 

## Server Routes - Manual Testing

I have tested my server routes thoroughly throughout the development of the app. During server development I ran testing via postman, running the server locally. I've screen-shotted all the results to demonstrate they're all returning with expected their outcome:

## USER Routes

users/register-account:

expects email and password, returns user_id, email, hashed password, and admin status. if user email already exists, returns error message. If pw is less than 8 characters, returns error message.
![Image](./docs/register-account.png)

users/login:

expects email and password, returns jwt. if email not found or pw does not match db password, returns error message
![Image](./docs/login.png)

users/get-me:

expects jwt in the req header, returns user object
![Image](./docs/get-me.png)

users/update-me

expects jwt in the header and new data to update in the req body, returns updated user object
![Image](./docs/update-me.png)

users/delete-me

expects jwt in header, returns success message
![Image](./docs/delete-me.png)

users/admin/delete/:user_id

expects admin jwt in header and user id in the url, returns success message
![Image](./docs/admin-user-delete.png)

## EQUIPMENT Routes

equipment/get-all

expects nothing, grants access to all. returns all equipment objects
![Images](./docs/equipment-get-all.png)

equipment/add-new

expects admin jwt in header and equipment data in body, returns new equipment object with _id
![Image](./docs/equipment-add-new.png)

equipment/update/:id

expects admin jwt in header, equipment id in url, and new data fields to update in req body. Returns updated equipment object.
![Image](./docs/equipment-update.png)

equipment/delete/:id

expects admin jwt in header, equipment id in url. Returns success message.
![Image](./docs/equipment-delete.png)

## BOOKING Routes

booking/get-all

expects admin jwt in header. Returns all booking objects

![Image](./docs/booking-get-all.png)

booking/add-new

expects jwt in header, startDate, endDate, equipmentIDs, totalPrice fields in req body. Returns success message, new booking object with id, and adds start date and end date to bookedDates fields on equipment objects.

![Image](./docs/booking-add-new.png)
![Image](./docs/booking-updatesequipment.png)

booking/update/:id

expects admin jwt in header, data to update in the req body. Returns updated booking object.

![Image](./docs/booking-update.png)

booking/delete/:id

expects jwt in header and booking id in url, returns success message, removes bookedDates data from equipment objects, and updates stock number on equipment objects.

![Image](./docs/booking-delete.png)

---

All routes handle errors - successfully returning unauthorized, bad request, or server error where appropriate. I haven't screen shotted all of those because Ive run out of time!


## Client - Manual Testing

I have run through some use case scenarios and provided screenshots of the deployed client functionality.

Case - Richard:

Richard is a regular user, he needs to make a booking Jan so he logs into WIS:

![Image](./docs/richard/richard-login.png)

He gets his password wrong and server returns an error message which is displayed:

![Image](./docs/richard/richard-pw-error.png)

He navigates to the hire page, enters the dates he needs to book for and hits check availability:

![Image](./docs/richard/richard-equipment-check.png)

Seeing the 2 items he needs are available for his booking period, he adds them to his cart and clicks the cart icon to navigate to the confirmation page:

![Image](./docs/richard/richard-confirmation.png)

The calculate price function returns the correct price to 2 weeks hire, satisfied that all his details are correct he clicks confirm booking. Success message is displayed and he is taken to his dashboard to view the booking:

![Image](./docs/richard/richard-dashboard.png)

From here he can delete the booking if he wishes. Updates to any booking must be performed by an admin as per business requirements, so if he needs to do that he can contact Kate directly or navigate to the contact page to look up her details:

<i>(note I intended to change the displaying of the booking id as its largely useless information to the user. I wanted to give the user the option of saving a booking name to the booking object - but ran out of time.)</i>

![Image](./docs/richard/richard-contact.png)

Other user functions available to Richard are:

<b>Update</b> his user info. He can click the edit button under his user details form on either his dashboard page or the confirm booking page. This makes the form editable, he can then change any detail in place and press save which will send the updated form data to the server to save to the database. The form then repopulates with the updated data.

![Image](./docs/richard/richard-update.png)
![Image](./docs/richard/richard-details-saved.png)

<i>(note - I intended to add some animated loading icons to the user form when updating, and when fetching user details - unfortunately have run out of time to implement this)</i>

 <b>Delete</b> his own account. He can do that via his user dashboard, he will be prompted with a confirm window, and if he proceeds his account and all associated bookings will be cleared from the database and the client navigates to the home page.

 <b>Log out.</b> By clicking the log out button in the nav bar, his user jwt and cart info are wiped from local storage and the client navigates to the home page.

 ---

 Case: Kate (admin)

 Kate is the owner operator of the business. I have tried to give her as much functionality as possible over the data but unfortunately die to time constraints have not implemented everything to the standard I'd like. However, running through it, on log in admins are directed to the admin portal:

![Image](./docs/kate/kate-portal.png)

As you can see there are some small issues with the layout (bookings text and container are not quite aligned correctly) and the forms displaying 'invalid date' as placeholder text. This is due to some date formatting issues that I haven't had the time to resolve. However the functionality is all working, all the dropdown menus contain all the users, bookings, and equipment as expected and display them in the fields when selected:

![Image](./docs/kate/kate-richard-booking.png)

Admins cannot directly create a user account through the portal but can register an account on behalf of a customer i needs be through the register page. Alternatively they can make bookings through the hire page etc. It would have been nice to be able to implement these functions through the admin portal but as the functionality is already present indirectly, I moved on for the sake of saving time.

A requirement from Kate was to be able to extend the booking period which is possible by clicking the edit button under the booking form:

![Image](./docs/kate/kate-update-booking.png)

This renders fields to add new start and end dates and to recalculate to the booking price. After selecting dates, clicking recalculate will call the calculate price function with the new date parameters and return the new price to the updated price field. Hitting the save button will send that data to the update booking route and save it to the database, a success message is then returned as an alert to the user. 

The equipment form functions in a similar way except that its fields are edit in place (I struggled to achieve this in the booking form because I was reformatting the dates and calling another function to display the booked equipment from the equipment ids, only the equipment ids are available on the booking object). 

The equipment form also allows admins to add new equipment, it functions in the same way as the edit in place function, only when 'save new' is pressed it calls a handler to send the data to the add new equipment server route.

<i>note the page does not re-render after any update, add, or deletion and needs to be manually refreshed to repopulate the dropdown menus - another victim of the time constraint unfortunately.</i>

## Trello

Ive continued to use the same trello board from the part A documentation.

It can be viewed here:

https://trello.com/b/HYZPSzNc/wissite

I generally used it to keep track of issues that came up, and overall progress through development. Admittedly my use of it is fairly basic, working solo though it was enough to keep me on track of my progress.
Heres a few slides to outline the general progression of the build and how Ive used trello:

![Image](./docs/trello_partB/Screenshot%202023-11-27%20221307.png)
![Image](./docs/trello_partB/Screenshot%202023-12-03%20130832.png)
![Image](./docs/trello_partB/Screenshot%202023-12-09%20162300.png)
![Image](./docs/trello_partB/Screenshot%202023-12-09%20162327.png)
![Image](./docs/trello_partB/Screenshot%202023-12-11%20234025.png)
![Image](./docs/trello_partB/Screenshot%202023-12-11%20234057.png)
![Image](./docs/trello_partB/Screenshot%202023-12-12%20215347.png)
![Image](./docs/trello_partB/Screenshot%202023-12-22%20172812.png)

## Git

Heres a link to the organisation repository:

https://github.com/watson-instrument-solutions

As a solo dev I stuck to direct commits to main, I know thats not ideal for assignment marks but it saved me time and head space. 

I committed often and didn't run into any problems.