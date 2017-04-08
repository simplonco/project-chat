# MiniChat Project

The project is a **Chat Web App**; groups will be set _randomly_, you will use [Firebase](https://www.firebase.google.com/) (a Remote Database based on `AJAX` Technology) and some CSS Preprocessors [Less](http://lesscss.org/) & [Sass](http://sass-lang.com/) !

What you need is what you have already learned : `HTML`, `CSS`, `JS` and `jQuery` !

On the first day you will focus on the UX / UI Design of the app, and write some specifications (few mockup tools <http://mashable.com/2012/06/07/mockup-tools/>).

And finally you will have the total freedom to use plugins or framework (_e.g.: [Bootstrap](http://getbootstrap.com/) or [Foundation](http://foundation.zurb.com/) or [Material Design Light](https://getmdl.io/)_).

## Specifications Templates

* [French version](https://docs.google.com/document/d/1ST1VZgpuEF_Qf739yo94eT_SmayzB5BYdifCaCYbIlU)
* [English version](https://docs.google.com/document/d/1T89SeKvqGPbgxmVAB4wYddXtoJqpFpFtnhowg9DJ3OA)

## Features

It's a chat, so you have to let people discuss together, of course:

* First, make one big global channel, and after allow other channels like private discussions ;
* Let users choose a pseudonym and maybe choose an avatar (check [Gravatar](https://fr.gravatar.com/)) ;
* Let people send Emoji Smiley, Links, Pictures, Youtube Videos, User Tags, etc.. (you will use `REGEX`) ;
* Make everything looks great (with a lot of `CSS`) and don't forget the app has to be responsive—think about how it will look on mobile devices!

## Design

Here's some advice and a few tricks to help you to work together on the same project code.

First, work with the whole team on global design; next, split the team between, for example, Backend and Frontend developers. A good idea is to use a demo function, e.g.:

```javascript
/* DEMO FUNCTIONS */

var sendMessage = function (message) {
    console.log("DEMO: sendMessage: " + message);
};

var retreiveMessages = function () {
    var messages = [
        { pseudo: "Roméo", message : "Ô Roméo ! Roméo ! pourquoi es-tu Roméo ? Renie ton père et abdique ton nom ; ou, si tu ne le veux pas, jure de m’aimer, et je ne serai plus une Capulet." },
        { pseudo: "Juliette", message : "Dois-je l’écouter encore ou lui répondre ?" }
    ];
    console.log("DEMO: retreiveMessages :" + messages);
    return messages;
};
```

The purpose is to start to code the interface and test using these functions and **at the same time** another member of the team can work on the function to make them work with real data.

Here is the `Javascript` code example given on the official `Firebase` website:

```javascript
// Create a connection to your Firebase database
firebase.initializeApp({
    apiKey: "<FIREBASE-API-KEY>",
    authDomain: "<FIREBASE-DOMAIN>.firebaseapp.com",
    databaseURL: 'https://<FIREBASE-DOMAIN>.firebaseio.com/'
});
var myFirebaseRef = firebase.database().ref('/');
// Save data
ref.set({ name: "Alex Wolfe" });
// Listen for realtime changes
ref.on("value", function(data) {
    var name = data.val().name;
    alert("My name is " + name);
});
```

Firebase has a realtime update design, so you can replace the `retreiveMessages` function with just an `updateConversation` function that will update the content of the conversation and will be called in the `ref.on` method, and of course `sendMessage` will use `ref.set`.

## Ressources

**REGEX (REGular EXpressions)**

* <https://en.wikipedia.org/wiki/Regular_expression>
* You can check it online with <https://regex101.com/> & <http://regexr.com/>
* and practice a bit here: <https://www.hackerrank.com/domains/regex/>

For example: `:smile_cat:` will be replaced by `<img src="graphics/emojis/smile_cat.png" />`.

**AJAX**

* <https://en.wikipedia.org/wiki/Ajax_%28programming%29>
* You can read the official jQuery documentation <https://api.jquery.com/jquery.get/> & <http://api.jquery.com/jquery.ajax/>
* and a bit of OpenClassrooms <https://openclassrooms.com/courses/simplifiez-vos-developpements-javascript-avec-jquery/premiers-pas-avec-ajax> & <https://openclassrooms.com/courses/un-site-web-dynamique-avec-jquery/le-fonctionnement-de-ajax>
