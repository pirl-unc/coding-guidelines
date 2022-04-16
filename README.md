# WIP: PIRL coding guidelines
Software engineering recommendations for tools developed by PIRL


## Source Control

Make a git repository for *everything*, even one-off analyses. This is extremely useful for collaboration, reproducibility, and can save your future self a lot of time. If a collaborator wants to keep data or analyses private until publication, start off with a private repo and switch it to publicly visible if/when possible. 

### Branching

For small/one-off projects it's fine to do just develop directly on the `main` branch. Once you have external users or multiple developers, try to use the [GitHub flow](https://gitversion.net/docs/learn/branching-strategies/githubflow/) branching strategy. Essentially this means creating a "feature branch" whenever you start working on something new and then merging it back to `main` once you're done. Only merge a branch if all of its unit tests are passing and preferably once someone else has looked over the changes through a code review. 

### Code Review

One nice benefit of using feature branches is that the merge back to main can be done through a [GitHub Pull Request](https://gist.github.com/vlandham/3b2b79c40bc7353ae95a), which is an opportunity for [code review](https://github.com/features/code-review). As a reviewer, try to focus on the most important feedback and give it quickly. If PRs languish waiting for reviews then everyone just abandons code review and goes back to merging their changes without any external feedback. 


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


