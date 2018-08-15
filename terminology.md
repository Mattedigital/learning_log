# Terminology

[https://semantic-ui.com/introduction/glossary.html](https://semantic-ui.com/introduction/glossary.html)

---

#### Atomic Design

Atomic design is methodology for creating design systems. There are five distinct levels in atomic design:

* **Atoms** - Atoms are the basic building blocks of matter. Applied to web interfaces, atoms are our HTML tags, such as a form label, an input or a button.
* **Molecules** - Molecules are groups of atoms. A form label, input or button aren’t too useful by themselves, but combine them together as a form and now they can actually do something together
* **Organisms** - Organisms are groups of molecules joined together to form a relatively complex, distinct section of an interface. These are considered standalone, portable, reusable components. An example being a websites main navigation.
* **Templates** - Templates consist mostly of groups of organisms stitched together to form pages. It’s here where we start to see the design coming together and start seeing things like layout in action.
* **Pages** - Pages are specific instances of templates. Here, placeholder content is replaced with real representative content to give an accurate depiction of what a user will ultimately see.

See BEM to see examples of how these principles can be implemented in code.

---

#### BEM

BEM is an acronym of Block, Element, Modifier. Essentially this is a CSS naming convention. It aims to create consistency among programmers whilst easing maintenance of large CSS code bases.

* **Block** - Standalone entity that is meaningful on its own.
  _Examples being:_

```
header, container, sidebar, menu, checkbox
```

* **Element** - A part of a block that has no standalone meaning and is semantically tied to its block.  
  _Examples being:_

```
menu item, list item, checkbox caption, header title
```

* **Modifier** - A flag on a block or element. Use them to change appearance or behaviour.  
  _Examples being:_

```
disabled, highlighted, checked, fixed, size big, color yellow
```

See the styles section on [BEM](/styles/bem.md "Link to BEM section") for greater detail and code examples.

---

#### Controller

The controller is what your application "does", it is the glue that binds the model and view together \(yet also acts as the insulation that keeps them apart \(separation of concerns\)\). The controller acts like a two-way adapter, translating user actions from the view into messages to the model and configuring the view with data from the model.

---

#### CRUD

CRUD is an acronym for Create, Read, Update, Delete. A basic example being a todo app where you can add, view, edit & delete todo list items. Often refers to back-end storage solutions.

---

#### Declarative Programming

Declarative Programming is like asking your friend to draw a landscape. You don’t care how they draw it, that’s up to them. See Imperative Programming for an alternate to this paradigm.

---

#### Express

A fast, un-opinionated, minimalist web framework for Node.js applications. Express.js basically helps you manage everything, from routes, to handling requests and views. The use of middleware is a prominent feature of Express.

---

#### Higher Order Functions

Higher Order Functions are functions that has as its inputs or outputs other functions.

---

#### Imperative Programming

Imperative Programming is like your friend listening to Bob Ross tell them how to paint a landscape. While good ole Bob Ross isn’t exactly commanding, he is giving them step by step directions to get the desired result. See Declarative Programming for an alternate to this paradigm.

---

#### Method

Objects can have their own functions. These are called methods.

---

#### Middleware

Middleware functions have access to the request & response objects within a Node/Express app. As such every time an app receives a req/res object an opportunity to use middleware to execute middleware functions is available. An example being to log a statement to the console each time a response is received.

---

#### Model

The model is a projection of your data and has to do with what your application "IS". Any code dealing with direct persistence to the database is considered the Model. Keep your business logic out of the database and UI, instead keep most logic here,  within the Model.

---

#### MVC

MVC is an acronym for Model, View, Controller. A software architectural pattern commonly used for developing user interfaces. In effect it allows for separation of concerns by delegating specific task to the M, V or C. See [Model](#model), [View](#view), [Controller](#controller) separately or see [MVC Explained](/mvc/mvc_overview.md "Go to MVC Explained") for greater detail.

---

#### Node

Node.js is an open-source, cross-platform JavaScript run-time environment that executes JavaScript code outside the browser. It allows developers to create all kinds of server-side tools and applications in JavaScript.

---


#### Object

Objects are like variables but can contain many key value pairs:

```js
const bike = {
    wheels: 2,
    seats: 1,
    doors: 0,
    color: 'red',
}
```

See the section on JS/Objects for a deeper insight into Objects.

---

#### Opinionated frameworks

Opinionated frameworks are those with opinions about the "right way" to handle any particular task. They often support rapid development in a particular domain (solving problems of a particular type) because the right way to do anything is usually well-understood and well-documented. However they can be less flexible at solving problems outside their main domain, and tend to offer fewer choices for what components and approaches they can use.

---

#### Paradigm

A programming paradigm is a style, or “way,” of programming. Examples of programming paradigms are functional, OOP, imperative, declarative and more.

---

#### Request

An HTTP request. A client submits an HTTP request message to a server, which returns a response. The request must use one of several request methods such as GET, POST, and so on.

---

#### Response

An HTTP response. A server returns an HTTP response message to the client. The response contains completion status information about the request and might also contain requested content in its message body.

---

#### Route

Part of a URL that identifies a resource. For example, in http://foo.com/products/id, “/products/id” is the route.

---

#### Unopinionated frameworks

Unopinionated frameworks, by contrast, have far fewer restrictions on the best way to glue components together to achieve a goal, or even what components should be used. They make it easier for developers to use the most suitable tools to complete a particular task, albeit at the cost that you need to find those components yourself.

---

#### View

The view visualises the state of the model, an example being a webpage, something the user can visually consume.

---

#### CSS

#### Sass

#### React

#### Angular

#### HTML

#### Javascript

#### Nunjucks

#### jQuery



