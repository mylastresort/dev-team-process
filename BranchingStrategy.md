# Feature Branch (Branching Strategy)

## Code Flow Branches

These branches which we expect to be permanently available on the repository follow the flow of code changes starting from development until the production.

* **Development** (*dev*)

  All new features, their tests and bug fixes should be brought to the development branch. Resolving developer codes conflicts should be done as early as here.

* **Master** (*master*)

  The production branch, if the repository is published, this is the default branch being presented.

Except for Hotfixes, we want our codes to follow a one-way merge starting from development > production.

## Temporary Branches

As the name implies, these are disposable branches that can be created and deleted by need of the developer or deployer.

* **Feature**

  Any code changes for a new module or use case should be done on a feature branch. This branch is created based on the current development branch. When all changes are **Done**, a Pull Request/Merge Request is needed to put all of these to the development branch.

  Examples:
  * feature/integrate-swagger
  * feature/JIRA-1234
  * feature/JIRA-1234_support-dark-theme

It is recommended to use all lower caps letters and hyphen (-) to separate words unless it is a specific item name or ID. Underscore (_) could be used to separate the ID and description.

* **Bug Fix**

  If the code that is originally developed and reviewed on a feature branch wasn’t accepted (happens if the stakeholders or QA team found issues with the feature or decided it didn’t fully meet the requirements), it's generally better to fix the issues on a **bugfix branch** rather than trying to modify the original feature branch. This keeps the original branch clean and ensures any urgent fixes can be tracked and deployed in an organized way.

  Examples:
  * bugfix/more-gray-shades
  * bugfix/JIRA-1444_gray-on-blur-fix

  Typically this happens early in dev branch, after the changes in the PR are fully merged (the feature branch is then deleted).
  
  However if the feature branch isnt fully merged, if the team working on the feature is more than 1, its better to have bugfix branches, once reviewed, the team can merge to the feature branch. Otherwise the changes can be made on the same branch.
* **Hot Fix**

  If there is a need to do a temporary patch, apply a critical framework or configuration change that should be handled immediately, it should be created as a Hotfix. It does not follow the scheduled integration of code and could be merged directly to the production branch, then on the development branch later (merging master with dev to keep the latest changes).

  Examples:
  * hotfix/disable-endpoint-zero-day-exploit
  * hotfix/increase-scaling-threshold
    
* **Experimental**

  Any new feature or idea that is not part of a release or a sprint. A branch for playing around.

  Examples:
  * experimental/dark-theme-support
    
* **Build**

  A branch specifically for creating specific build artifacts or for doing code coverage runs.

  Examples:
  * build/jacoco-metric
    
* **Release**

  A branch for tagging a specific release version

  Examples:
  * release/myapp-1.01.123

  Git also supports tagging a specific commit history of the repository. A release branch is used if there is a need to make the code available for checkout or use.
  
* **Merging**

  A temporary branch for resolving merge conflicts, usually between the latest development and a feature or Hotfix branch.
  
  This can also be used if two branches of a feature being worked on by multiple developers need to be merged, verified and finalized.

  Examples:
  * merge/dev_lombok-refactoring
  * merge/combined-device-support


