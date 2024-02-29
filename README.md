[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/Y4rZMh1t)
# Junior Seminar (CMPSC 580) Exemplar Project Repository

## Semester: Spring 2024

This repository contains student project materials, including project report, data, code, and references to literature for this departmentally-sponsored project. __As you complete each of the below sections in this document, please be sure to remove the preamble text so that it does not appear in your work.__ Please work with your first reader to answer any questions or concerns that you may have.

## GitHub Handle: MilesF25

## Name: Miles Franck

## Major: SE

## Project Name: Enter The Name Of Your Project

* Here, think of an interesting name of the work that bring a freshness and excitement to the area of this project. Consider using a name that carries some information about what the project and provides some hint at what the project does without being too wordy.


## Link to current progress
https://github.com/AstuteSource/SEERS/tree/main
---

## Overview

TODO (250 words minimum): Discuss the overview of the project using and building on the project description provided by the department. In this section, a concise summary is discussed of the study's key elements, offering the reader a quick understanding of the research's scope and goals. The section continues to outline the main topics, research questions, hypotheses, and /or theories in a clear and meaningful language to provide a type of roadmap for the reader to navigate the forthcoming details of the project. This section also needs to motivate the project by providing context for the study, outlining the current state of knowledge in the field, and highlighting any gaps or limitations in existing research. The section serves as a foundational guide that enables the reader to grasp the context of the study, in addition to its structure, before moving into a more technically-based discussion in the following sections of the article. In short, the "Overview" section needs to answer the `what` and `why` questions, that is `what is the project?` and `why is the project important?`



When developing new software, software engineers need to make test cases to test their functions. The big problem with creating test cases is ensuring that they work. In order to ensure that their test cases work, software engineers have developed a technique called mutation testing. Mutation testing is a technique where you purposely put defects into your program and then run the program's test suite to see if your test cases can catch the faulty input. Mutation testing tools will return a score after running. If you have a low score, then that means your program did not do a good job at catching the defects you gave; on the other hand, if you have a high score, then that means your program did do a good job at catching the defects. The problem with this is that running your test suite can be computationally expensive. The goal of this project is to use a tool like chasten or Symbex to help predict the mutation score of a test case so software engineers don't have to waste resources running the program. In order to do this, I need to find reputable Python programs. That means I will need to find Python programs from a trustworthy source like GitHub; I also need to ensure that these Python programs are using Python 3.11 or higher so it can work with my project. The program will also need a Poetry dependency management system; it needs the Pytest automation framework so it can test the test cases. Lastly, I need to ensure that I can use the testing tools like Chasten or Symbex on the program.

-lookf for corealation between count of pattern and the score. example for for if (hard to  test), as the amount of these are found the lower the score will be
-
-Find 1 or 2 anti patterns, write code using chasten or symber to find them xpaths


## Literature Review

Look for articles about mutation and mutation testing
https://dl.acm.org/doi/pdf/10.1145/2931037.2931038

https://www.jot.fm/issues/issue_2006_07/column4.pdf

https://spe-ed.com/papers/moreanti.pdf



TODO: Conduct literature review by describing relevant work related to the project and hence providing an overview of the state of the art in the area of the project. This section serves to contextualize the study within the existing body of literature, presenting a thorough review of relevant prior research and scholarly contributions. In clear and meaningful language, this section aims to demonstrate the problems, gaps, controversies, or unanswered questions that are associated with the current understanding of the topic. In addition, this section serves to highlight the current study's unique contribution to the field. By summarizing and critiquing existing works, this section provides a foundation for readers to appreciate the novelty and significance of the study in relation to the broader academic discourse. The "Literature Review" section further contributes to the `why is the project important?` question. The number of scholarly work included in the literature review may vary depending on the project.

-Explain what mutation testing is, explain what anti patterns are

As a software engineer when you create programs that desgined to do certain task it is important that your program is correct. A lot of software engineers will make a program that will make a program that will work but it will not
produce the correct output. For example if you make a program that can add two nunbers together, you enter 5 + 5, the expected output would be 10 but somehow you ended up with 20. Your program did work, it added the two numbers together
but it did not produce the correct answer. In oreder to help programmers make sure that their code is correct they create test cases. Test cases are used to make sure that your program does what it's supposed to do, the better the test
cases, the more confidence you can have with your output being correct. But how do you know your test cases are strong, the only way to know is to test them. This is where mutation testing will come in. The paper 'Predictive Mutation Testing' by Zhang, J., Wang, Z., Zhang, L., Hao, D., Zang, L., Cheng, S., & Zhang, L. (2016) discusses a good techinque for testing the strength of your test suite, mutation testing. They describe mutation testing as testing evaluates test suite quality by generating program variants, or mutants, through syntactic changes. In first-order mutation testing, mutants are created by applying one change at a time, such as deleting a statement. A mutant is considered "killed" if any test produces different results compared to the original program. If no differences occur, the mutant "survives." If multiple mutants survive then you know that you test weren't strong enough. But the question now is how to make test stronger. When coding, it's vital to recognize common mistakes, known as anti-patterns. These patterns, as described by Smith & Williams (2002), capture expert knowledge about 'best practices' in software design by documenting general solutions that may be customized for a particular context. Similarly, anti-patterns, as explained by Brown et al. (1998), are conceptually similar to patterns, documenting recurring solutions to common design problems. However, they are known as anti-patterns because their use (or misuse) produces negative consequences. Therefore, it is essential for developers to not only recognize anti-patterns but also be vigilant in identifying and correcting any detrimental coding practices that may compromise the quality and reliability of the software. My tool will be able to help developers avoid this problem.

talk about making test stronmger 
look for info in article, then move onto antipatterns, then talk about what the tool

What is mutation testing and what are anti-patterns.

-Explain talk about the research I found (what they say)
-Conclusion


## Methods


- First project: https://github.com/pytest-dev/pytest-env
- Second project: https://github.com/pytest-dev/pytest
- Thrid project: https://github.com/kieran-ryan/pyprojectsort
  
TODO: Discuss the methods of the project to be able to answer the `how` question (`how was this project completed?`). The methods section in an academic research outlines the specific procedures, techniques, and methodologies employed to conduct the study, offering a transparent and replicable framework for the research. It details the resources behind the work, in terms of, for example, the design of the algorithm and the experiment(s), data collection methods, applied software libraries, required tools, the types of statistical analyses and models which are applied to ensure the rigor and validity of the study. This section provides clarity for other researchers to understand and potentially replicate the study, contributing to the overall reliability and credibility of the research findings.

Draft

In order to do this I need to find reputable Python programs. That means I will need to find Python programs from a trust worthy source like github, I also need to ensure that these python programs are using Python 3.11 or higher so it can work with my project, the program will also need to a poetry dependency management system,it needs the pytest automation framewrok so it can test the test cases, lastly I need to ensure that I can use the testing tools like chasten or symbex on the program. Then I plan to use mutmut or mutatest to get a mutation score, I will use the data I get from mutmtut or mutatest and find away to feed the data into a NLP so I can train it to help predict the mutation score
of code before it runs.

## Using the Artifact

TODO: The result of your work will be the delivery of some type of artifact which will likely contain software programming solutions (i.e., Python code, HTML pages, or similar). To allow the user to experience and execute your artifact, you must first explain how to set up the initial conditions to run or use the artifact. Be sure to offer explicit details and instructions regarding the installation of the necessary foundational libraries, drivers, external software projects, containers and similar types of tertiary software which are involved in executing your artifact. Once these initial software installations have been completed, then you are asked to offer the necessary instructions for actually executing the artifact. For this, please provide all command line parameters or associated bash commands for execution. Please remember that users are unwilling to "figure-out" how to use code in absence of the essential instructions concerning the execution of project artifacts.

## Results and Outcomes

TODO: Discuss the outcomes of your project in this section. Depending on the project type, the presented results and outcomes will vary. In some projects, you will be asked to present a theoretical analysis, and in others your experimental study and its results. In this section, you are also to demonstrate an enhanced version of your artifact by showing its capabilities and applications, in light of the evaluation metrics for assessing the artifact

---

## Exemplar Projects Discussions

The department's project descriptions can be found at [https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects](https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects)

## Schedule

The schedule for this work can be found at [https://github.com/CMPSC-580-Allegheny-College-Spring-2024/classDocs?tab=readme-ov-file#schedule](https://github.com/CMPSC-580-Allegheny-College-Spring-2024/classDocs?tab=readme-ov-file#schedule)
