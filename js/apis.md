# API's

\(See bottom of file for list of open API's for tinkering/learning/projects\)

## Browser API's

### Vibration API

The **Vibration API** makes a device vibrate with JS. It's intended to be used on mobile devices to provide additional feedback.

To check if device is present:

```javascript
"vibrate" in navigator
```

To make the device vibrate for 1 second:

```javascript
navigator.vibrate(1000);
```

To make a device vibrate in a pattern you can pass in an array of millisecond values. The values alternate specifying vibration and pause time intervals:

```javascript
//vibrate for one second,
//pause for one second
//vibrate for two seconds then stop
navigator.vibrate([1000, 1000, 2000]);
```

Vibration can be stopped by passing a `0` or an empty array `[]` to the vibrate method.

### High Resolution Timing API

The **High Resolution Time Api** allows you to perform precise timing measurements.

To use the API call `performance.now()`

The API will return a numeric value representing the current time such as _773665.7000000001._

The values returned by `performance.now()` always increase constantly and are . not subjetc to time adjustments such as daylight savings and synchronisation logic \(NTP\).

The API can represent time up to microsecond precision and is much more accurate than other JS timing features such as `Date.now()` which will return a value to the nearest millisecond.

You can use this API to measure the performance of your code:

```javascript
let start = performance.now();
//do something
let end = performance.now();
console.log(`Do something took ${end - start} milliseconds`);
```

We could also use this for precise timing in game, animation or audio logic.

### Permission API

The **Permission API** is a standard way to check the permission status of an API.

You can check the status of a permission using `permissions.query()`. The status is either **granted**, **denied** or **prompt** \(if you need to request the permission from the user\).

For example:

```javascript
//Check for Geolocation API permissions.
//Pass permission's name into a method as 'permissionDescriptor' object.

navigator.permissions
    .query({name: 'geolocation'})
    //The promise resolves to 'permissionStatus' object.
    .then(function(permissionStatus) {
        //print state of geolocation permission
        console.log('geo permission state is: ', permissionState.state);
    });
```

You can also create an event handler for `permissionStatus.onChange`

Requesting permission from the user is still dependant on the specific API.

Currently only available in **Chrome**.

### Notifications API

The **Notifications API** displays desktop notifications to the user and is a great way to alert the user of important event occurring in the application.

The user needs to grant the notification API permission.

To check if the user has granted permission:

```javascript
if (Notification.permission === 'granted') {
...
}
```

To request permission to display notifications:

```javascript
Notification.requestPermission(
    function (permission) {
        if (permission === 'granted') {
            //notification logic
        }
    }
)
```

Once permission is granted you can create notifications:

```javascript
let notification = new Notification('Hello');
```

The notification can be further customised by passing in options to set an icon or body text:

```javascript
let options = {
    icon: anImage,
    body: someText
}
let n = new Notification(title, options);
```

### **Page Visibility API**

The **Page Visibility API** allows you to query whether a page is visible or in focus.

Use Case: It is common for users to have multiple pages and tabs option at once. The information provided by the visibility API could be used to trigger an action such as starting an animation or stopping network requests to save resources.

When the user moves to another tab or minimises the webpage the API sends a `visibilityChange` event.

Not the naming of this event and hidden property differs across browsers.

Detecting changes:

```javascript
document.addEventListener('visibilitychange', function(){
    if(document.hidden){
        console.log('hidden');
    }else{
        console.log('shown');
    }
}, false);
```

### Warn user if Back button is pressed

To prevent the loss of data you will want to warn the user before pressing the back button to leave the current page.

The following snippet will add a warning message if the button is pressed:

```javascript
window.onbeforeunload = function() {
    return "Your work will be lost.";
}
```

`onbeforeunload` event handler property contains the code executed when the `beforeunload` is sent. This event fires when a window is about to unload its resources. The document is still visible and the event is still cancelable.

**Cinemas** - [http://www.cinelist.co.uk/](http://www.cinelist.co.uk/)

**Cooking / Food:** [https://www.food2fork.com/about/api](https://www.food2fork.com/about/api)

**Deck of Cards:** [http://deckofcardsapi.com/](http://deckofcardsapi.com/)

**Design Quotes** - [http://quotesondesign.com/api-v4-0/](http://quotesondesign.com/api-v4-0/)

**Developer Zen Quotes** - [https://api.github.com/zen](https://api.github.com/zen)

**Flickr** - [https://api.flickr.com/services/feeds/photos\_public.gne?tags=yellow&tagmode=all&format=json&nojsoncallback=?](https://api.flickr.com/services/feeds/photos_public.gne?tags=yellow&tagmode=all&format=json&nojsoncallback=?)

\([https://www.flickr.com/services/feeds/docs/photos\_public/](https://www.flickr.com/services/feeds/docs/photos_public/%29\)\)

**IP / Geolocation** - [http://ip-api.com/json](http://ip-api.com/json)

**Movies** - [http://www.omdbapi.com/](http://www.omdbapi.com/)

**Movies** - [https://www.themoviedb.org/documentation/api](https://www.themoviedb.org/documentation/api)

**Photos / Images -** [https://unsplash.com/developers](https://unsplash.com/developers)

**Photos / Images -** [https://source.unsplash.com/](https://source.unsplash.com/)

**Pokemon png's** **\(lofi\)** - [https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/${id}.png](https://raw.githubusercontent.com/PokeAPI/sprites/master/sprites/pokemon/12.png)

**Pokemon png's \(hi res\) -**   
[https://assets.pokemon.com/assets/cms2/img/pokedex/detail/${id}.png](https://assets.pokemon.com/assets/cms2/img/pokedex/detail/111.png)  
****Note: ${id} needs to be three places long. i.e 001, 011, 111.

**Weather** - [http://openweathermap.org/api](http://openweathermap.org/api)

**Weather** - [https://darksky.net/dev](https://darksky.net/dev)

