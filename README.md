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
![instructor-manage-content.png](educa%2Feduca%2Fscreenshot%2Finstructor-manage-content.png)
![instructor-create-course.png](educa%2Feduca%2Fscreenshot%2Finstructor-create-course.png)
![instructor-add-content.png](educa%2Feduca%2Fscreenshot%2Finstructor-add-content.png)

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
- Front-end defined using simple html/css. Implemented javascript calls to perform operation after DOM completion
such as websocket instantiation/communication to support a real-time web-chatting system
- Provided API endpoint to allow students to perform enrolling activities using a Django REST framework
- Built CMS content structure based on model hierarchy having modules, subjects, and courses.
Implemented various models to enhance instructor experience allowing to work with images/videos/text and upload new content
- Built authentication view using a Django built-in authentication framework
- Defined course structure using Mixins and class-based views performing course list,edit,delete.Add remove modules

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