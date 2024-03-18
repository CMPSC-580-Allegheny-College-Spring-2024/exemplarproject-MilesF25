[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/Y4rZMh1t)
# Junior Seminar (CMPSC 580) Exemplar Project Repository

## Semester: Spring 2024

This repository contains student project materials, including project report, data, code, and references to literature for this departmentally-sponsored project. __As you complete each of the below sections in this document, please be sure to remove the preamble text so that it does not appear in your work.__ Please work with your first reader to answer any questions or concerns that you may have.

## GitHub Handle: MilesF25

## Name: Miles Franck

## Major: SE

## Project Name: COMMA


## Link to current progress
https://github.com/AstuteSource/SEERS/tree/main
---

## Overview


When developing new software, software engineers need to make test cases to test their functions. The big problem with creating test cases is ensuring that they work. In order to ensure that their test cases work, software engineers have developed a technique called mutation testing. Mutation testing is a technique where you purposely put defects into your program and then run the program's test suite to see if your test cases can catch the faulty input. Mutation testing tools will return a score after running. If you have a low score, then that means your program did not do a good job at catching the defects you gave; on the other hand, if you have a high score, then that means your program did do a good job at catching the defects. The problem with this is that running your test suite can be computationally expensive. The goal of this project is to use a tool like chasten or Symbex to help predict the mutation score of a test case so software engineers don't have to waste resources running the program. In order to do this, I need to find reputable Python programs. That means I will need to find Python programs from a trustworthy source like GitHub; I also need to ensure that these Python programs are using Python 3.11 or higher so it can work with my project. The program will also need a Poetry dependency management system; it needs the Pytest automation framework so it can test the test cases. Lastly, I need to ensure that I can use the testing tools like Chasten or Symbex on the program.

## Literature Review

In software engineering, ensuring the correctness of programs is important. While software engineers may create programs that seemingly work, making sure that they produce the correct output is a challenge. For example, a program designed to add two numbers together may have unexpected results, like adding 5 and 5 and getting 20 instead of the 10. To avoid this, programmers use test cases to verify that programs function as intended. The stronger the test suite the more confidence you can have in the program's correctness.

One approach to strengthening your test suite is mutation testing. This technique, described  in the paper "Predictive Mutation Testing" by Zhang et al. (2016), evaluates test suite quality by generating program variants, or mutants, through syntactic changes. First-order mutation testing involves introducing one change at a time, such as deleting a statement, to create mutants. A mutant is deemed "killed" if any test produces different results compared to the original program.But if no differences are found then the mutant "survives." If the mutant is “killed” that means that the test suite is strong and the suite will have a high mutation score, on the other hand if the mutant “survives” that means there are some potential weaknesses in the test suite and that will result in a low mutation score.

However, mutation testing is not the only way to strengthen test cases. It's imperative for programmers to be aware of common coding pitfalls known as anti-patterns. These patterns described by Smith & Williams (2002), encapsulate expert knowledge about 'best practices' in software design, while anti-patterns, as described by Brown et al. (1998), represent recurring solutions to common design problems that yield negative consequences when misapplied.

Mutation testing shows its effectiveness in finding deficiencies in test suites, however it’s very computationally expensive. Similarly, having to be constantly aware of anti-patterns can be draining for developers. COMMA. The tool that we are developing can help alleviate these problems. COMMA will be able to look at a test suite and give a predicted mutation score of the test suite without needing the user to run the test suite.

Sources and Links:
https://spe-ed.com/papers/moreanti.pdf
- Nafees, T., Coull, N., Ferguson, I., & Sampson, A. (2018, November). Vulnerability anti-patterns: a timeless way to capture poor software practices (vulnerabilities). In 24th Conference on Pattern Languages of Programs (p. 23). The Hillside Group.

-https://www.jot.fm/issues/issue_2006_07/column4.pdf
- Dodani, M. H. (2006). Patterns of Anti-Patterns. J. Object Technol., 5(6), 29-33.

- https://dl.acm.org/doi/abs/10.1145/2931037.2931038
- Papadakis, M., Kintis, M., Zhang, J., Jia, Y., Le Traon, Y., & Harman, M. (2019). Mutation testing advances: an analysis and survey. In Advances in computers (Vol. 112, pp. 275-378). Elsevier.

## Methods


- First project: https://github.com/pytest-dev/pytest-env
- Second project: https://github.com/pytest-dev/pytest
- Thrid project: https://github.com/kieran-ryan/pyprojectsort

In order to do this we had to find reputable Python programs. We were able find them from a trust worthy source like github. The python programs needed to meet a four requirements if it were to be used. The requirements include using Python 3.11 or higher, a Poetry dependency management system, a Pytest automation framework, and support for testing tools like Chasten, Symbex, or Mutmut. Once the are conditions met. We were able to move on to the next step which was creating a script that can run chasten and mutmut on the program. With chasten we were able to extract the possible anti-patterns from the python program, with mutmut we are able to test the test cases to see if it truly is an anti pattern. We then stored the results from both programs into a json file which we then passed to a Large Language Model (LLM) for training. The LLM uses this data to predict the mutation score of program code prior to execution.


## Using the Artifact


To analyze code using Comma:

1. Place the desired projects to test in the `demo` folder. Navigate into the `demo` folder in a terminal and use `git clone` to clone the desired project repositories.

2. Return to the `analyzer` folder and run the following command to install dependencies using Poetry `poetry install`

3. Once the installation is complete, execute the following command to run the analysis:

```bash
poetry run analyzer --search-path demo --save-directory subject-data --chasten-config-path Config

```

Replace the options --search-path, --save-directory, and --chasten-config-path with the desired paths where the project will be searched, files will be saved, and configuration files will be located, respectively. These should be Path objects passed in a manner similar to the example command provided above.

- Once the analysis and unfication complete, the following message will pop up

```script
Code analysis and mutation complete!
Result is stored in file named combined_result.json
🧹 Final sweeping, saved to new_output_with_functions.json
```

The complete data exists in `new_output_with_functions.json`

- Now, you can scan the ouput to confirm that, for instance, the mutation score for pattern named `add_files` that was inserted 3 mutants (01 survived, 02 killed) has a mutation score of 0.3333333333333333.
  
```script
{
    "file": "/Users/jaclynpham/AstuteSource/SEERS/scripts/analyzer/demo/lazytracker/lazytracker/lazytracker.py",
    "pattern": {
      "lineno": 29,
      "coloffset": 4,
      "linematch": "def add_files(self, filepaths: List[str], chunk_num_blocks=128):",
      "context": "        files_to_check = sorted(files_to_check)\n\n        self.add_files(files_to_check, chunk_num_blocks)\n\n    def add_files(self, filepaths: List[str], chunk_num_blocks=128):\n        \"\"\"Include hash of files\n\n        Args:\n            filepaths (List[str]): List of paths to files\n            chunk_num_blocks (int, optional): How many chunks to read at once. Defaults to 128.",
      "min": 1,
      "max": 10,
      "pattern": ".//FunctionDef",
      "check_id": "F001",
      "check_name": "all-function-definition",
      "description": "Ensure the presence of function definitions in the codebase."
    },
    "function_name": "add_files",
    "function_scope": "29-42",
    "mutants": [
      {
        "name": "Mutant #6",
        "line": 29,
        "description": [
          "    def add_files(self, filepaths: List[str], chunk_num_blocks=128):"
        ],
        "failure": [
          {
            "inner": "--- lazytracker/lazytracker.py\n+++ lazytracker/lazytracker.py\n@@ -26,7 +26,7 @@\n \n         self.add_files(files_to_check, chunk_num_blocks)\n \n-    def add_files(self, filepaths: List[str], chunk_num_blocks=128):\n+    def add_files(self, filepaths: List[str], chunk_num_blocks=129):\n         \"\"\"Include hash of files\n \n         Args:\n",
            "type": "failure",
            "message": "bad_survived"
          }
        ]
      },
      {
        "name": "Mutant #7",
        "line": 38,
        "description": [
          "                with open(p, \"rb\") as f:"
        ],
        "failure": []
      },
      {
        "name": "Mutant #8",
        "line": 39,
        "description": [
          "                    while chunk := f.read(chunk_num_blocks * self._hasher.block_size):"
        ],
        "failure": []
      }
    ],
    "mutation_score": 0.3333333333333333
  },
```


## Results and Outcomes

The JSON file generated from our mutation testing process provides valuable insights into the effectiveness of our testing approach. The mutation score, which is 0.33, shows that about one-third of the introduced mutations were detected by our test suite. This score serves as a gauge for measuring the robustness of our testing process.
The results show that there are some weaknesses in codes test cases. Some mutations remained undetected by the test suite. This highlights areas where test coverage may be lacking and suggests the need for additional test cases to address these gaps.

## Exemplar Projects Discussions

The department's project descriptions can be found at [https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects](https://github.com/ReadyResearchers-2023-24/cmpsc-580-exemplar-projects)

## Schedule

The schedule for this work can be found at [https://github.com/CMPSC-580-Allegheny-College-Spring-2024/classDocs?tab=readme-ov-file#schedule](https://github.com/CMPSC-580-Allegheny-College-Spring-2024/classDocs?tab=readme-ov-file#schedule)
