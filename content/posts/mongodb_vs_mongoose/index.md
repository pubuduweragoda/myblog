+++
title = 'MongoDB vs. Mongoose: Which one to use on your Express JS project?'
date = 2025-03-22T13:01:09+05:30
draft = false
+++

# MongoDB vs. Mongoose: Which one to use on your Express JS project?

Mongoose is an Object Data Modelling library made on top of the MongoDB native driver for Nodejs. While it's lacking in terms of performance compared to using MongoDB directly, it allows developers to build applications faster.

First of all, I need to clarify, MongoDB and MongoDB server are not the same. Here, MongoDB is referring to the `mongodb` npm package. MongoDB server on the other hand is installed on the server, as a service.

## Pros of using Mongoose over MongoDB

### Simple to get started
Mongoose for most parts, adds a layer on top of `mongodb` and makes it easier to handle database connection without needing to configure any low-level functionality.

This makes it easy for new developers to learn and use MongoDB databases without having to worry about the complex operations involved in it.

### Rapid development
The main reason to use Mongoose is it's simplicity and most importantly, it is faster to develop using Mongoose than to directly use `mongodb`,due to the built in features that comes with Mongoose. Following are some of the popular and commonly used ones:

- Schema validation
- Object modeling
- Instance and Static methods
- Virtuals
- Discriminator
- Middleware
    

Instead of doing things like schema validation manually, it is more productive to use these built in functionality of Mongoose.

## Draw backs of Mongoose

### Performance Issues

Since Mongoose is build on top of MongoDB native driver, it adds a layer of abstraction and processing overhead. Due to this Mongoose is less performant in comparison. The other issue is that, because of the abstractions on low-level functionalities, it limits the developers ability to optimize for performance.

### Being dependent on Mongoose

When using Mongoose, it abstracts the developer from the process of saving data to the database, and does everything in the background according to the mongoose api and it's conventions. So, if you want to make any customization in the future without using mongoose, it can get very complicated.

For this reason, it's not a good idea to use mongoose if you may need to be able to scale the app in the future.

### Limiting the power of MongoDB database

The reason why MongoDB is so popular is because it doesn't lock you into a rigid schema, which allows you to store data in unpredictable scenarios. However, with Mongoose, you are forced to use a fixed schema to build your models. This is counter intuitive to how MongoDB was intended to be used.

## Conclusion

The choice between using `mongoose` vs `mongodb` comes down to three main factors, Development time, Performance and Complexity of the application. If you want to increase performance, or you need to do complex data manipulations and queries which are not available in `mongoose`, using `mongodb` from the beginning maybe the best way to go.

However, if you're more concerned about developing the app faster and isn't concerned that much about customization and performance benefits, then Mongoose maybe a good option to consider.

Another option to consider is developing the project while leaving enough flexibility to switch between `mongodb` and `mongoose` later, depending on the needs. The actual decision always depends on your project requirements.


## Extra reading

### What is a Native Driver?

A **Native Driver** is a software component written in the same language as the platform that it is intended for. Here, the MongoDB( `mongodb` npm package) is written in JavaScript and Nodejs is written in C++.

However, Nodejs is a runtime environment that allows **running JavaScript code**. So, Nodejs is the platform while MongoDB is the software component(the native driver).
