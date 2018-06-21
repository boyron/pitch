# Git

- Let's learn together
- Tips, ticks and best practices

---

## Before diving into details, some basics to review

- Git is *Distributed* or *Decentralized* version control system.
- Git is designed for speed.
- It's fully distributed and can have thousands of parallel branches.
- It can handle super large projects like Linux Kernel.

---

## Some more basics

- Git doesn't delete data.
- It generally only adds data and maintains history.
- You can always recover data, though sometimes it may be a bit tricky.

---

## Git Workflow

![Simple Git Workflow](https://cdn-images-1.medium.com/max/2000/1*S1fNUzJCu7ftH5F-Gk6YOw.png)

[More read - article on Medium](https://medium.com/@jihdeh/simple-git-workflow-graphical-guide-2a1a0ae4e664)

---

## Practical Git

- Free lessons on Codeacademy 
- https://www.codecademy.com/courses/learn-git/lessons/git-workflow/exercises/hello-git
- https://try.github.io/

---

## Git commit best practices

---

### Why good commit messages matters

Compare

```
$ git log --oneline -5 --author cbeams --before "Fri Mar 26 2009"

e5f4b49 Re-adding ConfigurationPostProcessorTests after its brief removal in r814. @Ignore-ing the testCglibClassesAreLoadedJustInTimeForEnhancement() method as it turns out this was one of the culprits in the recent build breakage. The classloader hacking causes subtle downstream effects, breaking unrelated tests. The test method is still useful, but should only be run on a manual basis to ensure CGLIB is not prematurely classloaded, and should not be run as part of the automated build.
2db0f12 fixed two build-breaking issues: + reverted ClassMetadataReadingVisitor to revision 794 + eliminated ConfigurationPostProcessorTests until further investigation determines why it causes downstream tests to fail (such as the seemingly unrelated ClassPathXmlApplicationContextTests)
147709f Tweaks to package-info.java files
22b25e0 Consolidated Util and MutableAnnotationUtils classes into existing AsmUtils
7f96f57 polishing
```

vs 

```
$ git log --oneline -5 --author pwebb --before "Sat Aug 30 2014"

5ba3db6 Fix failing CompositePropertySourceTests
84564a0 Rework @PropertySource early parsing logic
e142fd1 Add tests for ImportSelector meta-data
887815f Update docbook dependency and generate epub
ac8326d Polish mockito usage
```

- Which would you rather read?

---

### Why good commit messages matters?


> Re-establishing the context of a piece of code is wasteful. We can’t avoid it completely, so our efforts should go to reducing it [as much] as possible. Commit messages can do exactly that and as a result, a commit message shows whether a developer is a good collaborator.

---

## The seven rules of a great Git commit message

1. Separate subject from body with a blank line
1. Limit the subject line to 50 characters
1. Capitalize the subject line
1. Do not end the subject line with a period
1. Use the imperative mood in the subject line
1. Wrap the body at 72 characters
1. Use the body to explain what and why vs. how

---

## Good commit message example

```
Summarize changes in around 50 characters or less

More detailed explanatory text, if necessary. Wrap it to about 72
characters or so. In some contexts, the first line is treated as the
subject of the commit and the rest of the text as the body. The
blank line separating the summary from the body is critical (unless
you omit the body entirely); various tools like `log`, `shortlog`
and `rebase` can get confused if you run the two together.

Explain the problem that this commit is solving. Focus on why you
are making this change as opposed to how (the code explains that).
Are there side effects or other unintuitive consequences of this
change? Here's the place to explain them.

Further paragraphs come after blank lines.

 - Bullet points are okay, too

 - Typically a hyphen or asterisk is used for the bullet, preceded
   by a single space, with blank lines in between, but conventions
   vary here

If you use an issue tracker, put references to them at the bottom,
like this:

Trello card: https://trello.com/c/ODjYl123
Resolves: #123
See also: #456, #789

```
---

A properly formed Git commit subject line should always be able to complete the following sentence:

- If applied, this commit will *your subject line here*

For example:

- If applied, this commit will refactor subsystem X for readability
- If applied, this commit will update getting started documentation
- If applied, this commit will remove deprecated methods
- If applied, this commit will release version 1.0.0
- If applied, this commit will merge pull request #123 from user/branch

Notice how this doesn’t work for the other non-imperative forms:

- If applied, this commit will fixed bug with Y
- If applied, this commit will changing behavior of X
- If applied, this commit will more fixes for broken stuff
- If applied, this commit will sweet new API methods

Remember: Use of the imperative is important only in the subject line. You can relax this restriction when you’re writing the body.

---

## Next

- More on git commit messages
- Advanced git tools - log, blame, rebase, revert, stash
- git pull alternatives

---

## Questions, Open discussions, Feedback

---

## References

- [Chris Beans](https://chris.beams.io/posts/git-commit/)
- [Peter Hutterer](http://who-t.blogspot.com/2009/12/on-commit-messages.html)
