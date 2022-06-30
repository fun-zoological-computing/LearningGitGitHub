# Why Version Control: polite and convenient sharing.

* Imagine eating dinner with your family, your sister at the table requests the salt shaker from you, knowing that you could pass the salt by gently pushing it along the table, or momentarily standing up and leaning towards your sister. Instead you decide to take the salt shaker outside, and place it in the families letter box, you reason that your sister looked to be busy chewing on some potatoe, and you thought rather than weighting for him, you should allow him to fetch the salt from the letter box asychronously from a location, where items are expected to enter the house.

* You realise, that she may not be expecting the salt shaker to be in the letter box, so you instead walk to the post office, so the salt shaker can be placed in a box with a label, salt shaker, and also a manual on how to use the salt shaker could be included in the postage package.

* When someone wants to do code collaboration with you, you might be tempted to send them a list of the latest files over email or a messenger, that would "feel" as appropriate as directly passing a salt shaker at the kitchen table. I will argue instead that sharing a git repository is a lot more like directly passing the salt shaker at the kitchen table.

My reasoning includes: "forthought", "empathy", "self-empathy", "convenience", "politeness".

Sharing for git can potentially be less work for you and the other person. This is because git allows you to share whole software execution environments as opposed to a mere collection of files. Additionally github allows you difference your code versus your team mates with a feature a lot like track chanages, and it allows you to share and verify the buildability, and testability of the code. 

### AKA continous integration
Tells you whether merging someones proposed code changes will break the upstream code branch.

## Why Git and GitHub: Beyond Mere version control.

I have come to think of GitHub Pull Requests as (MS Word) track changes for code. On a local resource, you can also Meld to difference your code with another person's proposed changes, or new changes.

Once code is moved to an online location, lots of other convenient GitHub integrations are possible, a lot of these integrations are relevant not just for code, but also for communication (research publication, project planning, type-setting, collaboration, and even now outreach).

GitHub is a Democratizing force and there is even now a research group called policy/government rules as code, which is part of Civic Makers Australia (kind of a volunteer open source code movement).

As I said, its possible to apply git and GitHub to diverse tasks using integrations. Although you should at least use github for regular de-centralized code sharing. You should also use GitHub for all of the convenient integrations, these include:


* Hosted dashboard deployment (heroku, streamlit). 
 * When deploying a data driven dashboard app, streamlit-share and heroku listen to github hooks. 

* Continuous integration
For-instance I am using .github actions to build and test software that I am socially developing.
 * Travis, CircleCI
When making a personal code portfolio, node-js automatically knows how to push to github.pages. 
* Communication and dissemination:
 * When I use Overleaf to write research, overleaf is integrated with Github so you can add figures using git add *.png. 
To summarize, I use GitHub for everything, and on 4 out of 7 days a week I edit some kind of markdown file on GitHub.


### Reproducibility of scientific results is a cornerstone of science. 

Direct qoute from website: https://conquaire.uni-bielefeld.de/project_proposal/
"Karl Popper [1, p. 45] wrote:

'We do not take even our own observations quite seriously, or accept them as scientific observations, until we have repeated and tested them. Only by such repetitions can we convince ourselves that we are not dealing with a mere isolated coincidence, but with events which, on account of their regularity and reproducibility, are in principle intersubjectively testable.'

This ability for constant, rigorous testing and validation of research results ensures the integrity and efficiency of science. Stating it in the words of the OECD [2]: 'Sharing and open access to publicly funded research data not only helps to maximise the research potential of new digital technologies and networks, but provides greater returns from the public investment in research.'"


-- end direct qoute.

Also, you might end up working with a team of people

[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-c66648af7eb3fe8bc4f294546bfd86ef473780cde1dea487d3c4ff354943c9ae.svg)](https://classroom.github.com/online_ide?assignment_repo_id=8044640&assignment_repo_type=AssignmentRepo)


## Exercises, Take home lab instructions:

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

## Future of collaboration

## Git lessons

Learn the basics of git (as opposed to github), with these Software Carpentry lessons:

http://swcarpentry.github.io/git-novice/
