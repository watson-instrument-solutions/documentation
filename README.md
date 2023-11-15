# Watson Instrument Solutions - Documentation


## Purpose

The aim of this site is deliver a professional web portal for the current customer base of WIS. Currently, they take hire bookings via email and phone call only so having an online booking system will save their customers time, and enable them more efficient project planning by being able to see equipment availability immediately without having to wait for a returned email or phone call.

Additionally, the site will enable them to grow their customer base by having another avenue for potential customers to find them and using tools like google ads / key words. 



## Functionality & Features

### Customer Users

#### Customer Account Creation

Customers can create a user account by providing a username, email and password.

#### Customer Log in

Customers can then log in using their email and password for verification and start making hire bookings.

#### Account / Profile page

Once logged in customers will be able to see and edit their current user information such as email, password, contact phone number, address as well as view any current bookings.

#### Log out

Customers will be able to logout of their account so their data is secure.

### Admin Users

#### Admin Creation

Admin accounts will be able to create other admin, and non admin accounts, the business owners frequently hire their own equipment to themselves for another side of their business, so being able to create their own bookings is a requirement. 

#### CRUD all bookings / users

Admin accounts will be able to view and edit / delete all current bookings from all users. They will also be able to view create/update/delete all users if necessary.

#### CRUD all equipment

Admin accounts will have full control over all equipment and it pricing listed on the site.

### Browsing

Anyone will be able to browse equipment, each item will have an image and description as well as a dynamic calendar to show its availability. This way any potential new customers will be able to quickly see if the equipment they need is available without going through a sign up process.

### Booking System

Customer users will be able to create a booking, then prompted to give the dates, and then the equipment they need (multiple items). They will be shown an alert if one of the pieces is unavailable. Then shown a confirmation page with all details. If they confirm they will have an invoice auto generated and sent to their user email address.

If once a booking is created, it needs to be updated or deleted they will need to contact one of the business owners directly via details provided on the contact page. This is subject to change depending on the business cancellation policy.

## Target Audience

The target audience for WIS are professional acoustician businesses only. It is very unlikely for anyone outside of the industry to need to hire this kind of equipment without at least using a subcontractor who has the expertise to use it. Therefore it is assumed that most users will be technical and already have a strong grasp of the products they need to hire, so the focus will be be on providing efficient, clear ease of navigation to save time and provide an easy transactional experience. 

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

## Application Architecture Diagram

![Image](./docs/WIS%20App%20architecture%20diagram.drawio.png)




