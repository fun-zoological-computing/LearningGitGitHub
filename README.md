# Version Control and Beyond: Not Just Convenient and Effective Sharing!

[Lab Assignment 1](lab_assignment1.md)

[Lab Assignment 2](lab_assignment2.md)

[presentation](presentation.md)


Sharing for git can potentially be less work for you (a solo worker) and or you and everyone else your team. This is because git allows you to share whole software execution environments as opposed to a mere collection of files. Additionally github allows you difference your code versus your team mates with a feature a lot like track chanages, and it allows you to share and verify the buildability, and testability of the code. Finally git "stages" files, this means git helps you to keep a history of your code files as they change over time.

A functioning software project can rarely be reduced to source files alone. Sharing the source code is not sufficient to reproduce scientific results from another person, what you really need is to recreate their whole software environment. A pip virtual environment might go along way to achieving this, but virtual environments are OS and dependentant and specific to the build state and system level dependencys too.

Imagine you share just the current version of the source code you are working on as a list of files, or even just some highlighted text. Your collaborator comes back to you, and says, the code wont run, unless you `conda install` `x,y,z` apt or brew install `a,b,c,` and additionally `pip install` `d,` since `conda` had no candidate for `d`.

Then after all of those installs the person may discover that some that the `PATH` environment variable needed editing (a binary needed to be added to the path).

Also you had hacked a package `beautiful soup` in order to make it compatible with your workflow, and your friend the collaborator would have to either comment out code lines that depended on beautiful soup, or install your hacked version, or write their own implementation of your code.

Fortuntately all of these project build idiosycracies can be absorbed into `.github/workflows` in a way that means you can pre-emptively share the hacks and workarounds that make your project unique from other projects. Almost any applied project will accumulate minor hacks. The important thing is that these workarounds are very often sharable too, and it can often be less work to find out how to make github automatically apply these workarounds.

## Continous Integration
Is a version control feature, where code that can sense source code contributions and changes:
* Is triggered to run given a change of source code.
* Runs build tests, and unit tests to establish if the proposed source code revisions would "break" the current code base given a merge.

Tells you whether merging someones proposed code changes will break the upstream code branch.

## Why Git and GitHub: Beyond Mere version control.

I have come to think of GitHub Pull Requests as (MS Word) track changes for code. On a local resource, you can also Meld to difference your code with another person's proposed changes, or new changes.

Once code is moved to an online location, lots of other convenient GitHub integrations are possible, a lot of these integrations are relevant not just for code, but also for communication (research publication, project planning, type-setting, collaboration, and even now outreach).

GitHub is a Democratizing force and there is even now a research group called policy/government rules as code, which is part of Civic Makers Australia (kind of a volunteer open source code movement).

As I said, its possible to apply git and GitHub to diverse tasks using integrations. Although you should at least use github for regular de-centralized code sharing. You should also use GitHub for all of the convenient integrations, these include:

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


### Reproducibility of scientific results is a cornerstone of science. 

<!---

"Karl Popper [1, p. 45] wrote:

'We do not take even our own observations quite seriously, or accept them as scientific observations, until we have repeated and tested them. Only by such repetitions can we convince ourselves that we are not dealing with a mere isolated coincidence, but with events which, on account of their regularity and reproducibility, are in principle intersubjectively testable.'

Also, you might end up working with a team of people

--->

Direct qoute from website: https://conquaire.uni-bielefeld.de/project_proposal/

The ability to do "constant, rigorous testing and validation of research results ensures the integrity and efficiency of science...", Furthermore: "...in the words of the OECD [2](https://conquaire.uni-bielefeld.de/project_proposal/): 'Sharing and open access to publicly funded research data not only helps to maximise the research potential of new digital technologies and networks, but provides greater returns from the public investment in research.'"

<!---

Don't say this:
* Imagine eating dinner with your family, your sister at the table requests the salt shaker from you, knowing that you could pass the salt by gently pushing it along the table, or momentarily standing up and leaning towards your sister. Instead you decide to take the salt shaker outside, and place it in the families letter box, you reason that your sister looked to be busy chewing on some potato, and you thought rather than waiting for her, under the principal of asynchronous development you should allow her to fetch the salt from the letter box from a location where items are expected to enter the house at a time when she is ready, you are aware that your decision will seem a bit rude, but your sister is a developer and you think she will understand.

You realise, that she may not be expecting to look for the salt shaker to be in the letter box, but you don't talk to her while eating, so you instead walk to the post office, so the salt shaker can be placed in a box with a label, salt shaker, and also a manual on how to use the salt shaker could be included in the postage package.

When someone wants to do code collaboration with you, you might be tempted to send them a list of the latest files over email or a messenger, that would "feel" as appropriate as directly passing a salt shaker at the kitchen table. I will argue instead that sharing a git repository is a lot more like directly passing the salt shaker at the kitchen table.

My reasoning includes: "forthought", "empathy", "self-empathy", "convenience", "politeness".
--->


