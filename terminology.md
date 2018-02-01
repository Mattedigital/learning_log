# Terminology

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

#### Model

The model is a projection of your data and has to do with what your application "IS". Any code dealing with direct persistence to the database is considered the Model. Keep your business logic out of the database and UI, instead keep most logic here,  within the Model.

---

#### MVC

MVC is an acronym for Model, View, Controller. A software architectural pattern commonly used for developing user interfaces. In effect it allows for separation of concerns by delegating specific task to the M, V or C. See [Model](#model), [View](#view), [Controller](#controller) separately or see [MVC Explained](/mvc/mvc_overview.md "Go to MVC Explained") for greater detail.

---

#### View

The view visualises the state of the model, an example being a webpage, something the user can visually consume.

---

#### 

#### CSS

#### Sass

#### React

#### Angular

#### HTML

#### Javascript

#### Nunjucks

#### Express

#### Node

#### jQuery



