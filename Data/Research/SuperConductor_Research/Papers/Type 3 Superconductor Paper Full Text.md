Type-III Superconductivity
M. C. Diamantini,1 C. A. Trugenberger,2 Sheng-Zong Chen,3 Yu-Jung Lu,4 Chi-Te Liang,5
and V. M. Vinokur6
1NiPS Laboratory, INFN and Dipartimento di Fisica e Geologia,
University of Perugia, via A. Pascoli, I-06100 Perugia, Italy
2SwissScientific Technologies SA, rue du Rhone 59, CH-1204 Geneva, Switzerland
3Department of Physics, National Taiwan University, Taipei 106, Taiwan
4Research Center for Applied Sciences, Academia Sinica, Taipei 115,
Taiwan and Department of Physics, National Taiwan University, Taipei 106, Taiwan
5Department of Physics, National Taiwan University, Taipei 106,
Taiwan and Center for Quantum Science and Engineering, National Taiwan University, Taipei 106, Taiwan
6Terra Quantum AG, St. Gallerstrasse 16A, 9400 Rorschach, Switzerland
Superconductivity remains one of most fascinating quantum phenomena existing on a macroscopic scale. Its
rich phenomenology is usually described by the Ginzburg-Landau (GL) theory in terms of the order parameter,
representing the macroscopic wave function of the superconducting condensate. The GL theory addresses one
of the prime superconducting properties, screening of the electromagnetic field because it becomes massive
within a superconductor, the famous Anderson-Higgs mechanism. Here we describe another widely-spread
type of superconductivity where the Anderson-Higgs mechanism does not work and must be replaced by the
Deser-Jackiw-Templeton topological mass generation and, correspondingly, the GL effective field theory must
be replaced by an effective topological gauge theory. These superconductors are inherently inhomogeneous
granular superconductors, where electronic granularity is either fundamental or emerging. We show that the
corresponding superconducting transition is a three-dimensional (3D) generalization of the 2D BerezinskiiKosterlitz-Thouless (BKT) vortex binding-unbinding transition. The binding-unbinding of the line-like vortices
in 3D results in the Vogel-Fulcher-Tamman (VFT) scaling of the resistance near the superconducting transition.
We report experimental data fully confirming the VFT behavior of the resistance.
INTRODUCTION
The macroscopic physics of traditional superconductors
(SC) is governed by the Ginzburg-Landau (GL) model, see
e.g., [1], describing superconductors in terms of a local order
parameter. The ground state of a macroscopic superconductor
of a size much exceeding the London penetration depth, λL,
has an order parameter that is constant in the system’s bulk,
outside a boundary shell of the width λL. There are, however, superconductors, for example thin films of a thickness
d comparable with the coherence length ξ, which are characterized by a completely different ground state exhibiting a
paradigmatic granularity [2, 3]. In these systems superconductivity sets in when global phase coherence is established
due to tunneling Cooper pairs percolation between droplets of
locally formed condensate. The granularity of these systems is
associated with a superconductor-to-superinsulator quantum
phase transition [4–6] which may occur via an intermediate
Bose metal [4, 7, 8] phase, see [9–11], and has been detected
experimentally [12, 13].
Two important features characterize these planar “selfgranular” superconductors. First, the gauge screening length,
the Pearl length λP = λ
2
L
/d due to the familiar Anderson-Higgs
mechanism, see e.g. [1], would become larger than the experimental system size for small d. Second, near the quantum
transition, the electric fields induced by charges residing in
the system remain in-plane over the whole sample because
of the large dielectric constant [9–11]. Usually, such electric
fields are not very relevant in standard superconductors. In
our planar superconductors, however, these 2D electric fields
are much stronger than the usual 3D ones, since they decay as
1/r with the increasing distance r from the charge and cannot
be neglected. When coupled to electromagnetism, the timedependent Ginzburg-Landau model becomes, therefore (nonrelativistic) scalar quantum electrodynamics (QED), which is
ill defined in 2D because of its infrared divergences tied to
the perturbative coupling scaling as ln(L/ξ), where L is the
sample size [14, 15]. If one tries to derive the free energy for
a putative order parameter from the elastic interaction with a
substrate one obtains a non-local functional describing a selforganized array of superconducting islands[16], confirming
the the original GL model breaks down. Hence, for planar systems with long-range interactions, the local Ginzburg-Landau
model does not provide an adequate description of the global
superconductivity [17] and can only address local superconductivity within droplets of the typical size of order ξ.
Notably, emergent granularity is not confined to thin films.
Recently, the same physics has been detected in bulk samples [18]. Even more importantly, the ground-state of the
high-Tc cuprates is inhomogeneous, especially in the underdoped regime and the same percolation model is thought to
be responsible for global superconductivity [19, 20]. In this
type of percolating superconductivity, electron pairs survive
above Tc, which is the case both in 2D [21] and 3D [22], and
there is a quantum transition to an insulating state, both in
2D, see [9–11], and 3D [23]. In 2D, the fragmentation into
separate condensate droplets is due to strong infrared divergences near the quantum insulating transition [17]. In general,
arXiv:2303.14673v1 [cond-mat.supr-con] 26 Mar 2023
2
however, this type of behaviour seems characteristic of superconductors in which the pairing mechanism is not the BCS
one [1] but arises from a stronger attractive interaction leading
to the pronounced bosonic pairs of a size much smaller than
their typical separation distance and forming a Bose-Einstein
condensate (BEC). The BECs with long-range dipole interactions of particles carrying magnetic moments are known to
fragment into liquid droplets due to strong quantum fluctuations [24].
Here we formulate the effective long-distance gauge theory of inhomogeneous superconductors in 3D and show that
superconductivity sets in via the Vogel-Fulcher-Tammann
(VFT) transition, the three dimensional counterpart of the
2D Berezinskii-Kosterlitz-Thouless (BKT) topological phase
transition, and we report an experiment confirming the VFT
scaling of the resistance at the transition. The crucial point
is that, contrary to type II superconductors, vortices in inhomogeneous superconductors are not Abrikosov vortices but,
rather, mobile vortices with no dissipative core which arise
due to non-trivial phase circulations on adjacent droplets.
Charges on the droplets and vortices between them have unavoidable topological mutual statistics interactions and a local
descriptions of these requires the introduction of gauge fields
[25]. Therefore, the effective field theory for these inhomogeneous superconductors must be a gauge theory. We refer to
this novel, topologically driven superconducting state (in any
dimension) as to type-III superconductivity. This choice is
dictated by the standard classification of superconductors with
respect to penetration of the applied magnetic field. Type I superconductors expel magnetic field H and are referred to be
in a Meissner state at H < Hc, while at the critical field Hc
superconductivity destroys. In type II superconductivity Hc
“splits” into the lower, Hc1, and upper, Hc2, critical fields. At
H < Hc1 type II superconductors are in the Meissner state; at
Hc1 < H < Hc2 (mixed or vortex state) magnetic field penetrates type II superconductors in a form of Abrikosov vortices
having a normal core; and at H = Hc2 vortex normal cores
overlap and superconductivity gets destroyed. In type III superconductors Hc1 = 0 and vortices, which, as mentioned
above, in this case do not possess normal core, can penetrate
at any magnetic field (corresponding to a flux at least equal
to a quantum flux), and there is no true Meissner state. Superconductivity is not destroyed at low temperatures because
the quantum diffusion of vortices is suppressed by the large
corresponding term in the action. This behavior has been experimentally detected [26] in Josephson junction arrays, the
paradigmatic example of type III superconductors in 2D. The
response can be both diamagnetic and paramagnetic, however
since it is preferentially paramagnetic this state is sometimes
called paramagnetic Meissner state. Finally, in type III superconductors, vortices can proliferate even without a magnetic
field when the temperature is high enough.
BKT AND VFT TRANSITIONS
As we have established in the Introduction, the local GL
model fails to provide a consistent description of granular or
droplet-composed superconductors [20] and has thus to be replaced by a generalized gauge theory introduced in [27, 28]
and recently discussed in detail in 2D in [17]. One of the fundamental implications of the gauge theory of granular superconductors is that its vortices, contrary to Abrikosov vortices,
have no dissipative core, since they arise from non-trivial circulations of the local phases of the condensate on adjacent
droplets. Hence, superconductivity in these materials that do
not possess a global order parameter is referred to as “Higssless superconductivity” [28]. Furthermore, since the ground
state of Higgsless superconductors may carry topological order they are also called “superconductors with topological order” [27].
Since superconductivity is realized by global phase coherence establishing over all pre-existing condensate droplets, its
destruction is caused by a proliferation of vortices and not by
breaking of Cooper pairs, as in traditional superconductors.
In 2D, this is the famed BKT transition, see [29] for a review,
resulting in the BKT resistance scaling
R(T) ∝ e
−
q
b
|T−TBKT |
, (1)
where b is a constant having the dimensionality of temperature. In 3D, the phase transition is again caused by vortex
liberation, but the vortices are now 1D extended objects, magnetic strings. The superconducting phase transition is thus
caused by 1D strings becoming tensionless. This transition
has been studied in [30]. The corresponding behaviour of the
resistance is modified to the VFT scaling
R(T) ∝ e
−
b
0
|T−TVFT |
. (2)
This same dual scaling, for vanishing conductivity and due
to electric strings becoming tensionless, see [11] for a review,
has already been detected at the superinsulating side of the
quantum transition [31] and has also been obtained in the XY
model with quenched disorder, which apparently is equivalent
to one more effective space dimension [32, 33].
GAUGE THEORY OF TYPE-III SUPERCONDUCTORS
We model an inhomogeneous superconductor by a cubic
lattice, with the sites representing the droplets and the links
encoding possible tunneling junctions between them. The
fundamental degrees of freedom of the model are of two types.
First, there are integer (in units of 2e) charges Q0 located
at the sites and currents Qi on the links of lattice. Together
they constitute a four-current Qµ, with Greek letters standing for the space-time indices. In the absence of background
charges, this current is conserved, dµQµ = 0 with dµ denoting
the forward lattice derivative in the direction µ; summation
3
over equal Greek indices is implied. Conservation requires
that only closed loops Qµ are allowed on the lattice, representing charge-hole fluctuations. The second type of excitations are integer (in units 2π/2e, we use natural units c = 1,
~ = 1, ε0 = 1) coreless Josephson vortices that arise from
the nontrivial circulations of the local condensate phases on
the droplets. Since these circulations are 1D extended objects
they are represented by integer lattice plaquette variables Mµν.
Since the vortices that we consider are closed loops, these are
also conserved, dµMµν = dνMµν = 0 and describe, thus, closed
surfaces representing the nucleation and subsequent annihilation of a vortex loop. Open vortices with magnetic monopoles
at their ends are also possible [34] but are not relevant for what
follows.
The infrared (IR) dominant interaction between charges
and vortices is topological, it encodes their mutual statistical interaction i.e., the Aharonov-Bohm [35] and AharonovCasher [36] (ABC) phases accumulating when one type of excitation encircles the other. In the Euclidean partition function, which we will consider in the rest of this paper, the ABC
topological interactions are accounted for by an imaginary
term representing the Gaussian linking of the closed loops and
surfaces in four Euclidean dimensions [37]. As pointed out by
Wilczek [25], this interaction can also be represented in local form by introducing two fictitious gauge fields interacting
with the two types of excitations and with a topological coupling to each other. In the 2D this is the well known ChernSimons term [38]; in the 3D case, this is the three-index BF
term [11], µναβ∂ν, coupling an effective gauge field aµ for the
charges with the two-index effective gauge field bαβ for the 1D
extended vortices. Here 
µναβ is the usual totally antisymmetric tensor. Then the Euclidean action acquires the form
S =
X
x
i
`
4
4π
aµkµαβbαβ + i`aµQµ + i`
2
1
2
bµνMµν , (3)
where x denotes the lattice sites, ` is the link length and kµαβ
is the lattice BF term, described in detail in Methods.
The two gauge fields are invariant under the gauge transformations
aµ → aµ + dµξ ,
bµν → bµν + dµλν − dνλµ , (4)
reflecting the fact that the charge world-lines and vortex
world-surfaces they couple to are closed. Note that, at the
classical level, the equations of motion imply that the gauge
fields themselves encode the charge and vortex currents, respectively,
Qµ = −
1
4π
`
3
kµαβbαβ ,
Mµν = −
1
2π
`
2
kµναaα . (5)
If aµ is a vector field and bµν a pseudotensor field, the model
is also invariant under the parity P and time-reversal T symmetries. In general, the BF action for a model defined on a
compact space with non-trivial topology has a ground state
degeneracy [40] reflecting the topology, exactly as the ChernSimons term in 2D. However, when the coefficient of the BF
term is 1/4π, as in (3), the ground state is unique[40].
Having established that the effective field theory for the inhomogeneous superconductors is a generalized gauge theory
we can proceed as usual in its construction, adding order by
order all interactions that respect the relevant symmetries. In
this case, the next-order gauge-invariant terms are the kinetic
terms for the two gauge fields. For the vector gauge field
aµ this is the usual Maxwell term, constructed from the field
strength fµν = dµaν−dνaµ. For the antisymmetric tensor gauge
field bµν, the kinetic term is quadratic in the field strength
hµνα = dµbνα + dνbαµ + dαbµν . (6)
It is easy to check that this is invariant under a gauge transformation (4). Adding these next-order terms, we obtain the
Euclidean effective action
S =
X
x
`
4
4 f
2
fµν fµν+i
`
4
4π
aµkµαβbαβ+
`
4
12Λ2
hµναhµνα+i`aµQµ+i`
2
1
2
bµνMµν .
(7)
The dimensionless parameter f = O(e) represents the effective Coulomb interaction strength in the material and 1/Λ is
the magnetic screening length. The two dimensionless parameters f and Λ` encode the strengths of the electric and magnetic interactions, respectively. Non-relativistic effects can be
easily incorporated by considering a velocity of light v < 1
but are of no particular relevance for what follows.
We now integrate out the emergent gauge fields to obtain an
effective (Euclidean) action for the charges and vortices alone,
S QM =
X
x
f
2
2`
2
Qµ
δµν
m2 − ∇2
Qν
+
Λ
2
8
Mµν
δµαδνβ − δµβδνα
m2 − ∇2 Mαβ + i
πm
2
`
Qµ
kµαβ
∇2

m2 − ∇2
 Mαβ(8).
where
m =
f Λ
2π
, (9)
is the gauge-invariant, topological mass, analogous to the
famed Chern-Simons mass in 2D [38, 39]. This is one of
the main points of this paper: the topological mutual statistics
interaction screens both the vortex-vortex interaction and the
Coulomb interaction between charges. Approximating these
screened potentials by delta functions one can estimate the
mass (coefficient multiplying the world-line length in the action) of charges and the string tension (coefficient multiplying the world-sheet area in the action) of vortices. In this
phase of the system both charges and vortices are gapped
excitations with mass M = f
2
/(2m
2
`
3
) and string tension
T = Λ2
/(8m
2
`
2
) interacting via short-range screened potentials. For temperatures low enough this is thus a thermally activated, insulating phase, for higher temperatures it is a metal
4
Let us now investigate what happens when charges condense, which can be described by letting the original integervalued variable Qµ become a real-valued field over which one
has to integrate (as opposed to sum) in the partition function.
Formally, this amounts to using the Poisson summation formula
X
{Qµ}
f

Qµ

=
X
{kµ}
Z
dQµ f

Qµ

e
i2πQµkµ
, (10)
and focusing only on the sector in which the dual variable
kµ = 0. However, since the current Qµ is conserved and thus
constrained by the equation dµQµ = 0, we must first introduce
the representation Qµ = `kµαβnαβ. The new variables nαβ are
now free but redundant, since they can be gauge transformed
as in (4). There are only three gauge-invariant degrees of freedom in the nαβ, corresponding to the three unconstrained variables Qµ. The removal of the three redundant variables can be
taken care of by the usual gauge fixing in the integration.
We consider a 4D Euclidean lattice with spacing ` representing the typical distance of the superconducting droplets.
Let dµ, dˆ
µ, S µ and Sˆ
µ denote forward and backward lattice
derivatives and shifts. Then the forward and backward lattice
BF terms are defined by the three-index operators[4]
kµνρ ≡ S µµανρdα ,
hatkµνρ ≡ µναρdˆ
αSˆ
ρ , (11)
where no summation over equal indices µ and ρ is implied.
The two lattice BF operators are interchanged (no minus sign)
upon summation by parts on the lattice and are gauge invariant,
kµνρdν = kµνρdρ = dˆ
µkµνρ = 0 ,
ˆkµνρdρ = dˆ
µ
ˆkµνρ = dˆ
ν
ˆkµνρ = 0 . (12)
They also satisfy the identities
ˆkµνρkρλω = −

δµλδνω − δµωδνλ
∇
2 +

δµλdνdˆ
ω − δνλdµdˆ
ω

+

δνωdµdˆ
λ − δµωdνdˆ
λ

,
ˆkµνρkρνω = kµνρ
ˆkρνω = 2

δµω∇
2 − dµdˆ
ω

(13) ,
where ∇
2 = dˆ
µdµ is the lattice Laplacian.
Using (13) we write the action (8) as
S nM =
X
x
Λ
2
8
Mµν
δµαδνβ − δµβδνα
m2 − ∇2 Mαβ
+
f
2
2
nµν
−

δµαδνβ − δµβδνα
∇
2 +

δµαdνdˆ
β − δναdµdˆ
β

m2 − ∇2
nαβ
+
f
2
2
nµν
δνβdµdˆ
α − δµβdνdˆ
α
m2 − ∇2
nαβ
−iπm
2
nµν
δµαδνβ − δµβδνα
m2 − ∇2 Mαβ
(14) .
Performing Gaussian integration over the field nµν, we obtain
S M =
X
x
Λ
2
8
Mµν
δµαδνβ − δµβδνα
−∇2 Mαβ . (15)
This is the second main result of this paper. The global condensation in the superconducting phase turns the vortex interaction into a long-range one, suppressing the topological
screening. As has been derived in [4], a 4D Coulomb potential for the elements of the world-surface of a vortex implies
that the self-energy of a circular vortex-loop of radius r scales
like r lnr, which amounts to logarithmic vortex confinement
as is the case in 2D. In these inhomogeneous 3D superconductors, thus, the destruction of global superconductivity via tunnelling percolation also takes places by vortex liberation, similarly to the 2D BKT transition. Since vortices are 1D objects,
this happens when the effective string tension of the vortices,
including the entropy correction, vanishes. This transition has
been studied in [30] and leads to the VFT critical behaviour
of the resistance given by Eq. (2).
EXPERIMENT
Standard four-terminal dc resistance measurements, see the
inset in Fig. 1a, are taken on films of the nitrides of the transition metals, NbTiN and NbN. The detailed preparation of the
20-nm-thick NbN film on an MgO substrate can be found in
Methods. The zero-temperature coherence length of this film
is measured to be (4.40 ± 0.05) nm, i.e., much shorter than
the film thickness d = 20 nm hence the NbN film is a 3D superconductor. The details of the preparation of the disordered
nonstoichiometric 86-nm-thick NbTiN film can be found in
Ref. [41]. This film is deposited on a Si (100) substrate by
radio frequency (RF) reactive magnetron co-sputtering from
two separate NbN and TiN targets. As the film is deposited
on a Si substrate, it is fully compatible with the existing Si
CMOS technology. We benefit from the fact that this NbTiN
film has been studied before [41]. The zero-temperature coherence length is measured to be (9.53 ± 0.04) nm, which is
much shorter than the film thickness 86 nm [41]. Therefore,
we also have a 3D superconductor system. Both samples are
approximately rectangular films with the length of ≈ 4.5 mm
and the width of ≈ 3.5 mm. As shown later, we see that the
VFT model fits the data much better than the corresponding
BKT one does.
Figure 1a shows the four-terminal dc resistance measurements of the 20-nm-thick NbN film grown on the MgO substrate as a function of temperature T. We observe a rather
broad metal-superconductor transition with decreasing T. In
order to further study this, we fit our experimental results with
the BKT- (red curve) and the VFT (blue curve) scaling resistivity. Note that we use the same three fitting parameters,
the critical temperature, the overall normalization of the resistance, and a constant b having the dimensionality of temperature) for the two fits. The aim is to compare the two scalings
and identify the best one. Marking the six data points that
5
a b
FIG. 1. Resistance measurements. a: Four-terminal dc resistance
measurements of the 20-nm-thick NbN film at different temperatures.
The red and blue curves correspond to BKT fitting and VFT fitting
to the experimental data, respectively. The gray points mark experimental data deviating from the fits. The inset depicts a sketch of the
four-terminal dc resistance measurements of NbN and NbTiN films.
Electrodes V+
and V−
correspond to the two voltage probes for measuring the voltage difference. Electrodes I+
and I−
are the source
and drain contacts. The symbols V and I stand the voltmeter and
ammeter measuring the voltage difference and current, respectively.
b: Four-terminal dc resistance measurements of a 20-nm-thick NbN
film at different temperatures. The red and blue curves correspond
to the BKT fitting and VFT fitting to the experimental data, respectively. The three data points marked gray show the noticeable deviation from the fits.
significantly deviate from any fit in grey, we see that the VFT
dependence fits the experimental results much better than the
BKT one does, see Fig. 1a. Analogous study is performed on
the much thicker NbTiN film with a thickness of 86 nm deposited on a Si substrate. Figure 1b displays the same kind of
the four-terminal dc resistance measurements. Again, we observe a broad metal-superconductor transition with decreasing
temperature. The BKT scaling clearly fails to fit the experimental data. The VFT fits describe the experimental data very
well, except for three points marked grey. While at present no
concrete model for this deviation, which could be caused by
nonstoichiometric disorder, can be offered, one can strongly
assume that it is caused by quantum corrections to the resistance which become essential in the close vicinity of the
superconducting transition temperature Tc which noticeably
exceeds TVFT. The fact that in thicker (86 nm thick) NbTiN
film these deviations are much smaller than in the 20 nm thick
NbN film excellently agrees with this assumption. However,
detailed calculations beyond the scope of the present work are
necessary to quantitatively explore this assumption.
The next step is to confirm that the observed resistance behavior reflects the genuine bulk superconducting properties
rather than stems from the local superconductivity that might
arise at the surface or 1D defect filaments of the investigated
samples. To that end, we perform magnetic susceptibility
measurements. As shown in Fig. 2, the investigated systems
demonstrate strong diamagnetic response in the magnetic susceptibility, evidencing that the observed superconductivity is
the genuine bulk superconductivity for both films. The downward then upward behavior of the magnetic susceptibility in
the 86-nm-thick NbTiN film in the FC condition indicates possible paramagnetic Meissner effect (PME) [42]. The PME
a b
FIG. 2. Magnetization measurements under zero-field-cooled
(ZFC) and field-cooled (FC) condictions. a: Magnetization of the
20 nm-thick NbN film. Insert: magnetic susceptibility. The measurements are taken under the external field of 20 Oe.b: Magnetization of
the 86 nm-thick NbTiN film. The measurements are taken under the
external field of 5 Oe.
generally appears in superconductors with strong vortex pinning at low temperatures.
CONCLUSION
Our results reveal the existence of a novel type of superconductivity, which we call type-III superconductivity. The
standard superconductivity is well described by the local
Ginzburg-Landau theory for a homogeneous, global order parameter in which gauge fields are screened by the AndersonHiggs mechanism and which usually corresponds to the microscopic BCS pairing mechanism. The type III superconductivity is described by a topological gauge theory and corresponds to an inhomogeneous network of condensate droplets
getting connected by tunneling pairs percolation and is destroyed by vortex liberation instead of pairs breaking. The underlying physics is the generalization of the BKT physics to
three dimensions. The corresponding predicted modified exponential VFT scaling of the resistance is fully confirmed by
experiment. In 2D, only this second type of superconductivity
survives due to strong infrared divergences in the GinzburgLandau theory, in 3D both types of superconductivity are possible. There are strong hints that the type of superconductivity
that we describe here is associated with the BEC of strongly
bound electron pairs and is realized in the high-Tc materials.
EXPERIMENTAL SECTION
Preparation of the NbN film
We used the radio frequency (RF) reactive magnetron sputter to deposit a 20-nm-thick NbN film on the MgO (100) substrate in an ultrahigh vacuum chamber with the base pressure of 3.9·10−9 Torr, We fixed the argon/nitrogen flow rate
to 12:0.5. The fixed gas pressure of 3 mTorr and the fixed RF
power of 120 W are used. The argon plasma (12 sccm) strikes
the NbN target and atoms or molecules are ejected from the
target surface. These atoms or molecules travel towards the
6
silicon substrate with the high temperature of 800 ◦ C and
deposit as the NbN film.
Preparation of the NbTiN film
The detailed description regarding the preparation of the
disordered nonstoichiometric 86-nm-thick NbTiN film is
given in [41]. In short, our film is deposited on a Si (100)
substrate by the RF reactive magnetron co-sputtering from
two separate NbN (99.5 %) and TiN (99.5 %) targets at 800
◦ C. The base pressure in the chamber is less than 9·10−9 Torr,
and the gas pressure is controlled at 3 mTorr during the deposition. The RF sputtering powers of both targets are set as
100 W. The gas flow rate ratio of argon and nitrogen is 12:0.5.
The argon plasma (12 sccm) strikes two targets, and atoms or
molecules are ejected from the target’s surface. These atoms
or molecules travel towards the silicon substrate with the high
temperature of 800 ◦ C and deposit as the NbTiN film. The
large lattice mismatch between NbTiN and Si possibly leads
to disordered and inhomogeneous nature of the NbTiN film.
Electrical measurements
The low-temperature four-terminal resistance measurements are performed in an Oxford Triton 200 cryo-free
3He/
4He dilution fridge. We use the Keithley 2400 current
source meter to provide a constant dc current that flows from
the source to the drain contact. On the other hand, A Keithley
2000 multimeter is used to measure the voltage drop between
the two voltage probes.
Magnetization measurements
Magnetic susceptibility measurements were carried out
using a dc superconducting quantum interference device
(SQUID) magnetometer. Both zero-field-cooled (ZFC) and
field-cooled (FC) regimes are used.