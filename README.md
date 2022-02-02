# Branching-Strategy

- A good branching strategy can help the development team to move fast and achieve parallel development allowing developers to work on tasks simultaneously.
- Parallel builds and testing ensure developers get the feedback quickly.
- CI-CD can be achieved.

# Our branching strategy will cover,

> Optimize productivity.

> Enable parallel development.

> Allow for a set of planned, structured releases.

> Provide a clear path for software changes through production.

> Evolve to accommodate changes that are delivered.

> Support multiple versions of software release and hotfix.

# List of Branches and their uses:

# Master:
- The Master branch stores the official release.
- Tag all commits in the master branch with a version number.
- Production build can happen only from the Master branch.
- This branch will be restricted and accepts only MR.

# Develop:
- The develop branch serves as an integration branch for features.
- Test env build will happen from this branch.
- After code review, the MR option will be enabled.
- This branch will be restricted and accepts only MR.

# Feature:
- Feature branches are generally created off to the latest develop branch.
- Feature branches use develop as their parent branch.
- The feature branch should never interact directly with the master.
- When you’re done with the development work on the feature, the next step is to merge the feature branch into develop and it will be deleted.
- Development env build will happen from this branch.

# Release:
- Once develop has enough features for a release(Code Freeze), Create release branch from develop branch.
- No new features can be added after this point.
- Only Bug Fixes and other release-related tasks can be added.
- Once the release branch is all set, it will be merged to the master branch and it can be deleted(based on use case).
- Stage env build will happen from this branch.
- This branch will be restricted and accepts only MR

# BugFix:
- During stage testing If any bugs are found, the BugFix branch will be created from the release branch.
- After fixing and testing. Bugfix branch will be merged to release branch and **back merged to develop branch** and it will be deleted.
- Creating a bugfix branch is not encouraged.

# HotFix:
- The hotfix branches are used to quickly patch production releases.
- This is the only branch that should **directly cut off from the master**.
- After the fix is complete, it should be **merged into both master & develop** and the master should be tagged with an updated version number.

# Best Practices:
- All the branches need to be restricted except feature branch.
- Code can be merged only using Merge Request(MR).
- All code will be reviewed before merging.
- Always maintain only Master, Develop, and current sprint branches.
