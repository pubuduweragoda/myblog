+++
title = 'Git workflow and git basics'
date = 2025-06-28T08:14:09+05:30
draft = false
+++

This is simple overview of the git workflow that I've been using for a while. This is by no means a fixed set of rules. I will be updating things over time as I incorporate new ideas and insights. This is to help set a basic convention that is easy to follow.

## Workflow
- Create the 2 branches dev and main or master
- Fork a feature branch from dev and start working on individual features
    - feature branches are usually names like `bugfix/token-expiry`, `feature/login-api` and etc, with the slash in some professional settings
    - we use a letter from the name of the one working on it, plus descriptive word or two such as `pb-user-management`
    - use `git checkout -b feature/my-task dev` for branching
- After feature is finished, sync with the latest dev code(if the dev was updated after I started working on the feature)
```bash
git fetch origin
git merge origin/dev
```
- After merging with latest dev and resolving conflicts, push to origin
```bash
git push origin
```
- If this is the first push after creating the feature branch, set the origin branch by creating it
```bash
git push -u origin feature/my-task
```
- On github, open a Pull Request
    - target the dev branch. Avoid main branch
    - request code review
    - add assignee
    - add a good description for the PR
- After review, use a regular merge(we usually don't use rebase or squash-and-merge)
- After merge, delete the local branch and the branch on origin
```bash
git branch -d feature/my-task
git push origin --delete feature/my-task
```

## Commit messages
### Commit types

|     Type    |   Description                                                 |
|-------------|---------------------------------------------------------------|
|   feature   |  Adding new features                                          |
|   bugfix    |  Fixing bugs                                                  |
|   refactor  |  Code changes that neither fix bugs nor add features          |
|   docs      |  Documentation only                                           |
|   style     |  Formatting, indentation, naming, etc. (no logic changes)     |
|   test      |  Adding or updating tests                                     |
|   chore     |  Non-user-facing changes (e.g., CI config, package updates)   |

- commit message format
```
<type>(<scope>): <short description>

<optional longer body explaining the why or how>
```

Example commit message 1:
```
feature(course): add update course controller

Allows course data to be updated by ID. Returns 200 on success.
```

Example commit message 2:
```
bugfix(auth): return refresh token with access token

Fixed missing return statement that broke frontend login.
```

Example commit message 3:
```
docs(readme): add API usage examples
```

### Commit message
- Use imperative mood: "add", "fix", "create", not "added", "fixed"
- Keep the subject line under 50 characters
- Use body if more detail is needed (wrap at ~72 characters)
- One commit = one logical change

Last updated: 2025-06-28 · Feedback welcome
