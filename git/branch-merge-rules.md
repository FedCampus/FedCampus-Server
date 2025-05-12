# Branch/Merge rules

When you are working on a _repository you don't own_, or when you are planning on creating a _significant change_, you should create a _new feature branch_ and open a _Pull Request_ to merge against the `main` branch.

* If you have any questions regarding the content, please ask immediately.
* Editors have buttons for each of the commands below. Feel free to use them as long as you know what you are doing and they work.

Please follow the steps below.

## Create a new feature branch

Make should you are already on the latest `main`:

```sh
git switch main
git pull
```

_Name your new feature branch what it does_. For example, when writing this document about Git rules, I name it `specify-git-rules`:

```sh
git switch -c specify-git-rules
```

The above command "branches off" `main`, creates a new branch `specify-git-rules`, and "switches" to it.

Push your branch to GitHub:

```sh
git push -u origin specify-git-rules
```

This will create a new branch on GitHub called `specify-git-rules` based on `main` and set the upstream of your local branch to it.

### Find out if the branch name is taken

You need to avoid using a name that is already taken. To find out if a branch name is taken:

```sh
git branch
```

The above command shows all the branch names that are taken.

## Make the changes you need to make

* Every time before you make a commit, _review the diff_ and go over every line that you just changed. Also, be sure to spot unwanted files that are going to be committed by mistake.
* _In your commit messages, specify what the commit does_. For example, when I commit the change for this document, I use the commit message `add branch/merge rules`.
  * Ideally, you should also comment on the reason for the commit. For example, I should modify the commit message to `add branch/merge rules for collaboration instruction`.
  * If you have no idea what you should be saying in commits, please look at [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/).
*   After you make a commit, immediately push to GitHub.

    ```sh
    git push
    ```
* Do not commit to feature branches other people created! If you wish to modify them, branch off them to a new feature branch.

### Clean up mistakes in commits

*   If you have a serious typo in the commit message, or a coding mistake in your previous commit, and you don't want to create another commit, you can modify your last commit and force push it.

    ```sh
    git add .
    git commit --amend
    ```

    An editor (by default Vi) would pops up. Edit the commit message if you need to, and close the editor.

    * You probably don't want to use Vi, so see [how to change the default editor for Git](https://stackoverflow.com/questions/2596805/how-do-i-make-git-use-the-editor-of-my-choice-for-editing-commit-messages).

    Force push the overriding change you just made to GitHub:

    ```sh
    git push -f
    ```

## Make a Pull Request

Go on GitHub and create a Pull Request from your branch (`specify-git-rules`) to `main`.

* Name your Pull Request what it does.
* Further explain what the Pull Request does if needed.
* Explain why you are making this Pull Request.

Review your own Pull Request, especially the file changes. If you spot any problems, you can still fix them by making a local commit on your branch and doing a Git push.

If you are making a Pull Request in someone else's repository, it is best to ask them to review and merge it.

## Review and merge the Pull Request

Ideally, a second person should review the Pull Request.

* Fully review every line of the Pull Request.
* For any questions, reference the line and ask the person making the Pull Request.
* All questions should be answered, all problems should be fixed, before merging the Pull Request.
* If the Pull Request has any conflict with `main`, merge `main` back into the feature branch first. (Technically, a rebase is better than a merge here, but it is harder).

When the Pull Request is ready and accepted, merge it by creating a merge commit. The commit message should still describe what the commit does, followed by the Pull Request number.

It is okay to just copy the name of the Pull Request and append the Pull Request number. For example, `Specify Git branch/merge rules for collaboration instruction #1`.

### Merge conflict

When there is a conflict in the Pull Request, merge `main` into to the feature branch to make them compatible.

* If you are confused at any stage, _don't try to solve it yourself_, ask for help.
*   Make sure you are already on your feature branch. If not, switch to it:

    ```sh
    git switch specify-git-rules
    ```
*   Start to merge `main` into the feature branch:

    ```sh
    git merge main
    ```

    You should see an error saying that the merge cannot be done automatically.
* Open up your editor and _solve all the conflicts_ manually. [What conflicts look like](https://git-scm.com/docs/git-merge#_how_conflicts_are_presented). Editors usually have features that make the process easier.
* _Review the diff_ just as you would for a regular commit.
* Make a merge commit just like a regular commit, and push.
