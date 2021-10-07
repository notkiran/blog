---
layout: post
title: Objects And Its Internal Representation In JavaScript
---

Objects, in JavaScript, is it’s most important data-type and forms the building blocks for modern JavaScript. These objects are quite different from JavaScript’s primitive data-types(Number, String, Boolean, null, undefined and symbol) in the sense that while these primitive data-types all store a single value each (depending on their types).

Objects are more complex and each object may contain any combination of these primitive data-types as well as reference data-types.
An object, is a reference data type. Variables that are assigned a reference value are given a reference or a pointer to that value. That reference or pointer points to the location in memory where the object is stored. The variables don’t actually store the value.

Loosely speaking, objects in JavaScript may be defined as an unordered collection of related data, of primitive or reference types, in the form of “key: value” pairs. These keys can be variables or functions and are called properties and methods, respectively, in the context of an object.

For example: Take the case of cars.

All cars have the same properties, but the property values differ from car to car. All cars have the same methods, but the methods are performed at different times.

Let’s have an example of my favorite merc car and list out its properties(Features):

> Make: Mercedes
> Model: C-Class
> Color: White
> Fuel: Diesel
> Weight: 850kg
> Mileage: 8Kmpl
> Rating: 4.5

Taking the above as reference, lets create a object.

Objects are variables, but objects can contain many values.
The following code assigns many values (Mercedes, C-class, White and soo on) to a variable named Car:

```
var car = {Make: “Mercedes”, Model: “C-Class”, Color: “White”, Fuel: Diesel, Weight: “850kg”, Mileage: “8Kmpl”, Rating: 4.5};
```

The values are written as name:value pairs (name and value separated by a colon).

Syntax:

```
var <object-name> = {key1: value1, key2: value2,... keyN: valueN};

```

So, conclusion and definition for JS objects is “JavaScript objects are containers for named values”.
