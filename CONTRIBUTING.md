# InnerSource Patterns Workflow

This document describes the workflow for writing, reviewing and publishing
InnerSource ideas, donuts and patterns. It utilizes Pull Requests to facilitate
collaborative reviews.

There are two separate repositories needed for this workflow:

* [InnerSourcePatterns][patternsRepo]
* [InnerSourceCommons][commonsRepo]

## InnerSourcePatterns repository

This is a private repository where new ideas, donuts and patterns are published
and reviewed by the patterns community **prior to** publishing them on
[innersourcecommons.org][commons]. Inside of this
repository we're using the standard GitHub workflow where we have one main
branch - the master branch.  Contributions are done via fork and pull-requests.

## InnerSourceCommons repository

This is where ideas, donuts and patterns will be published **after** they have
been reviewed and accepted by the reviewers. Inside of this repository we're
using the standard GitHub workflow where we have one main branch - the master
branch. Contributions are done via fork and pull-requests. This repository
contains the sources for the GitHub pages website for innersourcecommons.org.

## Workflow

### Working inside of the InnerSourcePatterns repository

1. [Create an issue] for each new idea, donut or pattern in the
  [patterns repository][patternsRepo]. The issue should
  * contain the name of the pattern,
  * contain a short description (at least the problem) and
  * be labeled with the appropriate label (_idea_, _donut_, _pattern_)
2. Create a new branch either in your clone or fork of the
  [patterns repository][patternsRepo]. Please use the following pattern for
  naming branches: `pattern/<patternName>`. Example:
  `pattern/contractedContributor`.
3. Create a _Markdown_ file with the description of the _idea_, _donut_ or
  _pattern_ and store it in the main directory. Commit and push.
4. Once your contribution is ready to be reviewed, create a pull request (PR)
  targeted at `master` and label it with _pattern_. Additionally decide whether
  to label it with _idea_, _donut_, or _draft_ and _Ready for Review_ or _Incomplete_
5. Reviewers can now use the PR features to comment on the pattern.
6. In case of required rework, the author should apply the labels
  _Ready for Additional Review_ and/or _Revised_ to indicate that a 2nd review is requested.
7. After reviews are complete, the reviewers or author should remove the label
  _Ready for Review_ and label the pattern _Accepted_.
8. Once a pattern is labeled _Accepted_ by the reviewers, one of the TCs of the
  [patterns repository][patternsRepo] will then move the pattern to either the
  `ideas`, `donuts` or `patterns` subdirectories, merge it to `master` and
  close the associated issue.

### Publishing an InnerSource pattern on innersourcecommons.org (InnerSourceCommons repository)

* for each new pattern to be published, a new issue should be created
  * the issue should contain the name of the pattern and a link to the accepted
  pattern inside of the InnerSourcePatterns repository
* every publishing process of a pattern idea, donut, or draft should start on a
  dedicated branch, originating from `master` starting with `pattern/<patternName>`

### Technical steps

If you want to contribute, the workflow is done through branches. You can see the
available branches of this repository at [the branches URL](https://github.com/paypal/InnerSourcePatterns/branches)
or by clicking on the 'branches' button on the main page.

Branches and Pull Requests (PR's) are used to bring discussion/review about a specific inner source pattern.
New patterns should use, as a first approach, the
[pattern template](https://github.com/paypal/InnerSourceCommons/wiki/InnerSource-Patterns-template). There are indeed multiple ways to start a discussion:
* Pull request your branch and the maintainers will receive a notification.
* Ask directly for comments to some of the maintainers. You can mention them
using the symbol '@' prior their nickname.
* Add reviewers to the Pull Request on the website - this sends requests to review your work

Please, when starting a new pattern, be aware that this does not exist. You can
have a look at some of the existing patterns in this repository.

#### How can you create a branch?

In first place you need to create a branch (no need to ask for permission!).
For this, let's clone the repository:

```
$ git clone https://github.com/paypal/InnerSourcePatterns.git
```

Then you should see some message similar to the following one:

```
Cloning into 'InnerSourcePatterns'...
remote: Counting objects: 73, done.
remote: Compressing objects: 100% (37/37), done.
remote: Total 73 (delta 35), reused 73 (delta 35), pack-reused 0
Unpacking objects: 100% (73/73), done.
Checking connectivity... done.
```

This means that you successfully cloned the repository. Then we need to access
the directory and check that everything is as expected.

```
$ cd InnerSourcePatterns/
$ ls
first-test.md  README.md  second-test.md  third-test.md  workflow.md
$ git branch
* master
$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
  remotes/origin/master-public
  remotes/origin/pattern/badly-named-piles
  remotes/origin/pattern/commonRequirements
  remotes/origin/pattern/contained-innersource-enables-collaborative-product-development
```

The command 'git branch' shows you which branch you are currently working within.
And with 'git branch -a' you see additional branches which are local and remote (on the web).
There is extra information using the command '$ man git branch' in linux based systems.

Next, in order to create a new branch as a way to start creating a new pattern,
you need to 'checkout' that branch. As a common nomenclature, all of the
pattern-related branches should start with the keyword 'pattern/'. Thus, a new
branch with a new pattern named as foo should be as follows:

```
$ git checkout -b pattern/foo
```

You are now in the 'pattern/foo' branch. When you create a new branch, the files 
in the directory might appear change. Each branch can have slightly different content,
and that is intentional. If you need to go again to the 'master' branch or another
branch, you can easily 'checkout' to those as follows:

```
$ git checkout <branchname>
```

#### Adding a new pattern

Let's imagine we want to work a new pattern related to the activities of the
Ewoks that for some reason gave up hunting. We should choose some initial
name for this pattern file that could be 'ewoks-do-not-hunt.md'.

```
$ git checkout -b pattern/ewoks-do-not-hunt
$ touch ewoks-do-not-hunt.md
```

Once our pattern file is ready to go, we need to add the file to the repo and
commit that change to our new branch.

```
$ git add ewoks-do-not-hunt.md
$ git commit -m "Inner Source Pattern to deal with Ewoks that do not hunt"
```

And we should finally upload that branch and file to the server.

```
$ git push origin pattern/ewoks-do-not-hunt
```

Then, if you feel the pattern is ready to review, you can start a Pull Request (PR) asking
to join your new branch to the master branch. To do this, navigate to the github web repo 
and get into your new branch. You should see a 'Create pull request' button while in in your branch.


## Licensing

![Creative Commons License](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)

InnerSourcePatterns by [InnerSourceCommons.org](http://innersourcecommons.org) is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International](http://creativecommons.org/licenses/by-sa/4.0/) License.


[commons]: http://innersourcecommons.org
[patternsRepo]: https://github.com/paypal/InnerSourcePatterns
[commonsRepo]: https://github.com/paypal/InnerSourceCommons