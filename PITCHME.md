# Git - Pitch 2

- More on git commit messages

---

## Looking back

- Why git commit messages matters
- Seven rules of good commit messages

---

## Seven rules of good commit messages

1. Separate subject from body with a blank line
1. Limit the subject line to 50 characters
1. Capitalize the subject line
1. Do not end the subject line with a period
1. Use the imperative mood in the subject line
1. Wrap the body at 72 characters
1. Use the body to explain what and why vs. how

---

### 1. Separate subject from body with a blank line

- Not all commit messages require a body

`git commit -m "Fix typo in introduction to user guide"`

---

### 1. Separate subject from body with a blank line

- Sometimes a body is required, specilly to describe *why*

```
git commit -m "Update the api url

* It turned out that the comodo api updated its versions and prefers clients to update uris to use the latest version
"
```

- Configure git editor

`git config --global core.editor "vim"`



---

### 1. Separate subject from body with a blank line

- More examples

```
git commit -m "Fix the infinite loop

* The infinite loop only happens when the product miss a attribute number 3. 
* It's a rare case and only found for product number 1 after a long trace.
* This commit checks if the product misses the specific attribute and
* fix the infinite loop.
*
* More details on trello card: https://trello.com/c/carduniquehash 
"
```

- Visible at gitlab commit page or with `git log` 

---

### 2. Limit the subject line to 50 characters

- `git log --oneline` and gitlab pages

---

### 3. Capitalize the subject line

---

### 4. Do not end the subject line with a period


- When there's a body message

---

### 5. Use the imperative mood in the subject line

```
A properly formed Git commit subject line should always be able to complete the following sentence:

- If applied, this commit will *Your subject line here*

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
```

---

### 6. Wrap the body at 72 characters

- For visibility and good format. optional

---

### 7. Use the body to explain what and why vs. how

- We need why vs. how
- We can always check how using `git diff` or `git show`

```
git commit -m "Fix the infinite loop

* The infinite loop only happens when the product miss a attribute number 3. 
* It's a rare case and only found for product number 1 after a long trace.
* This commit checks if the product misses the specific attribute and
* fix the infinite loop.
*
* More details on trello card: https://trello.com/c/carduniquehash 
"
```

---

### 7. Use the body to explain what and why vs. how

A good commit message should answer three questions about a patch:

- Why is it necessary? 
It may fix a bug, it may add a feature, it may improve performance, reliabilty, stability, or just be a change for the sake of correctness.
- How does it address the issue? 
For short obvious patches this part can be omitted, but it should be a high level description of what the approach was.
- What effects does the patch have? 
(In addition to the obvious ones, this may include benchmarks, side effects, etc.)

--- 

### 7. Use the body to explain what and why vs. how

- Cause the context finder to see the diffs and waste time on understanding context
- 

--- 

### Bonus: 8. One commit per logical change

- Commit often
- One commit per logical change
- Group changes for one logical changes 
- Never use `git add .`
- Use `git add -p` or `git add -i` or `git add <filename>`
- Use `git diff` very often - must use before git commit	

--- 

## Bad commit messages

- SCM is not a backup system!
- Per-file commit.
- Lazy commit messages
- Two changes in one patch.
- Whitespace changes together with code changes.
- The ever-so-lovely code drops.
- Unrelated whitespace changes in patches.
- Most fav. execuse: It works!

--- 

### Bad: SCM is not a backup system!

- One end-of-day commit is evil.
- Even the original author waste time to re-establish the context when a few months have passed.
- It's a VCS
- No need to comment old code, keep old files.

--- 

### Bad: Per-file commit.

- No, one commit per logical change please!

--- 

### Bad: Lazy commit messages

- `"misc fixes and cleanup"`
- 

--- 

### Bad: Two changes in one patch.

- `"Fixing bug number 48"`
- `"Fixes for gitlab issue #202"`

--- 

### Bad: Whitespace changes together with code changes.

- Separate commit for adding/updating new plugin/module
- Separate commit for Reformatting code/line ending changes (LF)
- Separate because it's like needle in the haystack.

--- 

### Bad: The ever-so-lovely code drops.

- Separate refactoring codes and new feature codes into different commits.

--- 

### Bad: Unrelated whitespace changes in patches.

- Separate indentation changes and actual changes in different commits.

--- 

### Bad: Most fav. execuses

- "but It works!"" - it may work, but in few weeks time it will be a mess.
- "but I'm the only one working on it" - not true, you can't predict the future.

--- 

# Questions

--- 

## References

- [Chris Beans](https://chris.beams.io/posts/git-commit/)
- [Peter Hutterer](http://who-t.blogspot.com/2009/12/on-commit-messages.html)
