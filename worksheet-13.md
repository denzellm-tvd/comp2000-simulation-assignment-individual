# COMP2000 Worksheet 2 — Final Submission

**Student name:** Denzell Muliana

**GitHub repo URL:** [https://github.com/denzellm-tvd/comp2000-simulation-assignment-thing-team](https://github.com/denzellm-tvd/comp2000-simulation-assignment-thing-team)

---

## 1. Design Patterns

Don't forget to submit a pdf file which shows a diagram of your pattern implemenation to supplement this text description.

**1.1.** Which design pattern(s) did you implement? Name them and state where each appears in your codebase. <br>
A design pattern that was implemented in the Ant Colony Simulation is a behavioural pattern known as Strategy. This can be seen in the Ant class that holds a MoveStrategy that determines where an individual ant goes, depending on its type (Scout, Forager, Soldier), and implements a concrete strategy like `random(ant, world)`, `followFoodTrail(ant, world)`, `goHome(ant, world)`, and `nearestFood()`.

**1.2.** For each pattern, paste a code snippet showing the key interaction between participants. <br>
```
// Ant.java
public void update() {
        if (returningHome) {
            Movement.goHome(this, world);
            if (distanceTo(world.getNest().getX(), world.getNest().getY()) < 10) {
                returnFoodToNest();
            }
            return;
        }
        strategy.chooseAndMove(this, world);
    }
```


**1.3.** For each pattern, explain why you chose it over an alternative. What trade-off did you make? <br>





---

## 2. Streams / Lambdas / Parallelism

**2.1.** List every file in your project that uses lambda expressions or the Streams API. <br>





**2.2.** For the most sophisticated use, paste the code and explain: what does it do, and why was a stream/lambda better than a loop? <br>





**2.3.** Did you use parallel streams, custom collectors, or the Fork/Join framework? If yes, how did you ensure thread safety? If no, where could parallelism be introduced? <br>





---

## 3. Uniqueness and Creativity

**3.1.** What did you add to your simulation that went beyond the in-class activities? Describe the feature and what inspired it. <br>
N/A




**3.2.** Paste a code snippet or describe a design decision that demonstrates emergent behaviour, non-trivial complexity, or a genuinely surprising outcome. <br>





**3.3.** If you had another 6 weeks, what would you add or change? <br>
I am unsure of what I would add or change if I had another 6 weeks, but assuming I would be more knowledgable about everything than I am I would likely do a complete overhaul of the assignment from the ground up, so in short I would change everything. I am unsatisfied with the end result of the project, and how often bugs and problems would appear in the code throughout the semester that would lead to it breaking and unable to even compile let alone run. It was frustrating, and I am even more frustrated at how everything looks and runs after all those issues were eventually fixed.

---

## 4. Log Book and Final Reflection

**4.1.** Attach or link your log book entries for Weeks 7–13. <br>
[https://docs.google.com/document/d/16jLZRBHE6x8DS-6E5wCxqDy3OaU6kCU0HIckpNlaMKc/edit?tab=t.giizokw7ramh](https://docs.google.com/document/d/16jLZRBHE6x8DS-6E5wCxqDy3OaU6kCU0HIckpNlaMKc/edit?tab=t.giizokw7ramh)




**4.2.** Reflect on the semester:

- What was the most important concept you learned? <br>
  N/A

- What design trade-off did you face, and how did you resolve it? <br>
  N/A

- If you started over, what would you do differently? <br>
  If I started over, I would do everything differently, starting with taking my first seat at a completely different table and hope the people sitting at the same table make for a better team, or at the very least, that teams would be assigned randomly instead of it being based on where everyone is seated. I never liked the hand I was dealt with, I did not like the team I was assigned. It was frustrating, exhausting and mentally taxing having to navigate this situation in the beginning with everyone being just as introverted, quiet and socially inept as me alongside their flagrant use of AI and how equally little they knew about everything as me alongside just how inferior and embarrassing I felt being here compared to the other groups, and it made me dislike this class and semester to the point that I briefly considered withdrawing from the unit, however instead I decided to just give up trying to act as the "de facto team leader" and forgo working with them, let alone show up to class. Nothing personal, I just do not like working in groups.

- What feedback from the Week 7 submission did you act on? <br>
  I do not believe I received any feedback from the Week 7 submission and so didn't act on anything.
