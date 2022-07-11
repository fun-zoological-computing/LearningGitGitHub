<!--![](tubeOfLondon.png)-->
## Why Git and GitHub: Beyond Mere version control.
I have come to think of GitHub Pull Requests as (MS Word) track changes for code. On a local resource, you can also Meld to difference your code with another person's proposed changes, or new changes.

Once code is moved to an online location, lots of other convenient GitHub integrations are possible, a lot of these integrations are relevant not just for code, but also for communication (research publication, project planning, type-setting, collaboration, and even now outreach).

GitHub is a Democratizing force and there is even now a research group called policy/government rules as code, which is part of Civic Makers Australia (kind of a volunteer open source code movement).

As I said, its possible to apply git and GitHub to diverse tasks using integrations. Although you should at least use github for regular de-centralized code sharing. You should also use GitHub for all of the convenient integrations, these include:

## Useful Obvious things you can achieve with Git+GitHub

Project history and branching. 
Projects with files (esp code files), that are "staged" by github are recorded and remembered. 
This recording function is a bit like the "Time Machine" Feature in Apple/MAC except that it has a more technical interface.


## Useful Non obvious things you can achieve with Git+GitHub
* Making unpublished work citable [Zendo](https://zenodo.org/).
* Hosted dashboard deployment (heroku, streamlit).
 * When deploying a data driven dashboard app, streamlit-share and heroku listen to github hooks.

* Continuous integration
For-instance I am using .github actions to build and test software that I am socially developing.
 * Travis, CircleCI
When making a personal code portfolio, node-js automatically knows how to push to github.pages.
* Communication and dissemination:
 * When I use Overleaf to write research, overleaf is integrated with Github so you can add figures using git add *.png.
To summarize, I use GitHub for everything, and on 4 out of 7 days a week I edit some kind of markdown file on GitHub.

# Why Version Control:Time-efficient, team-efficient and convenient sharing.


<!--
* Imagine eating dinner with your family, your sister at the table requests the salt shaker from you, knowing that you could pass the salt by gently pushing it along the table, or momentarily standing up and leaning towards your sister. Instead you decide to take the salt shaker outside, and place it in the families letter box, you reason that your sister looked to be busy chewing on some potato, and you thought rather than waiting for her, under the principal of asynchronous development you should allow her to fetch the salt from the letter box from a location where items are expected to enter the house at a time when she is ready, you are aware that your decision will seem a bit rude, but your sister is a developer and you think she will understand.

You realise, that she may not be expecting to look for the salt shaker to be in the letter box, but you don't talk to her while eating, so you instead walk to the post office, so the salt shaker can be placed in a box with a label, salt shaker, and also a manual on how to use the salt shaker could be included in the postage package.

When someone wants to do code collaboration with you, you might be tempted to send them a list of the latest files over email or a messenger, that would "feel" as appropriate as directly passing a salt shaker at the kitchen table. I will argue instead that sharing a git repository is a lot more like directly passing the salt shaker at the kitchen table.-->

## GitHub Pitfalls:

<!--![](tubeOfLondon.png)-->

![](tube_london_bad.png)

Classic Problem 1:
```
git pull origin master
From ssh://.../site.git
 * branch            master     -> FETCH_HEAD
...
CONFLICT (add/add): Merge conflict in admin/process_email.php
Automatic merge failed; fix conflicts and then commit the result.
```

Creating a merge conflict
In order to get real familiar with merge conflicts, the next section will simulate a conflict to later examine and resolve. The example will be using a Unix-like command-line Git interface to execute the example simulation.

$ mkdir git-merge-test
$ cd git-merge-test
$ git init .
$ echo "this is some content to mess with" > merge.txt
$ git add merge.txt
$ git commit -am"we are commiting the inital content"
[main (root-commit) d48e74c] we are commiting the inital content
1 file changed, 1 insertion(+)
create mode 100644 merge.txt
This code example executes a sequence of commands that accomplish the following.

Create a new directory named git-merge-test, change to that directory, and initialize it as a new Git repo.
Create a new text file merge.txt with some content in it.  
Add merge.txt to the repo and commit it.
Now we have a new repo with one branch main and a file merge.txt with content in it. Next, we will create a new branch to use as the conflicting merge.

$ git checkout -b new_branch_to_merge_later
$ echo "totally different content to merge later" > merge.txt
$ git commit -am"edited the content of merge.txt to cause a conflict"
[new_branch_to_merge_later 6282319] edited the content of merge.txt to cause a conflict
1 file changed, 1 insertion(+), 1 deletion(-)
The proceeding command sequence achieves the following:

create and check out a new branch named new_branch_to_merge_later
overwrite the content in merge.txt  
commit the new content
With this new branch: new_branch_to_merge_later we have created a commit that overrides the content of merge.txt

git checkout main
Switched to branch 'main'
echo "content to append" >> merge.txt
git commit -am"appended content to merge.txt"
[main 24fbe3c] appended content to merge.tx
1 file changed, 1 insertion(+)
This chain of commands checks out the main branch, appends content to merge.txt, and commits it. This now puts our example repo in a state where we have 2 new commits. One in the main branch and one in the new_branch_to_merge_later branch. At this time lets git merge new_branch_to_merge_later and see what happen!

$ git merge new_branch_to_merge_later
Auto-merging merge.txt
CONFLICT (content): Merge conflict in merge.txt
Automatic merge failed; fix conflicts and then commit the result.
BOOM 💥. A conflict appears. Thanks, Git for letting us know about this!

How to identify merge conflicts
As we have experienced from the proceeding example, Git will produce some descriptive output letting us know that a CONFLICT has occcured. We can gain further insight by running the git status command

$ git status
On branch main
You have unmerged paths.
(fix conflicts and run "git commit")
(use "git merge --abort" to abort the merge)

Unmerged paths:
(use "git add <file>..." to mark resolution)

both modified:   merge.txt
The output from git status indicates that there are unmerged paths due to a conflict. The merge.text file now appears in a modified state. Let's examine the file and see whats modified.

$ cat merge.txt
<<<<<<< HEAD
this is some content to mess with
content to append
=======
totally different content to merge later
>>>>>>> new_branch_to_merge_later
Here we have used the cat command to put out the contents of the merge.txt file. We can see some strange new additions

<<<<<<< HEAD
=======
>>>>>>> new_branch_to_merge_later
Think of these new lines as "conflict dividers". The ======= line is the "center" of the conflict. All the content between the center and the <<<<<<< HEAD line is content that exists in the current branch main which the HEAD ref is pointing to. Alternatively all content between the center and >>>>>>> new_branch_to_merge_later is content that is present in our merging branch.

https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts
How to resolve merge conflicts using the command line
The most direct way to resolve a merge conflict is to edit the conflicted file. Open the merge.txt file in your favorite editor. For our example lets simply remove all the conflict dividers. The modified merge.txt content should then look like:

this is some content to mess with
content to append
totally different content to merge later
Once the file has been edited use git add merge.txt to stage the new merged content. To finalize the merge create a new commit by executing:

git commit -m "merged and resolved the conflict in merge.txt"
Git will see that the conflict has been resolved and creates a new merge commit to finalize the merge.

Git commands that can help resolve merge conflicts
General tools
git status
The status command is in frequent use when a working with Git and during a merge it will help identify conflicted files.

git log --merge
Passing the --merge argument to the git log command will produce a log with a list of commits that conflict between the merging branches.

git diff
diff helps find differences between states of a repository/files. This is useful in predicting and preventing merge conflicts.

Tools for when git fails to start a merge
git checkout
checkout can be used for undoing changes to files, or for changing branches

git reset --mixed
reset can be used to undo changes to the working directory and staging area.

Tools for when git conflicts arise during a merge
git merge --abort
Executing git merge with the --abort option will exit from the merge process and return the branch to the state before the merge began.

git reset
Git reset can be used during a merge conflict to reset conflicted files to a know good state
https://www.atlassian.com/git/tutorials/using-branches/merge-conflicts

Classic Problem for Python development:
![json_diffs_bad.png](json_diffs_bad.png)
Sharing over git can potentially be less work for you and the other person. This is because git allows you to share whole software execution environments as opposed to a mere collection of files. Additionally github allows you difference your code versus your team mates with a feature a lot like track chanages, and it allows you to share and verify the buildability, and testability of the code.  My reasoning includes: "forthought", "empathy", "self-empathy", "convenience", "politeness".

Imagine you share just the current version of the source code you are working on as a list of files, or even just some highlighted text. Your collaborator comes back to you, and says, the code wont run, and they are right, together over hours to weeks you establish the code wont run unless you conda install `x,y,z` apt or brew install `a,b,c` and additionally pip install `d`, since conda had no candidate for `d`.

Then after all of those installs the person may discover that some that the `PATH` environment variable needed editing (a binary needed to be added to the path).

Also you had hacked a package `beautiful soup` in order to make it compatible with your workflow, and your friend the collaborator would have to either comment out code lines that depended on beautiful soup, or install your hacked version, or write their own implementation of your code.

Fortuntately all of these project build idiosycracies can be absorbed into `.github/workflows` in a way that means you can pre-emptively share the hacks and workarounds that make your project unique from other projects. Almost any applied project will accumulate minor hacks. The important thing is that these workarounds are very often sharable too, and it can often be less work to find out how to make github automatically apply these workarounds.

### AKA continous integration
Tells you whether merging someones proposed code changes will break the upstream code branch.


### Reproducibility of scientific results is a cornerstone of science.

Direct qoute from website: https://conquaire.uni-bielefeld.de/project_proposal/
"Karl Popper [1, p. 45] wrote:

'We do not take even our own observations quite seriously, or accept them as scientific observations, until we have repeated and tested them. Only by such repetitions can we convince ourselves that we are not dealing with a mere isolated coincidence, but with events which, on account of their regularity and reproducibility, are in principle intersubjectively testable.'

This ability for constant, rigorous testing and validation of research results ensures the integrity and efficiency of science. Stating it in the words of the OECD [2]: 'Sharing and open access to publicly funded research data not only helps to maximise the research potential of new digital technologies and networks, but provides greater returns from the public investment in research.'"


-- end direct qoute.

Also, you might end up working with a team of people

[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-c66648af7eb3fe8bc4f294546bfd86ef473780cde1dea487d3c4ff354943c9ae.svg)](https://classroom.github.com/online_ide?assignment_repo_id=8044640&assignment_repo_type=AssignmentRepo)


## Exercises, Take home lab instructions:


#### For Future reference only Git lessons

Learn the basics of git (as opposed to github), with these Software Carpentry lessons:

http://swcarpentry.github.io/git-novice/

## Resistance Safe Houses (cafe reviews, or nature park reviews).

Collaboration using Gitub and geojson

## Step 1: Fork this!

There are two methods to contributing on GitHub. The first and most direct is for the owner to grant push access to you. This allows you to clone their repository directly and push changes without requiring their approval. Very convenient, but also a security nightmare and a real hassle to add and remove people from the list.

<img src="images/fork.png" width="80" height="80" />


## Step  2: Adding content in geojson format

Create a new geojson file:

* Go to geojson.io and use the marker icon to place a marker at the Safehouse (cafe / bar) of your choice. This creates a Feature Collection with a geometry type Point...

<img src="images/point.png" width="120" height="120" />

* Add a short review of your safehouse. In particular add:
  * Name: Cafe name
  * Address: Cafe address
  * Review: quick review or star rating
  * Contributor: your name

<img src="images/review.png" width="120" height="120" />

* Copy the geojson text displayed in geojson.io

```
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "properties": {
        "marker-color": "#7e7e7e",
        "marker-size": "medium",
        "marker-symbol": "",
        "name": "Tsubu Bar",
        "Address": "gate 6, swanston st, building 1888 university of Melbourne 3010"
      },
      "geometry": {
        "type": "Point",
        "coordinates": [
          144.96211051940918,
          -37.79845872037568
        ]
      }
    }
  ]
}

```


## Step  3:

Start a new file in github, using the `newfile` button. You will need to do this in __Your Fork__. Make sure you:

* create this file in the `geojsons` directory (by clicking on that directory)
* name this file with the .geojson extension

Once you have created the file, paste in the contents of your geojson

## Step  4: Create a pull request

Time to create a pull request! In the main page of your `resistance-safe-houses` repository, click the `new pull request` button.

## Step  5: Merging pull requests

The owner of the repository will now 'merge' in the pull requests (after carefully reviewing the quality of each safehouse). Then `pull` the changes back to a local version of the repository on her computer.

## Step  6: Python Script merge the geojsons

In the local repository, the owner can now run`python merge_jsons.py` will merge the new files (merge all *.json files in the geojsons directory)

Don't forget to push these changes back to github..

## Step  7: Pull the upstream changes into your Fork

Run the following commands from the directory where you want to store a local copy of your repository.

First, make a local copy of the repository using `git clone`


Note see USERNAME in command below:
```
git clone https://github.com/USERNAME/resistance-safe-houses
cd resistance-safe-houses
```
There is one more thing left to do: keeping up to date with upstream. In Git upstream refers to some remote repository that you consider higher or more authoritative than yours. At the moment your local repository has one upstream repository, your GitHub repository. When you type git pull, that’s where it pulls from

```
git remote add upstream https://github.com/russelljjarvis/resistance-safe-houses.git
git fetch upstream
git merge upstream/master
git push
```
Push the merge to back to __your__ GitHub repository.

```
git push origin master
```

## Step  8: view the results

We embed the geojson into a gh-pages (project) web page here: http://russelljjarvis.github.io/resistance-safe-houses/

# Notes

## Acknowledgements

The idea came from dansand who taught this at the UoM research bazaar a long time ago.

http://dansand.github.io/resistance-safe-houses/

Dan Sand got the idea from Open Tech School:

http://opentechschool.github.io/social-coding/core/underground.html

##Rendering in github

 * Jupyter/IPython notebook (.ipynb) files will render directly on GitHub. GitHub encourage the adoption of the Jupyter notebook as a standard file format across a wide range of fields. Jupyter notebook files are a JSON-based open document format that supports code and results, narrative text, images, and equations in one file.

 * Any .geojson file in a GitHub repository will now be automatically rendered as an interactive, browsable map, annotated with your geodata.

 * images - png, etc

 * pdf

 * 3D (STL) File Viewing

## Project pages in github

## Geojson format

GeoJSON is a format for encoding a variety of geographic data structures.


The JSON format expects the keys to a dictionary to be strings. If you have other types as keys in your dictionary, trying to encode the object will produce a ValueError. One way to work around that limitation is to skip over non-string keys using the skipkeys argument:
