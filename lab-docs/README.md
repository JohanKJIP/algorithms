# Report for assignment 4

## Project

Name: keon/algorithms

URL: https://github.com/keon/algorithms

Minimal and clean example implementations of data structures and algorithms in Python 3.

## P+ points
We are aiming at P+ for the assignment and for that we did:

- **Optional (point 1): Architectural overview.** The architecture and purpose of the system are presented in an overview of about 1–1.5 pages. 
- **Optional (point 2): Relation to design pattern(s).** Updates in the source are put into context with the overall software architecture and discussed, relating them to design patterns and/or refactoring patterns.
- **Optional (point 3): Trace tests to requirements.** Relevant test cases (existing tests and updated/new tests related to the refactored code) are traced to requirements
- **Optional (point 4): The patch is clean.** Your patch is clean in that it (a) removes but does not comment out obsolete code and (b) does not produce extraneous output that is not required for your task
- **Optional (point 5): Make a pull request** Patches are accepted by the project, or considered for acceptance 
- **Optional (point 6): Context with best software engineering practice** You can argue critically about the benefits, drawbacks, and limitations of your work carried out, in the context of current software engineering practice, such as the SEMAT kernel.

----

## Onboarding experience

1. How easily can you build the project? 

We managed to build and run the project as documented. Since it is a python project, python 3 obviously had to be installed along with the following dependencies (via pip):

- flake8 
- python-coveralls 
- coverage 
- nose 
- pytest 
- tox 
- black

In general, it was very easy to set everything up since the setup was very well documented. Furthermore, python is quite an easy language to work with.

2. Do you plan to continue or choose another project?

Yes. We will continue with this project.

----

## UML class diagram and its description

TODO

The UML class diagram above shows the relevant classes that have been changed or added in this project. It includes all the public functions along with the parameters to give an overview of the class and the class structure.

----

#### Optional (point 1): Architectural overview.

The Open Source project Algorithms is a collection of data structures and algorithms written in Python by contributors. The purpose of the project is to provide a large amount of data structures and algorithms in one place to make it easy to use any of these. Having the project as an open-source project enables people to update and add functionality to ensure the code stays up to date and functioning but also that new data structures and algorithms that people need are added.

It is structured intuitively with three folders and all relevant information about the repository in general, licences, setup and continuous integration in the outermost directory. The three folders consist of an algorithms folder containing the code for algorithms and data structures, a test folder with tests for said code and a docs folder that is supposed to contain generated documentation for each folder inside algorithms (however it seems as most of the documentation is missing). In the algorithm folder, algorithms and data structured are categorized after more general topics, such as matrix, graph, heap etc. Each test file focuses on one category in the algorithms folder. This setup is supposed to facilitate contribution. 

If someone finds that a data structure or algorithm is missing, should be added or modified in any way, they write an issue. In most cases, the ones that write the issues, assign themselves to deal with them right away. The contributors are expected to provide corresponding test cases to the code as well. When adding an algorithm or data structure that does not belong to any already-existing category, they add a new folder with a general category. It is important that all new contributions are only additional and that everything works if excluding it. Hence, no existing code is to be modified or removed due to contribution.  The file with the new algorithm is more specific and sometimes more functions are added in the same file, for instance with different uses of data structures for the same algorithm.

In this assignment, we have resolved an issue in which more alternative implementations of Dijkstra’s algorithm, using other data structures, were requested. We chose to implement Dijkstra’s using a priority queue, both with binary heap and Fibonacci heap. Since the data structure for binary heap already existed in the category folder “Heap”, we only added the function in the “Dijkstra” folder and the relevant test cases in the test_graph file, where Dijkstra's algorithm was already tested. In the case with the Fibonacci Heap, that particular data structure was not included in the “Heap” folder. Therefore, we added the data structure as a new file in that folder and then implemented the use of it in a new function in the Dijkstra’s file. Tests were then added for testing the new data structure and for testing the new function where it was applied. This way of contributing to components separately enables the code to be implemented in other contexts as well. The Fibonacci heap, in case, can then be applied in other algorithms.

---

#### Optional (point 2): Relation to design pattern(s).

The updates to the source code follow the preexisting architecture of the project. As mentioned above under Architectural overview all updates are made to follow said architecture. The two new Dijkstra functions using binary heap and Fibonacci heap are added in the preexisting dijkstra.py file, tests are also added to the previously existing test file test_graph. We also ensure not to make any changes that may interrupt previous source code such as the preexisting Dijkstra function, this ensures that the functionality of these old functions does not change. 

We followed the design patterns of the project such as following the functions naming convention of using snake case. This is where the function name uses underscore “_” instead of capital letters to separate words, an example is the function for Dijkstra’s algorithm that uses a binary heap that was named “dijkstra_min_heap”. This is a common design pattern for python that the project uses. 

Formatting the code according to the design pattern was also done. We used black which is a standard python code formatter which the project uses. This ensures that the format is the same everywhere in the project which improves readability.

----

## Selected issue(s)

Title: "Please add methods in Dijkstra’s algorithm for finding minimum using priority queue (heap module etc.)) #565"

URL: https://github.com/keon/algorithms/issues/565

A version of Dijkstra’s algorithm using a list exists in the project. In order to improve time complexity, more versions should be implemented that use priority queues. We will implement a few different versions namely:
1. Dijkstra's algorithm using the binary min-heap already implemented in the project.
2. Dijkstra's algorithm using a Fibonacci heap.

----

### Project plan

