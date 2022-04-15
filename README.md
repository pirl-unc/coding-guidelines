# WIP: PIRL coding guidelines
Software engineering recommendations for tools developed by PIRL

## Source Control

* Make a repository for *everything*, even one-off analyses. This is extremely useful for collaboration, reproducibility, and can save your future self a lot of time. If a collaborator wants to keep data or analyses private until publication, start off with a private repo and switch it to publicly visible if/when possible. 
* 
## Unit Testing

Write unit tests for anything you plan to use more than once. You can also use unit tests to guide the software design/development process. 

* Python: [Nose](https://nose.readthedocs.io/en/latest/testing.html)
* R: [testthat](https://testthat.r-lib.org/)

## Continuous Integration

It's extremely useful to have your unit tests run on every commit so that you know immediately when you have made a breaking change. Travis is a "continuous integration" system (i.e. server that runs all your unit tests) which will work with any source control system. 

* [Travis Tutorial](https://docs.travis-ci.com/user/tutorial/)
* [Travis CI for R unit test](https://jef.works/blog/2019/02/17/automate-testing-of-your-R-package/)

## Code Style
* Python: There are several coding styles for Python, the best for scientific computing and machine learning libraries is the [NumPy style guide](https://numpydoc.readthedocs.io/en/latest/format.html) 

## Documentation 
* [Read The Docs](https://readthedocs.org/)


