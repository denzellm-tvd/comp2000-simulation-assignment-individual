# COMP2000 Worksheet 1 — Mid-Semester Submission

**Student name:** Denzell Muliana

**Student ID:** 48412953

**GitHub repo URL:** https://github.com/denzellm-tvd/comp2000-simulation-assignment-thing-team

---

## 1. Version Control

**1.1.** Paste the first 10 lines of the output of `git log --graph --oneline --all` from your repository:

```
* c03524c (HEAD -> main, origin/main, origin/HEAD) Made minor changes to the simulation
* d099d57 feat: update simulation
* a5d325e chore: add gitignore
* ab1f6de feat: update Main
* 3902277 Delete Main.java
* 43ad144 Delete MapObject.java
* 3528dd6 Delete Nest.java
* f4ae74d Delete Map.java
* f80299e Delete Food.java
* 458e7f0 Delete Cell.java
```

### 1.2. Describe your workflow. Did you use branches? Pull requests? <br>
I did not use branches or pull requests. My team members held a meeting where they discussed the assignment, what to do, and how to start. From there, they designed a rough UML diagram of the objects and classes to design in the simulation before getting to work, coding everything to match their diagram. I looked at the code they made, ran some tests to see how it functioned, then noted in my head certain things that I noticed and wanted to change before making those changes and running further tests. Once I was satisfied with the changes, I finally committed and pushed to the repository.

### 1.3. Estimate the percentage of commits you contributed relative to the total in your repository. <br>
2.6%. As of writing this, there are 38 commits in my team repository, and although I only contributed 1 commit, that is because I waited until I was done making all the changes I wanted to make before finally committing. I know that the optimal thing to do would be to commit and push as often as possible rather than at the last minute to prevent anything going wrong that would make me lose all my work, however I was frankly having fun watching the simulation run and making changes here and there which led to me forgetting to commit until I was done making all the changes.

---

## 2. Program Design

Don't forget to submit a pdf file of your program design along with this file.

**2.1.** List every class in your project and write 1–2 sentences describing its responsibility.
1. World <br>
The World class is a crucial class that sets up the map and initiates the ant colony, placing a nest in a random spot on the grid and setting up an ArrayList to track food sources. Alongside this, the World class is also responsible for updating the colony each frame and creating methods to allow other scripts to get objects such as the map, the colony, and the list of food sources on the map.
2. Map <br>
The Map class creates the grid when the simulation initiates alongside tracking each individual cell in said grid through methods such as getNeighbours() and getCell(). It also houses a method that allows cells with pheromone values above 0 to decay over time, ensuring that it does not last forever.
3. FoodSource <br>
The FoodSource subclass creates and tracks food sources that are scattered around the map that the ants will forage to and collect. It houses methods that allow the ants to take food if it is available (that is, its amount value is above 0) alongside methods that allow other scripts to track each individual source's food amount and the percentage remaining.
4. Colony <br>
The Colony class is arguably one of the most important in the simulation as it is directly responsible for controlling what each and every ant does, including movement and food collection.
5. Cell <br>
The Cell class is responsible for tracking each individual cell's pheromone values alongside housing methods to add or remove pheromones.
6. Nest <br>
The Nest subclass serves as the ant colony's home base. It is responsible for tracking the food stored within it alongside managing interactions between ants and itself.
7. MapObject <br>
The MapObject class is responsible for tracking the positions of each cell on the map and setting the position of objects when created.
8. Ant <br>
The Ant class houses all the variables and methods that allow each ant to function properly in the simulation. This includes tracking its position, movement, and picking up and dropping food.
9. Scout <br>
The Scout subclass is responsible for one of the two types of ants in the simulation. It serves to override the ant's movement function, slightly modifying it such that it will not be affected by the pheromone trails it leaves behind.
10. Forager <br>
The Forager subclass is responsible for one of the two types of ants in the simulation. It serves to override the ant's movement function, slightly modifying it such that it will prioritise moving towards cells with pheromones than those without.
11. Main <br>
Main is responsible for starting up the simulation and getting everything set up. It creates a world, creates food sources and scatters them in random cells, creates ants, and sets up the application's JFrame.
12. SimulationPanel <br>
This subclass is responsible for the application interface and its aesthetics. It allows objects such as food sources to be visible on the map with different colours to differentiate them from each other alongside showing basic stats such as the amount of food stored in the nest and the total amount of ants on the map.

 <br>
 
**2.2.** Identify any inheritance relationships. For each parent–child pair, list what the child inherits and what it overrides.
1. MapObject-FoodSource <br>
The child (FoodSource) inherits the getPosition() method and the primary MapObject constructor that sets its position on the map. It overrides the interact() method.
2. Ant-Scout <br>
The child (Scout) inherits all properties and methods of the Ant class including the primary Ant constructor that sets its position and whether it is carrying food or not. It overrides the abstract method chooseNextCell().
3. Ant-Forager <br>
The child (Forager) inherits all properties and methods of the Ant class including the primary Ant constructor that sets its position and whether it is carrying food or not. It overrides the abstract method chooseNextCell().
4. MapObject-Nest <br>
The child (Nest) inherits the getPosition() method and the primary MapObject constructor that sets its position on the map. It overrides the interact() method.
5. JPanel-SimulationPanel <br>
The child (SimulationPanel) inherits all properties and methods of the generic lightweight container JPanel. It overrides the paintComponent() method.

<br>


**2.3.** Pick the class that you think has the best design. Explain why. <br>
The class that I think has the best design is Map. I believe this is the case because it showcases some of the hallmarks of good class design such as encapsulation in the form of private fields like width, height and cells, it serves mostly one function which is to track individual cells and their positions, and it is immutable. Additionally, I believe everything within the Map class is readable and aesthetically pleasing in that sense as I believe it to be organised, simple, and easy to read.

<br>


**2.4.** Paste one code snippet that demonstrates your use of polymorphism or encapsulation.  Include an explanation of _how_ this demonstrates polymorphim or encapsulation.  Give a reference to a provided reading that talks about this type of polymorphism or encapsulation. <br>





---

## 3. Generics and Exceptions

**3.1.** List every place your code uses generics (e.g. `ArrayList<Actor>`, `Optional<Cell>`, `HashMap<String, Team>`). If you deliberately used none, explain why.





**3.2.** List every place your code handles exceptions (try/catch, throws, custom exception classes). What error is each protecting against?





**3.3.** Paste a code snippet showing either a generic class/method or a try/catch block.





---

## 4. Log Book

**4.1.** Attach or link your log book entries for Weeks 1–6.





**4.2.** Which week's activity taught you the most? What did you learn?

---

## 5. Uniqueness and Creativity

**5.1.** List everything you added to the project that was not part of the in-class activities.

**5.2.** Which feature required the most independent research or problem-solving? What did you learn from it?

**5.3.** Paste one code snippet that you are especially proud of. Explain why it goes beyond what was done in class.
