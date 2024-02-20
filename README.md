# PIRL coding guidelines (WIP)
Software engineering recommendations for tools developed by PIRL




## Source Control

Make a git repository for *everything*, even one-off analyses. This is extremely useful for collaboration, reproducibility, and can save your future self a lot of time. If a collaborator wants to keep data or analyses private until publication, start off with a private repo and switch it to publicly visible if/when possible. 

### Branching

For small/one-off projects it's fine to do just develop directly on the `main` branch. Once you have external users or multiple developers, try to use the [GitHub flow](https://gitversion.net/docs/learn/branching-strategies/githubflow/) branching strategy. Essentially this means creating a "feature branch" whenever you start working on something new and then merging it back to `main` once you're done. Only merge a branch if all of its unit tests are passing and preferably once someone else has looked over the changes through a code review. 

### Code Review

One nice benefit of using feature branches is that the merge back to main can be done through a [GitHub Pull Request](https://gist.github.com/vlandham/3b2b79c40bc7353ae95a), which is an opportunity for [code review](https://github.com/features/code-review). Code review is not required for PIRL projects but is encouraged, especially for code which you think may become an essential dependency for other projects. As a reviewer, try to focus on the most important feedback and give it quickly. If PRs languish waiting for reviews then everyone just abandons code review and goes back to merging their changes without any external feedback. 

## Languages

PIRL does not mandate the use of any particular language or infrastructure for one-off projects. *However*, unless there is a compelling reason for the problem you're trying to solve, use languages as high up this recommendation hierarchy as possible: 

* **Encouraged**: Python, R, Rust
* **Tolerated**:  Cython (try Rust + Maturin instead), C
* **Discouraged**: C++, Java (and other JVM languages like Scala), C# (and other .NET languages)

## Workflows

Whenever producing a research artifact involves a series of steps, try to at least capture them in a named shell script. Ideally, workflows intended for reuse are written in Nextflow and/or [RAFT](https://gitlab.com/landscape-of-effective-neoantigens-software/raft/-/wikis/home). 

* **Encouraged**: Bash (small scripts), Nextflow, RAFT
* **Tolerated**:  Snakemake, Make
* **Discouraged**: CWL, WDL, Airflow, less common scripting languages such as Zsh

## Unit Testing

Write unit tests for anything you plan to use more than once. You can also use unit tests to guide the software design/development process. 

* Python: [PyTest](https://nose.readthedocs.io/en/latest/testing.html](https://docs.pytest.org/en/8.0.x/))
* R: [testthat](https://testthat.r-lib.org/)

## Continuous Integration

It's extremely useful to have your unit tests run on every commit so that you know immediately when you have made a breaking change. GitHub Actions can be used as a "continuous integration" system (i.e. server that runs all your unit tests) which will work with any source control system. 

* [GitHub Actions](https://docs.travis-ci.com/user/tutorial/)
* [How to build a CI/CD pipeline with GitHub Actions in four simple steps](https://github.blog/2022-02-02-build-ci-cd-pipeline-github-actions-four-steps/)


## Code Style
* Python: There are several coding styles for Python, the best for scientific computing and machine learning libraries is the [NumPy style guide](https://numpydoc.readthedocs.io/en/latest/format.html) 

## Linting
Linting checks code against a known set of coding standards.
* Python: `flake8` and `pylint`

## Documentation 
* [Read The Docs](https://readthedocs.org/)


