Hello, my name is Eugeni Bykovski.
This is my CV.
[GitHub](https://github.com/EugeniBykovski)

1. Eugeni Bykovski
2. email: bykovskieugeni@mail.ru
phone: +37529 380 96 43
linkedin: https://www.linkedin.com/in/eugenibykovski/
3. I’m 24 years old. I’m looking for a job as a software developer.
It is important for me to strengthen my knowledge of layout,
deepen my knowledge in javascript, learn new frameworks and learn how to apply
programming patterns. I would also like to find a job in the field of web development.
I found myself in this and I want to connect my life with development.
In order to become an excellent specialist, I attended several programming courses
in JS (IBA, BellHard), constantly read various literature, and visit Internet sources.
I also improve my English level at English Papa. At the moment I have an
Intermediate level. My plus is that if something doesn’t work out for me, I definitely need to
thoroughly understand until I understand to the end.
4. I graduated from the magistracy of BNTU, Instrument Engineering Department. 
I have completed JavaScript programming courses in IBA (Web Application Development). 
They wrote small projects on React.js and Angular.js. I used the GitHub version control
system and various frameworks and preprocessors, such as Bootstrap, Less, Sass.
I have completed PHP programming courses at BellHard.
I have completed online courses at htmlacademy.ru, codeacademy.com, learnjavascript.ru.
5. Examples of when and my work can be seen in my profile on GitHub.
Here is a link to my recent project https://github.com/EugeniBykovski/Coffee-Shop-APP.
Among other things, I am developing websites using HTML5 and CSS3.
I have graduated from the magistracy of BNTU. Instrument Engineering Faculty. 
I have graduated from JavaScript programming courses in IBA. I have completed PHP 
programming courses at BellHard. Learning English in Papa Intermediate English. I work on freelance.

```javascript
(function (window) {// задача этого модуля в получении объекта window для использования в теле функции. Он так же извлекает конструкторы, описанные нами в качестве части пространства имен window.App
  var FORM_SELECTOR = '[data-coffee-order="form"]';
  var CHECKLIST_SELECTOR = '[data-coffee-order="checklist"]';
  var SERVER_URL = 'http://coffeerun-v2-rest-api.herokuapp.com/api/coffeeorders';

  var App = window.App;
  var Truck = App.Truck;
  var DataStore = App.DataStore;
  var RemoteDataStore = App.RemoteDataStore;
  var FormHandler = App.FormHandler;
  var Validation = App.Validation;
  var CheckList = App.CheckList;

  var remoteDS = new RemoteDataStore (SERVER_URL);

  // создание экземпляра truck
  var myTruck = new Truck ('ncc-1701', new DataStore ());
  window.myTruck = myTruck;

  var checkList = new CheckList (CHECKLIST_SELECTOR);
  checkList.addClickHandler (myTruck.deliverOrder.bind (myTruck)); // вызов метода addClickHandler

  var formHandler = new FormHandler (FORM_SELECTOR);
  formHandler.addSubmitHandler (function (data) {
    return myTruck.createOrder.call(myTruck, data).then(function () {
      checkList.addRow.call (checkList, data);
    });
  });

  formHandler.addInputHandler (Validation.isCompanyEmail); // связываем проверку допустимости с событием input

  myTruck.printOrders (checkList.addRow.bind (checkList));
})(window);
```


