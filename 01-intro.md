# Session 1 - Introduction and Initial Setup


In this session, we'll set up your AWS account and local environment to run the program code. I'll give you a quick introduction to the code to ensure you understand how I organized everything.

[Video Walk through]([https://youtu.be/153BboqWh-U](https://youtu.be/153BboqWh-U))

## Assignments

Complete the following assignments to reinforce the concepts we covered in this coding session. You don't have to work on every assignment. Pick the ones that you think will help you the most.

1. Ensure you can access AWS from your command line using the AWS CLI. For example, you should be able to run a command to list your S3 buckets from a terminal window.
    
2. Create a Python class `Configuration` to encapsulate all the functionality related to determining the correct configuration given the value of `LOCAL_MODE`. The class should have a function `load()` that will automatically set up the proper settings given the value of `LOCAL_MODE.`
    
3. Run the the first three sessions of the notebook using Local Mode (`LOCAL_MODE = True`) and then switch it to run it in SageMaker (`LOCAL_MODE = False`). The goal of this assignment is to ensure everything works correctly.
    
4. Read the article ["Best Practices and Design Patterns for Building Machine Learning Workflows with Amazon SageMaker Pipelines"](https://aws.amazon.com/blogs/machine-learning/best-practices-and-design-patterns-for-building-machine-learning-workflows-with-amazon-sagemaker-pipelines/) to better understand how SageMaker works with the three different session objects: [`Session`](https://aws.amazon.com/blogs/machine-learning/best-practices-and-design-patterns-for-building-machine-learning-workflows-with-amazon-sagemaker-pipelines/), [`PipelineSession`](https://aws.amazon.com/blogs/machine-learning/best-practices-and-design-patterns-for-building-machine-learning-workflows-with-amazon-sagemaker-pipelines/), and [`LocalPipelineSession`](https://aws.amazon.com/blogs/machine-learning/best-practices-and-design-patterns-for-building-machine-learning-workflows-with-amazon-sagemaker-pipelines/).
    
5. You'll find several Python cell and line magics throughout the notebook. Line magics use a single percent sign (`%`) and operate on a line. Cell magics use two percent signs (`%%`) and can operate on multiple lines. Read "Built-in Magic Commands" for an explanation of some of the most popular line and cell magics available.
    

Next session: [Exploratory Data Analysis](https://www.ml.school/program/code?session=2)

Copyright © 2024 Tideily LLC

All rights reserved.