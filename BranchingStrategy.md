# Feature Branch (Branching Strategy)

## Code Flow Branches

These branches which we expect to be permanently available on the repository follow the flow of code changes starting from development until the production.

* **Master** (*master*)

  All new features, their tests and bug fixes should be brought to the main branch. Resolving developer codes conflicts should be done as early as here (preferably using [merge branch](#merging)), the code on master always represents a pre-release version and collects changes towards the next major release.

* **Release** (*release*)

  A branch for tagging a specific release version

  Examples:
  * release/myapp-1.x
  * release/myapp-1.1.x
  * release/myapp-1.2.x
  * release/myapp-1.2.1

  Git also supports tagging a specific commit history of the repository. A release branch is used if there is a need to make the code available for checkout or use.

### Branch semantics
  * **master** collects changes towards the next major release.
  * **release/X.Y** branches collect changes towards the next minor release.
  * **release/X.Y.Z** branches collect changes towards the next patch release.
  * New features are directed either towards master or towards **release/X.Y** branches.
  * Patch release branches **release/X.Y.Z** never receive new features, they only receive bugfixes.

### Lifetime of branches
  * When a new release branch is created, support for previous versions can be dropped.
  * Bugfixes to previous versions are only released if a suitable PR addresses them.

## Temporary Branches

As the name implies, these are disposable branches that can be created and deleted by need of the developer or deployer.

#### **Feature**

  Any code changes for a new module or use case should be done on a feature branch. This branch is created based on the current development branch. When all changes are **Done**, a Pull Request/Merge Request is needed to put all of these to the development branch.

  Examples:
  * feature/integrate-swagger
  * feature/JIRA-1234
  * feature/JIRA-1234_support-dark-theme

It is recommended to use all lower caps letters and hyphen (-) to separate words unless it is a specific item name or ID. Underscore (_) could be used to separate the ID and description.

#### **Bug Fix**

  Bugfixes can be directed either towards release/X.Y.Z, or release/X.Y, or master, depending on the intent.

  Examples:
  * bugfix/more-gray-shades
  * bugfix/JIRA-1444_gray-on-blur-fix

#### **Hot Fix**

  If there is a need to do a temporary patch, apply a critical framework or configuration change that should be handled immediately, it should be created as a Hotfix. It does not follow the scheduled integration of code and could be merged directly to the production branch, then on the development branch later (merging master with dev to keep the latest changes).

  Examples:
  * hotfix/disable-endpoint-zero-day-exploit
  * hotfix/increase-scaling-threshold
    
#### **Experimental**

  Any new feature or idea that is not part of a release or a sprint. A branch for playing around.

  Examples:
  * experimental/dark-theme-support
    
#### **Build**

  A branch specifically for creating specific build artifacts or for doing code coverage runs.

  Examples:
  * build/jacoco-metric
  
#### **Merging**

  A temporary branch for resolving merge conflicts, usually between the latest development and a feature or Hotfix branch.
  
  This can also be used if two branches of a feature being worked on by multiple developers need to be merged, verified and finalized.

  Examples:
  * merge/dev_lombok-refactoring
  * merge/combined-device-support


