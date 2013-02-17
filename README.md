<h1>Section 5 Project 1</h1>

<h2>Overview</h2>

Till now we have created a basic UI and a basic backend. However both are totally disjoint from each other. In this exercise, we will begin to establish a connection between them.

In a real Minesweeper game, the UI class would render the state of it's board. When a user left-clicks a square, the UI would uncover the square. Similarly when a user right-clicks a square the UI would mark it as a mine, and consequently changes the state of the corresponding square object. The UI would perform all these actions by invoking methods on the ```Board``` object. We can see that a ```UI``` object and a ```Board``` object are very closely connected. We can say that a ```UI``` object is composed of a ```Board``` object, because it will (in this project) have a ```Board``` object as an instance attribute.

Take a look at the constructor of the ```UI``` class in this project. You will notice that we have changed the constructor to accept a ```Board``` object, which is then set as an instance attribute in ```UI```. An alternate way of setting the ```board``` attribute in ```UI``` would have been to instantiate ```Board``` in the constructor of ```UI```, instead of accepting it as an argument. However, by allowing clients of ```UI``` to give it a ```Board``` object, we increase the testability of the ```UI``` class. This allows a test case to give ```UI``` a pre-configured board, and then test it's behavior against it. Giving (injecting) objects like this is also known as dependency injection. We will look at [dependency injection](http://stackoverflow.com/questions/130794/what-is-dependency-injection) again in a later activity. For now we simply want to make you aware of this term and show you what it looks like in code.

In this activity, we will take the first baby step in integrating the user interface with the backend board. Since the ```UI``` class has an instance of ```Board```, which is initialized with mines, we will begin by rendering all squares which are mines, with a background color of RED. 

The purpose for this step is to get the UI to identify which squares are mines and to render them in a special way so we know they have been identified properly. This activity is simply a stepping stone to evolve the user interface towards it's real purpose.  

Figure 1 as shown on the next page is what you should see if you have completed the exercise properly. Since mine locations are determined randomly, you may see RED squares in a different location.

![Minesweeper board with mines  marked in red](https://raw.github.com/diycomputerscience/MinesweeperImages/master/images/MinesweeperWithMinesMarkedInRed.jpg)

_**Figure 1**_

<h2>Steps For This Project</h2>

 1. Run AllTests as a unit test and ensure that 27 tests are run, out of which 26 pass, and there is 1 failure - ```testMineIdentificationOnUI()```.
 1. Follow instructions in the ```layoutSquares(...)``` method in ```UI.java``` to implement the logic of setting the background of mines to RED.
 1. Run ```AllTests``` as a unit test and ensure all 27 tests pass.

<h2>Learning Outcomes</h2>

 1. How to set the background color of a component in Java.
 1. How to wire a use case end to end.
 1. How to break a large requirement into small manageable pieces and understand how to solve it in small steps.
