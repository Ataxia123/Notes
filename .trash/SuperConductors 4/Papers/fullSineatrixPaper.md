Origin of correlated isolated flat bands in copper-substituted lead phosphate apatite.
Sin´ead M. Griffin1,2
1Materials Sciences Division, Lawrence Berkeley National Laboratory, Berkeley, California, 94720, USA and
2Molecular Foundry Division, Lawrence Berkeley National Laboratory, Berkeley, California, 94720, USA
(Dated: August 1, 2023)
A recent report of room temperature superconductivity at ambient pressure in Cu-substituted
apatite (‘LK99’) has invigorated interest in the understanding of what materials and mechanisms
can allow for high-temperature superconductivity. Here I perform density functional theory calculations on Cu-substituted lead phosphate apatite, identifying correlated isolated flat bands at the
Fermi level, a common signature of high transition temperatures in already established families of
superconductors. I elucidate the origins of these isolated bands as arising from a structural distortion induced by the Cu ions and a chiral charge density wave from the Pb lone pairs. These results
suggest that a minimal two-band model can encompass much of the low-energy physics in this system. Finally, I discuss the implications of my results on possible superconductivity in Cu-doped
apatite.
INTRODUCTION
High-TC superconductors are arguably the holy grail
of condensed matter physics with huge potential applications for an energy-efficient future. The first class
of superconductors that were considered to be high-TC
were the cuprates which were discovered by Bednorz and
M¨uller in 1987 [1]. The cuprates have been subsequently
followed by several new classes including the Fe-pnictides
in 2008 [2] and the nickelates [3].
While significant strides have been made in the discovery and understanding of high-TC superconductors,
and we continue to unearth novel examples within established classes [4], a definitive roadmap to achieving roomtemperature TC under ambient pressures has remained
elusive. Common to many of these high-TC superconducting families are strongly correlated bands which can
give rise to unconventional mechanisms for Cooper pair
formation [5, 6], and proximity to multiple competing
interactions such as antiferromagnetism, charge density
waves and spin-density waves. These phases can compete
or coexist with superconductivity where fluctuations between these states are believed to play a significant role
for achieving high-TC . Searching for these features in
new materials systems is therefore a promising route for
finding new classes of high-TC superconductors. For instance, the nickelate supercondcutors were originally predicted in theory by Anisimov, Bukhvalov and Rice as an
analogy to the cuprate superconductors [7]. Similar approaches have also been proposed to selectively design a
material with the sought-after isolated d-manifold that
is associated strong correlations [8], and have inspired
high-throughput searches for good candidate materials,
further expanding the horizons of high-Tc superconductivity [9].
The recent report of possible room temperature superconductivity at ambient pressures in Cu-substituted
apatite (also known as ‘LK99’)[10, 11] motivates the need
for a thorough understanding of the structure-property
relationships in these compounds to begin to unravel
their potential correlated physics. In this Letter, I use
ab initio calculations to elucidate the key completing interactions in Cu-doped apatite at the mean-field density
functional level.
METHODS
I used the Vienna Ab initio Simulation Package
(VASP) [12–15] for all density functional theory (DFT)
calculations with full calculation details given in the SI.
I applied a Hubbard-U correction to account for the underlocalization of the Cu-d states. I tested values of U
between 2 eV and 6 eV, finding my results were similar
for all values calculated. The results in the main text are
for U = 4 eV which gives lattice parameters within 1%
of experiment [10, 16].
RESULTS
Structural Properties
Apatites are materials with the general formula
A10(TO4)6X2±x, where A = alkaline or rare earth metal;
M = Ge, Si, or P; and X = halide, O, or OH. The
name ‘apatite’ derives from the Greek apat¯e meaning
‘deceit’ as a result of the diverse range of forms it can
take [17]. Here I consider the lead-phosphate apatite
Pb10(PO4)6(OH)2. Taking its structure reported from
X-ray diffraction in Ref. [16] as the starting point, its
relaxed following a structural optimization is depicted in
Fig. 1. It adopts the typical crystal structure of various apatite chemistries, namely it forms a network comprising PbO6 prisms that are corner shared with PO4
tetrahedra. I refer to these Pb as Pb(1), in keeping with
the convention in literature [18]. This framework is filled
with Pb6(OH)2 where the (OH)2 forms a chain in the
arXiv:2307.16892v1 [cond-mat.supr-con] 31 Jul 2023
2
FIG. 1. (a) Lead-phosphate apatite structure with two inequivalent Pb sites as described in the main text. Columns of
O or OH sit in the center column defined by Pb(2) hexagonal
structure. (b) Calculated electronic localization function for
Pb10(PO4)6OH2. Oxygens surrounding Pb(2) are repelled by
the lone pair.
center of a hexagonal structure defined by these Pb(2)
atoms. While here I consider OH−1 filling the hexagonal column, I obtained similar results for O only in the
column. Typically apatites adopt the hexagonal P63/m
space group – here our resulting structure has P63 owing to the breaking of reflection from the OH molecule
ordering. However, small structural deviations from the
P63/m commonly occur depending on its constituents.
While the Pb(1) forms the overall framework with the
PO4 tetrahedra, the Pb(2) play a crucial role in Pb-O
connectivity and polyhedra tilts throughout the structure. In fact, while both Pb(1) and Pb(2) possess 6s2
lone pairs, only the latter is stereochemically active. I
verify this by calculating the electronic localization function (ELF) as shown in Fig. 1(b), finding that the Pb(2)
lone pairs form a chiral arrangement that make angle of
∼ 105◦ with the a-axis (see SI for more details). The
chiral arrangement of the lone pairs sets the resulting
oxygen coordination of the Pb(2), namely its six oxygens
are arranged asymmetrically as a result of their repulsion from the lone pair forming a chiral charge density
wave. Since these oxygen are corner shared with the PO4,
the structural distortions associated with the Pb(2) lone
pair activity propagate throughout the structure. Such
an effect has been discussed previously in various apatite
materials, noting that the lone pair ordering differs depending on the specific system [18, 19].
I next consider the substitution of Cu on a Pb(1) site
resulting in CuPb9(PO4)6OH2, with the fully optimized
structure shown in Fig. 2(b). I find several changes to
the structure with the inclusion of Cu. Firstly, all lattice parameters decrease with a going from 9.875 ˚A to
9.738 ˚A and c going from 7.386 ˚A to 7.307 ˚A. While
my calculated lattice parameters agree well with those
reported in Ref.[10], I find a greater structure collapse
than their report of a going from 9.865 ˚A without Cu to
9.843 ˚A with Cu, and c going from 7.431 ˚A without Cu
to 7.428 ˚A with Cu. Interestingly, I find Cu substitution
results in a global structural distortion that results in a
change in coordination from nine to six (with a cutoff
FIG. 2. (a) Lead-phosphate apatite structure showing ninecoordinated Pb(1) sites. (b) Cu-substituted structure showing six-coordinated Cu and Pb(1) sites with distorted trigonal
prism coordination with two different bondlengths are a rigid
twist of ∼ 24◦ between the upper and lower triangles. A cartoon of the resulting crystal-field diagram for Cu-d
9
is given
on the right.
of 3 ˚A) not only for the Cu on the Pb(1) site, but also
for all other Pb(1) sites. This results in a modification
of the polyhedral tilts throughout the structure, most
notably in the PO4 polyhedra, as seen in Fig. 2(b). I
classify the distortion through analysis of the symmetryadapted phonon modes before and after Cu substitution
finding the structural distortion to be caused by Γ1 and
Γ2 modes of amplitudes 1.19˚A and 1.78˚A respectively.
Visualization of these symmetry-adapted modes is given
in the SI (Fig. S1); this analysis confirms that the structural distortion caused by the Cu substitution on Pb(1)
is primarily driven by polyhedral tilts of the PO4 and
their corner-shared oxygen neighbors.
Looking closely at the change in coordination of Cu on
the Pb(1) site, I see the Cu2+ is now six-coordinated with
oxygen forming a distorted Jahn-Teller trigonal prism.
In an ideal trigonal prism the anions are arranged at the
vertices of a regular triangular prism with the transition
metal at the center with D3h symmetry. However, breaking in-plane mirror symmetry results in Jahn-Teller distorted trigonal crystal field with C3v symmetry, such as is
found in the Janus compounds [20]. Here I find the mirror is already broken by the next-nearest neighbor P ions
the Cu-O distance that has nearby P is 2.06 ˚A, whereas
the Cu-O without surround P ions is 2.35 ˚A. Such out-ofplane asymmetry in the Cu environment results in a local dipole in z which can also influence the resulting electronic structure [20]. In addition to the mirror symmetry
breaking, the O triangles are also rotated at a small angle
of ∼ 24◦ with respect to each other, referred to as a Bailar
twist in molecules[21], giving the final distorted trigonal
prism. Interestingly, the same structural distortion has
been observed upon substitution of U on the Ca(1) site in
fluorapatite Ca10(PO4)6F2 as measured from X-ray absorption spectroscopy [22]. There the authors found that
3
FIG. 3. Calculated spin-polarized electronic band structure
(left) and corresponding density of states (right). The spin-up
bands are depicted in solid orange, and the spin-down bands
are dashed blue. The total density of states is shaded grey
with projections shown of the Cu-d orbitals (pink) and its
neighboring O-p orbitals (green). In both plots the Fermi
level is set to 0 eV and is marked by the dashed line.
the U substitution on the Ca(1) sites causes an usual 6-
coordinated structure – a trigonal prism with six equal
bondlengths of 2.06˚A with an undetermined Bailar twist
angle, however.
Electronic Structure
I present the calculated spin-polarized electronic structure in Fig. 3. Remarkably, I find an isolated set of flat
bands crossing the Fermi level, with a maximum bandwidth of ∼130 meV (see Fig.4) that is separated from
the rest of the valence manifold by 160 meV. Such a
narrow bandwidth is particularly indicative of strongly
correlated bands. These especially flat bands are consistent with the Cu-O coordination where I find Cu-O
bondlengths of 2.35 ˚A and 2.06 ˚A in the distorted trigonal prism. For comparison, the Cu-O bondlengths in the
cuprate superconductors are typically ≤ 2˚A (in-plane)
and ≤ 2.3˚A (apical) [3], giving further evidence of the
unusual coordination and resulting band localization in
this isolated Cu-d manifold.
The crystal-field splitting for the trigonal prism comprises a single dz
2 , doubly degenerate dxy and dx2−y2 , and
doubly degenerate dyz and dxz. In fact, the relative positioning of the dz
2 and the dyz/dxz is set by the anisotropy
induced by the mirror-symmetry breaking large values
of asymmetry can cause the dz
2 to be destabilized. In our
case for Cu2+ with a d
9
configuration I expect half filling
of the doubly degenerate dyz/dxz bands - this is corroborated with our calculations in Fig. 3 where I find two
bands of dyz/dxz character at Fermi level that are are half
filled. My results suggest that low-energy physics of this
system can be described by a two-band dyz/dxz model,
FIG. 4. Calculated spin-polarized electronic band structure
in smaller energy range around the Fermi level showing the
isolated two-band Cu-d manifold. The Fermi level is set to 0
eV and is marked by the dashed line.
similar to that originally suggested for Fe-pnictide superconductors [23, 24]. However, unlike other correlated-d
band superconductors, in this system the Cu-d bands are
particularly flat – there is minimal band broadening from
neighboring oxygen ions. If previous assumptions about
band flatness driving superconductivity are correct, then
this result would suggest a much more robust (higher
temperature) superconducting phase exists in this system, even compared to well-established high-TC systems.
While the calculations presented here are performed
for GGA+U with a U = 4 eV applied to the Cu-d, I find
the same qualitative features of the band structures for a
wide range of U values, as presented in the SI. This suggests that the presence of such an isolated manifold of
flat Cu-d bands is a feature of the structural reconstruction and new crystal field environment provided by the
apatite network. I further confirm this by calculating the
band structure of the Cu-substituted compound without
performing a structural relaxation, that is, taking structure of the ideal Pb10(PO4)6(OH)2 and replacing a Pb(1)
with Cu without allowing the structure to relax. In this
case, I find slight spin-polarization in the band structure, however all Cu-d states are now in the bulk valence
manifold and do not form an isolated manifold (see SI
Fig. S3). Finally, the top of the valence band is made
up of the Pb(2)-s states, confirming their contribution to
the stereochemical activity of the lone pairs (see SI).
I next investigate the exchange interactions between
Cu ions in different unit cells by constructing doubled
unit cells in the in-plane and out-of-plane directions. I
find that there is a preference of 2 meV/Cu for ferromagnetic coupling in the out-of-plane direction (with a
Cu-Cu separation of c = 7.307 ˚A), whereas a preference
of 7 µeV/Cu for antiferromagnetic coupling in the inplane direction (with a Cu-Cu separation of a = 9.738˚A).
However, while this result is indicative of the potential
exchange interactions in the system, it relies on the unrealistic assumption that the Cu ions will sit on the same
4
substitution position in each unit cell. A full study of
potential exchange interactions for various Cu locations
is out of the scope of this work, and will crucially be
informed by the Cu locations determined in experiment.
So far all calculations have been for Cu on the Pb(1)
site, which is the site occupancy reported in Ref.[10]. I
also calculated the structural and electronic properties
of Cu in the Pb(2) site with the resulting structure and
bands given in the SI. In this location, the Cu interrupts
the hexagonal network that is characteristic of the apatite structure, which causes a structural rearrangement
to the lower P1 symmetry. The Cu substituted in this
position is now tetrahedrally coordinated by oxygen, and
has a significantly different electronic structure with no
correlated d bands crossing the Fermi level, as detailed
in the SI. In fact, I find that Cu on this Pb(2) is 1.08 eV
more energetically favorable that Cu on the Pb(1) site,
suggesting possible difficulties in robustly obtaining Cu
substituted on the Pb(1) site.
DISCUSSION
These theoretical results suggest that the apatite structure provides a unique framework for stabilizing highly
localized Cu-d
9
states that form a strongly correlated flat
band at the Fermi level. The central role of stereochemically active 6s2
lone pairs of Pb(2) manifests in the formation of a chiral charge density wave and the propagation of structural distortions with connected polyhedra.
When Cu is substituted on a Pb(1) site, the result is a
cascade of structural alterations, including reduced lattice parameters, changes in coordination, and modified
polyhedral tilts, leading to a local Jahn-Teller distorted
trigonal prism around Cu. This results in an unusually
flat set of isolated dyz/dxz bands with half-filling.
I briefly note that achieving such a crystal field environment should also be possible in intercalated twisted
heterogeneous bilayers where selection of different heterobilayers can provide the mirror symmetry breaking, while
moir´e twist can provide an arbitrary rotation of the upper and lower triangles. In fact such a platform would be
ideal for probing the physics found here given its broad
range of tunability and the state-of-the-art characterization probes for their interrogation [25].
I now discuss the potential implications of these features of Cu-substituted apatite for possible high-TC superconductivity, and in particular the role of the flat
bands and the presence of competing magnetic interactions and phonons. Isolated, flat bands have long been
a target for achieving high-TC as predicted from BCS
theory[26–28]. The critical temperature TC given by by
TC ∝ exp(−1/|U|ρ0(EF )), where |U| is the magnitude
of the effective attractive interaction and ρ0(EF ) is the
density of states at the Fermi surface. In a flat band
where the density of states diverges, TC is proportional
to |U|. This suggests that, at low interaction strengths,
the critical temperature in flat bands could be significantly enhanced, as is currently being explored in various
moir´e systems[29]. In our case, the correlated bands have
a bandwidth of ∼ 130 meV which is less than their separation from the rest of the valence manifold (160 meV) at
the level of density functional theory. While strong correlations will need to be taken into account adequately
to accurately describe these scenarios, these are promising hints for these proposals that predicts that the TC is
proportional to the interaction strength.
In contrast to conventional superconductors, where
phonon-mediated interactions govern Cooper pair formation, there is wide consensus that other bosonic excitations are responsible for the attractive pair formation in
high-TC superconductors ranging from paramagnons to
spin- and charge-density waves [30]. In this system, I
have identified several potential sources of fluctuations
that could contribute to pairing. Firstly, I identified a
charge density wave (CDW) driven by chiral lone pair
ordering on the Pb(2) sites – the presence of this CDW
is strongly connected to the structural rearragement that
occurs when Cu is incorporated into the Pb(1) lattice
sites. In addition to this, I identified two zone-center
phonon modes that trigger the global structural deformation that occurs as a result of the Cu substitution, suggesting potentially strong electron-phonon coupling for
these modes. Finally, I calculated the relative exchange
interactions between Cu in neighboring unit cells. Interestingly for the out-of-plane coupling, that is, along the
Cu-Pb-Cu one-dimensional chains, I find ferromagnetic
coupling is favored by 2 meV/Cu over antiferromagnet
coupling, even though the Cu are over 7 ˚A apart, suggesting that spin fluctuations could also play a key role.
Finally, the calculations presented here suggest that
Cu substitution on the appropriate (Pb(1)) site displays
many key characteristics for high-TC superconductivity,
namely a particularly flat isolated d-manifold, and the
potential presence of fluctuating magnetism, charge and
phonons. However, substitution on the other Pb(2) does
not appear to have such sought-after properties, despite
being the lower-energy substitution site. This result hints
to the synthesis challenge in obtaining Cu substituted on
the appropriate site for obtaining a bulk superconducting
sample. Nevertheless, I expect the identification of this
new material class to spur on further investigations of
doped apatite minerals given these tantalizing theoretical
signatures and experimental reports of possible high-TC
superconductivity.
Acknowledgements-. I am grateful to David Prendergast, Adam Schwartzberg, Shuhada’ Sadaqat and John
Vinson for insightful discussions and encouragement. I
also thank D. Kwabena Bediako, Donnie Evans, Adam
Schwartzberg and John Vinson for feedback on this draft.
This work was funded by the U.S. Department of Energy, Ofce of Science, Ofce of Basic Energy Sciences,
[[gptSummarySineatrixPaper]]
