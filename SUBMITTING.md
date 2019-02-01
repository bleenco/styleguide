## <a name="submit"></a> Submission Guidelines

### <a name="submit-issue"></a> Submitting an Issue

Before you submit an issue, please search the issue tracker, maybe an issue for your problem already exists and the discussion might inform you of workarounds readily available.

### <a name="submit-pr"></a> Submitting a Pull Request (PR)
Before you submit your Pull Request (PR) consider the following guidelines:

1. Be sure that an issue describes the problem you're fixing, or documents the design for the feature you'd like to add.
  Discussing the design up front helps to ensure that we're ready to accept your work.
1. Fork the `bleenco/*` repo you want to work on.
1. Clone your fork locally and name it `origin`.
1. Add a new remote that points to the main bleenco organisational repository and name it `upstream`
1. Make your changes in a new git branch:

     ```shell
     git checkout -b my-fix-branch master
     ```

1. Create your patch, **including appropriate test cases**.
1. Follow our [Coding Rules](/README.md).
1. Run the full test suite and ensure that all tests pass.
1. Commit your changes using a descriptive commit message that follows our
  [commit message conventions](/COMMITTING.md).

     ```shell
     git commit -a
     ```
    Note: the optional commit `-a` command line option will automatically "add" and "rm" edited files.
  * If you have more commits please squash them into one with a descriptive message.
    ```shell
      git rebase -i HEAD~<number of commits>
    ```
    * Replace "pick" with "s" from all commits except the first. Save (:wq!).
    * Comment "#" all the commit messages except the one you want to have. You can also change the message here. Save (:wq!).
  * If you think there should be two commits, please open up another PR for the second one

1. Push your branch to GitHub:

    ```shell
    git push origin my-fix-branch
    ```
1. In GitHub, send a pull request to `bleenco/*:master`.
* If we suggest change or your branch is behind the master then:
  * Make the required updates.
  * Re-run the test suites to ensure tests are still passing.
  * Rebase your branch and force push to your GitHub repository (this will update your Pull Request):

    ```shell
    git fetch upstream
    git rebase upstream/master
    git push -f
    ```

That's it!

#### After your pull request is merged

After your pull request is merged, you can safely delete your branch and pull the changes
from the main (upstream) repository:

* Delete the remote branch on GitHub either through the GitHub web UI or your local shell as follows:

    ```shell
    git push origin --delete my-fix-branch
    ```

* Check out the master branch:

    ```shell
    git checkout master -f
    ```

* Delete the local branch:

    ```shell
    git branch -D my-fix-branch
    ```

* Update your master with the latest upstream version:

    ```shell
    git rebase upstream/master
    ```
