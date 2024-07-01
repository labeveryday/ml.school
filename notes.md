# Machine Learning School

cohort 14

Website: https://www.ml.school/program

Setup: https://www.ml.school/program/setup

Building Machine Learning Systems That Don't Suck: https://www.ml.school/program#code-walkthroughs

> The first principle is that you must not fool yourself, and you are the easiest person to fool into solving the wrong problem or trying to solve the right problem using the wrong solution.


Become really good at Sagemaker and forget everything else. 

## Day 1

Start every project by drawing a treasure map. Focus on the main landmarks. Forget about the details. Iterate and ask questions until the direction is clear.

**Questions to ask?**

1. What problem are you solving?

2. What problems are you ignoring?
Difference between a mediocre solution and an exceptional one are the problems you avoid.

3. Who is your customer and why do they care?
Avoid the telephone game. Cut the middleman. Identify who cares and why this is important to them.

4. What do existing solutions look like?
Learn from past pitfalls and best practices.

5. How do you measure success?
You can't solve a problem without a benchmark to assess progress and guide future improvements.


>You win by framing problems in a way that makes it impossible not to build solutions that fail. 

==Example solution - Determine how many people enter Disney without paying:==
![[Screenshot 2024-07-01 at 4.34.17 AM.png]]

>The haystack principle is a powerful mental model. Instead of trying to find the needle in a haystack, make the haystack as small as you possibly can. 

**Frame the problem correctly!**

- Never start a project with machine learning. Do the simplest thing that could possibly work. Make it work first. Make it better later. 
- Simple ideas are better than clever ideas. Machine learning is clever and powerful, but is not free. A better alternative is to start using simple heuristics (simple rules).
- In most situations, if you don't know how to build a good application using a manual approach, machine learning after that. 

![[Screenshot 2024-07-01 at 4.47.11 AM.png]]
*Use this chart of a on-boarding workflow*

>Start by doing things that don't scale. Start by identifying opportunities to become the software instead of having to build software.


![[Screenshot 2024-07-01 at 4.55.48 AM.png]]


>Before you build the product make it work. What can you do before machine learning. Sell it first. 

There are no datasets in the real world. A working solution is the best way to collect real production data from the users of the system.

*In real life data is messy and its all over the place.*

Good datasets need quality, diversity, and quantity. More data is not always better - and its often worse. Better data is better than more data. 

How do you know if you need more data?
- If the cross validation score of model is improving steadily with more data, keep feeding it more. Else stop

![[Screenshot 2024-07-01 at 5.04.05 AM.png]]

*On the left the model continues to increase with more data*

Selection bias is inevitable. It makes training and production data different. 

A few common causes of selection bias are time, the location where collected data, demographics bias, response bias, and availability bias. 

Collect metadata that helps explain your data. This information will become critical to evaluate your model and counter the effects of selection bias. 

![[Screenshot 2024-07-01 at 5.21.32 AM.png]]

>Models need ground truth labels to learn. Human annotations consist of subject matter experts providing labels for each sample in a dataset. Labeling is one of the most fundamental things you can do to improve your models. 

Some problems have built-in, natural labels. In these problems, we can automatically evaluate the model's predictions without needing manual labels.

![[Screenshot 2024-07-01 at 5.26.10 AM.png]]

![[Screenshot 2024-07-01 at 5.27.04 AM.png]]
![[Screenshot 2024-07-01 at 5.29.43 AM.png]]

Weak supervision can help us scale labeling. The process generates labels automatically by using high-level and often noisier sources of supervision. (https://snorkel.ai/)

![[Screenshot 2024-07-01 at 5.32.36 AM.png]]


![[Screenshot 2024-07-01 at 5.34.59 AM.png]]

![[Screenshot 2024-07-01 at 5.37.50 AM.png]]![[Screenshot 2024-07-01 at 5.40.57 AM.png]]

![[Screenshot 2024-07-01 at 5.41.52 AM.png]]

![[Screenshot 2024-07-01 at 5.45.05 AM.png]]

![[Screenshot 2024-07-01 at 5.45.18 AM.png]]![[Screenshot 2024-07-01 at 5.46.13 AM.png]]

![[Screenshot 2024-07-01 at 5.49.05 AM.png]]
### Questions at the end

- Office hours has no agendas. Bring questions
	- Talk about LLMs
	- Freelancing
	- Talk about content creation
	- How to leave the corporate world.
- Ask coding questions in discord
- Docker is important for applications you build.
	- It is used in the code walk throughs
- What is the next step?
	- Try to apply what we discussed today into your life. 
- Homework: 
	- Session 1: https://www.ml.school/program/code?session=1
	- Additional Trainings:
		- Kaggle Tutorials: https://www.kaggle.com/learn
		- Google Crash Course: https://developers.google.com/machine-learning/crash-course
		- Coursera Machine Learning Specialization: https://www.coursera.org/specializations/machine-learning-introduction
	- Books:
		- [Designing Machine Learning Systems: An Iterative Process for Production-Ready Applications](https://amzn.to/43oZcZg) by Chip Huyen.
		- [Human-in-the-Loop Machine Learning: Active learning and annotation for human-centered AI](https://amzn.to/49hkmeM) by Robert (Munro) Monarch.
		- [Introducing MLOps. How to Scale Machine Learning in the Enterprise](https://amzn.to/456tq57) by Mark Treveil and the Dataiku Team.
		- [Machine Learning Design Patterns. Solutions to Common Challenges in Data Preparation, Model Building, and MLOps](https://amzn.to/3s2b9a4) by Valliappa Lakshmanan, Sara Robinson, and Michael Munn.
		- [Machine Learning Engineering with Python](https://amzn.to/3rcrY2b) by Andrew P. McMahon.
- Recommendation is to not time the code with the sessions. 
	- His recommendation is work on the live sessions during the cohort.
	- Its not a 1 for 1

How does Sagemaker stack up to opensource?
- The opensource alternatives are not as popular but they are way better. A developer enjoys working with opensource more. 
- Open source has a bunch of people working on problems. 
- Sagemaker does not have enough support. People report problems and they don't get back to them often.

_____

