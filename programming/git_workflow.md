# Git Workflow

- Centralized Workflow
- Feature Branch Workflow
- Gitflow Workflow
- Forking Workflow

`git remote add upstream https://bitbucket.org/maintainer/repo`

##Centralized Workflow

##Feature Branch Workflow
When someone completes a feature, they don’t immediately merge it into master. Instead, they push the feature branch to the central server and file a pull request asking to merge their additions into master.

Once a pull request is accepted, the actual act of publishing a feature is much the same as in the Centralized Workflow. First, you need to make sure your local master is synchronized with the upstream master. Then, you merge the feature branch into master and push the updated master back to the central repository.

##Gitflow Worlflow
- Historical Branches
- Features should never interact directly with master.

Once it's ready to ship, the release gets merged into master and tagged with a version number. In addition, it should be merged back into develop, which may have progressed since the release was initiated.

##Forking Workflow

---

References:
- https://www.atlassian.com/git/tutorials/comparing-workflows/centralized-workflow