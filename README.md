# e-learning-platform
E-learning platform with CMS

### 🚀 Overview
The E-learning Platform is essentially a CMS allowing students and instructors to collaborate together. Students
can register to the platform and enroll to courses. Instructors can add content to the modules, create new subjects 
and provide multimedia content to each course. The platform enables students/instructor to exchange real-time
ideas/concerns using a web-based chat system
![course-modules.png](educa%2Feduca%2Fscreenshot%2Fcourse-modules.png)
![admin-modules-content-definition.png](educa%2Feduca%2Fscreenshot%2Fadmin-modules-content-definition.png)
![course-enroll.png](educa%2Feduca%2Fscreenshot%2Fcourse-enroll.png)
![login-form.png](educa%2Feduca%2Fscreenshot%2Flogin-form.png)
![register-form.png](educa%2Feduca%2Fscreenshot%2Fregister-form.png)
![websocket-chat.png](educa%2Feduca%2Fscreenshot%2Fwebsocket-chat.png)

### 🏂 Architecture
The following is a high-level overview of the actual infrastructure architecture, designed for production usage.
A reverse proxy takes incoming connections and passes the requests to the application server uWSGI for synchronous 
requests and to Daphne for asynchronous request specific to websocket protocol using channel/redis. 
Static files such as html/css/js are served via nginx for increased performances. Django MVT architecture handles 
the actual backend logic taking requests matching urls and returning rendered templates via specific views.
![architectural-diagram.jpg](educa%2Feduca%2Fscreenshot%2Farchitectural-diagram.jpg)

### 🍁 Model definition
![models.png](educa%2Feduca%2Fscreenshot%2Fmodels.png)

### ✨ Features
- Front-end defined using simple html/css with fine-grained design including navbar/sub-bar, header, sidebar, 
product detail, order info, form payment
- Built product catalog (Drinks shop: tea,coffee,ginseng) based on predefined models product and category.
- Catalogue view defined using function based views and django template rendering offering a clear and concise 
catalogue space
- Built shopping cart allowing users to store and buy products including actions/methods such: "add" "remove"
"save" "get total price" "clear". Utilised django session framework as middleware to store cart data
- Registered application to the admin interface to easily allow users for simple interaction with the model flow
- Defined asynch tasks using celery and rabbitmq to process and store orders
- Implemented stripe payment gateway to process payment data using credit card. Defined webhook to actually successfully flag models payment flag
when the payment correctly completes
- Defined coupon system to actually apply discounts to the products and have them discounted at the order level toward the stripe payment process
- Defined recommendation engine using redis based on purchased products

## Urls router endpoint

### 🚀 Technology Stack
- python 3.9
- django 4.1
- psql
- html/css/javascript/AJAX
- docker/docker-compose
- redis
- memcache
- websocket/channels 
- ASGi Daphne
- uWSGi
- REST framework 
- Nginx Reverse proxy with SSL termination

### 🔎 TODO
- re-write the front end using react/angular for better granularity/ui experience