# <img src="https://cloud.githubusercontent.com/assets/7833470/10423298/ea833a68-7079-11e5-84f8-0a925ab96893.png" width="60"> Project 0 Feedback

Overall, excellent, excellent project. You're really flying! I've included some possible directions for thought and improvement at the end here. Look into refactoring and optimizing readability. This isn't currently a problem, but it's something that programmers are always thinking about. It's impressive that you're at the place where you can start working on this now!

* **Technical Requirements**: Did you deliver a project that met all the technical requirements?

*Exceeds expectations*: Great work! You went far above and beyond the project requirements here and made an excellent project. Your game is fun and entertaining and feels like a unified whole. You have edge detection, enemies, score counter, color selection, and player name choice. These are all great features that add to the experience.

* **Creativity**: Did you add a personal spin or creative element to your project? Did you deliver something of value to the end user?

*Exceeds expectations*: You picked the arcade theme and made the whole project fit within that theme. Great styling and feel. All of the features mentioned in the section above apply here too. Excellent creativity.

* **Code Quality**: Did you follow code style guidance and best practices covered in class, such as spacing, modularity, and semantic naming? Did you comment your code?

There's a lot of code here, so I can't dive into all of it. Clearly, this project is complex and takes a lot of processing at each step, and I don't want you to think that I haven't taken that into account. That being said, I think that your direction for improvement is breaking down functionality even further. I'm going to pick out the `moveOnBoard()` function as a place for possible improvement. You have two `if`s in a row that could be combined into one with an `&&`. I could imagine you breaking this down further and having `moveUp()`, `moveDown()`, `moveLeft()`, and `moveRight()` functions:

```javascript
function moveOnBoard(){
  if(/* up keypress && up direction is open */){
    moveUp(/* necessary arguments to move the right piece */);
  }else if (/* down keypress && down direction is open */) {
    moveDown(/* necessary arguments to move the right piece */);
  }
  //...
}

```

You might even be able to optimize further and create a `move()` function that would take in a direction as its first argument and behave properly:

```javascript
function moveOnBoard(){
  if(/* up keypress && up direction is open */){
    move('up', /* necessary arguments to move the right piece */);
  }else if (/* down keypress && down direction is open */) {
    move('down', /* necessary arguments to move the right piece */);
  }
  //...
}

```

You might also be able to refactor the `checkDown()`, `checkUp()`, `checkLeft()`, and `checkRight()` family of functions similarly into a `check()` function. E.g. `check('down', /* other args */);`.

I also think that the ```this.orientationOptions``` actually makes the code harder to read.

```javascript
if(this.orientation === 'up'){
  // Respond to up orientation
}
```
Is slightly easier to read than:

```javascript
if(this.orientation === this.orientationOptions[0]){
  // Respond to up orientation
}
```


These are minor refactors, but you could continue refactoring down this path for a long time. Breaking down large functions into smaller ones helps make your code easy to read (for yourself in the future and for anybody else who comes along to look at your code). Aim to make your code as readable and clear as possible. The strongest coders pride themselves on the readability of their code. They state that they don't need to comment their code because their naming and structure is good enough to state exactly what's going on.
