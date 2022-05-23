---
layout: post
title:  "React + Redux App"
date:   2020-08-21 05:10:47 +0200
permalink: "/reactredux"
categories: react redux
---

## Dev Fail Story

dev fail story is a platform for developer to share their lessons learned through failure in the Tech industry. The Web App is built in React and uses Redux for state with a REST API build in Node.js for its backend.

Technologies used : React, Redux, Html & CSS, GIT, redux-thunk, react-devtools, markdown editor

### React Frontend

The **landing** **page** is a static file in react rendering html & CSS with images and links to signup, login, about, and contact pages

![code](/ThinkLynk/assets/devfailstory/1.png)

The **login & signup pages** send https post requests to a rest endpoint with the email and login. The response which is the users id and information is then stored in the browsers session story until the tab is closed for it timeout. The backend then uses the users stored information to verify the user when accessing other pages and making other requests.

![code](/ThinkLynk/assets/devfailstory/2.png)

The **main feed page** dynamically displays posts retrieved from the backend and store in redux state. Each post has a title, the link slug, and a short description. As more posts are created by the app users they will be added to the feed with the newest displaying on top.

![code](/ThinkLynk/assets/devfailstory/3.png)

The **story page** fetches the article data through its slug link from the backend and dynamically displays it as it stores it in redux for faster app loading speeds. You also have the ability to like a post, save it and share to twitter and read more related posts.

![code](/ThinkLynk/assets/devfailstory/4.png)

The **account page** will display how many people have followed you on the app, your bio, has links to your twitter or any other social media and blogs you link. The nav takes you to posts you've written before, comments on those posts and your account settings if you wish to change them. You can also write more posts by clicking the write button.

![code](/ThinkLynk/assets/devfailstory/5.png)

The **write post page** is the most important and complex on the app. From here users add the title and description of their posts. They then add the content of the post which can include images, tables, ordered and unordered lists, headings, code blocks links and page dividers. They then save and publish the post which is then sent to the backend, validated and sent back to the main feed page.

![code](/ThinkLynk/assets/devfailstory/6.png)



### Redux

This is a centralized place to contain the global state of the application and this allows the app to use the state without worrying about the hierarchy.

This app uses **redux-thunk**, a middleware that lets you call action creators that return a function instead of an action object. This allows it to achieve asynchronous operations.

It also uses **axios** to make requests to the backend api.

The endpoint of the application changes based on the environment the app is started on i.e production or dev

![code](/ThinkLynk/assets/devfailstory/7.png)



Reducers for the redux state

![code](/ThinkLynk/assets/devfailstory/8.png)



The signup function...

![code](/ThinkLynk/assets/devfailstory/9.png)
