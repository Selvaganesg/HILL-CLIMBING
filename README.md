<h1>ExpNo 5 : Implement Simple Hill Climbing Algorithm</h1> 
<h3>Name: SELVAGANESH B </h3>
<h3>Register Number: 212224230258 </h3>
<H3>Aim:</H3>
<p>Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration </p>
<h2> Theory: </h2>
<p>Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space.
Feedback is provided in terms of heuristic function
</p>


<h2>Algorithm:</h2>
<p>
<ol>
 <li> Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.</li> 
<li>Loop until a solution is found or there are no new operators left to be applied in current state:
<ul><li>Select an operator that has not yet been applied to the current state and apply it to produce a new state</li>
<li>Evaluate the new state:
  <ul>
<li>if it is a goal state, then return it and quit</li>
<li>if it is not a goal state but better than current state then make new state as current state</li>
<li>if it is not better than current state then continue in the loop</li>
    </ul>
</li>
</ul>
</li>
</ol>

</p>
<hr>
<h3> Steps Applied:</h3>
<h3>Step-1</h3>
<p> Generate Random String of the length equal to the given String</p>
<h3>Step-2</h3>
<p>Mutate the randomized string each character at a time</p>
<h3>Step-3</h3>
<p> Evaluate the fitness function or Heuristic Function</p>
<h3>Step-4:</h3>
<p> Lopp Step -2 and Step-3  until we achieve the score to be Zero to achieve Global Minima.</p>

## Program
```python
import random
import string
def generate_random_solution(answer):
    solution=[random.choice(string.printable) for _ in range(len(answer))]
    return solution
def evaluate(solution,answer):
    target=list(answer)
    diff=0
    for i in range(len(target)):
        s=solution[i]
        t=target[i]
        diff +=abs(ord(t)-ord(s))
    return diff
def mutate(solution):
    ind=random.randint(0,len(solution)-1)
    solution[ind]=random.choice(string.printable)
    return solution
    
def simplehillclimbing():
    answer=input()
    solution=generate_random_solution(answer)
    score=evaluate(solution,answer)
    while True:
        print("Score:{} {}".format(score,''.join(solution)))
        if score==0:
            break
        new_solution=mutate(list(solution))
        new_score=evaluate(new_solution,answer)
        if new_score<score:
            score=new_score
            solution=new_solution
simplehillclimbing()
    

```
<hr>
<h2>Sample Input and Output</h2>
<h2>Sample String:</h2> Siddarth A S
<h2>Output:</h2>

<img width="1490" height="758" alt="Screenshot 2026-05-16 084151" src="https://github.com/user-attachments/assets/9115ee32-1620-407a-8191-814f0067dc67" />


Score: 643  Solution :  8RzF:oG ]%;CPORRMe!zGvk<br>
Score: 609  Solution :  8RzF:oG ]%;CPqRRMe!zGvk<br>
Score: 604  Solution :  8RzF:oG ]%;CPqRRMe!zGqk<br>
Score: 594  Solution :  8RzF:oG ]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
Score: 551  Solution :  8RzF:oGK]%;CPqRRWe!zGqk<br>
....................................................<br>
..................................................<br>
................................................<br>
Score: 1  Solution : Siddbrth A S<br>
Score: 1  Solution :  Siddbrth A S<br>
Score: 1  Solution :  Siddbrth A S<br>
Score: 1  Solution :  Siddbrth A S<br>
Score: 0  Solution :  Siddarth A S<br>

## Result

Thus, the Simple Hill Climb Algorithm Implemented successfully.
