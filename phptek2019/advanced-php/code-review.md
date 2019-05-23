# Code Review

Slides by Steve Grunwell, Talk by Samantha Quinone

* Formal Code Review
    * Official Part of dev workflow
    * Dev -> Code Review -> Merge
    * Pair Programming
    * "Bug sweeps"
        * Usually after merge, going through things that changed that day/week
* Informal Code Review
* Catch Bugs
    * Second set of eyes
    * Catch egregious style things
        * Should be automated
* Facilitating Code Reviews
    * We try to be egalitarian, but power dynamics are prevalent!
        * Not just manager vs IC, also old vs. new, different demographics
    * Other things to consider
        * Code ownership - "Have someone from the payments team review this"
        * Learning opportunity for reviewer - e.g. X is looking to get better at testing
        * Learning opportunity for dev - e.g. first time implementing new pattern, have someone review who's most familiar with the pattern
    * Be mindful about who to assign to
    * Go to reviewer with specific request - "This is the first time doing currency conversion, can I get a second set of eyes", "Can you check for any bugs"
        * This helps avoid adversarial reviews since the scope of the review is clearly defined.
* Audience question: How to solicit meaningful reviews when you're the one with more power in the dynamic.
    * Be explicit about it.
    * Good opportunity for pair reviewing. Walk through it together, when they have a moment of "huh", take a moment to reconsider. Put the burden on yourself.
* Audience question: Checklists? They've tried checklists but they can make it a chore.
    * Look at checklist, see what can be automated. PSR-2, needs tests, etc. Pare down the checklist.
    * Checklists aren't necessarily necessary. Instead develop a code review culture where expectations are clear. Write down "here's what should be in a Pull Request" but doesn't need to be a checklist.
* Providing feedback
    * Don't bombard with comments. Before you comment, do quick read. If they're on the wrong track, "Hey I saw your PR and I had some thoughts, can we sit down together?" is much better and lets you watch body language etc.
    * Note common themes. If they do something weird 15 times, talk about it rather than putting 15 comments.
    * Give critical/negative feedback in person as much as possible.
    *
    
    
Personal takeaways:
    * I should probably do some pair reviewing - help other devs get better at reviews, and make the reviews happen promptly.