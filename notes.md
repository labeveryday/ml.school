# Machine Learning School

cohort 14

**Website:** https://www.ml.school/program

**Setup:** https://www.ml.school/program/setup

**Building Machine Learning Systems That Don’t Suck ebook**: https://s3.amazonaws.com/www.ml.school/archive/program-notes-130143f9a13e7f25467f8de94b01872b6439.pdf

**Cohort Outline:** https://cohort.ml.school/cohort.html

**Building Machine Learning Systems That Don't Suck Code Walk-Throughs:** https://www.ml.school/program#code-walkthroughs

**What is Amazon SageMaker:** https://docs.aws.amazon.com/sagemaker/latest/dg/whatis.html

**Amazon SageMaker Python SDK:** https://sagemaker.readthedocs.io/en/stable/


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

## Day - 2: Better Data

**Better data **is crucial for building better models. The biggest impact on the quality of a model comes from the quality of the features of the features we use to train it. 

![[Screenshot 2024-07-04 at 4.04.26 AM.png]]

![[Screenshot 2024-07-04 at 4.10.22 AM.png]]

There are multiple ways to do vectorization. 
- label encoding
- one-hot encoding
- target encoding

![[Screenshot 2024-07-04 at 4.11.15 AM.png]]>NOTE: The challenge of neural networks is that they are capable of using the numbers to get patterns even when we don't want them to. 

![[Screenshot 2024-07-04 at 4.16.16 AM.png]]

>NOTE: The challenge of this is the course of dimensionality. Meaning more features more columns we will need exponentially more samples to get a model to do what we want it to do well. YOU NEED to been careful with using this. 

![[Screenshot 2024-07-04 at 4.23.55 AM.png]]

>NOTE: The challenge with this is you can overfitting. Overfitting is **an undesirable machine learning behavior that occurs when the machine learning model gives accurate predictions for training data but not for new data**.

![[Screenshot 2024-07-04 at 4.35.54 AM.png]]

When working with data the first thing you will need to do is vectorization. The next step is normalization and standardization.

![[Screenshot 2024-07-04 at 4.38.33 AM.png]]

![[Screenshot 2024-07-04 at 4.39.46 AM.png]]


When dealing with the outliers you build a new layer to deal with outliers. 

![[Screenshot 2024-07-04 at 4.49.43 AM.png]]

>NOTE: Models do not like working with features that do not have values. 

![[Screenshot 2024-07-04 at 4.50.53 AM.png]]


![[Screenshot 2024-07-04 at 4.52.57 AM.png]]



![[Screenshot 2024-07-04 at 4.56.06 AM.png]]

>NOTE: Before you remove missing values you need to understand why the values are missing. In the example above you can understand that there maybe an issue in the warehouse.


![[Screenshot 2024-07-04 at 4.57.52 AM.png]]
![[Screenshot 2024-07-04 at 4.58.15 AM.png]]

>NOTE: Binning is when you build values into different buckets. 

![[Screenshot 2024-07-04 at 5.07.12 AM.png]]
![[Screenshot 2024-07-04 at 5.09.35 AM.png]]


Creating a baseline:
- This is something before you start to building a model. 


![[Screenshot 2024-07-04 at 5.23.09 AM.png]]
![[Screenshot 2024-07-04 at 5.23.56 AM.png]]
![[Screenshot 2024-07-04 at 5.24.27 AM.png]]

==This Titanic example is the hello world of machine leanring.

![[Screenshot 2024-07-04 at 5.25.21 AM.png]]


![[Screenshot 2024-07-04 at 5.26.30 AM.png]]


![[Screenshot 2024-07-04 at 5.28.09 AM.png]]


![[Screenshot 2024-07-04 at 5.31.49 AM.png]]
![[Screenshot 2024-07-04 at 5.32.05 AM.png]]

![[Screenshot 2024-07-04 at 5.36.55 AM.png]]

>NOTE: Please do not go for the state of the art model. 

![[Screenshot 2024-07-04 at 5.38.00 AM.png]]

==You must earn the right to introduce complexity. ==

![[Screenshot 2024-07-04 at 5.38.36 AM.png]]

**Considerations when starting a project:**
1. Is this model capable of solving my problem.
2. Hardware, time and costs: You may need models that are fast and do not require a lot of hardware. 
3. How good does the model scale?
4. Interpretability and explainability: This is important is you are dealing with models that work with people. 
5. Team familiarity with the model

![[Screenshot 2024-07-04 at 5.39.49 AM.png]]
![[Screenshot 2024-07-04 at 5.41.13 AM.png]]
![[Screenshot 2024-07-04 at 5.42.07 AM.png]]

![[Screenshot 2024-07-04 at 5.43.34 AM.png]]

![[Screenshot 2024-07-04 at 5.45.20 AM.png]]
![[Screenshot 2024-07-04 at 5.46.17 AM.png]]

==Go for the tried and true. Don't go chasing models. ==

After you have your baseline and choose a model now you build a pipeline. Put all of the pieces together. 

![[Screenshot 2024-07-04 at 5.48.41 AM.png]]

![[Screenshot 2024-07-04 at 5.50.12 AM.png]]

![[Screenshot 2024-07-04 at 5.54.03 AM.png]]
>NOTE: The goal of building this model is to generalize and do this by overfitting.  Once you overfit then you regularize. Here is more info: https://aws.amazon.com/what-is/overfitting.

Overfitting is **an undesirable machine learning behavior that occurs when the machine learning model gives accurate predictions for training data but not for new data**

![[Screenshot 2024-07-04 at 6.05.39 AM.png]]
==- Use print statements to debug and troubleshoot.==

![[Screenshot 2024-07-04 at 6.06.06 AM.png]]

![[Screenshot 2024-07-04 at 6.06.39 AM.png]]


![[Screenshot 2024-07-04 at 6.13.28 AM.png]]


![[Screenshot 2024-07-04 at 6.15.44 AM.png]]


![[Screenshot 2024-07-04 at 6.18.56 AM.png]]
![[Screenshot 2024-07-04 at 6.19.41 AM.png]]

![[Screenshot 2024-07-04 at 6.20.19 AM.png]]


Gradients are instructions on how to change the weights. 

- Node can be a GPU but it can be any level
- You can use PyTorch or Tensorflow to implement data parallelism

![[Screenshot 2024-07-04 at 6.22.48 AM.png]]


You use data parallelism when the data is too big. Think GPT-3.

![[Screenshot 2024-07-04 at 6.29.39 AM.png]]

![[Screenshot 2024-07-04 at 6.31.23 AM.png]]
![[Screenshot 2024-07-04 at 6.31.35 AM.png]]

![[Screenshot 2024-07-04 at 6.32.00 AM.png]]


## Day 3: Model Evaluation



![[Screenshot 2024-07-08 at 4.03.11 AM.png]]
![[Screenshot 2024-07-08 at 4.04.01 AM.png]]

![[Screenshot 2024-07-08 at 4.04.38 AM.png]]


![[Screenshot 2024-07-08 at 4.07.45 AM.png]]

![[Screenshot 2024-07-08 at 4.09.05 AM.png]]

![[Screenshot 2024-07-08 at 4.09.45 AM.png]]


![[Screenshot 2024-07-08 at 4.14.07 AM.png]]
The solution to this is to use:
![[Screenshot 2024-07-08 at 4.15.31 AM.png]]

![[Screenshot 2024-07-08 at 4.16.08 AM.png]]


>NOTE: The challenge with this that you end up having 5 different models. How do you select which model to use?

![[Screenshot 2024-07-08 at 4.19.25 AM.png]]

>NOTE: To fix this you train a 6th model with all of the data and then you deploy it. Another option is to deploy all 5 models and average the prediction. Another thing to note is that it makes sense not to deploy the model with the highest score and the lowest score.

**What is the reason of deploying number 2 over number 1?**

The advantage of number 2 is that you don't have to train another model. 

![[Screenshot 2024-07-08 at 4.31.18 AM.png]]

![[Screenshot 2024-07-08 at 4.37.41 AM.png]]

![[Screenshot 2024-07-08 at 4.38.55 AM.png]]


>The problem here is that you have multiple images coming from the same patients. This means that the model can learn relationships between x-ray images that are in correct. The way to fix this is to make sure all of the images from the same patient are in the train set or the test set. But never in both. 

![[Screenshot 2024-07-08 at 4.47.02 AM.png]]

==Look for papers that discuss how many different ways you can make this mistake. ==

![[Screenshot 2024-07-08 at 4.49.37 AM.png]]

![[Screenshot 2024-07-08 at 4.52.54 AM.png]]


![[Screenshot 2024-07-08 at 4.53.38 AM.png]]

![[Screenshot 2024-07-08 at 4.54.26 AM.png]]

![[Screenshot 2024-07-08 at 4.55.12 AM.png]]

![[Screenshot 2024-07-08 at 4.56.23 AM.png]]

![[Screenshot 2024-07-08 at 4.57.17 AM.png]]


![[Screenshot 2024-07-08 at 5.06.04 AM.png]]

>NOTE: In this example the zip should have no barrying on the loan being approved. Another issue is the income being $0 but in the zipcode of `33510` the loan should not be approved. 


![[Screenshot 2024-07-08 at 5.18.22 AM.png]]

![[Screenshot 2024-07-08 at 5.19.34 AM.png]]

![[Screenshot 2024-07-08 at 5.23.18 AM.png]]

![[Screenshot 2024-07-08 at 5.25.18 AM.png]]

![[Screenshot 2024-07-08 at 5.25.31 AM.png]]
Simpon's Paradox: https://youtu.be/ebEkn-BiW5k?si=37Vcfy713hxzzgww

![[Screenshot 2024-07-08 at 5.26.41 AM.png]]


![[Screenshot 2024-07-08 at 5.26.58 AM.png]]

![[Screenshot 2024-07-08 at 5.29.55 AM.png]]

![[Screenshot 2024-07-08 at 5.30.53 AM.png]]

>NOTE: As time goes on the world will change. When sampling randomly you are showing the model events that happen in the future. Using this you can be sure you are testing on current data and always testing with future data.

![[Screenshot 2024-07-08 at 5.34.00 AM.png]]

![[Screenshot 2024-07-08 at 5.34.57 AM.png]]

![[Screenshot 2024-07-08 at 5.35.21 AM.png]]

**How do you determine the biggest problem with your model is?**

![[Screenshot 2024-07-08 at 5.38.39 AM.png]]
![[Screenshot 2024-07-08 at 5.39.13 AM.png]]


![[Screenshot 2024-07-08 at 5.41.23 AM.png]]


![[Screenshot 2024-07-08 at 5.43.29 AM.png]]

![[Screenshot 2024-07-08 at 5.44.13 AM.png]]


>NOTE: Establish baselines you measure against those baseline to find the biggest gap to determine where you need to improve your model. 

![[Screenshot 2024-07-08 at 5.53.33 AM.png]]

**Things you want to identify:**
- Spam (Good email)
- Terrorist
- Fraud Credit card transactions

![[Screenshot 2024-07-08 at 5.55.15 AM.png]]

>NOTE: The challenge with undersampling you get rid of samples that may be important. With Oversampling you are making things up. You need to avoid class imbalancing. 

![[Screenshot 2024-07-08 at 5.57.11 AM.png]]

![[Screenshot 2024-07-08 at 5.58.55 AM.png]]

![[Screenshot 2024-07-08 at 5.59.57 AM.png]]

![[Screenshot 2024-07-08 at 6.02.50 AM.png]]
![[Screenshot 2024-07-08 at 6.04.41 AM.png]]
![[Screenshot 2024-07-08 at 6.08.56 AM.png]]


>In this situation you don't use integers you use floats because the image is 80% cat and 20% dog and now your model is even better. https://keras.io/examples/vision/mixup/



## Day - 5: 

![[Screenshot 2024-07-11 at 4.03.21 AM.png]]
![[Screenshot 2024-07-11 at 4.04.07 AM.png]]

Having the data and source code is what makes a model open source.

![[Screenshot 2024-07-11 at 4.06.12 AM.png]]

![[Screenshot 2024-07-11 at 4.06.38 AM.png]]



![[Screenshot 2024-07-11 at 4.08.27 AM.png]]
![[Screenshot 2024-07-11 at 4.08.47 AM.png]]


![[Screenshot 2024-07-11 at 4.10.59 AM.png]]
![[Screenshot 2024-07-11 at 4.19.59 AM.png]]

Questions you should ask:
- How good should my predictions be?
- How fast should my predictions be?
- And is cost a factor?

>The right decision too late is the wrong decision. The wrong decision is still the wrong decision.

![[Screenshot 2024-07-11 at 4.24.43 AM.png]]

![[Screenshot 2024-07-11 at 4.25.54 AM.png]]
![[Screenshot 2024-07-11 at 4.26.36 AM.png]]

![[Screenshot 2024-07-11 at 4.27.09 AM.png]]

![[Screenshot 2024-07-11 at 4.28.11 AM.png]]

![[Screenshot 2024-07-11 at 4.30.48 AM.png]]

![[Screenshot 2024-07-11 at 4.35.35 AM.png]]

![[Screenshot 2024-07-11 at 4.41.40 AM.png]]

![[Screenshot 2024-07-11 at 4.43.40 AM.png]]
![[Screenshot 2024-07-11 at 4.43.53 AM.png]]

![[Screenshot 2024-07-11 at 4.46.55 AM.png]]
![[Screenshot 2024-07-11 at 4.49.23 AM.png]]

![[Screenshot 2024-07-11 at 4.53.08 AM.png]]

![[Screenshot 2024-07-11 at 4.54.45 AM.png]]

**Two-phase predictions:**
![[Screenshot 2024-07-11 at 4.55.14 AM.png]]
![[Screenshot 2024-07-11 at 4.55.42 AM.png]]

![[Screenshot 2024-07-11 at 4.58.42 AM.png]]


![[Screenshot 2024-07-11 at 5.01.36 AM.png]]

- Keep it simple
- Break things down into smaller moduals.

Inference pipeline: A set of models working together to make a prediction.

![[Screenshot 2024-07-11 at 5.03.19 AM.png]]

![[Screenshot 2024-07-11 at 5.06.17 AM.png]]

>NOTE: You measure the success of a recommendation system by watch time. The longer someone stays on a recommendation the better the recommendation system is. Unfortunately this is a delayed metric since it is dependant on user feedback. 


![[Screenshot 2024-07-11 at 5.09.13 AM.png]]

![[Screenshot 2024-07-11 at 5.13.37 AM.png]]

![[Screenshot 2024-07-11 at 5.30.32 AM.png]]


![[Screenshot 2024-07-11 at 5.33.37 AM.png]]


![[Screenshot 2024-07-11 at 5.35.28 AM.png]]
![[Screenshot 2024-07-11 at 5.36.37 AM.png]]

![[Screenshot 2024-07-11 at 5.44.24 AM.png]]

![[Screenshot 2024-07-11 at 5.44.42 AM.png]]



![[Screenshot 2024-07-11 at 6.00.25 AM.png]]

![[Screenshot 2024-07-11 at 6.00.48 AM.png]]

![[Screenshot 2024-07-11 at 6.04.15 AM.png]]
![[Screenshot 2024-07-11 at 6.04.56 AM.png]]
![[Screenshot 2024-07-11 at 6.05.08 AM.png]]


![[Screenshot 2024-07-11 at 6.08.50 AM.png]]

![[Screenshot 2024-07-11 at 6.09.59 AM.png]]


## Day 6

![[Screenshot 2024-07-15 at 4.14.16 AM.png]]


![[Screenshot 2024-07-15 at 4.15.32 AM.png]]

![[Screenshot 2024-07-15 at 4.16.57 AM.png]]

![[Screenshot 2024-07-15 at 4.25.47 AM.png]]


![[Screenshot 2024-07-15 at 4.28.16 AM.png]]

![[Screenshot 2024-07-15 at 4.31.39 AM.png]]

![[Screenshot 2024-07-15 at 4.32.14 AM.png]]


![[Screenshot 2024-07-15 at 4.42.01 AM.png]]
![[Screenshot 2024-07-15 at 4.45.48 AM.png]]
![[Screenshot 2024-07-15 at 4.47.14 AM.png]]

![[Screenshot 2024-07-15 at 4.48.01 AM.png]]


![[Screenshot 2024-07-15 at 5.00.47 AM.png]]
![[Screenshot 2024-07-15 at 5.01.31 AM.png]]


![[Screenshot 2024-07-15 at 5.02.13 AM.png]]






#### Resources

Lora: https://www.entrypointai.com/blog/lora-fine-tuning/

Overfitting: https://aws.amazon.com/what-is/overfitting

CleanLab: https://github.com/cleanlab/cleanlab

To SMOTE or not to SMOTE: https://arxiv.org/abs/2201.08528

MixUp augmentation for image classification: https://keras.io/examples/vision/mixup/

List of Open LLMs: https://github.com/eugeneyan/open-llms






