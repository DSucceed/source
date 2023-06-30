---
title: "Mastering the Secrets of OOP: Inheritance, Polymorphism, Abstraction, and Encapsulation"
subtitle: ""
date: 2023-06-04T11:30:31+00:00
lastmod: 2023-06-04T11:30:31+00:00
draft: false
author: "Sandeep Undrakonda"
authorLink: ""
description: "Object Oriented Programming 101"
license: ""
images: []

tags: [tips,OOP's,software job basis]
categories: ["Object Oriented Programming"]


featuredImage: "oops101.png"
featuredImagePreview: ""

hiddenFromHomePage: false
hiddenFromSearch: false
twemoji: false
lightgallery: true
ruby: true
fraction: true
fontawesome: true
linkToMarkdown: true
rssFullText: false

toc:
  enable: true
  auto: true
code:
  copy: true
  maxShownLines: 50
math:
  enable: false
  # ...
mapbox:
  # ...
share:
  enable: true
  # ...
comment:
  enable: true
  # ...
library:
  css:
    # someCSS = "some.css"
    # located in "assets/"
    # Or
    # someCSS = "https://cdn.example.com/some.css"
  js:
    # someJS = "some.js"
    # located in "assets/"
    # Or
    # someJS = "https://cdn.example.com/some.js"
seo:
  images: [gettoit.png]
  # ...
---

![oops 101](https://i.ibb.co/BZqZ2hX/oops101.png "oops 101")

# Inheritance, Polymorphism, Abstraction, and Encapsulation: Pillars of Object-Oriented Programming

Welcome to this fun and informative blog post where we'll dive into some important concepts of object-oriented programming: inheritance, polymorphism, abstraction, and encapsulation. These concepts form the foundation of modern software development and play a crucial role in creating reusable, modular, and maintainable code. So, let's get started and explore each concept in detail, with a touch of fun along the way!

## Inheritance: Passing Down the Traits


Imagine a world where cars are represented as objects in a Java program. In this world, we have a generic car called `GenericCar`. It has certain characteristics and behaviors that are common to all cars, such as the number of wheels and the ability to move in different directions. Here's an example of how it can be defined in code:

```java
public class GenericCar {
    int noOfWheels = 4;

    public void moveW() {
        System.out.println("Flooring it Yo!");
    }

    public void moveS() {
        System.out.println("Stopping");
    }

    public void moveA() {
        System.out.println("Left Turn");
    }

    public void moveD() {
        System.out.println("Right Turn");
    }
}

```

In the code above, we have a class called `GenericCar` that represents a generic car. It has a property `noOfWheels` set to 4, and several methods to perform different movements such as moving forward, stopping, turning left, and turning right.

Now, let's say we have a specific type of car called `MercedesEQS` which is a hybrid model. This car inherits all the properties and behaviors of the `GenericCar` class but also has some additional features specific to the `MercedesEQS` model. Here's an example of how it can be defined:

```java
public class MercesdesEQS extends GenericCar {
    String name = "Mercedes EQS Hybrid";

    public void hybrid() {
        System.out.println("Hybrid Mode Engaged! I Save Money!");
    }

    public void sport() {
        System.out.println("Sport Mode Engaged! I Go Bruuuuuuuuuuuuuuuuuuuuuuu......!");
    }
}

```

In the code above, we have a class called `MercedesEQS` which extends the `GenericCar` class. It inherits the properties and behaviors of the `GenericCar` class, such as the `noOfWheels` property and the `moveW()`, `moveS()`, `moveA()`, and `moveD()` methods. Additionally, it has its own unique features, such as the `hybrid()` and `sport()` methods.

Now, let's see how we can use inheritance to access the methods of the parent class and the additional methods of the child class. Here's an example:

```java
public class Main {
    public static void main(String[] args) {
        System.out.println("Using Inheritance");
        MercesdesEQS model1 = new MercesdesEQS();
        System.out.println("Features of " + model1.name);
        model1.hybrid();
        model1.moveW();
        model1.sport();
    }
}

```

Output:

```shell
Using Inheritance
Features of Mercedes EQS Hybrid
Hybrid Mode Engaged! I Save Money!
Flooring it Yo!
Sport Mode Engaged! I Go Bruuuuuuuuuuuuuuuuuuuuuuu......!

```

In the code above, we create an instance of the `MercedesEQS` class called `model1`. We can access the methods inherited

from the `GenericCar` class, such as `moveW()`, as well as the additional methods specific to the `MercedesEQS` class, such as `hybrid()` and `sport()`. This demonstrates how inheritance allows child classes to inherit properties and behaviors from parent classes, providing code reusability and extensibility.

## Polymorphism: Embracing Many Forms

Polymorphism, derived from the Greek words "poly" meaning many and "morphism" meaning forms, refers to the ability of objects to take on different forms and perform the same tasks. It allows us to write code that can work with objects of different classes as long as they share a common interface or superclass.

To illustrate polymorphism, let's consider a world where motorcycles are represented as objects in a Java program. We have a parent class called `GenericBike` that defines common characteristics and behaviors of all bikes. Here's an example:

```java
public class GenericBike {
    int numOfWheels = 2;
    String name;

    public void start() {
        System.out.println("Ignition ON! Engine Running @ 1.5k RPM");
    }

    public GenericBike(String name) {
        this.name = name;
    }

    public GenericBike() {
        this.name = "generic bike";
    }
}

```

In the code above, we have a class called `GenericBike` that represents a generic bike. It has a property `numOfWheels` set to 2 and a method `start()` to start the bike's engine. It also has two constructors, one that takes a `name` parameter and another default constructor.

Now, let's define some child classes that inherit from the `GenericBike` class. These child classes represent specific bike models and provide their own implementations for the `start()` method. Here are a couple of examples:

```java
public class Kawasaki extends GenericBike {
    public Kawasaki(String name) {
        super(name);
    }

    public void start() {
        System.out.println("Ignition ON! Engine Running @ 2.5K RPM");
    }
}

public class YamahaVmax extends GenericBike {
    public YamahaVmax(String name) {
        super(name);
    }

    public void start(int rpm) {
        System.out.println("Ignition ON! Engine Running @ " + rpm + " RPM");
    }
}

```

In the code above, we have two child classes: `Kawasaki` and `YamahaVmax`. Both classes extend the `GenericBike` class and provide their own implementations for the `start()` method. The `Kawasaki` class starts the engine at 2.5K RPM, while the `YamahaVmax` class allows specifying the RPM as a parameter.

Now, let's see how polymorphism allows us to use objects of different classes interchangeably. Here's an example:

```java
public class Main {
    public static void main(String[] args) {
        // Using Polymorphism
        GenericBike splender = new GenericBike("Splender");
        System.out.println("I am " + splender.name);
        splender.start();

        Kawasaki z900 = new Kawasaki("Z900");
        System.out.println("I am " + z900.name);
        z900.start();

        YamahaVmax vmax = new YamahaVmax("Yamaha VMAX");
        System.out.println("I am " + vmax.name);
        vmax.start(1150);
    }
}

```

*Output*:

```shell
I am Splender
Ignition ON! Engine Running @ 1.5k RPM
I am Z900
Ignition ON! Engine Running @ 2.5K

 RPM
I am Yamaha VMAX
Ignition ON! Engine Running @ 1150 RPM

```

In the code above, we create objects of different classes (`GenericBike`, `Kawasaki`, and `YamahaVmax`) but store them in variables of the parent class type (`GenericBike`). This allows us to treat them interchangeably and call the `start()` method without knowing the specific class of the object. This is the power of polymorphism, where objects can take on different forms while still exhibiting the same behavior.

## Abstraction: Hiding the Complexity

Abstraction is an essential concept in object-oriented programming that allows us to hide the internal implementation details of an object and provide a simplified interface for interacting with it. It focuses on the "what" rather than the "how," enabling us to work with high-level concepts and ignore the intricate details.

In our world of vehicles, let's consider an abstract class called `Vehicle` that defines the common properties and behaviors of all vehicles. Here's an example:

```java
public abstract class Vehicle {
    int numOfWheels;
    String name;

    public Vehicle(int numOfWheels, String name) {
        this.numOfWheels = numOfWheels;
        this.name = name;
    }

    public abstract void start();

    public void stop() {
        System.out.println("Vehicle stopped!");
    }
}

```

In the code above, we have an abstract class called `Vehicle`. It has properties `numOfWheels` and `name`, as well as abstract method `start()` and a concrete method `stop()`. The `start()` method is declared as abstract, meaning it doesn't provide any implementation in the abstract class and must be implemented by any concrete subclasses.

Now, let's create a concrete subclass called `Car` that extends the `Vehicle` class and provides its own implementation for the `start()` method. Here's an example:

```java
public class Car extends Vehicle {
    public Car(String name) {
        super(4, name);
    }

    public void start() {
        System.out.println("Car engine started!");
    }
}

```

In the code above, we have a `Car` class that extends the `Vehicle` class. It provides an implementation for the `start()` method, specific to a car's engine.

Now, let's see how abstraction allows us to work with high-level concepts without worrying about the specific implementation details. Here's an example:

```java
public class Main {
    public static void main(String[] args) {
        // Using Abstraction
        Vehicle vehicle = new Car("BMW");
        System.out.println("I am a " + vehicle.name);
        vehicle.start();
        vehicle.stop();
    }
}

```

Output:

```shell
I am a BMW
Car engine started!
Vehicle stopped!

```

In the code above, we create an object of the `Car` class and store it in a variable of the `Vehicle` type. By doing this, we can interact with the object using the `Vehicle` interface, which includes the `start()` and `stop()` methods, without knowing the specific class or implementation details of the object. This allows us to work with abstract concepts and focus on what the object can do, rather than how it does it.

## Encapsulation: Wrapping It Up

Encapsulation is a fundamental principle of object-oriented programming that combines data and methods into a single unit called an object. It aims to protect the internal state of an object from external interference by providing controlled access to the object's properties and behaviors.

In our vehicle world, let's consider a class called `Vehicle` that encapsulates the properties `numOfWheels` and `name` using private access modifiers. Here's an

example:

```java
public class Vehicle {
    private int numOfWheels;
    private String name;

    public Vehicle(int numOfWheels, String name) {
        this.numOfWheels = numOfWheels;
        this.name = name;
    }

    public int getNumOfWheels() {
        return numOfWheels;
    }

    public String getName() {
        return name;
    }

    public void start() {
        System.out.println("Vehicle started!");
    }

    public void stop() {
        System.out.println("Vehicle stopped!");
    }
}

```

In the code above, we have a class called `Vehicle` with private properties `numOfWheels` and `name`. To provide controlled access to these properties, we have defined public getter methods (`getNumOfWheels()` and `getName()`) that allow other classes to retrieve their values. The `start()` and `stop()` methods provide public access to the vehicle's behaviors.

Now, let's see how encapsulation helps protect the internal state of an object. Here's an example:

```java
public class Main {
    public static void main(String[] args) {
        // Using Encapsulation
        Vehicle vehicle = new Vehicle(4, "Tesla");
        System.out.println("I am a " + vehicle.getName());
        System.out.println("I have " + vehicle.getNumOfWheels() + " wheels");
        vehicle.start();
        vehicle.stop();
    }
}

```

Output:

```shell
I am a Tesla
I have 4 wheels
Vehicle started!
Vehicle stopped!

```

In the code above, we create an object of the `Vehicle` class and use the public getter methods (`getName()` and `getNumOfWheels()`) to retrieve the values of its private properties. This allows us to access the necessary information about the object while keeping the internal state protected from direct external modification. Encapsulation helps maintain data integrity, improves code maintainability, and promotes modular development.

And that wraps up our journey through the pillars of object-oriented programming: inheritance, polymorphism, abstraction, and encapsulation. These concepts provide a solid foundation for creating flexible, reusable, and well-organized code. Remember to have fun while exploring these concepts and continue building amazing software solutions!