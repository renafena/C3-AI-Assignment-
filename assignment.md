# Using git rebase

Rebase, like merge, enables you to integrate, or commit, changes from a branch into the main branch. With merge, you preserve the branching structure and can see the commits from each branch. With rebase, you reapply all the commits as one commit to the main branch. 

## Benefits of rebase

Use rebase to:

* Declutter the version history.
* Minimize collaboration conflicts.

As a best practice, regularly rebase when you want to integrate the latest changes from the main branch into your working branch. This essentially applies commits on the tip of the base branch.

### Declutter version history

When many contributors make small but frequent updates, you can rebase to squash them into a single commit. Look at this example of a version history with merge commits:

```text
*   Merge branch 'fix-typos'  
|\
| * Fixed typo in chapter 2  
| * Fixed typo in chapter 1  
* Updated introduction  
```

Now look at the same version history after rebasing:
```text
* Fixed typo in chapter 2  
* Fixed typo in chapter 1  
* Updated introduction  
```

Simplifying the version history especially helps when looking back at project changes or performing reviews.

### Minimize collaboration conflicts

Rebasing enables you to update your branch with the latest changes before finalizing your work. This means you can handle any conflicts proactively on your branch. It also helps reduce the chance of introducing new conflicts into the main branch.

## When to avoid rebasing

Avoid rebasing public or shared branches. Because rebasing changes the commit history, it might cause confusion or disrupt collaborative work when others have already pulled your changes.

## Steps to rebase

1. Check out your feature branch: <br>
```text
git checkout my-branch
```
2. Update your main branch.
3. Rebase your branch onto the main branch.
4. Edit any conflicting files and mark them as resolved: <br>
```text
git add <file>
git rebase --continue
```
5. Push your changes: <br>
```text
git push --force
```
