
## Pull recent updates from original repository into forked.

So the accepted answer above didn't work for me perfectly. Namely, it seemed to lose the link to the original github author when it worked, and then didn't seem to work anymore after that. I think the problem was that the answer left out the / between the remote name and the branch. So it would fetch a branch called master from the remote, but then not be able to do anything with it. Not really sure why.

Here's the way [github recommends from their site][1].

Once you have cloned your forked repo, you do need to add a remote pointing to the original like the previous answer said. They like to call it upstream, but it doesn't matter.

    git remote add upstream git://github.com/octocat/Spoon-Knife.git

Then you fetch

    git fetch upstream

and you'll see the versions available for merging

	From git://github.com/octocat/Spoon-Knife.git
	 * [new branch]      gh-pages   -> upstream/gh-pages
	 * [new branch]      master     -> upstream/master

Then you just need to choose the branch you want to merge in. Mind you these aren't local branches, they are stored under remotes. But provided you don't have a local branch called upstream/master (which is allowed) you should be fine merging with the line below:

    git merge upstream/master

Alternatively you could shortcut the fetch/merge (after the initial fetch at least) with this line: 

    git pull upstream/master


  [1]: http://help.github.com/fork-a-repo/


## check remotes
git remote -v


## pushing

If you have a branch named serverfix that you want to work on with others, you can push it up the same way you pushed your first branch. 
Run 

    git push <remote> <branch>:


## git remotes

Add a new remote, fetch, and check out a branch from it
```
$ git remote
origin
$ git branch -r
  origin/HEAD -> origin/master
  origin/master
$ git remote add staging git://git.kernel.org/.../gregkh/staging.git
$ git remote
origin
staging
$ git fetch staging
...
From git://git.kernel.org/pub/scm/linux/kernel/git/gregkh/staging
 * [new branch]      master     -> staging/master
 * [new branch]      staging-linus -> staging/staging-linus
 * [new branch]      staging-next -> staging/staging-next
$ git branch -r
  origin/HEAD -> origin/master
  origin/master
  staging/master
  staging/staging-linus
  staging/staging-next
$ git switch -c staging staging/master
...
```