---
layout: post
title: Web Application Aspects
---

This post is to catalog how I have been tackling some aspects of my node.js projects.

- **Coding Standards**
  - Code Linting
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
- **Database Scalability**
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
- **Documenting**
- **Bug Reporting**
  - Using Github Issues
- **Build Process**
- **Continous Integration**
- **Deployment**
  - Amazon EC2
- **Good practices**
  - Shrinkwrap  
    
<div style="margin-top:15px;"></div>

## Coding Standards

In the effort to make the entire code base look like the same person has typed it we must follow some conventions. The ones that I adopt in my code base are listed in [Principles of Writing Consistent, Idiomatic JavaScript](https://github.com/rwaldron/idiomatic.js/) which I deeply recommend you reading.

Conventions that I avoid using but are recently becoming popular are: skipping `;` at the end of lines and the [Comma First](https://gist.github.com/isaacs/357981/) pattern. 
