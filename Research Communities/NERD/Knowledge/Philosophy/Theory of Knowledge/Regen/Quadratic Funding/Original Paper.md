> A Flexible Design for Funding Public Goods

  

Vitalik Buterin

  

+-----------------------+-----------------------+-----------------------+

| > arXiv:1809.06421v2  | > Ethereum            |                       |

| > \[econ.GN\] 16 Aug  | > Foundation\         |                       |

| > 2020                | > Zo¨e Hitzig\        |                       |

|                       | > Harvard University, |                       |

|                       | >                     |                       |

|                       | zhitzig@g.harvard.edu |                       |

|                       | >                     |                       |

|                       | > E. Glen Weyl\       |                       |

|                       | > Microsoft Research, |                       |

|                       | > g                   |                       |

|                       | lenweyl@microsoft.com |                       |

|                       | >                     |                       |

|                       | > We propose a design |                       |

|                       | > for philanthropic   |                       |

|                       | > or publicly-funded  |                       |

|                       | > seeding to allow    |                       |

|                       | > (near) optimal      |                       |

|                       | > provision of a      |                       |

|                       | > decentralized,      |                       |

|                       | > self-organizing     |                       |

|                       | > ecosystem of public |                       |

|                       | > goods. The concept  |                       |

|                       | > extends ideas from  |                       |

|                       | > Quadratic Voting to |                       |

|                       | > a funding mechanism |                       |

|                       | > for endogenous      |                       |

|                       | > community           |                       |

|                       | > formation. Citizens |                       |

|                       | > make public goods   |                       |

|                       | > contributions to    |                       |

|                       | > projects of value   |                       |

|                       | > to them. The amount |                       |

|                       | > received by the     |                       |

|                       | > project is          |                       |

|                       | > (proportional to)   |                       |

|                       | > the square of the   |                       |

|                       | > sum of the square   |                       |

|                       | > roots of            |                       |

|                       | > contributions       |                       |

|                       | > received. Under the |                       |

|                       | > "standard model"    |                       |

|                       | > this mechanism      |                       |

|                       | > yields first best   |                       |

|                       | > public goods        |                       |

|                       | > provision.          |                       |

|                       | > Variations can      |                       |

|                       | > limit the cost,     |                       |

|                       | > help protect        |                       |

|                       | > against collusion   |                       |

|                       | > and aid             |                       |

|                       | > coordination. We    |                       |

|                       | > discuss             |                       |

|                       | > applications to     |                       |

|                       | > campaign finance,   |                       |

|                       | > and highlight       |                       |

|                       | > directions for      |                       |

|                       | > future analysis and |                       |

|                       | > experimentation.    |                       |

|                       | >                     |                       |

|                       | > Key words: public   |                       |

|                       | > goods, free rider   |                       |

|                       | > problem, mechanism  |                       |

|                       | > design              |                       |

+=======================+=======================+=======================+

|                       | ****1.****                | > ****Introduction****    |

+-----------------------+-----------------------+-----------------------+

|                       | > In many contexts, a |                       |

|                       | > sponsor with        |                       |

|                       | > capital wishes to   |                       |

|                       | > stimulate and       |                       |

|                       | > support the         |                       |

|                       | > creation of pub-lic |                       |

|                       | > goods but is        |                       |

|                       | > ill-informed about  |                       |

|                       | > the appropriate     |                       |

|                       | > goods to create.    |                       |

|                       | > Thus, such a        |                       |

|                       | > sponsor may want to |                       |

|                       | > delegate this       |                       |

|                       | > allocation to a     |                       |

|                       | > decentralized       |                       |

|                       | > market process.     |                       |

|                       | > Examples of these   |                       |

|                       | > contexts include    |                       |

|                       | > campaign finance,   |                       |

|                       | > funding open source |                       |

|                       | > software, public or |                       |

|                       | > charitable support  |                       |

|                       | > for news media and  |                       |

|                       | > the funding of      |                       |

|                       | > intraurban public   |                       |

|                       | > projects. Recent    |                       |

|                       | > work on the theory  |                       |

|                       | > of Quadratic Vot-   |                       |

+-----------------------+-----------------------+-----------------------+

  

> ing (henceforth QV; see Posner and Weyl 2017 for a survey) suggests

> that near-optimal collective decision-making may be feasible in

> practice, but relies on an assumption of a fixed set of commu-nities

> and public goods that is inappropriate to this context. In this paper

> we propose an extension of the logic of QV to this setting.

>

> The basic problem we address can be seen by comparing two extreme ways

> of funding such a ecosystem, both of which are problematic. On the one

> hand, a simple private contributory system famously leads to the

> under-provision of public goods that benefit many people because of

> the free-rider problem (Samuelson 1954). The larger the number of

> people the benefit is split amongst, the greater the proportional

> under-provision. Conversely, a system based purely on membership

  

1

  

  -----------------------------------------------------------------------

  2                                   ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

or on some other one-person-one-vote (1p1v) system cannot reflect how

important various goods are to individuals and will tend to suppress

smaller organizations of great value. We aim to create a system that is

as flexible and responsive as the market, but avoids free-rider

problems.

  

Our solution is to modify the funding principle underlying the market to

make it nonlinear. In a standard linear private market, the funding

received by a provider is the sum of the contri-butions made by the

funders. In our "Quadratic Finance" (QF) mechanism, the funding received

by a provider is the square of the sum of the square roots of the

contributions made by the fun-ders. Holding fixed contribution amounts,

funding thus grows with the square of the number of members. However,

small contributions are heavily subsidized (as these are the most likely

to be distorted by free-riding incentives) while large ones are least

subsidized, as these are more like private goods. Under the standard

selfish, independent, private values, quasi-linear utility frame-work,

our mechanism leads to the utilitarian optimal provision of a

self-organizing ecosystem of public goods.

  

Existing systems such as matching funds for infrastructure projects,

political campaigns, char-itable contributions, and other public goods

aim to capture similar benefits, but do so in an unsystematic way. For

example, a variety of public goods are funded through matching

pro-grams, whereby an institutional body (a government, corporation,

political party, etc.) matches individual contributions either 1:1 or in

some other ratio. For example, New York City matches small contributions

to campaigns for elected office (city council, mayor, comptroller,

public advo-cate), matching contributions 6:1 and up to \$175. Many

corporations use similar rules: one of our employers matches charitable

contributions by all full-time employees up to \$15,000 a year. Doing so

amplifies small contributions, incents more contributions and greater

diversity in potential contributors, and confers a greater degree of

influence on stakeholders in determining ultimate funding allocations.

  

Matching programs are not only common in public and charitable funding,

but also follow an intuitive logic that has built a variety of public

policies. Indeed, the very idea of tax deductibil-ity for charitable

contributions is a form of governmental matching. But while matching

funds share the spirit of our funding principle, they lack a systematic

design. Funding ratios and match thresholds are often set in largely

arbitrary ways. The QF mechanism can be seen as offering a coherent

design that captures the central motivation of matching funds in a

mechanism that is (approximately) optimal from the perspective of

economic theory.

  

We begin the paper in Section 2 by providing background on the economic

theory of public goods. We then develop a simple but general

mathematical model in Section 3 of public good provision and use it to

illustrate the failures of both private contributory systems (Bergstrom

et al. 1986) and 1p1v (Bowen 1943). Then in Section 4, we describe QF

formally in a simple model. We

  

  -----------------------------------------------------------------------

  ****Buterin, Hitzig, and Weyl:**** A    3

  Flexible Design for Funding Public  

  Goods                               

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

show mathematically that QF leads to optimal public goods provision. We

then turn, in Section 5, to variations and extensions that enrich our

understanding of QF and its range of applications.

  

Having developed this apparatus, we change gears in Section 6 to

describing one application of QF in detail, to campaign finance reform.

We also briefly describe how QF may be applied to open source software

ecosystems, news media finance, charitable giving and urban public

projects, and how QF aligns with qualitative features of previous

solutions while more smoothly covering a wider range of cases and

problems. We conclude the paper in Section 7 with a discussion of

directions for future research and experimentation.

  

****2.**** ****Background****

  

****2.1.**** ****Public Goods Problems****\

One of the most fundamental problems in political economy is variously

known as the "free-rider", "collective action" or "public goods"

problem; we will use the term "public goods". All these terms refer to

situations in which individuals can or do receive benefits from shared

resources and investments that may be more valuable than the

contribution they individually make to those resources. These goods

cannot be efficiently priced due to the expense or ineffi-ciency

required to exclude individuals from access. By "public good" we refer

to any activity with increasing returns in the sense that the socially

efficient price to charge for the activity (marginal cost) is

significantly below the average cost of creating the good.

  

Seen in this broader light, public goods are at the core of human

flourishing. Civil society sustains itself precisely because the whole

is greater than the sum of its parts. Contemporary economic thought has

increasingly emphasized the centrality of increasing returns, especially

through investment in innovation and knowledge, to development,

beginning with the work of Romer (1986). As the exploding literature on

agglomeration and spatial economics emphasizes, the cities that created

the idea of middle classes (viz. bourgeoisie) and the citizen could not

exist without increasing returns (Krugman 1991). Yet, despite this

centrality, classical capitalism deals poorly with such activities.

Because each individual, if she acts selfishly, only accounts for the

benefits she receives and not the benefits to all other individuals,

funding levels will not scale with the number of individual

beneficiaries as would be desirable.

  

A range of institutions have emerged to address the public goods problem

in modern society. The most canonical and perhaps the most important

institution that coordinates provision of pub-lic goods is the

contemporary democratic nation state. Such states use taxation and

voting-based governance systems to determine which public goods should

be provided. The other most preva-lent method for addressing public

goods involves converting them to private goods by imposing

  

  -----------------------------------------------------------------------

  4                                   ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

technologies (e.g. walls, fee collectors at parks, digital rights

management for information, etc.) that allow individuals to be excluded.

Other institutions draw on moral, cultural, religious or social motives

to induce individuals to contribute to charitable providers of public

goods. Some intermediate institutions mix elements of these three ideal

types.1\

Unfortunately, all of these institutions have limitations. 1p1v

democratic systems (even when they work appropriately) respond to the

will of the majority, not necessarily to what would cre-ate the greatest

overall value. They often oppress minorities or are subverted by

minorities to avoid such oppression. They are also costly to set up,

rigid and do not easily adapt to demands for different and new levels of

organization. Private (usually corporate) exclusion-based efforts are,

while more flexible, usually cumbersome and costly to impose, often lack

effective feedback mechanisms that ensure they serve the interests of

their members and, perhaps most importantly, inefficiently exclude

potential users. Charitable organizations are often more responsive and

flex-ible than either of the other forms, but they rely on motives that

can be difficult to closely align reliably with the common good outside

of the relatively small groups in which they are often very effective

(Ostrom 1990). Outside such groups the often instead get captured by

status motivations and parochial, even exclusionary, interests.2

  

****2.2.**** ****Literature****\

Clarke (1971) and Groves (1973), recasting the insights of Vickrey

(1961), proposed a solution to the collective action problem, in the

form of a mechanism for individuals to reveal their prefer-ences over

public goods to a government or other central clearinghouse to overcome

the rigidity and inefficiency of majority rule. This system, known as

the VCG mechanism, was shown in Green and Laffont (1977, 1979) to be the

only dominant strategy incentive-compatible mechanism for producing

public goods. The system is fragile to collusion and risky for

participants. Though Smith (1980) showed that variants of VCG succeed in

laboratory experiments, others have con-cluded that VCG mechanisms are

generally impractical (Rothkopf 2007).

  

+-----------------+-----------------+-----------------+-----------------+

| Other           | mechanisms for  | near-optimal    | > been          |

|                 |                 | collective      | > proposed.     |

|                 |                 | decision-making |                 |

|                 |                 | have            |                 |

+=================+=================+=================+=================+

+-----------------+-----------------+-----------------+-----------------+

  

Groves and Ledyard (1977) and Hylland and Zeckhauser (1979) both

suggested a quadratic mechanism for determining the level of continuous

public goods. But, their methods require either a centralized iterative

process or depend heavily on a strong assumption of complete

infor-mation, and they do not, in general, satisfy individual

rationality. The basic insight of quadratic pricing of collective

choices reemerged recently in Weyl (2012)'s proposal for what he called

  

1 One example of an institution that mixes these ideal types is a local

government with some ability to exclude, which citizens can move across

at some cost and to which they have some loyalty (and thus often donate

their time). Another example is an exclusive but not-for profit club.

  

2 See Reich (2018) for a discussion of these issues in the context of

contemporary American capitalism.

  

  -----------------------------------------------------------------------

  ****Buterin, Hitzig, and Weyl:**** A    5

  Flexible Design for Funding Public  

  Goods                               

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

"Quadratic Vote Buying". In particular, he proposed allowing individuals

to buy votes, paying the square of the votes they buy. He argued, and

Lalley and Weyl (2018) proved, that under stan-dard assumptions (similar

to those we use below) in large populations QV leads to approximately

optimal decisions on public goods.

  

However, while QV addresses the inefficiency of standard 1p1v voting

systems for a given set of decisions and collectives, it doesn't solve

the problem of flexibility. That is, it does not allow the set of public

goods to emerge from a society organically, and effectively assumes a

previously-specified organizational structure that has to be taken as an

assumption or imposed by an author-ity. In this paper we extend the

ideas around QV to address these limitations. In sum, our mech-anism

improves on existing mechanisms by allowing for greater flexibility in

the set of goods to be funded, by eliminating the assumption of complete

information and by satisfying individual rationality constraints.

  

****3.**** ****Model****

  

We develop a flexible model for a society choosing which public goods to

fund. Consider a society of N citizens i = 1,\...N. We assume throughout

what follows that we can verifiably distinguish among and identify these

citizens, though we will discuss the possibility that they may collude

(see 5.2 below). We use the term "society" to refer to the set of all

participants and the word "com-munity" to refer to groups that fund a

particular public good; however, in many applications, the relevant

"society" is itself a community within a broader setting.

  

There is a set of potential public goods P. We do not make any

assumption about the nature of this set. There may be measure theoretic

issues for some cardinalities of the set, but we will ignore these

issues in our first presentation of the basic idea. In particular, there

is no sense in which the set of public goods need be specified

externally or in advance; any citizen may at any time propose a new

public good. We denote a typical public good p ∈ P.

  

****3.1.**** ****Individual preferences and actions****\

Let Vp i(F p) be the currency-equivalent utility citizen i receives if

the funding level of public good p is Fp. We assume all public goods

generate independent value to citizens (no interactions across public

goods) and that citizens have quasi-linear utility denominated in units

of currency. We also assume a setting of complete information, though

given the flexible set up of the problem, our results do not rely

heavily on this assumption. We also abstract away from issues about

observ-ability and timing of contributions.

  

Our interest here is in maximization of dollar-equivalent value rather

than achieving an equi-table distribution of value (we assume that an

equitable distribution of basic resources has been

  

  -----------------------------------------------------------------------

  6                                   ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

achieved in some other manner, such as an equal initial distribution of

resources). For purposes of simplifying the analysis below, we assume

all functions Vp iare concave, smooth and increasing. Absent these

assumptions some complications may arise (as we return to in 5.5) but it

is easier to abstract from them in presenting the core ideas.

  

Each citizen i can make contributions to the funding of each public good

p out of her personal resources cp i. The total utility of citizen i is

then

  

+-----------------------+-----------------------+-----------------------+

|                      | > Vp i(F p) − cp i−   | \(1\)                 |

|                       | > ti                  |                       |

+=======================+=======================+=======================+

+-----------------------+-----------------------+-----------------------+

  

where ti is a tax imposed on individual i. In this framework, different

funding mechanisms for public goods are different formulae for relating

{Fp}p∈P to {cp i}i∈I,p∈P, with any surplus or deficit being made up for

by taxes that do not influence behavior.

  

****3.2.**** ****Funding mechanisms****\

A funding mechanism in our flexible public goods setting defines the

total amount of funding received for each good in the set P, given all

individual contributions cp i. Formally, a mechanism is a mapping from

the set of all individual contributions to funding levels for all goods.

The 2,\...,cp N) where subscripts index set of individual contributions

is comprised of vectors cp= (cp 1,cp citizens. Thus, cpis a vector in

RN, and we denote by C\|P \|the space of all possible collections of

funding levels for each good p given contributions from the N citizens,

i.e. {cp}p∈P . The set of all final funding levels for all goods p ∈ P

is the set F, which has \|P\| real-valued elements F = (F1,F2,\...,F\|P

\|), with Fp∈ R.

  

DEFINITION 1 (FUNDING MECHANISMS). A funding mechanism Φ : C\|P \|→ F

determines the i) = {F p}p∈P.3 total level of funding for each good p ∈

P, such that Φ(cp\

Budget balance requires thatindividual contributions and total funding

levels. Before studying such mechanisms, however, iti = p(F p − \

icp i), i.e. taxes make up for any deficit between

  

we consider what social welfare maximization requires. Our analysis here

is the special case of Samuelson's analysis in the case of quasi-linear

utility.

  

****3.3.**** ****Welfare and optimality****\

Given the simple set up of our model, welfare calculations are

straightforward. Total social wel-

  

+-----------+-----------+-----------+-----------+-----------+-----------+

| fare is   |          |         | Vp i(F    | > − Fp    | \(2\)     |

|           |           |           | p)       |           |           |

+===========+===========+===========+===========+===========+===========+

+-----------+-----------+-----------+-----------+-----------+-----------+

  

3 In a slight abuse of notation, we will sometimes use Φ to refer to the

subcomponent Φp which maps individual contributions to good p into

funding levels Fpfor that particular good p.

  

****Buterin, Hitzig, and Weyl:**** A Flexible Design for Funding Public

Goods\

7

  

iV p i(F p) be the total value all citizens derive from the by the

budget constraint. Let Vp(Fp) ≡\

Maximizing Vp(Fp) over all weakly positive funding levels {Fp}p∈P for

all goods, given con-cavity and smoothness of the V functions gives a

simple solution: Fpis 0 if Vp′(0) ≤ 1; Fptakes on the unique value

satisfying Vp′= 1 otherwise. That is, the total marginal value derived

from the good should equal 1.

  

DEFINITION 2 (OPTIMALITY). A funding mechanism Φ is optimal if for all p

∈ P: (i) Vp′(0) ≤ 1 implies Fp= 0, and (ii) Vp′(0) \> 1 implies Vp′= 1.

  

****3.4.**** ****Suboptimal mechanisms****\

We now consider two suboptimal funding mechanisms. The first, which we

refer to as "private contributions", has the total contributions exactly

equal to the sum of individual contributions, as analyzed in Bergstrom

et al. (1986). There is no centralized funding based on individual

contribu-tions, and thus no need for taxes or transfers.

  

> DEFINITION 3 (PRIVATE CONTRIBUTIONS MECHANISM). Under private

> contributions,

  

+-----------+-----------+-----------+-----------+-----------+-----------+

| {Fp}p∈P = |         | cp i      |          | p∈P       | > .       |

| Φpriv(cp  |           |           |           |           |           |

| i) =      |           |           |           |           |           |

+===========+===========+===========+===========+===========+===========+

+-----------+-----------+-----------+-----------+-----------+-----------+

  

Note that ti = 0 under private contributions. This mechanism corresponds

to the traditional for-mula used for charitable giving; while there are

sometimes public matching funds that linearly scale contributions, these

will not greatly change our conclusions, which closely follow the

anal-ysis of Bergstrom et al.4In this case, every citizen i seeks to

maximize, in determining her contri-bution to good p

  

> Vp i cp j− cp i. (3)

  

PROPOSITION 1 ****(Suboptimality of Private Contributions)****. The private

contributions mechanism Φprivis suboptimal.

  

****Proof.**** Maximization requires (differentiating) that for any citizen

i making a positive contribu-tion to good p that\

Vp′i(F p) = 1.

  

That is, the level funding must be such that a single citizen's marginal

value equals 1. Summing across citizens, Vp′= 1 only when cp i\> 0 for a

single i, and cp j= 0 for all j ̸= i. When there is more than one

contribution to good p, generically Vp′\> 1.

  

4 An extension that accounts for linear matching funds would simply add

a scaling factor to private contributions. This mechanism for linearly

scaled financing, which we might call ΦLFhas total funding defined by

ΦLF(cp i) = {iαcp i}p∈P , with α \> 1. This scaling factor clearly does

not change our analysis, it simply scales the degree of under-funding.

  

  -----------------------------------------------------------------------

  8                                   ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

If a large set of citizens benefit significantly from a public good,

this will typically lead to severe underfunding. For example, if all

citizens are homogeneous, this is equivalent to Vp′= N, or setting the

total marginal utility of the good to N times the level it should be at.

When citizens have heterogeneous preferences, matters are even worse, at

least from a distributive perspective: only the single citizen who cares

most on the margin about the good has any influence on its provision.

Matters are more pessimistic yet if citizens can make negative

contributions (privatize public goods), as then the lowest valuation

citizen determines the provision level.5\

Another mechanism, which we will call "1p1v" works as follows. Majority

voting determines whether to fund each public good, and the goods

selected receive funding through taxes and transfers.

  

> DEFINITION 4 (1P1V MECHANISM). The 1p1v Mechanism Φ1p1vsatisfies

  

{Fp}p∈P = Φ1p1v(cp i) = {N · \[MedianiV p′FP= 1\]}p∈P .

  

Clearly 1p1v does not lead to optimality, as the mean must be used in

the above formula rather than the median to recover Vp′= 1, as Bowen

(1943) observed. Bergstrom (1979b) discussed the situations under which

the mean is likely to be a good approximation for the median, and

demonstrated the generic inefficiency of 1p1v type systems.

  

PROPOSITION 2 ****(Suboptimality of 1p1v )****. The 1p1v Mechanism Φ1p1vdoes

not guarantee optimal funding levels.

  

****Proof.**** In order for Φ1p1vto recover optimal funding levels, it must

be that ∀p ∈ P,

  

+--------+--------+--------+--------+--------+--------+--------+--------+

| Media  | FP   | > = 1  | N      | Vp′i   | FP   | > .    | \(4\)  |

| niVp′i |        | > N    |        |        |        |        |        |

+========+========+========+========+========+========+========+========+

|        |        |        |       |        |        |        |        |

+--------+--------+--------+--------+--------+--------+--------+--------+

  

The fact that condition (4) implies efficient funding follows from

quasilinear utility (so that Vp′i(F p) is monotone and decreasing).

While there are some cases in which (4) will hold, as dis-cussed in

Bowen (1943), it may be that

  

+-----------+-----------+-----------+-----------+-----------+-----------+

| Me        | F P \>  | N         | Vp′i      | > F P   | \(5\)     |

| dianiVp′i | 1 N       |           |           |           |           |

+===========+===========+===========+===========+===========+===========+

|           |           |          |           |           |           |

+-----------+-----------+-----------+-----------+-----------+-----------+

  

5 Ackerman and Ayres (2002) suggest a system that sounds superficially

different from purely private contributions but will typically lead to

similar results. They suggest every citizen be compelled to give some

fixed amount to public goods (in fact, they suggest funding this using

progressive taxes, but from the efficiency perspective we take here

these are basically equivalent). If there is a constrained set of public

goods, this may have some impact in raising overall funding levels, but

will not move things much towards optimality. But if there is a

sufficiently rich set of goods, such that each individual has a good

that is equivalent to giving the money back to herself, this yields just

the same result as capitalism: every individual uses the money to pay

herself back, unless she has the greatest value for the public good.

  

****Buterin, Hitzig, and Weyl:**** A Flexible Design for Funding Public

Goods\

9

  

or\

N\

MedianiVp′i \<1 Vp′i (6) FP N FP\

and thus, generically, Φ1p1vis not always efficient. Depending on

whether (4), (5), or (6) holds, it may be that: (i) Vp′= 1, (ii) Vp′\<

1, or (iii) Vp′\> 1. That is Φ1p1vmay recover optimal funding levels, or

lead to over or under funding on the margin.

  

Public good funding levels will tend to be higher and probably more

accurate than under purely private contribution schemes, which is likely

why most developed countries use demo-cratic mechanisms for determining

levels of public goods. However, clearly the median is often a poor

approximation for the mean, especially for goods of value to smaller

communities or for"entrepreneurial public goods," the value of which is

not widely understood at the time of fund-ing. Such goods may well

receive no funding from 1p1v---indeed, in practice small communities and

entrepreneurial public goods are often funded primarily by charity or

other private contrib-utory schemes rather than 1p1v.

  

Some improvements on 1p1v are possible. Bergstrom (1979a,b) argued that

if there is some proxy for which citizens will benefit most from a good

and we can tax them for it, 1p1v systems yield better outcomes. In such

settings, everyone will agree on whether a given good is desirable. But

this result begs the question in an important sense: if we know how much

citizens benefit from a good, then any consensual mechanism will work

well. Our goal is to find appropriate funding level without assuming

such prior centralized knowledge.

  

****4.**** ****Design and Analysis****\

Consider the funding mechanism, which we refer to as the Quadratic

Finance (henceforth QF) mechanism.

  

DEFINITION 5 (QUADRATIC FINANCE MECHANISM). The Quadratic Finance

Mechanism sat-isfies

  

For the moment, assume ΦQFis funded by the deficit {Fp}p∈P = ΦQF(cp i)

=cp i2p∈P .

  

>   cp i2− ci  (7)

  

being financed by a per-capita tax on each citizen. We also will, for

the moment, assume that citizens ignore their impact on the budget and

costs imposed by it. Whether this is an innocuous

  

  -----------------------------------------------------------------------

  10                                  ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

assumption will depend on context as we discuss further in 4.5.6Many

potential applications of this mechanism will involve dedicated

government funding or funding from philanthropy, in which case citizens'

impact on the deficit may matter much less (if at all). Nevertheless,

for now it is easiest to understand the logic of the mechanism without

worrying about the deficit.

  

****4.1.**** ****Baseline analysis****\

Under this assumption, citizen i's contribution to good p will be chosen

to maximize

  

+-------+-------+-------+-------+-------+-------+-------+-------+-------+

| Vp i  |       |   |       |      | cp j  | >     | > cp  | \(8\) |

|       |       |       |       |       |       |  2 | > i   |       |

|       |       |       |       |       |       | > −   | >     |       |

|       |       |       |       |       |       | > cp  | >     |       |

|       |       |       |       |       |       | > i.  | cp |       |

+=======+=======+=======+=======+=======+=======+=======+=======+=======+

| > Any |       |       |       |       |       |       |       | \(9\) |

| > pos |       |       |       |       |       |       |       |       |

| itive |       |       |       |       |       |       |       |       |

| > co  |       |       |       |       |       |       |       |       |

| ntrib |       |       |       |       |       |       |       |       |

| ution |       |       |       |       |       |       |       |       |

| >     |       |       |       |       |       |       |       |       |

|  will |       |       |       |       |       |       |       |       |

| >     |       |       |       |       |       |       |       |       |

|  thus |       |       |       |       |       |       |       |       |

| >     |       |       |       |       |       |       |       |       |

|  have |       |       |       |       |       |       |       |       |

| > to  |       |       |       |       |       |       |       |       |

| > sa  |       |       |       |       |       |       |       |       |

| tisfy |       |       |       |       |       |       |       |       |

+-------+-------+-------+-------+-------+-------+-------+-------+-------+

| by    | > 2   | cp   |      | = 1 ↔ |       |       |       |       |

| d     | >   |       |       | V     |       |       |       |       |

| iffer | >     |       |       | p′i(F |       |       |       |       |

| entia | > 2V  |       |       | p) =  |       |       |       |       |

| tion. | p′i(F |       |       |       |       |       |       |       |

|       | > p)  |       |       |       |       |       |       |       |

|       | > j   |       |       |       |       |       |       |       |

|       |       |       |       |       |       |       |       |       |

|       |      |       |       |       |       |       |       |       |

+-------+-------+-------+-------+-------+-------+-------+-------+-------+

  

PROPOSITION 3 ****(Optimality of Quadratic Finance)****. The Quadratic

Finance mechanism ΦQF guarantees optimal funding levels.

  

****Proof.**** Adding the expression in (9) across citizens yields Vp′(Fp)

= 1. Thus, ΦQFsatisfies opti-mality.

  

It is easy to check that the conditions for any positive contribution

being made are also optimal (viz. precisely when Vp′\> 1).

  

****4.2.**** ****Intuition****\

We briefly discuss an alternative derivation of the QF rule to provide

further intuition and insight into the logic of the mechanism. This

derivation translates an appealing normative property of a generic

solution to a public goods problem into a differential equation, and

shows that QF is its solution.

  

Each citizen has a "degree of contribution" to a collective good that is

a function of how much she gives: h(cj) for some scalar function h.

These contributions are at least quasi-additive across citizens so the

total amount of funding is g (citizens choose their degree of

contribution? One appealing normative property to counter free-ih(ci))

for some scalar function h. How should

  

riding might be: individuals should not act in line with solely

self-serving motives.

  

6 Indeed, it is easy to see that for goods with widespread support, the

individual contributions will only supply a small fraction of total

funding. For these goods, the mechanism serves as a mode of eliciting

preferences more than anything else, and thus a per-capita tax may be

problematic for goods with highly skewed benefits.

  

  -----------------------------------------------------------------------

  ****Buterin, Hitzig, and Weyl:**** A    11

  Flexible Design for Funding Public  

  Goods                               

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

How might this normative property govern behavior in public goods

provision?7The standard logic of free-riding is that each citizen

imagines that she would be willing to contribute to a public good if, by

her doing so, everyone else would as well. For example, each citizen

might be willing to see her taxes increase by 1% to fund a public good,

but would be unwilling to contribute unilaterally.

  

Thus following this logic, it may be desirable to have a mechanism such

that a citizen j could, by increasing h(cj) by 1% see funding increase

by 1% ofby a simple ordinary differential equation. Namely, for each j

we want\

ih(ci). Such a rule can be represented

  

> ∂g (∂cj ih(ci)) =h(cj) ih(ci) . (10)

  

This differential equation directly implies QF. To see this, note that

  

> ∂g (∂cj ih(ci)) = g′h(ci)h′(cj) (11)

  

so that (10) becomes\

g′h(ci)h′(cj) =h(cj) ih(ci) . (12)

  

Structurally, the g′term must treat all elements in the sum of h's

symmetrically and the h′term must only include cj. Thus we must have

that

  

g′h(ci)= kh(ci) ⇐⇒ g′(x) = kx

  

for some constant k and\

1 1 h′(cj) = kh(cj)⇐⇒ h′(x) = kh(x).

  

\+ n. If we want the funding of Integrating these we obtain that g(x) =k

2x2 + m and h(x) = 2√x\

a project with no contributions to be 0, m and n should both be 0,

narrowing our solution to g(x) =k 2x2 and h(x) = 2√x k. If we want a

mechanism in which a good with a single contributor is funded as in

private contributory schemes, we obtain k = 2 and thus QF.

  

****4.3.**** ****Properties of the Quadratic Finance mechanism****\

This discussion leads us naturally to a consideration of the properties

of the QF mechanism.

  

First, QF is homogeneous of degree one in the sense that if a fixed set

of citizens are contributing and double their contributions, the funding

also doubles. Homogeneity of degree one is a useful and reassuring

property, as it implies:

  

7 This normative property is closely related to a principle in moral

philosophy famously formalized by Kant (1785) as the "categorical

imperative": "act only according to that maxim whereby you can, at the

same time, will that it should become a universal law". Relatedly,

Roemer (2010) has suggested that the right solution to the public good

problem is to induce a change in human behavior so that every citizen

acts according to a "Kantian equilibrium."

  

  -----------------------------------------------------------------------

  12                                  ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

> • Changing currencies makes no difference to the mechanism.

  

• Groups can gain nothing by splitting or combining projects with the

same group of partici-pants.

  

• It matters little precisely how frequently the mechanism is run

(whether donations are aggre-gated at the monthly, daily or yearly

level) unless the pattern of donations is temporally uneven in a

systematic way.

  

Second, consider the case in which every contributing citizen makes an

equal contribution, say of one unit, as we vary the number of citizens

contributing Nc. In this case, the funding received is N2 c. Thus,

holding fixed the amount of the contribution, the funding received grows

as the square of the community size. This property is also intuitive and

reassuring, as we saw above that under purely private contributions,

there is a factor Nc underfunding of goods on the margin. It is thus

natural to solve this underfunding by scaling funding levels by the

community size.

  

Third, and relatedly, note that a community that splits in half with

roughly similar contribution profiles will receive half the aggregate

funding of the total community: both halves will receive one quarter.

This feature of the mechanism is a clear deterrent against fragmentation

and atomiza-tion, and is the core reason why the QF mechanism can solve

the public goods problem. However, this feature does not at all imply

that under QF only extremely large communities will form. Dif-ferent

collections of citizens will have different purposes in using their

funds, some in smaller groups and some in larger ones.

  

The trade-off between preference heterogeneity and the benefits of scale

is well-known to polit-ical economists. For example, this trade-off is

discussed in the literature on the optimal size of nations (Alesina and

Spolaore 1997). QF does not prejudge the optimal size of collectives,

but unlike purely private contributory schemes or 1p1v offers a

mechanism that creates neutral incen-tives among social organization of

different sizes. This feature turns out, however, to require much

greater funding for a given contribution profile to larger grouping for

the obvious collective action reason (see below): each citizen will tend

to contribute less, absent this incentive, to larger group-ings where

she receives a smaller share of relevant benefits.

  

Fourth, note that the mechanism reverts to a standard private good in

the case that a single citizen attempts to use the mechanism for her own

enrichment. In cases in which the overwhelm-ing bulk of contributions

come from one citizen, other contributions to the sum of square roots

approximately drop out and we are left with the square of the square

root, which is simply the contribution itself. More broadly, as we

approach the limit in which goods are private, the mech-anism treats the

contributions as contributions to a private good.

  

  -----------------------------------------------------------------------

  ****Buterin, Hitzig, and Weyl:**** A    13

  Flexible Design for Funding Public  

  Goods                               

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

Fifth, and really just to summarize, the mechanism provides much greater

funding to many small contributions than to a few large ones. This

feature does not result from imposing an exter-nal principle of equity

or distributive justice, though there may be good reasons from those

per-spectives to admire the outcome it delivers. It instead results

directly from the logic of the mech-anism. This logic aligns well with a

central concern in democratic theory since at least Madison (1787) and

famously associated with Mancur Olson's (1965) Logic of Collective

Action: Large com-munities of citizens that each receive only a small

benefit tend to be disadvantaged by private contributory schemes

relative to concentrated interests.

  

It is useful to highlight the more primitive attributes of our design

that underlie the above prop-erties by comparing QF to other efficient

mechanisms for funding public goods. As mentioned in 2.2, QF is a marked

improvement over other proposals in certain ways, though a more rigorous

comparison is left for future work. In particular, under QF, individuals

have private information---there is no need for complete information or

a centralized process as in Groves and Ledyard (1977) and Hylland and

Zeckhauser (1979). In addition, unlike Groves and Ledyard (1977), QF

respects individual rationality constraints, which is the key to solving

the free-rider problem. Any citizen with a positive valuation of a

particular good has incentives to contribute. QF is also flexible in the

sense that it does not require an enumeration of all participants, and

does not rely on pre-conceived estimates of the number of individuals

who benefit from particular goods. Contrast this flexibility with the

mechanism proposed in Falkinger (1996) which achieves individual

ratio-nality by rewarding and penalizing deviations from the average

contribution in order to achieve efficient funding levels---such a

mechanism is obviously problematic for goods of value to small

communities, and requires a full specification of the set of taxable

citizens.

  

Some of these properties may make a QF system vulnerable to collusion or

manipulation, as we will return to in 5.2. But, overall we view these

properties as heartening confirmations that our analysis addresses a

wide range of issues relevant to public goods problems.

  

****4.4.**** ****User interface****\

Precisely what the QF mechanism would "look like" is beyond our scope

here, but a brief descrip-tion of a possibility will hopefully help

readers imagine how it might be feasible. Any citizen could at any time

propose a new organization to be included in the system. Depending on

the con-text, there might be a more or less extensive process of being

approved to be listed in the system by an administrator; this approval

process would be especially important for a philanthropically-sponsored

implementation, as the philanthropist is unlikely to be willing to fund

just any project.

  

Citizens could contribute their funds towards (or possibly against, see

5.3 below) any listed project at some regular interval, such as monthly.

Citizens would be given some (possibly imper-fect and delayed, for

security purposes) indication of the total funding level of various

projects.

  

  -----------------------------------------------------------------------

  14                                  ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

Such information would help citizens determine: (i) the amount of

funding projects would receive if they contributed a bit extra (likely

aided by appropriate visualizations and "calculators") to a particular

project; and (ii) whether a project has enough funding to be successful.

The dissemina-tion of funding information would help avoid

fragmentation. Given the far greater funding that a project supported by

many can receive as compared to a project with a few supporters, there

would be far less incentive than under private contributions for a

thousand projects to proliferate.

  

As we discuss in 5.2 and 5.5 below, various more detailed features of

the system would be needed to help ensure security and enable

coordination among participants. Furthermore, the precise look and feel

of the system requires much more thought and even might affect the

formal rules in some way.

  

****4.5.**** ****Incorporating the deficit****\

In the preceding analysis, we assumed that citizens ignore their impact

on the deficit for clarity. We will now see how the elimination of this

assumption may alter our results.

  

Suppose that citizen i has a shadow value of λi on reducing the budget

deficit. We can think of λi as the fraction of the deficit that will be

funded by taxing citizen i. Alternatively, as we will explore in 5.1

below, λi can be interpreted as the cost to citizen i of reduced funding

of other public goods that a greater deficit will require.

  

> DEFINITION 6 (AGGREGATE COST OF DEFICIT). The aggregate cost of an

> increased deficit is

  

Λ ≡We assume that λi is on the order of iλi.

  

> 1\

> N, so that the aggregate cost of an increased deficit, Λ is

  

around 1. Under these assumptions, in a large society no citizen is

financing a large share of the

  

deficit. Citizen i seeks to maximize in her contributions to project p

  

> Vp i   cp j2 − cp i− λi  cp i2− ci . (13)

  

The associated first-order condition for maximization is

  

Aggregating the expression in (14) across all citizens yields 2  Vp′i(F

p) − λi

  

> 2  cp j cp= 1 − λi ↔ Vp′i(F p) − λi=  cp cp i (1 − λi). (14)

  

The approximation follows from the fact that λi is of order Vp′(Fp) − Λ

= 1 −  j cp ↔ Vp′(Fp) − Λ ≈ 1 ↔ Vp′(Fp) ≈ 1 + Λ.

  

> N. In a large population the denomi- 1\

> (15) jλj

  

nator in the square root sum ratio is much larger than the numerator.

Thus, underfunding to good

  

****Buterin, Hitzig, and Weyl:**** A Flexible Design for Funding Public

Goods\

15

  

p, when λi is of order1 Nis on the order of 1 + Λ. Underfunding is thus

bounded by the sum of the shadow values λi of reducing the deficit.

  

This analysis suggests that once we account for the deficit, the QF

mechanism does not yield efficiency. Instead it yields underfunding of

all public goods by roughly 1+Λ. How to interpret this conclusion is

somewhat subtle, and further analyses must be done to illustrate its

consequences in a wider range of cases. In many cases, incorporating

citizens' impact on the deficit may not fundamentally change our

conclusions. We now briefly run through some of these cases, though we

acknowledge that many further analyses are required to make general

statements. In addition, experimentation is necessary to understand the

settings in which these circumstances are more or less likely to obtain.

  

****1.**** First consider the case in which most of the goods funded by the

mechanism only benefit a relatively small fraction of the community and

negative contributions are not allowed. In this case, there is little or

no problem, because our analysis relies on negative contributions being

made by all of the citizens that do not benefit (the left-hand side of

the first-order condition in (14) is negative). As long as negative

contributions are disallowed (as in the baseline analysis in 4.1), most

contributions will drop towards Λ and we will obtain a conclusion very

close to the one obtained by ignoring the financing considerations.

  

****2.**** In some cases with negative contributions, there will

underfunding but it will still be, gener-ically, an improvement over

under private schemes because: (i) the magnitude of underfunding will

often be moderate compared to purely private contributions and (ii)

underfunding will be constant across different goods. We may want to

allow for negative contributions because certain"goods" are public

"bads" for some, such as financing hate speech. Allowing such

"shorting"may be undesirable in some cases, as we discuss in 5.3 below.

Consider the setting in which some non-wasteful tax is used to fund the

deficit so that Λ = 1. In this case, QF will lead to Vp′= 2, which is

underfunding of public goods, but not severe underfunding relative to

private contribu-tory schemes. Importantly, the degree of underfunding

is neutral across different goods and thus approximately optimal in the

sense of Ramsey-Atkinson-Stiglitz taxation, as will be discussed in more

depth in 5.1 below. Furthermore, these considerations are entirely

irrelevant for goods con-sumed by a small part of the population if we

assume that most citizens will not be bothered to make tiny negative

contributions to goods from which they do not benefit. Finally, this

pessimistic conclusion can be overcome by reducing the cost of

contributions to be proportionally smaller than the amount they

influence outcomes.8

  

8 If everyone is perfectly rational, this occurs in the extreme case in

which a minuscule contribution affects funding by a large amount. We

would not advocate this in practice as the risks of manipulation of such

a system seem much worse than the underfunding by a factor of 2.

  

  -----------------------------------------------------------------------

  16                                  ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

****3.**** In cases with an external philanthropist funding the subsidies in

the mechanism, as will be discussed in 5.1, citizens are likely to

ignore their impact on the deficit. When there is an external

philanthropist, there is no need for a tax, and thus citizens are less

likely to worry about their impact on the deficit in choosing their

contribution levels.9There will be some underfunding, but this is

determined by the constraints of the philanthropist and not by a

financing quirk in the mechanism.

  

In short, while incorporating citizens' impact on the deficit creates

some complications and potential deviations from optimality, the impact

may be small or irrelevant in particular cases of interest. Note,

however, that the cases discussed here are not in any sense general. We

have not discussed the precise formal conditions under which QF

represents an improvement over purely private contributions, we have

merely provided suggestive conditions that may or may not obtain in

settings of interest. We have also not offered an analysis of when QF is

superior to 1p1v when individuals take into account their impact on the

deficit. Furthermore, the cases require further analysis: case ****2****

(which allows negative contributions) and case ****3**** (which relies on

philanthropic funds) both present a host of other potential issues that

will be discussed in more detail though not completely resolved in 5.3

and 5.1, respectively.

  

****5.**** ****Variations and Extensions****\

The above sketch leaves us with many open questions. In this section we

address a handful of the most critical outstanding questions about the

mechanism, and highlight particularly important directions for future

analysis.

  

****5.1.**** ****Budgeted matching funds****\

In many practical applications the funding for QF is likely to come from

philanthropists or some dedicated government appropriation rather than

from unlimited tax revenue. There are clear the-oretical advantages of

such philanthropic (or dedicated government) funding. If participants do

not personally care about the philanthropist's wealth, the issues around

incorporating impacts on the deficit (as discussed in 4.5 above)

disappear. However, even the wealthiest philanthropists do not have

infinite funds and thus cannot simply agree to finance arbitrarily large

deficits. In this subsection we describe a variant on the QF mechanism

that can limit the funding required.

  

Consider a rule that is an α mixture of QF with a 1−α weight on

un-matched private contribu-tions. We call this the Capital-constrained

Quadratic Finance (CQF) mechanism.

  

9 It would be interesting, in future work, to compare the results under

pure philanthropically-funded subsidies vs. taxes, as discussed in

Roberts (1992).

  

+-----------------------------------+-----------------------------------+

| ****Buterin, Hitzig, and Weyl:**** A  | 17                                |

| Flexible Design for Funding       |                                   |

| Public Goods                      | > Capital-                        |

|                                   |                                   |

| > DEFINITION 7                    |                                   |

| > (CAPITAL-CONSTRAINED QUADRATIC  |                                   |

| > FINANCE MECHANISM). The         |                                   |

+===================================+===================================+

+-----------------------------------+-----------------------------------+

  

constrained Quadratic Finance Mechanism ΦCQFsatisfies

  

+---------+---------+---------+---------+---------+---------+---------+

| Fp=     |       | > cp i | 2      | \+ (1 − |        | > cp i. |

| ΦCQF(·) |         |         |         | α)      |         |         |

| = α     |         |         |         |         |         |         |

+=========+=========+=========+=========+=========+=========+=========+

+---------+---------+---------+---------+---------+---------+---------+

  

The first feature to note about ΦCQFis that for any budget B, α may be

adjusted to ensure the budget is not exceeded. To see this, note that

when α → 0 the mechanism is both directly self-financing and,

indirectly, the amount invested in the public good falls for the reasons

we have discussed above. Thus, the deficit can be eliminated by setting

α low enough. This flexibility ensures that a philanthropist can

reliably set a low level of α and perhaps gradually increase it over

time to increase support.

  

Second, note that no one would ever choose to contribute outside this

system (no one's contri-butions through it are taxed), so CQF is

individually rational.

  

+-----------------------+-----------------------+-----------------------+

| PROPOSITION 4. The    | \>∂Φpriv∂cp i         | > .                   |

| mechanism ΦCQFis      |                       |                       |

| individually rational |                       |                       |

| in the sense          |                       |                       |

| that∂ΦCQF∂cp i        |                       |                       |

+=======================+=======================+=======================+

+-----------------------+-----------------------+-----------------------+

  

****Proof.**** To show that CQF is individually rational, compare the

marginal impact of individual i's a contribution to good p through

ΦCQFto the marginal impact of her contribution to p through a separate

mechanism Φpriv. We showed in 3 that the marginal value of a

contribution under Φpriv is equal to 1. Consider the marginal

contribution under ΦCQF:

  

> ∂cp i = α cp + 1 − α. (16)∂Fp j

  

The factor multiplying α is by construction always at least 1, so this

always exceeds unity, the

  

marginal impact of a contribution made through a separate, purely

private channel.

  

The individual rationality property suggests that CQF is consistent with

existing within a broader society in which private contributory schemes

are the norm, not just in terms of funding but also in terms of getting

citizens to "play ball" with the mechanism.

  

> Third, consider equilibrium incentives under CQF. In choosing her

> contribution to good p, citi-

  

<table>

<colgroup>

<col style="width: 8%" />

<col style="width: 8%" />

<col style="width: 8%" />

<col style="width: 8%" />

<col style="width: 8%" />

<col style="width: 8%" />

<col style="width: 8%" />

<col style="width: 8%" />

<col style="width: 8%" />

<col style="width: 8%" />

<col style="width: 8%" />

<col style="width: 8%" />

</colgroup>

<thead>

<tr class="header">

<th>zen i maximizes</th>

<th>Vp i</th>

<th><blockquote>

<p><br />

α</p>

</blockquote></th>

<th></th>

<th></th>

<th>cp j</th>

<th>2</th>

<th>+ (1 − α)</th>

<th></th>

<th>cp j</th>

<th><blockquote>

<p> − cp i.</p>

</blockquote></th>

<th>(17)</th>

</tr>

</thead>

<tbody>

</tbody>

</table>

  

PROPOSITION 5. If the population M funding good p is large relative to

any individual contribution cp i, then ΦCQF leads to underfunding

relative to purely private contributions. Underfunding for good p is α.

When 1 α≪ M, ΦCQF yields less underfunding than Φpriv.

  

  -----------------------------------------------------------------------

  18                                  ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

****Proof.**** The first order condition of (17) is

  

The approximation comes from the fact that cp Vp′i α \

j cp + 1 − α= 1 ↔ Vp′

  

> i≪ M. i≈ α  cp cp i ↔ Vp′= 1 α. (18)

  

The approximation requires that the population funding the good is large

relative to any indi-vidual. This approximation is natural for a

genuinely public good; for goods supplied to very small communities or

citizens, funding will be greater than implied by this approximation,

but this extra funding will mostly come through the private channel and

not be subsidized by the philanthropist and thus should not be of great

concern to her.

  

Thus, the CQF mechanism will lead to underfunding of the good by a

factor of1 αas compared to the (rough) underfunding under purely private

contributions by a factor of the typical size of the benefiting

community. Assuming1 αis small relative to M, CQF can dramatically

improve funding relative to purely private contributions.

  

Furthermore, subject to the budget constraint, funding is approximately

optimally allocated across different public goods in the sense of Ramsey

(1927) taxation and the important extension to allow for heterogenous

consumers by Atkinson and Stiglitz (1976). The basic idea of

Atkinson-Stiglitz taxation is that, when considering commodity taxation,

it is optimal to distort the con-sumption of all goods equally, so that

the marginal rate of substitution across all goods is the same. To see

how the Atkinson-Stiglitz logic applies in our setting, we consider the

planner's problem which is the same as in the baseline set up, but with

a new interpretation of the budget iVi (F p) subject to the budget

constraint which is constraint. The planner seeks to maximizepF p = B.

Solving the constrained maximization problem,\

simply\

Vi (Fp) − λFp− B, (19)

  

gives Vp′= λ, i.e. Vp′is a constant. Thus our above result that Vp′=1

αsuggests that CQF funding is optimally allocated across goods if α is

chosen to just exhaust the budget.

  

Of course, this analysis ignores the fact that funding different goods

differentially may help stimulate more private contributions. We also

ignore the fact that CQF does not quite achieve Vp′=1 αas there are also

some contributions through the private channel. Atkinson and Stiglitz's

analysis is much more careful on these points and gives (fairly

specific) conditions under which equal distortion ratios are nonetheless

optimal. Verifying conditions when CQF is exactly optimal is an

interesting direction for future research, but is beyond the scope of

this paper.

  

Some of the underfunding implied by CQF may not be entirely undesirable.

This underfunding may balance under-investment in private goods creation

required by the distortionary taxes that will often be necessary to fund

the mechanism. As we now discuss, the underfunding implied by CQF may

also help to deter collusion.

  

+-----------------------+-----------------------+-----------------------+

| ****Buterin, Hitzig,    |                       | 19                    |**

**| and Weyl:**** A         |                       |                       |

| Flexible Design for   |                       |                       |

| Funding Public Goods  |                       |                       |

+=======================+=======================+=======================+

| ****5.2.****              | > ****Collusion and     |                       |**

**|                       | > fraud****             |                       |

+-----------------------+-----------------------+-----------------------+

  

The central vulnerabilities of QF are collusion and fraud. These

vulnerabilities are common to most other mechanisms designed based on

the assumption of unilateral optimization. Collusion takes place when

multiple agents act in their mutual interest to the detriment of other

participants. Fraud takes place when a single citizen misrepresents

herself as many.

  

It is useful to spell out precisely what these threats are and the harms

they could bring to QF or CQF. Consider, for concreteness, a case of CQF

with α = .1. First suppose one citizen is able to misrepresent herself

fraudulently as 20. If she contributes x dollars in the capacity of each

of these citizens, she will pay 20x but her cause (which could just

deposit to her bank account) will receive

  

.1 ·20√x2 = 40x.

  

Thus, on net, she doubles her money. This is a sure arbitrage

opportunity and could easily convert QF into a channel for lining the

pockets of the fraudster. The minimum fraud size required to run this

racket at positive profit is1 α.

  

A perfectly colluding group of citizens could achieve something similar.

The colluding group may all be participants in the mechanism, or they

may be partially formed of participants in the mechanism together with

one or more outside observers with an interest in the mechanism's

outcome. Collusion can either happen "horizontally", between multiple

participants with similar goals, or "vertically", between one or more

participants in the mechanism and an outside partici-pant (or a

participant in a different side of the mechanism, e.g. a potential

recipient of a subsidy) that can offer conditional payments (i.e.

bribes) to induce the participants to behave in particular αand the

group can perfectly coordinate, ways. Again, if the size of this group

is greater than1 there is no limit (other than the budget) to how much

it can steal.

  

However, note that unilateral incentives run quite strongly against

certain forms of collusion. Consider a colluding group with 100 members

each investing \$1000, which is thus funded at a level of .1 · 1002·

1000 =\$1,000,000. If this cartel divides the spoils equally among its

members, the group members each receive \$10,000 and thus achieve a net

benefit of \$9000. Now consider what happens if one member decides to

defect and contribute nothing. The funding level is now 992· 100

=\$980,100. The defecting member would see her pay out fall to \$9801,

but would have saved \$1000 and thus on net would now be making \$801

more than she was before. There is thus very little incentive for any

member of the cartel to actually participate. Unless activity can be

carefully monitored and actual payment levels directly punished,

defection is likely to be very attractive and the cartel is likely to

die the death of a thousand cuts. Simply sharing revenue with

participants is not sufficient to sustain collusion.

  

  -----------------------------------------------------------------------

  20                                  ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

There is a broader point here. If perfect harmonization of interests is

possible, purely private contributions lead to optimal outcomes. QF is

intended to overcome such lack of harmonization and falls prey to

manipulation when it wrongly assumes harmonization is difficult. So

we're led into a bit of a paradox: QF seeks to foster community

direction through its design, but in doing so QF relies on the strong

ties of community flowing outside the design not existing.

  

The appropriate way of deterring fraud and collusion will depend on the

affordances of the system. First consider fraud, which is the simpler

and more devastating of the issues. If fraud cannot be reasonably

controlled, QF simply cannot get off the ground; it will immediately

become a money pump for the first fraudster to come along. Note,

however, that this is true of nearly any system with a democratic

flavor: 1p1v can easily be exploited through fraud. The simplest and

most clearly necessary solution to fraud is an effective system of

identity verification. Beyond identity verification, relatively small

groups giving large contributions and thus receiving large funding

should be audited when possible to determine if fraud has occurred and

large penalties (much larger than the scale of the fraud, to adjust for

the chance of detection) should be imposed on the fraudsters and

transferred to other, honest citizens.

  

Collusion is a subtler and more pernicious problem to root out, and

perhaps the greatest chal-lenge for QF, given the tension between

community building and collusion deterrence. In all cases, a modest

value of α and auditing of small, highly funded groups will help deter

tight collusive groups. Yet the best approach to deterring broader

collusion will depend on the nature of the set-ting: a case in which

citizens are friendly and all know each other, as in a small town, will

differ from the case in which participants have low trust for each other

and are highly diverse, as in a blockchain community.

  

****5.3.**** ****Negative contributions****\

Not all public projects bring benefits alone; some may harm certain

citizens by creating negative externalities such as pollution or

offense. The existence of negative externalities does not imme-diately

imply we should allow negative contributions to reflect these harms.

Some of these nega-tive externalities can be addressed directly through

legislation. Furthermore, there are dangers of allowing citizens to

defund projects they don't like. Allowing negative contributions opens

many thorny issues as we discussed in 4.5 above. However, in some cases

the benefits of allowing the expression of negative externalities will

outweigh the potential costs and thus negative contri-butions will be

desirable. While further theoretical analyses are required to fully

understand the conditions under which negative contributions would be

desirable, we provide a brief discussion here of how allowing negative

contributions changes the baseline analysis presented in 4.1.

  

The natural extension of QF to allow negative contributions is one in

which citizens may choose to defund a public good according to the same

cost structure.

  

****Buterin, Hitzig, and Weyl:**** A Flexible Design for Funding Public

Goods\

21

  

DEFINITION 8 (± QUADRATIC FINANCE MECHANISM). The ± Quadratic Finance

Mechanism, Φ±QF(·) satisfies\

Fp= Φ±QF±i cp i2 ,

  

where ±i is positive or negative at the discretion of citizen i.

  

Citizens with Vp′i ≥ 0 or λi in the cases where they account for their

budget impact will choose the positive sign; those with the opposite

will choose the negative sign.

  

We already know the first-order condition for positive contributors;

let's consider it for negative contributors (for simplicity we focus on

the deficit-ignoring, fully financed case):

  

Note that together with the first-order condition for those making

positive contributions, (9) and − Vp′i(F p)   cp i j±jcp= 1 ↔

Vp′i(F p) = − j±j cp cp i . (20)

  

\(20\) can be summarized as

  

> Aggregating across citizens yields Vp′(Fp) = 1, as is optimal.

> Allowing negative contributions Vp′i(F p) =  ±i j±jcp cp i . (21)

  

is thus desirable in the following sense: without allowing them, there

may be negative externali-ties of a project that are not internalized

into its funding.

  

However, as noted in 4.5 above, it is principally allowing negative

contributions that leads to underfunding if citizens consider their

impact on the deficit. More broadly, negative contributions may be a

quite powerful way to deter collusive schemes as they offer a way for

any citizen to be a "vigilante enforcer" against fraud and abuse. The

downside of this benefit, however, is obvi-ously that, in some cases,

absolute free speech and other protections may lead us to distrust such

vigilantism.

  

In short, there are a variety of costs and benefits to allowing negative

contributions and we suspect their desirability will vary across

contexts.

  

****5.4.**** ****Variations on functional form****\

One might naturally wonder if the functional form we propose is uniquely

optimal.10We leave a formal proof for future work. Here, we plumb

intuition by considering a class of rules that nests both QF and purely

private contributions.

  

10 As Eguia and Xefteris (2018) show, in a sufficiently large population

(holding fixed value distributions), any function with a zero first

derivative and positive second derivative will behave like QV; this idea

likely extends to our present context. However, this result may be of

limited relevance in our setting---the appropriate limit is often one

where value distributions also change as the population grows, so that

behavior of the function away from zero also matters.

  

  -----------------------------------------------------------------------

  22                                  ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

> Consider rules Φβthat satisfy

>

> Fp= Φβ(·) =(cp i) ββ . (22) 1

  

Again, we analyze Φβabstracting from deficits and incentives created by

mechanisms that take

  

this form. To avoid redundancy, we skip straight to citizen i's

first-order condition:

  

> A convenient property of this form is that for β \> 1, unlike for the

> β = 1 case, every citizen Vp′i (cp j

>

> i)\

> cp

>

> β−1\

> j

>

> β1 ββ−1 = 1 ↔ Vp′i=

>

> \

> j\

> (cp

>

> \

> i)

>

> cp j\

> β−1

>

> 1\

> β

  

ββ−1 ↔ V p′ =

  

> j\

> j

>

> \

> cp\

> cp

>

> j\

> j

>

> 1β−1 ββ−1 . (23)

  

with strictly positive Vp′i will make a positive contribution. Note that

as β → 1 however, this rule

  

approaches purely private contributions, while when β → 2 the rule

becomes QF.

  

> Away from these now-familiar cases, it is useful to consider what

> happens for β ∈ (1,2) and β ∈

  

(2,∞). Note that our reasoning above implies that Vp′is in all these

cases equated to something

  

of the form

  

where xi ≡cp by Jensen's inequality.That is, public goods will be over

(under) funded if the function xβ−1is1 β and h(x) ≡ xβ−1. Whether this

ratio is greater than or less than one is determined h( ixi), (24)

ih(xi)

  

convex (concave). Given that β = 2 leads to efficiency and β = 1 leads

to the severe underfunding

  

of purely private contributions, this result should not be too

surprising.

  

> Might β ∈ (1,2) be a superior interpolation between purely private

> contributions and QF when

  

compared to our CQF mechanism in 5.1 above? While such solutions are

worthy of experimen-

  

tation, theory indicates their inferiority. To see why, note that β ∈

(1,2) does not simply lead to

  

underfunding, but to differential underfunding of projects with many

small contributors. To see

  

this note that we can rewrite citizen i's first-order condition as

  

1

  

Thus the efficiency condition that the aggregate marginal utility equals

one obtains except that  Vp′i \

β−1 =\

1

  

> \

> (cp

>

> j\

> \

> i)

>

> cp j\

> β

>

> 1 β↔ Vp′j  β−1 = 1.\

> 1

  

\(25\)

  

> 1

  

the transformation x β−1 is applied to it. For β \< 2 this

transformation is convex, which will thus

  

exaggerate large marginal utilities and dampen small ones. Thus, β \< 2

systematically leads to

  

the underfunding of goods with many small beneficiaries and over-funding

of goods with a few

  

large beneficiaries.

  

> This result may be problematic for two reasons. First, it is

> problematic from an efficiency stand-

  

point. It is worse than the budget-constrained efficiency we

(approximately) obtained in 5.1 above

  

from CQF. In addition, it would seem to make small group collusion quite

profitable.

  

  -----------------------------------------------------------------------

  ****Buterin, Hitzig, and Weyl:**** A    23

  Flexible Design for Funding Public  

  Goods                               

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

We do not mean to suggest that using a function other than quadratic has

no purpose. It may be useful, in some cases, to replace the square root

and square functions with ones that behave more like the absolute value

near the origin and only become quadratic further out to avoid large

groups engaging in collusion. If a group of individuals colluded and

each contributed very small amounts of money each, they could run a

highly profitable scheme for very little cost. And CQF does relatively

overfund goods with intense supporters, though the extent to which it

does so is modulated by α. Generally, we view these other functional

forms primarily as a foil that helps us understand QF and the failures

of private contributory schemes, rather than as viable alternative

funding mechanisms.

  

****5.5.**** ****Failures of concavity and dynamic solutions****\

Above we assumed that all functions Vp iwere smooth and concave. Further

analysis is required to fully understand the limitations of this

assumption---indeed further analyses may point to alter-native ways of

structuring the mechanism. However, for now we illustrate that this

assumption is innocuous in many circumstances.

  

Consider, for example, the case in which the value derived from a public

good is S-shaped (sinusoidal). Unless the good is funded "sufficiently"

citizens derive little value from it. Once it is funded sufficiently the

marginal value of funding quickly diminishes. This is a natural

structure for projects with a nearly-fixed budget, such as public

infrastructure projects. In this case, citizens will not be willing to

contribute unless they expect others to do so as well.

  

A natural solution to this problem is what is often called an "assurance

contract" and was pro-posed by Dybvig and Spatt (1983). The most natural

implementation is dynamic, and we suspect this is how an QF mechanism

would operate in practice in any case, but static implementations are

also possible.11Essentially, there is a window of time during which

contributions and with-drawals of contributions to the mechanism are

made. Citizens are thus able to contribute without fear that they will

be left "exposed" to the risk that others will not contribute. Given

this, every citizen may as well make a reasonable contribution until the

relevant threshold has been reached. In the spirit of Tabarrok (1998),

an entrepreneur confident that a good is worth funding can further

sweeten the deal by offering citizens a payment if they agree to

temporarily fund the mechanism to avoid any potential coordination

problems.12

  

11 For example, citizens could state a schedule of how much they would

like to contribute, conditional on the con-tributions of others, or some

coarse approximation thereof, such as a minimum threshold for their

contribution. An automated system could then calculate an equilibrium of

these requests.

  

12 Note, however, that Tabarrok's suggestion that such a scheme alone is

enough to fund public goods is problematic: it is based on a non-generic

assumption of precisely infinite derivative in the utility functions at

a single point. Any sinusoidal structure that is smooth will destroy the

result and lead to arbitrary underfunding, whatever the

"assurance"structure. The same logic applies to proposals that draw on

discontinuous payoff functions for generic informational structures on

values (Mailath and Postlewaite 1990).

  

+-----------------------------------+-----------------------------------+

| 24                                | ****Buterin, Hitzig, and Weyl:**** A  |

|                                   | Flexible Design for Funding       |

|                                   | Public Goods                      |

|                                   |                                   |

|                                   | This dynamic implementation is    |

|                                   | very likely to be desirable even  |

|                                   | if Vp iis concave, as the optimal |

+===================================+===================================+

+-----------------------------------+-----------------------------------+

  

contribution will still depend on others' contributions. Thus, it makes

little practical difference whether the value functions are concave,

except possibly for the chance of a weak cold start prob-lem, which an

assurance contract scheme, \`a la Tabarrok, could address. Similar

resolutions may apply to cases in which smoothness fails.

  

****6.**** ****Applications****\

We discuss several applications of QF in order to illustrate the

importance of its many nice features in practice. We focus on an

application to campaign finance reform. Then, we briefly discuss a few

other potential applications to illustrate the range of settings, across

quite distinct domains, in which we believe QF can be implemented in the

relatively near term.

  

****6.1.**** ****Campaign finance****\

In the US, the regulation of individual and collective contributions to

political campaigns has been hotly debated since the first attempts to

regulate campaign finance in the mid-1800s. The 1971 Fed-eral Election

Campaigns Act and subsequent amendments introduced extensive rules and

proce-dures for campaign funding geared toward balancing transparency

and equity with freedom of expression, and established the Federal

Elections Commission (FEC) to regulate the fundraising activities of

candidates for public office. Campaign finance issues frequently make

their way to the Supreme Court---and the court's Citizens United

decision has maintained a steady stream of vigorous opposition since its

ruling in 2010.

  

The proposals for campaign finance reform are manifold. Suggesting

modifications to munic-ipal, state, and federal election law, these

proposals range from simple tweaks of existing laws (e.g. capping

contributions, stricter enforcement, restricting contributions from

unions and cor-porations, etc.) to extensive re-envisioning of electoral

systems (e.g. public financing schemes, anonymous capped contributions,

etc.).13The proposals for reform offer solutions to the core legal and

political question: How can regulatory bodies strike a balance between

freedom of expres-sion through contributions to campaigns for elected

office, while restricting the undue influence of special interests?

  

The motivating problem for campaign finance reform can be analyzed using

the formal appa-ratus presented in previous sections. When un-checked,

permissive campaign finance laws such as the ones upheld in Citizens

United are purely private contributory schemes. As demonstrated above,

the private contributions mechanism for flexible funding of public goods

leads to tyranny of the few who have resources to make very large

contributions. In the campaign finance setting,

  

13 For influential discussions of campaign finance reform, see Ackerman

and Ayres (2002), Lessig (2011) and Hasen (2016).

  

  -----------------------------------------------------------------------

  ****Buterin, Hitzig, and Weyl:**** A    25

  Flexible Design for Funding Public  

  Goods                               

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

the failure of a purely private contributory mechanism implies that on

the margin, only a sin-gle contributor (the largest contributor) has any

influence. The motivating problem of campaign finance is existing

systems' vulnerability to tyranny of the rich, especially when one

considers the possibility for quid pro quo corruption. Just as the QF

mechanism answers to the central problem of purely private funding, it

provides a template for a new proposal for campaign finance reform.

  

The QF mechanism solves the funding problems with existing systems by

boosting the contri-butions of small donors, thereby effectively

diluting the influence of larger ones. Under existing schemes,

individuals able to make only small contributions have little incentive

to contribute, knowing that their contributions are just a drop in the

bucket. Under QF-based campaign finance, all individuals have incentive

to contribute as long as their evaluation of the candidate is positive.

This fact also has good second-order outcomes that are the converse of

quid pro quo corruption under purely private contributions---since all

individuals have incentive to contribute, campaign-ing politicians thus

have to give some weight to every individual in their electorate. Under

QF-based campaign finance, fundraising and outreach are intertwined,

leading politicians to engage more thoroughly and deeply with their

electorate.

  

The rationale for moving toward QF in campaign finance in part parallels

the rationale behind existing political matching funds. Public matching

funds for campaigns---such as the federal matching fund for presidential

elections14and municipal and state matching funds for legisla-tures and

mayoral races15---aim to amplify small contributions to campaigns for

elected office. Thus, like the QF mechanism, matching funds subsidize

small contributions. Yet existing match-ing funds systems are highly

arbitrary: often they match contributions linearly with some chosen

scaling factor, and up to some selected level. How are the maximums and

the match ratios cho-sen? Shouldn't there be a more gradual taper of

matching commitments? QF gives an optimal mechanism for achieving a

flexible matching fund, with clear logic behind the match ratio for any

given contribution.

  

The usual rationale behind matching systems, at least as described to

the public, is some pre-tense of equity. Meanwhile, the rationale for an

QF-based system does not even rely on an argu-ment from equity. Indeed,

QF is an (approximately) optimal mechanism from an efficiency

per-spective as we showed in 5.1 above. QF for campaign finance is thus

joined to matching funds proposals in spirit, while offering substantial

improvements over these existing proposals in prac-tice.

  

14 The federal matching fund for presidential campaigns is financed by a

\$3 voluntary contribution on income tax returns.

  

15 As mentioned in the introduction, New York City's matching fund

policy has led other cities and states to consider similar procedures.

However, several states had publicly financed matching funds deemed

unconstitutional by the 2011 Supreme Court Cases, Arizona Free

Enterprise Fund v. Bennett and McComish v. Bennett.

  

  -----------------------------------------------------------------------

  26                                  ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

The efficiency rationale for QF and the fact that it does not tax speech

has another important practical benefit: it would likely pass

constitutional muster even under the post-Citizens United state of

American constitutional law. Large contributions are not taxed as we

showed in 5.1. Thus, the system simply boosts the relative importance of

small donors.

  

The design details of an implementation of QF in the context of local,

state or federal campaigns require attention to many subtleties. Should

there continue to be contribution limits until enough funds can be

raised to make α reasonably high? What should a campaign have to do to

be allowed to list in the system? Should different candidates be allowed

to form "parties" then disperse funds to their candidates? Should

contributions be public or doubly blind (as in Chile) so that candidates

and parties do not know their own contributors, thus reducing corruption

and collusion? Though many questions remain, overall, we believe the

structure of QF/CQF could simplify the byzantine patchwork of current

campaign finance regulations.

  

****6.2.**** ****Other applications****\

To gesture to the range of other possible applications of QF/CQF, we

briefly review four other promising domains: open source software, news

media finance, charitable giving and urban pub-lic projects.

  

****1.**** The open source software movement is based on the principle that

code is or should be a public good. Software is a classic example of an

increasing returns activity, as it is nearly cost-less to copy and apply

broadly, yet has potentially large upfront development costs, especially

when the uncertainty of any solution working out is factored in. Many in

the software commu-nity view exclusionary capitalist solutions as wildly

inefficient and undesirable, yet democratic or government-driven

provision is usually far too hierarchical and centralized for fast

moving technology appreciated primarily at first by a small

community.16QF could provide a flexible solution that allows for public

and private contributions to open source development, without

compromising the principles upon which the movement was founded.17\

****2.**** Financing the production of news is an especially fitting

application of the QF mechanism. On the one hand, news (especially

high-quality, investigative journalism) is perhaps the clearest example

of a public good. It can be costly to create, but it is essentially

impossible to exclude anyone from consuming it beyond a very tiny window

of time and thus it is very difficult to earn value without highly

costly and wasteful mechanisms of exclusion.18Yet news is also often

  

16 For a classic exposition of dynamics of open source development, see

Benkler (2007).

  

17 The organization Gitcoin used the CQF mechanism to dedicate \$25,000

to open source software projects in February 2019 (). 18 This problem

has become increasingly acute with the rise of information and

communications technology, leading to an increasing sense of crisis in

the funding of news, which some have even labeled as "existential" (Foer

2017).

  

  -----------------------------------------------------------------------

  ****Buterin, Hitzig, and Weyl:**** A    27

  Flexible Design for Funding Public  

  Goods                               

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

relevant to a very broad community, making purely charitable funding

difficult to pull off. This creates a strong desire for public funding

and is the reason that governments all over the world are involved in

news production. However, the drawbacks of government involvement in

news creation could hardly be more evident, given the central role of

media in holding governments to account. QF offers a potentially

appealing resolution. Governments and philanthropists inter-ested in

supporting high-quality news without exerting or being seen to exert

undue influence over content could use QF to effectively match donations

to news creators in much the way that they already match contributions

to organizations like National Public Radio in the United States. Using

CQF rather than standard matching would create greater efficiency and

would require less targeted and discretionary applications of funds,

thereby allowing a truly diverse ecosystem of news outlets to flourish.

  

****3.**** QF also aligns well with existing movements toward more

democratic forms of charita-ble giving. Many philanthropists provide

matches to favorite charities and many are seeking more creative ways to

harness decentralized information outside the philanthropist's whims to

give away money. The Open Philanthropy and "effective altruism"

movements are based on the idea that donor discretion should be removed

from philanthropy to the greatest extent possible. In areas where

randomized controlled trials and other precise measurements are

insufficient to direct funds, QF seems well-suited. Across a wide range

of domains, from funding educational start-ups to large scale

interventions in developing countries, CQF holds the potential to

provide more accurate and less hierarchical signals for directing

charitable funds. Such non-hierarchical mechanisms for charitable giving

are increasingly relevant as backlash continues to grow against the

top-down dictates of well-intentioned but ultimately elitist class of

donors (Easterly 2007, Giriharadas 2018, Reich 2018).19\

****4.**** While urbanists have long recognized the importance of

community-level decision-making in cities, cities often lack mechanisms

that allow goods valued in communities to emerge. QF, as applied to

urban public funding decisions, could allow communities at all scales to

fund projects that would struggle to get funding under centralized

systems. A growing body of evidence sug-gests that policies emphasizing

community values and diversity generate major improvements in city life.

But city councils and other municipal governments struggle to meet the

needs of sub-communities. Even though they are democratic systems

intended to represent the will of a constituency, the needs of very

small groups cannot be heard for reasons we have discussed. Some public

goods are intensely important to a select few, for example a small group

of households clustered in a few city blocks. And yet, the systems in

place for communicating those needs and

  

19 In fact, one organization, WeTrust, has already run a charity

donation matching campaign for 501(c)3 nonprofits using CQF ().

  

  -----------------------------------------------------------------------

  28                                  ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

receiving the adequate funding are highly inefficient. QF, as applied to

city planning, aligns nicely with the ideas advanced by some of the most

prominent modern urban theorists.20The city is a fertile site for

application of QV, and these applications align with the logic

long-advanced by political economists and urban theorists alike.

  

****7.**** ****Conclusion****\

In this paper, we presented a novel funding mechanism for an emergent

ecosystem public goods, and highlighted key areas for further analysis,

experimentation and application. Our treatment of the economic theory

around this mechanism was superficial. Our analysis is based on

sim-plified assumptions of quasi-linear utility and independent values.

There is significant room for improvement in the analysis of the

financing mechanism and deficits' influence on incentives. Our

discussion of collusion is thin. Moreover, we do not even touch

distributive issues. Experiments can help guide these theoretical

analyses---it would be especially valuable to see experiments that

compare QF to related mechanisms such as VCG.

  

Beyond economic theory, there are countless implementation questions our

discussion leaves open. QF's formal structure will initially strike many

as bizarre. Designing interfaces, helping participants to "see" how QF

works would require educating citizens and planners prior to

imple-mentation. Is it possible to make wide publics largely unfamiliar

with mathematics comfortable with the QF mechanism? What can be done to

further defend QF from attacks and hacks? Would QF optimally encourage

community formation or would the norms and rules needed to avoid

col-lusion inadvertently undermine important communities? Further, it is

critical to understand how participants dynamically assess the marginal

benefits they derive from different types of goods at different funding

levels. Psychological constraints may suggest particular domains of

application over others.

  

We hope for a wide range of experimentation around QF---thus we have

laid out a variety of narrower domains in which experimentation has

already begun or otherwise may be most plausible in the near term. Such

experimentation is critical for a variety of reasons: to investigate the

weaknesses of the formal mechanisms and address these flaws with new

designs, to acquaint people with their operation and build awareness of

their value, to build social institutions around them that make them

effective, and to provide rigorous empirical evidence of their value.

  

20 Activist and intellectual Jane Jacobs (1961) famously condemned the

urban planning ethos of her time, arguing that"rationalist" urban

planners do a poor job serving the needs of actual city-dwellers,

undoing the sense of commu-nity that makes people move to cities in the

first place through their top-down, deductive approach to allocation and

decision-making. Similarly, anthropologist and geographer David Harvey

has long recognized the importance of the city as a locus of

self-definition through community attachment (Harvey 2009). Harvey

emphasizes that precisely because the urbanization process creates so

much surplus, the "right to city" demands new forms of democratic

man-agement of that surplus.

  

  -----------------------------------------------------------------------

  ****Buterin, Hitzig, and Weyl:**** A    29

  Flexible Design for Funding Public  

  Goods                               

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

****References****\

****Ackerman, Bruce and Ian Ayres****, Voting with Dollars: A New Paradigm

for Campaign Finance, New Haven, CT: Yale University Press, 2002.

  

****Alesina, Alberto and Enrico Spolaore****, "On the Number and Size of

Nations," Quarterly Journal of Eco- nomics, 1997, 107 (4), 1027--1056.

  

****Atkinson, A. B. and J. E. Stiglitz****, "The Design of Tax Structure:

Direct Versus Indirect Taxation," Journal of Public Economics, 1976, 6

(1--2), 55--75.

  

****Benkler, Yochai****, The Wealth of Networks: How Social Production

Transforms Markets and Freedom, New Haven, CT: Yale University Press,

2007.

  

****Bergstrom, Ted****, "Do Governments Spend Too Much," National Tax

Journal, 1979, 32 (2), 81--86.

  

> , "When Does Majority Rule Supply Public Goods Efficiently?,"

> Scandinavian Journal of Ecnomics, 1979, 81 (2), 216--226.

  

****Bergstrom, Theodore, Lawrence Blume, and Hal Varian****, "On the Private

Provision of Public Goods," Journal of Public Economics, 1986, 29 (1),

25--49.

  

****Bowen, Howard R.****, "The Interpretation of Voting in the Allocation of

Economic Resources," Quarterly Journal of Economics, 1943, 58 (1),

27--48.

  

****Clarke, Edward H.****, "Multipart Pricing of Public Goods," Public

Choice, 1971, 11 (1), 17--33.

  

****Dybvig, Phillip H. and Chester S. Spatt****, "Adoption Externalities as

Public Goods," Journal of Public Eco- nomics, 1983, 20 (2), 231--247.

  

****Easterly, William****, The White Man's Burden: Why the West's Efforts to

Aid the Rest Have Done So Much Ill and So Little Good, Oxford: Oxford

University Press, 2007.

  

<table>

<colgroup>

<col style="width: 9%" />

<col style="width: 9%" />

<col style="width: 9%" />

<col style="width: 9%" />

<col style="width: 9%" />

<col style="width: 9%" />

<col style="width: 9%" />

<col style="width: 9%" />

<col style="width: 9%" />

<col style="width: 9%" />

<col style="width: 9%" />

</colgroup>

<thead>

<tr class="header">

<th><strong>Eguia,</strong></th>

<th><strong>Jon</strong></th>

<th><strong>X.</strong></th>

<th><strong>and</strong></th>

<th><strong>Dimitrios</strong></th>

<th><strong>Xefteris</strong>,</th>

<th>“Implementation</th>

<th>by</th>

<th>Vote-Buying</th>

<th>Mechanisms,”</th>

<th><blockquote>

<p>2018.</p>

</blockquote></th>

</tr>

</thead>

<tbody>

</tbody>

</table>

  

> https://ssrn.com/abstract=3138614.

  

****Falkinger, Josef****, "Efficient Private Provision of Public Goods by

Rewarding Deviations from Average," Journal of Public Economics, 1996,

62 (3), 413--422.

  

****Foer, Franklin****, World Without Mind: The Existential Threat of Big

Tech, New York: Penguin, 2017.

  

****Giriharadas, Anand****, Winners Take All: The Elite Charade of Changing

the World, New York: A. Knopf, 2018. ****Green, Jerry and Jean-Jacques**

**Laffont****, "Characterization of Satisfactory Mechanisms for the

Revelation of Preferences for Public Goods," Econometrica, 1977, pp.

427--438.

  

> , "On Coalition Incentive Compatibility," The Review of Economic

> Studies, 1979, 46 (2), 243--****and****\

> 254.

  

****Groves, Theodore****, "Incentives in Teams," Econometrica, 1973, 41 (4),

617--631.

  

> ****and John Ledyard****, "Optimal Allocation of Public Goods: A Solution

> to the "Free Rider" Problem,"Econometrica, 1977, 45 (4), 783--809.

  

  -----------------------------------------------------------------------

  30                                  ****Buterin, Hitzig, and Weyl:**** A

                                      Flexible Design for Funding Public

                                      Goods

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

****Harvey, David****, Social Justice and the City (Revised Edition),

University of Georgia Press, 2009.

  

****Hasen, Richard L****, Plutocrats United: Campaign Money, the Supreme

court, and the Distortion of American Elec- tions, Yale University

Press, 2016.

  

****Hylland, Aanund and Richard Zeckhauser****, "The Efficient Allocation of

Individuals to Positions," Journal of Political Economy, 1979, 87 (2),

293--314.

  

****Jacobs, Jane****, The Death and Life of Great American Cities, New York:

Random House, 1961.

  

****Kant, Immanuel****, Grounding for the Metaphysics of Morals, tr. James

Ellington, Hackett Publishing \[1993\], 1785. ****Krugman, Paul****,

"Increasing Returns and Economic Geography," Journal of Political

Economy, 1991, 99 (3), 483--499.

  

<table style="width:100%;">

<colgroup>

<col style="width: 7%" />

<col style="width: 7%" />

<col style="width: 7%" />

<col style="width: 7%" />

<col style="width: 7%" />

<col style="width: 7%" />

<col style="width: 7%" />

<col style="width: 7%" />

<col style="width: 7%" />

<col style="width: 7%" />

<col style="width: 7%" />

<col style="width: 7%" />

<col style="width: 7%" />

</colgroup>

<thead>

<tr class="header">

<th><strong>Lalley,</strong></th>

<th><strong>Steven</strong></th>

<th><strong>P.</strong></th>

<th><strong>and</strong></th>

<th><strong>E.</strong></th>

<th><strong>Glen</strong></th>

<th><strong>Weyl</strong>,</th>

<th>“Nash</th>

<th>Equilibria</th>

<th>for</th>

<th>Quadratic</th>

<th>Voting,”</th>

<th><blockquote>

<p>2018.</p>

</blockquote></th>

</tr>

</thead>

<tbody>

</tbody>

</table>

  

> https://arxiv.org/abs/1409.0264.

  

****Lessig, Lawrence****, Republic, Lost: How Money Corrupts Congress -- and

a Plan to Stop It, New York: Twelve, 2011.

  

****Madison, James****, "The Federalist No. 10: The Utility of the Union as

a Safeguard Against Domestic Faction and Insurrection," Daily

Advertiser, 1787, Thursday, November 22.

  

****Mailath, George J. and Andrew Postlewaite****, "Asymmetric Information

Bargaining Problems with Many Agents," Review of Economic Studies, 1990,

57 (3), 351--367.

  

****Olson, Mancur****, The Logic of Collective Action, Cambridge, MA:

Harvard University Press, 1965.

  

****Ostrom, Elinor****, "Governing the Commons: The Evolution of

Institutions for Collective Action," 1990. ****Posner, Eric A. and E. Glen**

**Weyl****, "Introduction," Public Choice Special Issue: Quadratic Voting

and the Public Good, 2017, 172 (1--2), 1--22.

  

****Ramsey, F. P.****, "A Contribution to the Theory of Taxation," Economic

Journal, 1927, 37 (145), 47--61. ****Reich, Rob****, Just Giving: Why

Philanthropy is Failing Democracy and How It Can Do Better, Princeton

University Press, 2018.

  

****Roberts, Russell D****, "Government subsidies to private spending on

public goods," Public Choice, 1992, 74 (2), 133--152.

  

****Roemer, John E.****, "Kantian Equilibrium," Scandinavian Journal of

Economics, 2010, 112 (1).

  

****Romer, Paul M****, "Increasing Returns and Long-run Growth," Journal of

Political Economy, 1986, 94 (5), 1002-- 1037.

  

****Rothkopf, Michael H.****, "Thirteen Reasons Why the

Vickrey-Clarke-Groves Process is Not Practical," Oper- ations Research,

2007, 55 (2), 191--197.

  

****Samuelson, Paul A.****, "The Pure Theory of Public Expenditure," Review

of Economics and Statistics, 1954, 36 (4), 387--389.

  

  -----------------------------------------------------------------------

  ****Buterin, Hitzig, and Weyl:**** A    31

  Flexible Design for Funding Public  

  Goods                               

  ----------------------------------- -----------------------------------

  

  -----------------------------------------------------------------------

  

****Smith, Vernon L****, "Experiments with a Decentralized Mechanism for

Public Good Decisions," The American Economic Review, 1980, 70 (4),

584--599.

  

****Tabarrok, Alexander****, "The Private Provision of Public Goods via

Dominant Assurance Contracts," Public Choice, 1998, 96 (1--2), 345--362.

  

****Vickrey, William****, "Counterspeculation, Auctions and Competitive

Sealed Tenders," Journal of Finance, 1961, 16 (1), 8--37.

  

****Weyl, E. Glen****, "Quadratic Vote Buying," 2012. http://goo.gl/8YEO73.