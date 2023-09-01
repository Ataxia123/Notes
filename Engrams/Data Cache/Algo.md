## How does the Community Notes algorithm work?

Anyone with a Twitter account [matching some criteria](https://communitynotes.twitter.com/guide/en/contributing/signing-up) (basically: active for 6+ months, no recent rule violations, verified phone number) can sign up to participate in Community Notes. Currently, participants are slowly and randomly being accepted, but eventually the plan is to let in anyone who fits the criteria. Once you are accepted, you can at first participate in rating existing notes, and once you've made enough good ratings ([measured by](https://communitynotes.twitter.com/guide/en/under-the-hood/contributor-scores) seeing which ratings match with the final outcome for that note), you can also write notes of your own.

When you write a note, the note gets a score based on the reviews that it receives from other Community Notes members. These reviews can be thought of as being votes along a 3-point scale of `HELPFUL`, `SOMEWHAT_HELPFUL` and `NOT_HELPFUL`, but a review can also contain some other tags that have roles in the algorithm. Based on these reviews, a note gets a score. If the note's score is above 0.40, the note is shown; otherwise, the note is not shown.

The way that the score is calculated is what makes the algorithm unique. Unlike simpler algorithms, which aim to simply calculate some kind of sum or average over users' ratings and use that as the final result, **the Community Notes rating algorithm explicitly attempts to prioritize notes that receive positive ratings from people across a diverse range of perspectives**. That is, if people who usually disagree on how they rate notes end up agreeing on a particular note, that note is scored especially highly.

Let us get into the deep math of how this works. We have a set of users and a set of notes; we can create a matrix M, where the cell Mi,j represents how the i'th user rated the j'th note.

  

![](https://vitalik.ca/general/2023/08/16/communitynotes.html../../../../images/communitynotes/matrix.png)

  

For any given note, most users have not rated that note, so most entries in the matrix will be zero, but that's fine. The goal of the algorithm is to create a four-column model of users and notes, assigning each user two stats that we can call "friendliness" and "polarity", and each note two stats that we can call "helpfulness" and "polarity". The model is trying to predict the matrix as a function of these values, using the following formula:

  

![](https://vitalik.ca/general/2023/08/16/communitynotes.html../../../../images/communitynotes/formula.png)

  

Note that here I am introducing both the terminology used in the [Birdwatch paper](https://github.com/twitter/communitynotes/blob/main/birdwatch_paper_2022_10_27.pdf), and my own terms to provide a less mathematical intuition for what the variables mean:

- μ is a "**general public mood**" parameter that accounts for how high the ratings are that users give in general
- iu is a user's "**friendliness**": how likely that particular user is to give high ratings
- in is a note's "**helpfulness**": how likely that particular note is to get rated highly. **Ultimately, this is the variable we care about**.
- fu or fn is user or note's "**polarity**": its position among the dominant axis of political polarization. In practice, negative polarity roughly means "left-leaning" and positive polarity means "right-leaning", but note that **the axis of polarization is discovered emergently from analyzing users and notes; the concepts of leftism and rightism are in no way hard-coded**.

The algorithm uses a pretty basic machine learning model (standard [gradient descent](https://en.wikipedia.org/wiki/Gradient_descent)) to find values for these variables that do the best possible job of predicting the matrix values. The helpfulness that a particular note is assigned is the note's final score. If a note's helpfulness is at least +0.4, the note gets shown.

**The core clever idea here is that the "polarity" terms absorb the properties of a note that cause it to be liked by some users and not others, and the "helpfulness" term only measures the properties that a note has that cause it to be liked by all**. Thus, selecting for helpfulness identifies notes that get cross-tribal approval, and selects against notes that get cheering from one tribe at the expense of disgust from the other tribe.

I made a simplified implementation of the basic algorithm; you can find it [here](https://github.com/ethereum/research/blob/master/community_notes_analysis/basic_algo.py), and are welcome to play around with it.

Now, the above is only a description of the central core of the algorithm. In reality, there are a _lot_ of extra mechanisms bolted on top. Fortunately, they are described in the [public documentation](https://communitynotes.twitter.com/guide/en/under-the-hood/ranking-notes). These mechanisms include the following:

- The algorithm gets run many times, each time adding some randomly generated extreme "pseudo-votes" to the votes. This means that the algorithm's true output for each note is a range of values, and the final result depends on a "lower confidence bound" taken from this range, which is checked against a threshold of 0.32.
- If many users (especially users with a similar polarity to the note) rate a note "Not Helpful", and furthermore they specify the same "[tag](https://communitynotes.twitter.com/guide/en/under-the-hood/ranking-notes)" (eg. "Argumentative or biased language", "Sources do not support note") as the reason for their rating, the helpfulness threshold required for the note to be published increases from 0.4 to 0.5 (this looks small but it's very significant in practice)
- If a note is accepted, the threshold that its helpfulness must drop below to de-accept it is 0.01 points lower than the threshold that a note's helpfulness needed to reach for the note to be originally accepted
- The algorithm gets run _even more times_ with multiple models, and this can sometimes promote notes whose original helpfulness score is somewhere between 0.3 and 0.4

All in all, you get some pretty complicated python code that amounts to 6282 lines stretching across 22 files. But it is all [open](https://github.com/twitter/communitynotes), you can download the [note and rating data](https://communitynotes.twitter.com/guide/en/under-the-hood/ranking-notes) and run it yourself, and see if the outputs correspond to what is actually on Twitter at any given moment.
