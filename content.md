# Code Review & Pull Requests

## Why is Code Review Important?
Code review is a crucial part of any development process because:

- It promotes learning within the team, allowing team members to exchange knowledge and ideas.
- You can gain alternative ideas on how to solve a problem that you may not have considered.
- It allows junior developers to learn and contribute, while also sometimes teaching senior developers new tricks.
- It breaks down knowledge silos, meaning the entire team is familiar with more areas of the codebase, reducing risk.
- And yes, it helps catch bugs too!

## Git Flow
Git Flow is a branching model that helps organize the development workflow. Here’s a quick overview:

- **Master or Main Branch**: This is the stable, production-ready branch.
- **Feature Branches**: These are created to work on specific features or bug fixes without affecting the main branch.

To create a feature branch:

```bash
git checkout main
git pull
git checkout -b feature/my-new-feature
```

![](/assets/commit-graph.png)

## Git Flow Lifecycle
### 1. Create a feature branch
Always branch from main to ensure you are working on the latest code.

### 2. Implement and commit changes
After making your changes, stage and commit them:

```bash
git add .
git commit -m "Describe your changes"
```

### 3. Push your branch to the remote repository
Push your work to a remote branch so that others can see it:

```bash
git push origin feature/my-new-feature
```

### 4. Create a Pull Request (PR)
Open a PR to merge your feature branch into main. Your team will review the code, request changes, or approve the PR.

![](/assets/pr.png)

## Why Pull Requests?
Pull requests (PRs) offer many benefits:

- They allow code review before changes are merged.
- They provide a clear diff of what has changed in the code.
- They help ensure quality control by letting team members suggest improvements and find potential issues.


![](/assets/pr-diff.png)

![](/assets/pr-comments.png)

![](/assets/pr-review.png)

## Merge Conflicts
Merge conflicts occur when Git is unable to automatically combine changes made in different branches. This happens when two branches modify the same parts of the code in different ways.

![](/assets/merge-conflict.png)

### Steps to resolve conflicts:

1. Identify the conflicted areas of the code.
2. Decide which changes to keep and which to discard.
3. After resolving, commit the changes:

```bash
git add .
git commit -m "Resolve merge conflict"
```

<aside>
We'll be using a "merge" strategy for resolving conflicts. If prompted, please enter `git config pull.rebase false`.

![](/assets/config-merge.png)
</aside>

## Best Practices for Pull Requests and Code Reviews
Pull regularly from the `main` branch to keep your feature branch up to date and avoid large, complex merge conflicts:

```bash
git pull origin main
```

Make small, focused feature branches to make it easier to review code and integrate changes.

Write clear and concise commit messages to explain the changes you made.

Request reviews early: Don’t wait too long to ask for a review. Reach out if you need feedback or approval.

## Key Git Commands

### Check your current branch

```bash
git branch
```

### Switch between branches

```bash
git checkout main
```

### Pull the latest changes from main

```bash
git pull origin main
```

### Push a feature branch to the remote repository

```bash
git push origin feature/my-new-feature
```

### Check the status of your branch (see which files are changed and staged)

```bash
git status
```

- What is the main purpose of a code review?
- It allows team members to share ideas and improve the quality of code.
  - Correct! Code reviews ensure quality control and promote learning.
- It only helps junior developers learn.
  - Not quite. Code reviews benefit developers at all levels.
- It automatically merges changes into main.
  - No, code reviews help review and suggest improvements before merging.
{: .choose_best #code_review_purpose title="Code Review Purpose" points="1" answer="1"}

- What should you do before creating a feature branch?
- Start directly from your current branch.
  - Not quite. You should make sure you're working off the latest main branch.
- Pull the latest changes from main.
  - Correct! Always ensure your feature branch is up-to-date by pulling changes from main.
{: .choose_best #before_feature_branch title="Starting a New Feature Branch" points="1" answer="2"}

- What can cause a merge conflict?
- Two branches modify the same part of a file differently.
  - Correct! Conflicting changes need to be manually resolved.
- A teammate's PR was merged before yours.
  - Not necessarily. Only overlapping changes cause conflicts.
{: .choose_best #merge_conflict_cause title="Merge Conflict Causes" points="1" answer="1"}

- When is a PR considered ready to be merged into main?
- After team member(s) have approved it.
  - Correct! A PR should be merged only after it’s been reviewed and approved.
- As soon as you create the PR.
  - Not quite. The PR needs to be reviewed before it can be merged.
{: .choose_best #pr_approval title="PR Approval" points="1" answer="1"}

- How do you update your current feature branch with the latest changes from the main branch?
- Use `git merge main`
  - Correct! Merging the main branch into your current branch will incorporate the latest changes.
- Use `git pull origin feature/my-branch`
  - Not quite. This would pull changes from a remote feature branch, not main.
- Use `git pull origin main`
  - Correct! This pulls the latest changes from the main branch into your current branch.
{: .choose_all #update_branch_with_latest title="Updating Your Branch with Latest Changes" points="1" answer="[1,3]" }

- What are the steps to resolve a merge conflict?
- Identify the conflicted areas in the code.
  - Correct! You need to figure out where the conflicts are and resolve them manually.
- Decide which changes to keep and which to discard.
  - Correct! Once the conflicts are identified, you’ll have to choose how to resolve them.
- Commit the resolved changes.
  - Correct! After resolving the conflict, you should commit the changes to complete the process.
- Revert all changes.
  - Not quite. You only need to resolve the conflicts, not revert everything.
{: .choose_all #merge_conflict_resolution title="Resolving Merge Conflicts" points="1" answer="[1,2,3]" }

## Be patient
Senior and Lead developers can be very busy so be patient, but make sure to reach out if you are waiting on a review.

## 🤪 Fun Facts
[Fun Facts](https://github.com/DPI-WE/fun-facts) is an index of fun facts. Follow the contribution guidelines to add your fun fact and practice your pull request skills.

- Did you create a pull request for `https://github.com/DPI-WE/fun-facts/`?
- Yes
  - Great job!
- No
  -Please follow the contribution guidelines for the [Fun Facts](https://github.com/DPI-WE/fun-facts) repository.
{: .choose_best #fun_facts_pull_request_url title="Fun Facts Pull Request URL" points="1" answer="1" }

<div class="alert alert-danger mt-2">

Return to Canvas and submit the pull request URL again in the assignment "Pull Request URL for Fun Fact".

An instructor will provide additional feedback on your submission there.
</div>

---

- Approximately how long (in minutes) did this lesson take you to complete?
{: .free_text_number #time_taken title="Time taken" points="1" answer="any"}
