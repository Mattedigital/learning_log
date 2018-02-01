# Terminology

---

#### 

#### Atomic Design

Atomic design is methodology for creating design systems. There are five distinct levels in atomic design:

* **Atoms** - Atoms are the basic building blocks of matter. Applied to web interfaces, atoms are our HTML tags, such as a form label, an input or a button.
* **Molecules** - Molecules are groups of atoms. A form label, input or button aren’t too useful by themselves, but combine them together as a form and now they can actually do something together
* **Organisms** - Organisms are groups of molecules joined together to form a relatively complex, distinct section of an interface. These are considered standalone, portable, reusable components. An example being a websites main navigation.
* **Templates** - Templates consist mostly of groups of organisms stitched together to form pages. It’s here where we start to see the design coming together and start seeing things like layout in action.
* **Pages** - Pages are specific instances of templates. Here, placeholder content is replaced with real representative content to give an accurate depiction of what a user will ultimately see.

See BEM to see examples of how these principles can be implemented in code.



---

#### 

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

#### 

#### CRUD

CRUD is an acronym for Create, Read, Update, Delete. A basic example being a todo app where you can add, view, edit & delete todo list items. Often refers to back-end storage solutions.



---

#### 

#### MVC

MVC is an acronym for Model, View, Controller. A software architectural pattern commonly used for developing user interfaces. See MVC Overview for greater detail.



---

#### CSS

Model

View

Controller

#### Sass

#### React

#### Angular

#### HTML

#### Javascript

#### Nunjucks

#### Express

#### Node

#### jQuery



