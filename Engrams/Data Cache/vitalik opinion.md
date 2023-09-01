## What do I think of the algorithm?

The main thing that struck me when analyzing the algorithm is just how _complex_ it is. There is the "academic paper version", a gradient descent which finds a best fit to a five-term vector and matrix equation, and then the real version, a complicated series of many different executions of the algorithm with lots of arbitrary coefficients along the way.

Even the academic paper version hides complexity under the hood. The equation that it's optimizing is a [degree](https://en.wikipedia.org/wiki/Degree_of_a_polynomial)-4 equation (as there's a degree-2 fu∗fn term in the prediction formula, and compounding that the cost function [measures error squared](https://en.wikipedia.org/wiki/Least_squares)). While optimizing a degree-2 equation over any number of variables almost always has a unique solution, which you can calculate with fairly basic linear algebra, a degree-4 equation over many variables often has many solutions, and so multiple rounds of a gradient descent algorithm may well arrive at different answers. Tiny changes to the input may well cause the descent to flip from one local minimum to another, significantly changing the output.

The distinction between this, and algorithms that I helped work on such as [quadratic funding](https://vitalik.ca/general/2019/12/07/quadratic.html), feels to me like a distinction between an **economist's algorithm** and an **engineer's algorithm**. An economist's algorithm, at its best, values being simple, being reasonably easy to analyze, and having clear mathematical properties that show why it's optimal (or least-bad) for the task that it's trying to solve, and ideally proves bounds on how much damage someone can do by trying to exploit it. An engineer's algorithm, on the other hand, is a result of iterative trial and error, seeing what works and what doesn't in the engineer's operational context. Engineer's algorithms _are pragmatic and do the job_; economist's algorithms _don't go totally crazy when confronted with the unexpected_.

Or, as was [famously said](https://twitter.com/tszzl/status/1473156331297120256) on a related topic by the esteemed internet philosopher roon (aka tszzl):

  

![](https://vitalik.ca/general/2023/08/16/communitynotes.html../../../../images/communitynotes/roontweet.png)

  

Of course, I would say that the "theorycel aesthetic" side of crypto is necessary precisely to distinguish protocols that are [actually trustless](https://vitalik.ca/general/2021/01/05/rollup.html) from janky constructions that look fine and seem to work well but under the hood require trusting a few centralized actors - or worse, actually end up being [outright scams](https://vitalik.ca/general/2022/05/25/stable.html).

Deep learning works when it works, but it has inevitable vulnerabilities to all kinds of [adversarial machine learning](https://en.wikipedia.org/wiki/Adversarial_machine_learning) attacks. Nerd traps and sky-high abstraction ladders, if done well, can be quite robust against them. And so one question I have is: **could we turn Community Notes itself into something that's more like an economist algorithm**?

To give a view of what this would mean in practice, let's explore an algorithm I came up with a few years ago for a similar purpose: [pairwise-bounded quadratic funding](https://ethresear.ch/t/pairwise-coordination-subsidies-a-new-quadratic-funding-design/5553).

  

![](https://vitalik.ca/general/2023/08/16/communitynotes.html../../../../images/communitynotes/pairwiseqf.png)

  

The goal of pairwise-bounded quadratic funding is to plug a hole in "regular" quadratic funding, where if even two participants collude with each other, they can each contribute a very high amount of money to a fake project that sends the money back to them, and get a large subsidy that drains the entire pool. In pairwise quadratic funding, we assign each pair of participants a limited budget M. The algorithm walks over all possible pairs of participants, and if the algorithm decides to add a subsidy to some project P because both participant A and participant B supported it, that subsidy comes out of the budget assigned to the pair (A,B). Hence, even if k participants were to collude, the amount they could steal from the mechanism is at most k∗(k−1)∗M.

An algorithm of _exactly_ this form is not very applicable to the Community Notes context, because each user makes very few votes: on average, any two users would have exactly zero votes in common, and so the algorithm would learn nothing about users' polarities by just looking at each pair of users separately. The goal of the machine learning model is precisely to try to "fill in" the matrix from very sparse source data that cannot be analyzed in this way directly. But the challenge of this approach is that it takes extra effort to do it in a way that does not make the result highly volatile in the face of a few bad votes.

### Does Community Notes actually fight polarization?

One thing that we could do is analyze whether or not the Community Notes algorithm, as is, actually manages to fight polarization _at all_ - that is, whether or not it actually does any better than a naive voting algorithm. Naive voting algorithms already fight polarization to some limited extent: a post with 200 upvotes and 100 downvotes does worse than a post that just gets the 200 upvotes. But does Community Notes do better than _that_?

Looking at the algorithm abstractly, it's hard to tell. Why wouldn't a high-average-rating but polarizing post get a strong polarity _and_ a high helpfulness? The idea is that polarity is supposed to "absorb" the properties of a note that cause it to get a lot of votes if those votes are conflicting, but does it actually do that?

To check this, I ran [my own simplified implementation](https://github.com/ethereum/research/blob/master/community_notes_analysis/basic_algo.py) for 100 rounds. The average results were:

```
Quality averages:
Group 1 (good): 0.30032841807271166
Group 2 (good but extra polarizing): 0.21698871680927437
Group 3 (neutral): 0.09443120045416832
Group 4 (bad): -0.1521160965793673
```

In this test, "Good" notes received a rating of +2 from users in the same political tribe and +0 from users in the opposite political tribe, and "Good but extra polarizing" notes received a rating of +4 from same-tribe users and -2 from opposite-tribe users. Same average, but different polarity. And it seems to actually be the case that "Good" notes get a higher average helpfulness than "Good but extra polarizing" notes.

One other benefit of having something closer to an "economist's algorithm" would be having a clearer story for how the algorithm is penalizing polarization.

## How useful is this all in high-stakes situations?

We can see some of how this works out by looking at one specific situation. About a month ago, Ian Bremmer complained that a highly critical Community Note that was added to a tweet by a Chinese government official [had been removed](https://twitter.com/ianbremmer/status/1676590373727088647).

  

![](https://vitalik.ca/general/2023/08/16/communitynotes.html../../../../images/communitynotes/chinanote.png)

_The note, which is now no longer visible. Screenshot by [Ian Bremmer](https://twitter.com/ianbremmer)._

  

This is heavy stuff. It's one thing to do mechanism design in a nice sandbox Ethereum community environment where the largest complaint is $20,000 [going to a polarizing Twitter influencer](https://vitalik.ca/general/2020/01/28/round4.html). It's another to do it for political and geopolitical questions that affect many millions of people and where everyone, often quite understandably, is assuming maximum bad faith. But if mechanism designers want to have a significant impact into the world, engaging with these high-stakes environments is ultimately necessary.

In the case of Twitter, there is a clear reason why one might suspect centralized manipulation to be behind the Note's removal: Elon has a lot of [business interests in China](https://www.nbcnews.com/tech/elon-musks-business-ties-china-draw-scrutiny-twitter-purchase-rcna26057), and so there is a possibility that Elon forced the Community Notes team to interfere with the algorithm's outputs and delete this specific one.

Fortunately, the algorithm is open source and verifiable, so we can actually look under the hood! Let's do that. The URL of the original tweet is [`https://twitter.com/MFA_China/status/1676157337109946369`](https://twitter.com/MFA_China/status/1676157337109946369). The number at the end, `1676157337109946369`, is the tweet ID. We can search for that in the [downloadable data](https://communitynotes.twitter.com/guide/en/under-the-hood/ranking-notes), and identify the specific row in the spreadsheet that has the above note:

  

![](https://vitalik.ca/general/2023/08/16/communitynotes.html../../../../images/communitynotes/commandline1.png)

  

Here we get the ID of the note itself, `1676391378815709184`. We then search for _that_ in the `scored_notes.tsv` and `note_status_history.tsv` files generated by running the algorithm. We get:

  

![](https://vitalik.ca/general/2023/08/16/communitynotes.html../../../../images/communitynotes/commandline2.png)

![](https://vitalik.ca/general/2023/08/16/communitynotes.html../../../../images/communitynotes/commandline3.png)

  

The second column in the first output is the note's current rating. The second output shows the note's history: its current status is in the seventh column (`NEEDS_MORE_RATINGS`), and the first status that's not `NEEDS_MORE_RATINGS` that it received earlier on is in the fifth column (`CURRENTLY_RATED_HELPFUL`). Hence, we see that **the algorithm itself first showed the note, and then removed it once its rating dropped somewhat - seemingly no centralized intervention involved**.

We can see this another way by looking at the votes themselves. We can scan the `ratings-00000.tsv` file to isolate all the ratings for this note, and see how many rated `HELPFUL` vs `NOT_HELPFUL`:

  

![](https://vitalik.ca/general/2023/08/16/communitynotes.html../../../../images/communitynotes/commandline4.png)

  

But if you sort them by timestamp, and look at the first 50 votes, you see 40 `HELPFUL` votes and 9 `NOT_HELPFUL` votes. And so we see the same conclusion: the note's initial audience viewed the note more favorably then the note's later audience, and so its rating started out higher and dropped lower over time.

Unfortunately, the exact story of _how_ the note changed status is complicated to explain: it's not a simple matter of "before the rating was above 0.40, now it's below 0.40, so it got dropped". Rather, the high volume of `NOT_HELPFUL` replies triggered one of the [outlier conditions](https://communitynotes.twitter.com/guide/en/under-the-hood/ranking-notes#tag-outlier-filtering), increasing the helpfulness score that the note needs to stay over the threshold.

This is a good learning opportunity for another lesson: making a credibly neutral algorithm truly _credible_ requires [keeping it simple](https://vitalik.ca/general/2018/11/25/central_planning.html). If a note moves from being accepted to not being accepted, there should be a simple and legible story as to why.

**Of course, there is a totally different way in which this vote could have been manipulated: brigading**. Someone who sees a note that they disapprove of could call upon a highly engaged community (or worse, a mass of fake accounts) to rate it `NOT_HELPFUL`, and it may not require that many votes to drop the note from being seen as "helpful" to being seen as "polarized". Properly minimizing the vulnerability of this algorithm to such coordinated attacks will require a lot more analysis and work. One possible improvement would be not allowing any user to vote on any note, but instead using the "For you" algorithmic feed to randomly allocate notes to raters, and only allow raters to rate those notes that they have been allocated to.