---
layout: post
title: Web Application Aspects
---

This post is to catalog how I have been tackling some aspects of my node.js web projects. Each aspect will become a link to an individual post about the subject.

- **Introduction**
- **Coding Standards**
- **Folder Structure**
- **Internationalisation (i18n)**
  - Date and Time
  - Numbers
  - Currency
  - Timezone
- **Authentication**
- **Role Based Authorization**
- **Database Decision**
- **Scalability**
  - Database Scalability
- **Static File Storage**
  - Amazon S3
- **Logging**
- **Distributing Static Content**
  - NGINX
  - Content Delivery Networks
    - Amazon Cloud Front
- **Testing**
  - Unit Testing
  - Integration Testing
- **Front End**
  - Frameworks
- **Documentation**
- **Bug Reporting**
  - Using Github Issues
- **Build Process**
- **Continous Integration**
  - Test
  - Build
  - Archive Binaries
  - Deploy
- **Deployment**
  - Amazon EC2
- **Good practices**
  - Shrinkwrap  
    
<div style="margin-top:15px;"></div>
## Coding Standards

In the effort to make the entire code base look like the same person has typed it we must follow some conventions. The ones that I adopt in my code base are listed in [Principles of Writing Consistent, Idiomatic JavaScript](https://github.com/rwaldron/idiomatic.js/) which I deeply recommend you reading.

Conventions that I avoid using but are recently becoming popular are: skipping `;` at the end of lines and the [Comma First](https://gist.github.com/isaacs/357981/) pattern.   

You can enforce some of this conventions by running [JSHint](https://github.com/jshint/jshint/) as a [test task](https://github.com/gruntjs/grunt-contrib-jshint) with [Grunt](http://gruntjs.com/). If JSHint fails I don't even run my unit tests.

<div style="margin-top:15px;"></div>
## Folder Structure

The folder structure is a very important part of code organization, so having an appropriate and consistent folder structure is a key for fast development.

The folder structure I have found to be the most appropriate and have been using for my web apps is shown and explained below.

```
|
|--- controllers
|--- domain
|   |
|   |--- models
|   |--- repositories
|
|--- views
|--- static
|   |
|   |--- js
|   |--- img
|   |--- css
|   |--- audio
|   |--- i18n //may look redudant having two folder for i18n, but it will be explained
|   |   |
|   |   |--- en.json
|   |   |--- es.json
|   |   |--- pt.json
|
|--- infra
|--- i18n
|   |
|   |--- en.json
|   |--- es.json
|   |--- pt.json
|
|--- utils
|--- tests
|
|--- app.js //application start point
|--- env.json //environment specific configurations (not versioned)
|--- Gruntfile.js
|--- package.json
|--- README.md
```

I start my application with a single `app.js` file, containing initialization code for express. I usually have lots of routes so it is impossible to organize all of them in a single file, then I create the `controller` directory, and I create one individual controller for each entity in the project. Actually I separate files by entity, it means that I will have an individual model file, repository file and controller file for `Client` (say we have this entity). Also I create a different folder for each entity in the `views` folder, as we are sure we wil surely end up with lots of different views per entity.
