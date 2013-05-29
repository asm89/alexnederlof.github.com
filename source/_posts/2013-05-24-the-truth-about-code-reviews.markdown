---
layout: post
title: "The truth about code reviews"
date: 2013-05-24 16:31
comments: true
categories: Research
---
During the [International Conference of Software Engineering 2013 ](http://2013.icse-conferences.org/) I visited a great talk by [Alberto Baccheli](https://twitter.com/sback_) on modern code reviews. It resonated my experiences with code reviews and I'd like to share the highlights of [his research](http://www.inf.usi.ch/phd/bacchelli/publications/icse2013.pdf) conducted among several developers Microsoft.

I think by now most developers have come in to contact with some form of code reviewing. When you use GitHub, every pull request can be seen as a code review, among other things. When I have to explain to someone why code reviews are important, I come up with the same arguments most developers come up with:

1. Finding defects
2. Code quality improvement
3. Alternative Solutions
4. Knowledge Transfer

However, research shows a different result:

> Although the top motivation driving code reviews is still finding defects, the practice and the actual outcomes are less about finding errors than expected: Defect related comments comprise a small proportion and mainly cover small logical low-level issues

<!--more-->

So what does research show us? Here's the overview of what developers indicate is their motivation for code reviews:

{% img  /images/code-reviews-motivations.png 500 'Motivations' 'Source: ' %}

By observing developers doing code reviews, research has found quite a different outcome. In order of preference, the actual use of code reviews turns out to be:

1. __Code improvements:__ Taking up 29% of the comments are things like better code practices, removing unnecessary code, and improving readability.
2. __Understanding:__ Discussions about what the code does take up a little over 20%
3. __Social communication:__
4. __Defects:__ In contrast to what developers believe is the most important reason, defect finding comes fourth with 14% of the comments. These include logical issues, high-level issues, security issues and exception handling.

### Code Reviewing Is Understanding

So why is finding defects in fourth place instead of the first? The problem is that most pieces of code delivered in a review are hard to understand. The study reports that most defects found weren't complicated errors:

>  …most of the comments on “defects” regard uncomplicated logical errors, e.g., corner cases, common configuration values, or operator precedence.

To this extend, the researchers asked the developers and testers what activities require most understanding when giving a code review. The majority votes for a _complete_ or _high_ understanding to find defects or offer alternative solutions. Sharing code ownership and knowledge require _low_ or _high_ understanding of the code.

### Can we improve the way we review?
Most of the code reviews I do go via GitHub pull requests. Although they give an excellent textual presentation of the diff, the code is ordered alphabetically and it isn't interactive. There are a couple of ways this could be improved in my opinion:

* By showing something like a class/module/file diagram diff. This would make it easier for a developer to see in which modules most changes occurred and how those propagate through the code.
* Allow method jumping in a diff. Especially in a large diff you quickly lose the overview of where methods lead to or come from. Being able to jump from the method you're reading to the method that is being called would be a huge improvement in code diff navigation.

*N.B. All data and graphs used in this post are from the [original paper](http://www.inf.usi.ch/phd/bacchelli/publications/icse2013.pdf).*