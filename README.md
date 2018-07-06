# Collaboration Using `Git`

## Problem Statement

Two golden practices in collaborating with `git` are:

1. Keep the `master` _branch_ working at all times
2. Keep lines of work (_branches_) separate from each other

Collaboration with `git` relies on _branches_. They allow our "golden
practices". Let's explore `git` _branches_ and we'll come back to review why
these golden practices are so helpful.

## Objectives

1. Define what a `git` branch is
2. Explain branching and committing changes
3. Explain switching branches with `git checkout`
4. Explain merging branches
6. Explain the motivation of the "golden practices"

## Define What a `git` Branch is

A `git` branch is a means to separate a new set of commits or edits from
another branch. Typically we create a new branch off of `master`. If all
developers we collaborate with honor Golden Practice 1, we can trust that
`master` will be a safe starting point.

When we branch, we're creating a separate parallel universe. We can experiment
there without any bad effect. It's a contained sandbox where mistakes can be
made or ideas can incubate.

It's an idea that a lot of fiction has presented in the last 50 years.

|Parallel Universe|Source|
|-----------------|------|
|Mirror Dimension | Dr. Strange (2016)|
|Darkest Timeline | "Community" / "Inspector Spacetime" |
|The entire premise of..| "Dr. Who" |
|Mirror, Mirror (Evil Kirk / Spock) | Star Trek|
|_Plot Against America_ | Philip Roth|
|The entire plot of...| "Primer" (2004)|

If you understand multiple-timeline fiction, you get the idea of branches.

![Annie Edison Says Farewhen to the Inspector](https://gph.is/XI1yzM)

By doing work in branches, all collaborators can do work without messing with
the main line known as `master`. OK, so how can we _actually_ leverage this
reality-shattering idea?

## Explain Branching and Committing Changes

Best practices suggest that any new set of changes related to fixing a bug,
creating a feature, or even messing around with experimental code in a
"sandbox", should be started on a new branch.

In order to start a new branch, in the terminal type: `git branch <branch name>`
to create the newly defined branch.

This creates a new branch which can be seen in the branch list by typing `git
branch` in the terminal.

In the case of a branch relating to writing a new feature, you could name the
branch `add-rainbow-background`. Thus: `git branch add-rainbow-background`.
This will take the entire commit history of the branch you're on (usually
`master`) and make it available in the `add-rainbow-background` branch.

At this moment `master` and `add-rainbow-background` **are the same branches /
realities** etc.  As you add more commits on the feature branch you're changing
_only_ the `add-rainbow-background` reality. The `master` branch **will not be
affected**. Let's talk about adding those commits.

## Explain Switching Branches with `git checkout`

In order to start making changes on your new branch, you need to "checkout" or
move into the `add-rainbow-background` branch, so that `git` knows that all
commits made apply to only that branch. You can move between branches with `git
checkout <branch name>`.

> **PROTIP**: You can create and checkout a new branch in one command using:
> `git checkout -b new-branch-name`.  That will both create the branch
> `new-branch-name` and move into it by checking
> it out.

You can always move between branches with `git checkout <branch name>`. If you
are currently on `add-rainbow-background`, you can move back to `master` with
`git checkout master`. If the last branch that you switch from was `master`,
you can also type `git checkout -` in order to move back to the previous
branch.  Then to get back to `add-rainbow-background` you can switch it again
using `git checkout add-rainbow-background`.

To make sure that you don't lose work, you should make sure all your changes
are committed before you switch branches. If you're doing work in
`add-rainbow-background` that updates `style.css`, because `master` *also* has
a `style.css` file, `master` could overwrite your changes. Make sure all your
changes are committed before you switch branches.

> **ADVANCED**: `git` has a powerful feature called `stash` which can be used,
> when you're ready to hold changes-in-progress. When you're very comfortable
> with `git`, look into it!

If you add commits to  `add-rainbow-background` and then `git checkout master`,
you will see that the `master` branch only has the code up to the moment you
"branched" into the `add-rainbow-background` timeline, er, branch. The code
from our `add-rainbow-background` is tucked away in that branch, waiting
patiently in isolation from the rest of your code in `master` until the feature
is considered complete.

The final step of completing the `add-rainbow-background` work is to merge that
reality into the `master` branch.

## Explain Merging Branches

Now that you have some additions to the code that you'd like to combine back
with the `master`, the goal is to bring the branch of commits that occurred on
the `add-rainbow-background` branch into the `master`. By merging the branch,
`master` will have all of the commits from the `add-rainbow-background` branch
as though those events occurred on the `master` branch.

When merging a branch with `git merge`, it's important to be currently working
on your target branch, the branch you want to gain the content of the feature
branch. The first step for our `add-rainbow-background` merge is to checkout
`master` because that is where you want the commits to end up.

When performing `git merge -m "merge in feature add rainbow-background"` you
add a message and complete the commit in one action.

Now the branches have been merged. If you type `git log --graph`, you'll see
the commits from the `add-rainbow-background` branch on your master branch.
The `git log` command displays the history of commits for the branch you're on.
The `--graph` "flag" tells `git` to make it pretty, like a timeline.

## Explain The Motivation Of The "Golden Practices"

As developers we try to make sure that everyone has a clean place to start
from: be that for writing a new feature or fixing a bug. Branching lets us keep
`master` working at all times. If an emergency bug comes up, we know we have a
solid foundation to build from. Feature branches also help us look at `git
log` and see what the intention of a feature was.

## Conclusion

`Git` is a complex tool, and these tools are just scratching the surface for
collaborating with people. These workflows are just being introduced to
you--and it may be challenging for the time being. You'll have lots of time to
practice them and get used to what each command does. Don't try to cram it it
all in at once; instead just start to get an understanding of what is at your
disposal.

![XKCD Git](http://imgs.xkcd.com/comics/git.png)

_Do not do as stick man suggests!_

<p class='util--hide'>View <a href='https://learn.co/lessons/git-collaboration-readme'>Git Collaboration</a> on Learn.co and start learning to code for free.</p>

[vi]: https://www.youtube.com/watch?v=_NUO4JEtkDw
