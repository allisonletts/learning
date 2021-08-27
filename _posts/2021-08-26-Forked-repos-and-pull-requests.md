---
Layout: post
Title: "Forked repos and pull requests"
---

I have to say, I definitely don’t have this one figured out. I was working on two separate issues tonight for the NPSP Snowfakery Sample Recipes repo. I finished up with one issue and moved onto another. Because I had initially planned to just do one chunk and then stop, I had committed everything for the first issue to `main` instead of a standalone branch… so then when I created a new branch from `main` it brought over all of my earlier issue’s commits, even though they weren’t really related to the new work. I fought through several rounds of git rebase and interactive commits before eventually giving up and just copy/pasting the contents of the ***one changed file*** in a separate standalone branch. That kind of sucked. 

I did get to use Stash, though, which was nice. As in, I have these changes that I want to use to start a new branch and not get in the way of my open PR on this branch. 