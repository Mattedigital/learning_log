# MVC Explained {#mvc}

#### The MVC Pattern

**Model:** Structures your data in a reliable form and prepares it based on controller’s instructions. Domain Logic should go here \(An example of domain logic: in an accounting application domain rules would be rules regarding accounts, postings & taxation. The data as such.\)

**View:** Displays data to user in easy-to-understand format, based on the user’s actions

**Controller:** Takes in user commands, sends commands to the model for data updates, sends instructions to view to update interface. Application logic should go here \(An example of application logic: continuing with the Models accounting application example - CSV import/export could be relevant, but the rules of CSV import/export has nothing to do with the actual domain. This kind of logic is application logic.\)



![](/assets/MVC_visual copy.png)

#### 

#### MVC analogy: Ordering drinks at a bar.

You \(the **user**\), order an Old Fashioned at a bar \(**user request**\).

To the bartender, this cocktail is merely a series of steps:

1. Grab glass
2. Add whiskey
3. Add bitters
4. Add water
5. Add sugar cube
6. Stir drink
7. Add orange peel
8. Ask for credit card and charge.

When the bartender’s brain \(the **controller**\) hears the word “Old Fashioned” in a language that they understand, the work begins. The bartender can only use the tools and resources that are behind the bar. This limited tool set \(the **model**\) could include glasses, mixers, condiments, syrups and so on.

The final product is the drink \(the **view**\), which you \(the **user**\) consume.

#### Consideration points

Want another drink? Shouting at an empty glass \(the **view**\) will do nothing. You need to speak to the barman \(the **controller**\).

The time spent between the bartender hearing your request and starting to create the drink should be absolutely minimal. This is sometimes known as a “skinny controller”- in other words, the controller should contain a minimal amount of logic, and delegate as much as possible to the model.

You want to keep as much of your logic within the model as possible as opposed to within the view. i.e. making the drinks behind the bar is preferable to mixing it within the customer’s mouth.

#### Tying this into web development {#tying-into-webdevelope}

The user makes a request along a route, let’s say /home.

The controller receives this request and gives a specific set of orders that are related to that route. These instructions could either be for the view to update or serve a certain page, or for the model to perform specific logic. Let’s assume this request has some logic associated with it.

The model carries out the logic, pulls from a database and sends back a consistent response based on the controller’s instructions.

The controller then passes this data to the view to update the user interface.

_All credit should go to the original article found here: _[_https://medium.freecodecamp.org/model-view-controller-mvc-explained-through-ordering-drinks-at-the-bar-efcba6255053_](https://medium.freecodecamp.org/model-view-controller-mvc-explained-through-ordering-drinks-at-the-bar-efcba6255053)

