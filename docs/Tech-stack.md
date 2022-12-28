---
sidebar_position: 2
---

# Tech stack

## Back-end:

1. NodeJS

2. [Fastify server](https://www.npmjs.com/package/fastify)

3. Typescript

4. [MySQL2](https://www.npmjs.com/package/mysql2)

5. [JWT](https://www.npmjs.com/package/json-web-token)

6. [Validator.js](https://www.npmjs.com/package/validator)

7. [Fastify compress](https://www.npmjs.com/package/@fastify/compress)- to compress data between server and front-end

8. [uuid](https://www.npmjs.com/package/uuid) - to generate random unique ID. we need it for generating unique Identifiers for reseting passwords or creating accounts. This unique ID can stay the same or be updated regularly on every use. It will also be used to name file uploads/images to give them unique names.

9. [dotenv](https://www.npmjs.com/package/dotenv) - used to read .env files in dev or production.

10. [fastify/cookie](https://www.npmjs.com/package/@fastify/cookie) - used to create, parse, ..

11. [CORS](https://www.npmjs.com/package/@fastify/cors) - Cross Origin Resource Sharing. This allows to the browser to communicate with the server, withour it, thefrontend would not trust the backend unless they are on the same domain.
12.

---

## Front-end:

1. ReactJS
1. [Tailwind CSS](https://tailwindcss.com/)
1. [React-router](https://reactrouter.com/en/main)
1. typescript
1. [ViteJS](https://vitejs.dev/)

# PHP vs NodeJS

It took me time to decide whether to migrate to JavaScript for the back-end. For the front-end, JavaScript is the best option, since it allows us to easily create **Single Page Applications** using ReactJS (which will be used).

For the back-end, a suitable language should meet the following criteria:

- Speed
- Effective memory usage — We will be constrained when the app will be deployed. The more resources we use, the more the costs.
- Database connectivity
- **Static typing.**

## <div align="center">Why not PHP?</div>

## 1. PHP does not offer pretty URLs by default

We would need to use a big framework like Laravel or code Igniter to implement the API endpoints. This would be overkill since these frameworks are made to be full stack.

Another option was using Laravel with a React front-end. This is a good option, but still slightly overkill: using a MVC framework just for API.

## 2. Speed

Yes, Nodejs is faster than PHP since it has concurrency built in it. In Nodejs, you can run code in parallel and multiple tasks can be done at the same time. Meanwhile, PHP is procedural and runs one task a time. NodeJS is like 10x faster than PHP  
References:

## 3. Libraries and tooling

Node has a lot of open source dependencies that we can install and use for our purposes. PHP has also a similar ecosystem but does not have the same number of packages who are updated on a regular basis. Update ensure security, as a programmer your dependencies should always be up to date.

## 4. Typing

JS and PHP are both dynamically typed languages (you don't need to specify the types of your data, the compiler will figure it out at compile time). The downside of this is `security`. If a variable can be both a string and sometimes an integer, this opens doors to exploitation and overflows. Having a type system will ensure that our system receives and send the right data in the right types.

Since PHP 7.4, PHP now has an optional type system that can be included in a project. JavaScript does not have one, but Typescript does and would provide the same level of security as PHP type system. The downside of a type system include: a longer development phase since type systems usually give so many errors (these errors need to be addressed before deployment).
