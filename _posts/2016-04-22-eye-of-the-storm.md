---
layout: post
title: Eye of the Storm
---

Did you think I forgot about you? Well, your not entirely wrong. With tests around the corner and my attemp... You don't really care about my excuses do you? Well, In that case, I'm sorry about forgetting you. I will not make empty promises about the future, however, I will try to be more responsible. 

<amp-img width="1269" height="634" layout="responsive" src="http://www.goliath.com/wp-content/uploads/2015/09/underwood.png"></amp-img>

Today (or [yesterday](https://www.reddit.com/r/polyphasic/comments/4fuhiq/day_1_sptyfu/)), I learnt a little about clustering and about 1 possible implementation of such an algorithm. I was faced with the following problem:

> Given a list of points (xy coordinates), and a certain query point, find the subset of points, q such that all points in q are within some threshold distance from our query point.

Now, the first way you might think about going about this, is just filtering through the entire list of points and run a distance algorithm. If this is below our threshold, then let it through to our final list. The problem witht his solution is that it doeesn't scale too well, and it becomes computationally expensive to do this after a certain point.

Clustering is a way of grouping points that are close to each other and assigning this group a coordinate that represents the points it holds. For instance, if we had a cluster of points in Manhattan, then we can have one point instead that groups all of these individual points, and use this one point for our algorithm. This way, if you were trying to query Chicago later on, the algorithm would check if the Manhattan cluster is close to Chicago. Since it isn't, it'll ignore the entire chunk, and we can significantly reduce computation time.

Ofcourse, you can implement multiple levels of clustering and have it make a tree (Something that might represent Countries -> States -> Cities for instance?) if you wanted to. This would make for a neat data structure.

There may be a library out there that does this in JS, but regardless, I'm planning to take a stab at implementing this myself. It's good to know how things work rather than have [dependencies](http://blog.npmjs.org/post/141577284765/kik-left-pad-and-npm). Ideally, you should never have a dependency that you don't know how to implement yourself.

<amp-img width="242" height="332" layout="responsive" src="http://imgs.xkcd.com/comics/laws_of_physics.png"></amp-img>

Cheers
