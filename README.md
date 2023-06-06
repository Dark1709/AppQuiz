# AppQuiz

Hi, an AppQuiz application was made with JavaScript, with Object Oriented Programming, following the guide of this youtube video https://www.youtube.com/watch?v=t_2PI3fHp_I&t=3780s&ab_channel=FaztCode.

Next I will explain what was done and what is the purpose of each decision:

- We will start by creating the basic structure of the project, as follows:

- Here I tell you summarily, what you will find in each of the files or folders:

    - **index.html** Main document

    - appp.js** Main file where the logic of the project is started.

    - data - questions** Folder with a file with the questions and answers that we want the user to see.

    - **models** Here we will find the classes of our application, definition, etc.

    - styles** Here we are going to find the style of the app.

- Next we will give the basic structure to the index, according to our needs.

- Now we give style to what we carry,

- We continue adding the js, making a `console.log()` in app.js and adding the `script` tag calling the file in the index.html, so that our html can read it and make sure of the same.

- Already sure that our js is being read, we continue with the basics, so we go to the data folder and create a data.js file, in which we are going to place multiple objects within an array, the questions and the options that we want the user to answer.

- Then we make the parent object and the child objects for those questions with their respective answer.

- We must also add a property called `type`, in the `script` tag of the html, to allow us to import files, with the `import` and `export` .

- When an import is made from another js file, we must add the extension js and we indicate between braces what we want to import.

- In the folder models we add a file Questions.js

- We define a class called Questions, which has a constructor that will be executed when a new instance of the class is created, when we use the word new.

- Inside the constructor, we are going to define the properties of the instance, in this case text, choices and answer.

- Here what is observed is that in the class "Questions" represents a question with answer options and a correct answer. When creating a new instance of the class with `new Questions()`, an object will be created with the aforementioned properties, which will be used to access the question, the options and the correct answer.

- Then we declare a const `questions` , which becomes an instance of the class `Questions` , allowing access to the properties and methods defined in the class using the dot syntax.

- Now we define the methods of the object

- We also define what parameters the constructor will receive, in this case a text, an array choices and an answer, and the values will be those parameters, with this we avoid that all the objects have the same text.

- Now we want the simple object, which is in data, to pass through a Question object, for that we will use the new

- Now we will make a brief documentation of the parameters in the following way

Note: @param is to document the parameters of either a function or a class (jsdoc).

- Now we will create a file in data, called questions.js

- Then we import the `Question` class and import the js file and from there the constant called `date`.

- We are going to use a `map()` to run through all the arrays and return the values, with a new array in this case a question and that for each path of this question is going to be passed to a class called Question, telling it what parameters we are going to pass.

- Now we are going to give a constant question to this data and to be able to export it, we add the word export, as usual.

- We go to app.js and import the file with the two previous steps we guarantee that each array has a questions object, with its properties and method, in this case `correctAnswer`.

- Now we are going to create a class in a file called Quiz that will be in the folder models that is going to serve us to be able to have the logic of our application, that is to say the correct, successful and pending questions.

- Now I will explain what was done in this file

- `///@ts-check` with this line we rely on TypeScript to perform code analysis, even if we are only using JavaScript.

- We export the Quiz class and now we are going to pass some data to it, for example the question to our polls and methods.

- We also import { Question}, so we can use it in our file

- **`questionIdex = 0;`**: This is a declaration of a class property called **`questionIdex`** with an initial value of 0. This property is used to keep track of the index of the current question in the quiz.

- **`score = 0;`**: This is another class property named **`score`** with an initial value of 0. This property is used to keep track of the user's score in the quiz.

- **`constructor(questions) { ... }`**: This is the constructor of the **`quiz`** class. It receives a **`questions`** parameter, which is expected to be an array of objects of type **`Question`**. The array of questions is assigned to the **`this.questions`** property.

- **`getQuestionIndex() { ... }``**: This is a class method that returns the current question based on the **`questionIdex`* index. It returns the corresponding question object from the **`questions`** array.

- **`isEnded() { ... }``**: This is another class method that returns **`true`* if all questions in the questionnaire have been exhausted, that is, if the **`questionIdex`* is equal to the length of the **`questions`* array. Otherwise, it returns **`false`**.

- **`guess(answer) { ... }``**: This class method takes an answer (**`answer`*) as argument and checks if the answer provided by the user is correct using the **`correctAnswer()`* method of the current question. If the answer is correct, it increments the score (**`score`*). Then, it increments the question index (**`questionIdex`**) to advance to the next question in the quiz.

- We go to app.js, and create an instance of the Quiz class and assign it to the quiz variable. The main() function is called to start the execution of the program.

- We make a new file in the models folder called UI.

- We export the UI class to be able to use it in other files.

- **`constructor() { ... }`**: This is the constructor of the **`UI`** class. In this case, the constructor is empty, which means that it does not perform any specific operation when creating an instance of the class.

- **`showQuestion(text) { ... }`**: This is a class method called **`showQuestion`**, which is used to display a question in the user interface. It receives a **`text`** argument which is expected to be a text string representing the question to be displayed.

- **`const questionTitle = document.getElementById('questions')`**: Declares a constant **`questionTitle`** and initializes it with the HTML element that has the ID "questions". This code assumes that there is an HTML element in the document with the ID "questions".

- Now we import the UI from app.js.

- We set it up, from `new UI` although for now it does not receive parameters, no constructor.

- Then we use the **`iu`** instance of the **`UI`** class to display the current question in the user interface. It gets the question text from the **`quiz`** instance of the **`Quiz`** class using the **`getQuestionIndex()`** method, and then calls the **`showQuestion()`** method of the **`iu`** instance to display the question text in the user interface.

- We go back to IU.js and place `questionTitle.innerText = text;` we set us text content of the HTML element by **`questionTitle`** with the value of **`text`**, which results in updating the text and showing us the question.

- Now we are going to show the choices so we create a function called `showChoices(choices){``
    
    `}`
    
- We go to the html and delete the buttons, since we are going to do them manually.

- We do the same thing that was done with the question, this code looks for and gets a reference to the HTML element with the ID "choices" and assigns it to the constant **`choicesContainer`**. Subsequently, you can use the **`choicesContainer`** constant to perform operations with the HTML element, such as adding answer choices and/or modifying its content.

- We insert iu in app.js, with the `showChoices` method and we send it as argument an array

- Now in UI.js, instead of showing the element that is being selected, we are going to go through the string array and make a button. For that we will do a for.

- To style the buttons, we place a property called `button.className = "button"`.

- Now we return again to app.js and we install iu in app.js, with the `showChoices` method and we send as argument an array choices.

- We pass to UI.js and where we put in the `button.innerText = choices[i];` to tell it to go through all the choices.

- Then we need the user to select and execute something and for this we go to the button and we put `button.addEventListener('click', () => console.log('clicked'))` so that now it is clickable, but that's not all, now we must give a function to each button.

- Then we go back to app.js to tell it that we want each button to do something different and for that we tell it the function that we want it to execute `showChoices(choices, callback)` and we modify the line mentioned in the previous point like this: `button.addEventListener('click', () => callback())`.