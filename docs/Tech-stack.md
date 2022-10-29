# Tech stack

## Back-end:

1. NodeJS
2. Fastify server
3. Typescript
4. MySQL2

---

## Front-end:

- ReactJS
- Tailwind CSS

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

Yes, Nodejs is faster than PHP since it has concurrency built in it. In Nodejs, you can run code in parallel and multiple tasks can be done at the same time. Meanwhile, PHP is procedural and runs on task a time. NodeJS is like 10x faster than PHP  
References:

## 3. Libraries and tooling

Node has a lot of open source dependencies that we can install and use for our purposes. PHP has also a similar ecosystem but does not have the same number of packages who are updated on a regular basis. Update ensure security, as a programmer you dependencies should always be up to date.

## 4. Typing

JS and PHP are both dynamically typed languages (you don't need to specify the types of your data, the compiler will figure it out at compile time). The downside of this is security. If a variable can be both a string and sometimes an integer, this opens doors to exploitation and overflows. Having a type system will ensure that our system receives and send the right data in the right types.

Since PHP 7.4, PHP now has an optional type system that can be included in a project. JavaScript does not have one, but Typescript does and would provide the same level of security as PHP type system. The downside of a type system include: a longer development phase since type systems usually give so many errors (these errors need to be addressed before deployment).
