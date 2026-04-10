---
layout: post
title: "My Mathematically Technical Paper"
date: 2026-04-10
custom_css: ["ltx-article.css", "LaTeXML.css"]
---

<!DOCTYPE html><html prefix="dcterms: http://purl.org/dc/terms/" lang="en">
<head>
<meta http-equiv="content-type" content="text/html; charset=UTF-8">
<title>A Companion to Shamkanov’s Circular Proofs for the Gödel–Löb Provability Logic Understanding how Proof System Transformations, Circularity, and Fixed-point Theorems, give Interpolation in GL</title>
<!--Generated on Fri Apr 10 18:38:38 2026 by LaTeXML (version 0.8.8) http://dlmf.nist.gov/LaTeXML/.-->

<link rel="stylesheet" href="LaTeXML.css" type="text/css">
<link rel="stylesheet" href="ltx-article.css" type="text/css">
<meta name="viewport" content="width=device-width, initial-scale=1, shrink-to-fit=no">
</head>
<body>
<div class="ltx_page_main">
<div class="ltx_page_content">
<article class="ltx_document ltx_authors_1line">
<div id="p1" class="ltx_para">
<span class="ltx_ERROR undefined">\newmdenv</span>
<p class="ltx_p">[
backgroundcolor=lightblue,
linecolor=midblue,
linewidth=0.8pt,
roundcorner=3pt,
innertopmargin=7pt, innerbottommargin=7pt,
innerleftmargin=9pt, innerrightmargin=9pt,
skipabove=8pt, skipbelow=4pt
]keybox
<span class="ltx_ERROR undefined">\newmdenv</span>[
backgroundcolor=boxgray,
linecolor=rulecolor,
linewidth=0.8pt,
roundcorner=3pt,
innertopmargin=7pt, innerbottommargin=7pt,
innerleftmargin=9pt, innerrightmargin=9pt,
skipabove=8pt, skipbelow=4pt
]graybox</p>
</div>
<h1 class="ltx_title ltx_title_document" style="font-size:120%;">
<span class="ltx_text ltx_font_bold" style="font-size:83%;">A Companion to Shamkanov’s
<br class="ltx_break"><span class="ltx_text ltx_font_italic">Circular Proofs for the Gödel–Löb Provability Logic
<br class="ltx_break"></span><span class="ltx_text ltx_font_medium">
</span></span>Understanding how Proof System Transformations, Circularity, and Fixed-point Theorems, give Interpolation in GL</h1>
<div class="ltx_authors">
<span class="ltx_creator ltx_role_author">
<span class="ltx_personname">Siva Sanjai G. Arumugam
</span></span>
</div>

<div class="ltx_abstract">
<h6 class="ltx_title ltx_title_abstract">Abstract</h6>
<p class="ltx_p">This is a companion to the 2014 paper by D. S. Shamkanov
<cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib1" title="" class="ltx_ref">1</a>]</cite>, which gives the first syntactic proof of the Lyndon
interpolation property for the Gödel–Löb provability logic <math id="m1" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math>.
Instead of an explanation of his whole proof flush with the many theorems and lemmas, this companion takes on, for elaboration and explanation, the most important questions that naturally arise when trying to follow Shamkanov’s paper:
what is it about the standard modal rule for <math id="m2" class="ltx_Math" alttext="\mathbf{GL}_{\mathbf{Seq}}" display="inline"><msub><mi>𝐆𝐋</mi><mi>𝐒𝐞𝐪</mi></msub></math> that makes Lyndon interpolation difficult; why replacing it with a simpler rule in <math id="m3" class="ltx_Math" alttext="\mathbf{GL}_{\infty}" display="inline"><msub><mi>𝐆𝐋</mi><mi mathvariant="normal">∞</mi></msub></math> makes infinite proofs possible; how the admissibility of the Löb rule and the structure of circular proofs together give the three-way equivalence; and how the GL fixed-point theorem resolves the twofold self-reference encountered when building interpolants from split circular proofs.</p>
</div>
<div id="p2" class="ltx_para ltx_noindent">
<p class="ltx_p"><span class="ltx_text ltx_font_bold">Note that</span>
all theorem numbers, lemma numbers, and equation labels match those of
<cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib1" title="" class="ltx_ref">1</a>]</cite> unless otherwise indicated.</p>
</div>
<section id="S1" class="ltx_section">
<h2 class="ltx_title ltx_font_bold ltx_title_section" style="font-size:120%;--ltx-fg-color:#0F3773;">1.  Background: Provability Logic and Why It Matters</h2>

<div id="S1.p1" class="ltx_para">
<p class="ltx_p">Gödel’s 1931 incompleteness theorems revealed that Peano Arithmetic
(<math id="S1.p1.m1" class="ltx_Math" alttext="\mathbf{PA}" display="inline"><mi>𝐏𝐀</mi></math>) contains a predicate <math id="S1.p1.m2" class="ltx_Math" alttext="\mathrm{Prov}(x)" display="inline"><mrow><mi>Prov</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>x</mi><mo stretchy="false">)</mo></mrow></mrow></math>,definable in the language of
arithmetic, that expresses “the formula with code <math id="S1.p1.m3" class="ltx_Math" alttext="x" display="inline"><mi>x</mi></math> is provable in
<math id="S1.p1.m4" class="ltx_Math" alttext="\mathbf{PA}" display="inline"><mi>𝐏𝐀</mi></math>.” This predicate satisfies three <em class="ltx_emph ltx_font_italic">derivability conditions</em>
(Hilbert–Bernays–Löb): it distributes over implication, is self-aware
(if <math id="S1.p1.m5" class="ltx_Math" alttext="\mathbf{PA}\vdash\varphi" display="inline"><mrow><mi>𝐏𝐀</mi><mo>⊢</mo><mi>φ</mi></mrow></math> then <math id="S1.p1.m6" class="ltx_Math" alttext="\mathbf{PA}\vdash\mathrm{Prov}(\lceil\varphi\rceil)" display="inline"><mrow><mi>𝐏𝐀</mi><mo>⊢</mo><mrow><mi>Prov</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mrow><mo stretchy="false">⌈</mo><mi>φ</mi><mo stretchy="false">⌉</mo></mrow><mo stretchy="false">)</mo></mrow></mrow></mrow></math>), and is
introspective (<math id="S1.p1.m7" class="ltx_Math" alttext="\mathrm{Prov}(\lceil\varphi\rceil)\to\mathrm{Prov}(\lceil\mathrm{Prov}(\lceil%
\varphi\rceil)\rceil)" display="inline"><mrow><mrow><mi>Prov</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mrow><mo stretchy="false">⌈</mo><mi>φ</mi><mo stretchy="false">⌉</mo></mrow><mo stretchy="false">)</mo></mrow></mrow><mo stretchy="false">→</mo><mrow><mi>Prov</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mrow><mo stretchy="false">⌈</mo><mrow><mi>Prov</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mrow><mo stretchy="false">⌈</mo><mi>φ</mi><mo stretchy="false">⌉</mo></mrow><mo stretchy="false">)</mo></mrow></mrow><mo stretchy="false">⌉</mo></mrow><mo stretchy="false">)</mo></mrow></mrow></mrow></math>
is provable). Logician Löb wondered then, if it is possible to characterize formulae for which it is possible to prove their provability will give their truth. This resulted in his coming up with Löb’s theorem <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib3" title="" class="ltx_ref">3</a>]</cite>:</p>
</div>
<div id="S1.Thmtheorem1" class="ltx_theorem ltx_theorem_theorem">
<h6 class="ltx_title ltx_runin ltx_title_theorem">
<span class="ltx_tag ltx_tag_theorem"><span class="ltx_text ltx_font_bold" style="--ltx-fg-color:#0F3773;">Theorem 1.1</span></span><span class="ltx_text ltx_font_bold" style="--ltx-fg-color:#0F3773;"> <span class="ltx_text ltx_font_medium">(Löb, 1955)</span>.</span>
</h6>
<div id="S1.Thmtheorem1.p1" class="ltx_para">
<p class="ltx_p"><math id="S1.Thmtheorem1.p1.m1" class="ltx_Math" alttext="\mathbf{PA}\vdash\mathrm{Prov}(\lceil\varphi\rceil)\to\varphi" display="inline"><mrow><mi>𝐏𝐀</mi><mo>⊢</mo><mrow><mrow><mi>Prov</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mrow><mo stretchy="false">⌈</mo><mi>φ</mi><mo stretchy="false">⌉</mo></mrow><mo stretchy="false">)</mo></mrow></mrow><mo stretchy="false">→</mo><mi>φ</mi></mrow></mrow></math><span class="ltx_text ltx_font_italic">   if and only if  
<math id="S1.Thmtheorem1.p1.m2" class="ltx_Math" alttext="\mathbf{PA}\vdash\varphi" display="inline"><mrow><mi>𝐏𝐀</mi><mo>⊢</mo><mi>φ</mi></mrow></math>.</span></p>
</div>
</div>
<div id="S1.p2" class="ltx_para">
<p class="ltx_p">Formulae for which their provability gives truth are those that are already provable outright.</p>
</div>
<div id="S1.p3" class="ltx_para">
<p class="ltx_p">It was soon noticed that replacing <math id="S1.p3.m1" class="ltx_Math" alttext="\mathrm{Prov}(\lceil\varphi\rceil)" display="inline"><mrow><mi>Prov</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mrow><mo stretchy="false">⌈</mo><mi>φ</mi><mo stretchy="false">⌉</mo></mrow><mo stretchy="false">)</mo></mrow></mrow></math> by a modal operator <math id="S1.p3.m2" class="ltx_Math" alttext="\Box\varphi" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>φ</mi></mrow></math>
turns the derivability conditions into the axioms of a modal logic.
The <em class="ltx_emph ltx_font_italic">Gödel–Löb logic</em> <math id="S1.p3.m3" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math> is the normal modal logic axiomatised by
the classical tautologies, <math id="S1.p3.m4" class="ltx_Math" alttext="\Box(A\to B)\to(\Box A\to\Box B)" display="inline"><mrow><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mrow><mi>A</mi><mo stretchy="false">→</mo><mi>B</mi></mrow><mo stretchy="false">)</mo></mrow></mrow><mo stretchy="false">→</mo><mrow><mo stretchy="false">(</mo><mrow><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow><mo stretchy="false">→</mo><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>B</mi></mrow></mrow><mo stretchy="false">)</mo></mrow></mrow></math>, and
<em class="ltx_emph ltx_font_italic">Löb’s axiom</em></p>
<table id="S1.Ex1" class="ltx_equation ltx_eqn_table">

<tbody><tr class="ltx_equation ltx_eqn_row ltx_align_baseline">
<td class="ltx_eqn_cell ltx_eqn_center_padleft"></td>
<td class="ltx_eqn_cell ltx_align_center"><math id="S1.Ex1.m1" class="ltx_Math" alttext="\Box(\Box A\to A)\to\Box A." display="block"><mrow><mrow><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mrow><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow><mo stretchy="false">→</mo><mi>A</mi></mrow><mo stretchy="false">)</mo></mrow></mrow><mo stretchy="false">→</mo><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow></mrow><mo lspace="0em">.</mo></mrow></math></td>
<td class="ltx_eqn_cell ltx_eqn_center_padright"></td>
</tr></tbody>
</table>
<p class="ltx_p">By Solovay’s completeness theorem <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib4" title="" class="ltx_ref">4</a>]</cite>, <math id="S1.p3.m5" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math> is exactly
the logic of arithmetic provability: a modal formula is provable in <math id="S1.p3.m6" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math>
if and only if all its arithmetic substitution instances are provable in
<math id="S1.p3.m7" class="ltx_Math" alttext="\mathbf{PA}" display="inline"><mi>𝐏𝐀</mi></math>. Semantically, <math id="S1.p3.m8" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math> is sound and complete for the class of
<em class="ltx_emph ltx_font_italic">finite strict partial orders</em> (Segerberg <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib5" title="" class="ltx_ref">5</a>]</cite>):
Kripke frames in which the accessibility relation is transitive,
irreflexive, and well-founded. The well-foundedness is the semantic
counterpart of Löb’s theorem; this turns out to be a crucial point when thinking of generalisations of Shamkanov’s proof beyond <math id="S1.p3.m9" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math>.</p>
</div>
<div id="S1.p4" class="ltx_para">
<p class="ltx_p">The paper <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib1" title="" class="ltx_ref">1</a>]</cite> works in the one-sided Tait-style sequent
calculus <math id="S1.p4.m1" class="ltx_Math" alttext="\mathbf{GL}_{\mathbf{Seq}}" display="inline"><msub><mi>𝐆𝐋</mi><mi>𝐒𝐞𝐪</mi></msub></math>, in which a sequent <math id="S1.p4.m2" class="ltx_Math" alttext="\Gamma" display="inline"><mi mathvariant="normal">Γ</mi></math> is a finite multiset of
formulas whose intended meaning is <math id="S1.p4.m3" class="ltx_Math" alttext="\Gamma^{\sharp}=\bigvee_{A\in\Gamma}A" display="inline"><mrow><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup><mo rspace="0.111em">=</mo><mrow><msub><mo>⋁</mo><mrow><mi>A</mi><mo>∈</mo><mi mathvariant="normal">Γ</mi></mrow></msub><mi>A</mi></mrow></mrow></math>.
Formulas are built from propositional constants, their duals <math id="S1.p4.m4" class="ltx_Math" alttext="\bar{A}" display="inline"><mover accent="true"><mi>A</mi><mo>¯</mo></mover></math>
(defined via de Morgan’s laws so that <math id="S1.p4.m5" class="ltx_Math" alttext="\overline{\Box A}=\Diamond\bar{A}" display="inline"><mrow><mover accent="true"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow><mo stretchy="true">¯</mo></mover><mo>=</mo><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mover accent="true"><mi>A</mi><mo>¯</mo></mover></mrow></mrow></math>
and <math id="S1.p4.m6" class="ltx_Math" alttext="\overline{\bar{A}}=A" display="inline"><mrow><mover accent="true"><mover accent="true"><mi>A</mi><mo>¯</mo></mover><mo stretchy="true">¯</mo></mover><mo>=</mo><mi>A</mi></mrow></math>), and the connectives <math id="S1.p4.m7" class="ltx_Math" alttext="\wedge,\vee,\Box,\Diamond" display="inline"><mrow><mo rspace="0em">∧</mo><mo rspace="0em">,</mo><mo lspace="0em" rspace="0em">∨</mo><mo>,</mo><mi mathvariant="normal">□</mi><mo>,</mo><mi mathvariant="normal">◇</mi></mrow></math>.
The calculus <math id="S1.p4.m8" class="ltx_Math" alttext="\mathbf{GL}_{\mathbf{Seq}}" display="inline"><msub><mi>𝐆𝐋</mi><mi>𝐒𝐞𝐪</mi></msub></math> has axioms <math id="S1.p4.m9" class="ltx_Math" alttext="\Gamma,A,\bar{A}" display="inline"><mrow><mi mathvariant="normal">Γ</mi><mo>,</mo><mi>A</mi><mo>,</mo><mover accent="true"><mi>A</mi><mo>¯</mo></mover></mrow></math> and <math id="S1.p4.m10" class="ltx_Math" alttext="\Gamma,\top" display="inline"><mrow><mi mathvariant="normal">Γ</mi><mo rspace="0em">,</mo><mo lspace="0em">⊤</mo></mrow></math>,
propositional rules <math id="S1.p4.m11" class="ltx_Math" alttext="\wedge,\vee" display="inline"><mrow><mo rspace="0em">∧</mo><mo rspace="0em">,</mo><mo lspace="0em">∨</mo></mrow></math>, and the modal rule <math id="S1.p4.m12" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math>
(recalled below).</p>
</div>
</section>
<section id="S2" class="ltx_section">
<h2 class="ltx_title ltx_font_bold ltx_title_section" style="font-size:120%;--ltx-fg-color:#0F3773;">2.  The <math id="S2.m1" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi style="--ltx-fg-color:#0F3773;" mathcolor="#0F3773" mathvariant="normal">□</mi><mi style="--ltx-fg-color:#0F3773;" mathcolor="#0F3773">𝐆𝐋</mi></msub></math> Rule and
the Obstacle to Lyndon Interpolation</h2>

<section id="S2.SS1" class="ltx_subsection">
<h3 class="ltx_title ltx_font_bold ltx_title_subsection" style="--ltx-fg-color:#0F3773;">2.1. The rule and its meaning</h3>

<div id="S2.SS1.p1" class="ltx_para">
<p class="ltx_p">The modal rule of <math id="S2.SS1.p1.m1" class="ltx_Math" alttext="\mathbf{GL}_{\mathbf{Seq}}" display="inline"><msub><mi>𝐆𝐋</mi><mi>𝐒𝐞𝐪</mi></msub></math> is:</p>
</div>
<div id="S2.SS1.p2" class="ltx_para">
<table id="S2.E1" class="ltx_equation ltx_eqn_table">

<tbody><tr class="ltx_equation ltx_eqn_row ltx_align_baseline">
<td class="ltx_eqn_cell ltx_eqn_center_padleft"></td>
<td class="ltx_eqn_cell ltx_align_center"><math id="S2.E1.m1" class="ltx_Math" alttext="\dfrac{\displaystyle\Gamma,\;\Diamond\Gamma,\;\Diamond\bar{A},\;A}{%
\displaystyle\Diamond\Gamma,\;\Box A,\;\Delta}\;[\mathrm{\Box_{\mathbf{GL}}}]" display="block"><mrow><mfrac><mrow><mi mathvariant="normal">Γ</mi><mo rspace="0.447em">,</mo><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mi mathvariant="normal">Γ</mi></mrow><mo rspace="0.447em">,</mo><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mover accent="true"><mi>A</mi><mo>¯</mo></mover></mrow><mo rspace="0.447em">,</mo><mi>A</mi></mrow><mrow><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mi mathvariant="normal">Γ</mi></mrow><mo rspace="0.447em">,</mo><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow><mo rspace="0.447em">,</mo><mi mathvariant="normal">Δ</mi></mrow></mfrac><mo lspace="0.280em">⁢</mo><mrow><mo stretchy="false">[</mo><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub><mo stretchy="false">]</mo></mrow></mrow></math></td>
<td class="ltx_eqn_cell ltx_eqn_center_padright"></td>
<td rowspan="1" class="ltx_eqn_cell ltx_eqn_eqno ltx_align_middle ltx_align_right"><span class="ltx_tag ltx_tag_equation ltx_align_right">(1)</span></td>
</tr></tbody>
</table>
</div>
<div id="S2.SS1.p3" class="ltx_para ltx_noindent">
<p class="ltx_p">From the bottom-up: to justify <math id="S2.SS1.p3.m1" class="ltx_Math" alttext="\Box A" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow></math> in the conclusion
<math id="S2.SS1.p3.m2" class="ltx_Math" alttext="\Diamond\Gamma,\Box A,\Delta" display="inline"><mrow><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mi mathvariant="normal">Γ</mi></mrow><mo>,</mo><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow><mo>,</mo><mi mathvariant="normal">Δ</mi></mrow></math>, It is needed that <math id="S2.SS1.p3.m3" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math> is proved in a context consisting of:</p>
<ul id="S2.I1" class="ltx_itemize">
<li id="S2.I1.i1" class="ltx_item" style="list-style-type:none;">
<span class="ltx_tag ltx_tag_item">•</span> 
<div id="S2.I1.i1.p1" class="ltx_para">
<p class="ltx_p"><math id="S2.I1.i1.p1.m1" class="ltx_Math" alttext="\Gamma" display="inline"><mi mathvariant="normal">Γ</mi></math> : the raw background context;</p>
</div>
</li>
<li id="S2.I1.i2" class="ltx_item" style="list-style-type:none;">
<span class="ltx_tag ltx_tag_item">•</span> 
<div id="S2.I1.i2.p1" class="ltx_para">
<p class="ltx_p"><math id="S2.I1.i2.p1.m1" class="ltx_Math" alttext="\Diamond\Gamma" display="inline"><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mi mathvariant="normal">Γ</mi></mrow></math> : the holding of transitivity,i.e, in the accessible
worlds the same background holds (since <math id="S2.I1.i2.p1.m2" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math> has the transitivity
axiom <math id="S2.I1.i2.p1.m3" class="ltx_Math" alttext="\Box A\to\Box\Box A" display="inline"><mrow><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow><mo stretchy="false">→</mo><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow></mrow></math>);</p>
</div>
</li>
<li id="S2.I1.i3" class="ltx_item" style="list-style-type:none;">
<span class="ltx_tag ltx_tag_item">•</span> 
<div id="S2.I1.i3.p1" class="ltx_para">
<p class="ltx_p"><math id="S2.I1.i3.p1.m1" class="ltx_Math" alttext="\Diamond\bar{A}" display="inline"><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mover accent="true"><mi>A</mi><mo>¯</mo></mover></mrow></math> : the <em class="ltx_emph ltx_font_italic">Löb challenge</em>: some accessible
world may falsify <math id="S2.I1.i3.p1.m2" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math>.</p>
</div>
</li>
</ul>
<p class="ltx_p">There is particular emphasis on <math id="S2.SS1.p3.m4" class="ltx_Math" alttext="\Diamond\bar{A}" display="inline"><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mover accent="true"><mi>A</mi><mo>¯</mo></mover></mrow></math> as the term encodes Löb’s theorem directly: one must prove
<math id="S2.SS1.p3.m5" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math> even in the face of a potential counterexample, preventing the
circular inference “<math id="S2.SS1.p3.m6" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math> is provable, therefore <math id="S2.SS1.p3.m7" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math>.” It is useful to notice, and keep in mind, that even when moving on to circular proofs, the structure of this logic ensures the exclusion of outright circular reasoning.</p>
</div>
</section>
<section id="S2.SS2" class="ltx_subsection">
<h3 class="ltx_title ltx_font_bold ltx_title_subsection" style="--ltx-fg-color:#0F3773;">2.2. Why this breaks Lyndon interpolation</h3>

<div id="S2.SS2.p1" class="ltx_para">
<p class="ltx_p">The <em class="ltx_emph ltx_font_italic">Lyndon interpolation property</em> for <math id="S2.SS2.p1.m1" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math> states: if
<math id="S2.SS2.p1.m2" class="ltx_Math" alttext="\mathbf{GL}\vdash A\to B" display="inline"><mrow><mi>𝐆𝐋</mi><mo>⊢</mo><mrow><mi>A</mi><mo stretchy="false">→</mo><mi>B</mi></mrow></mrow></math> then there exists <math id="S2.SS2.p1.m3" class="ltx_Math" alttext="C" display="inline"><mi>C</mi></math> with
<math id="S2.SS2.p1.m4" class="ltx_Math" alttext="w(C)\subseteq w(A)\cap w(B)" display="inline"><mrow><mrow><mi>w</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>C</mi><mo stretchy="false">)</mo></mrow></mrow><mo>⊆</mo><mrow><mrow><mi>w</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>A</mi><mo stretchy="false">)</mo></mrow></mrow><mo>∩</mo><mrow><mi>w</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>B</mi><mo stretchy="false">)</mo></mrow></mrow></mrow></mrow></math>, <math id="S2.SS2.p1.m5" class="ltx_Math" alttext="\mathbf{GL}\vdash A\to C" display="inline"><mrow><mi>𝐆𝐋</mi><mo>⊢</mo><mrow><mi>A</mi><mo stretchy="false">→</mo><mi>C</mi></mrow></mrow></math>, and <math id="S2.SS2.p1.m6" class="ltx_Math" alttext="\mathbf{GL}\vdash C\to B" display="inline"><mrow><mi>𝐆𝐋</mi><mo>⊢</mo><mrow><mi>C</mi><mo stretchy="false">→</mo><mi>B</mi></mrow></mrow></math>,
where <math id="S2.SS2.p1.m7" class="ltx_Math" alttext="w(\cdot)" display="inline"><mrow><mi>w</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mo lspace="0em" rspace="0em">⋅</mo><mo stretchy="false">)</mo></mrow></mrow></math> records both the polarity and the modal position
(inside or outside <math id="S2.SS2.p1.m8" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math>) of each literal.</p>
</div>
<div id="S2.SS2.p2" class="ltx_para">
<p class="ltx_p">The standard syntactic method for interpolation i.e, the
<em class="ltx_emph ltx_font_italic">Maehara method</em>, works by labelling every formula in a
cut-free proof as belonging to the “<math id="S2.SS2.p2.m1" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math>-side” or the “<math id="S2.SS2.p2.m2" class="ltx_Math" alttext="B" display="inline"><mi>B</mi></math>-side,” and
propagating these labels upward through each inference rule. Of course, this onely works without hassle when formulas maintain a consistent polarity role as one
works their way up the proof.</p>
</div>
<div id="S2.SS2.p3" class="ltx_para">
<p class="ltx_p">It is not hard at all then, to see that rule (<a href="#S2.E1" title="In 2.1. The rule and its meaning ‣ 2. The □_GL Rule and the Obstacle to Lyndon Interpolation ‣ A Companion to Shamkanov’s Circular Proofs for the Gödel–Löb Provability Logic Understanding how Proof System Transformations, Circularity, and Fixed-point Theorems, give Interpolation in GL" class="ltx_ref"><span class="ltx_text ltx_ref_tag">1</span></a>) breaks this. The formula <math id="S2.SS2.p3.m1" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math> appears positively
in the conclusion (inside <math id="S2.SS2.p3.m2" class="ltx_Math" alttext="\Box A" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow></math>) and in the premise (directly, as <math id="S2.SS2.p3.m3" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math>);
but <math id="S2.SS2.p3.m4" class="ltx_Math" alttext="\bar{A}" display="inline"><mover accent="true"><mi>A</mi><mo>¯</mo></mover></math> also appears in the premise (as <math id="S2.SS2.p3.m5" class="ltx_Math" alttext="\Diamond\bar{A}" display="inline"><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mover accent="true"><mi>A</mi><mo>¯</mo></mover></mrow></math>). Assigning
<math id="S2.SS2.p3.m6" class="ltx_Math" alttext="\Box A" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow></math> to one side forces <math id="S2.SS2.p3.m7" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math> and <math id="S2.SS2.p3.m8" class="ltx_Math" alttext="\bar{A}" display="inline"><mover accent="true"><mi>A</mi><mo>¯</mo></mover></math> to appear simultaneously in
the premise on both sides, destroying any coherence in polarity preservation and bookeeping.
Hence, despite <math id="S2.SS2.p3.m9" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math> being known to have the Lyndon interpolation
property semantically <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib2" title="" class="ltx_ref">2</a>]</cite>, no syntactic proof existed
before <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib1" title="" class="ltx_ref">1</a>]</cite>.</p>
</div>
<div id="S2.SS2.p4" class="ltx_para">
<span class="ltx_ERROR undefined">{keybox}</span>
<p class="ltx_p"><span class="ltx_text ltx_font_bold">TL;DR:</span> The <math id="S2.SS2.p4.m1" class="ltx_Math" alttext="\Diamond\bar{A}" display="inline"><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mover accent="true"><mi>A</mi><mo>¯</mo></mover></mrow></math> term in the premise of
<math id="S2.SS2.p4.m2" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math> is a syntactic encoding of Löb’s theorem. It makes the rule
semantically powerful but very hard to work with from a proof theoretic perspective: any formula assigned
to the left side of an interpolating split also appears on the
right negated, making a consistent polarity assignment impossible.</p>
</div>
</section>
</section>
<section id="S3" class="ltx_section">
<h2 class="ltx_title ltx_font_bold ltx_title_section" style="font-size:120%;--ltx-fg-color:#0F3773;">3.  Replacing <math id="S3.m1" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi style="--ltx-fg-color:#0F3773;" mathcolor="#0F3773" mathvariant="normal">□</mi><mi style="--ltx-fg-color:#0F3773;" mathcolor="#0F3773">𝐆𝐋</mi></msub></math> with a
Simpler Rule: The Price of Infinity</h2>

<div id="S3.p1" class="ltx_para">
<p class="ltx_p">The remedy? Replace <math id="S3.p1.m1" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math>
with the <em class="ltx_emph ltx_font_italic">K4 modal rule</em>:</p>
</div>
<div id="S3.p2" class="ltx_para">
<table id="S3.E2" class="ltx_equation ltx_eqn_table">

<tbody><tr class="ltx_equation ltx_eqn_row ltx_align_baseline">
<td class="ltx_eqn_cell ltx_eqn_center_padleft"></td>
<td class="ltx_eqn_cell ltx_align_center"><math id="S3.E2.m1" class="ltx_Math" alttext="\dfrac{\displaystyle\Gamma,\;\Diamond\Gamma,\;A}{\displaystyle\Diamond\Gamma,%
\;\Box A,\;\Delta}\;[\mathrm{\Box}]" display="block"><mrow><mfrac><mrow><mi mathvariant="normal">Γ</mi><mo rspace="0.447em">,</mo><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mi mathvariant="normal">Γ</mi></mrow><mo rspace="0.447em">,</mo><mi>A</mi></mrow><mrow><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mi mathvariant="normal">Γ</mi></mrow><mo rspace="0.447em">,</mo><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow><mo rspace="0.447em">,</mo><mi mathvariant="normal">Δ</mi></mrow></mfrac><mo lspace="0.280em">⁢</mo><mrow><mo stretchy="false">[</mo><mi mathvariant="normal">□</mi><mo stretchy="false">]</mo></mrow></mrow></math></td>
<td class="ltx_eqn_cell ltx_eqn_center_padright"></td>
<td rowspan="1" class="ltx_eqn_cell ltx_eqn_eqno ltx_align_middle ltx_align_right"><span class="ltx_tag ltx_tag_equation ltx_align_right">(2)</span></td>
</tr></tbody>
</table>
</div>
<div id="S3.p3" class="ltx_para">
<p class="ltx_p">Rule (<a href="#S3.E2" title="In 3. Replacing □_GL with a Simpler Rule: The Price of Infinity ‣ A Companion to Shamkanov’s Circular Proofs for the Gödel–Löb Provability Logic Understanding how Proof System Transformations, Circularity, and Fixed-point Theorems, give Interpolation in GL" class="ltx_ref"><span class="ltx_text ltx_ref_tag">2</span></a>) has no <math id="S3.p3.m1" class="ltx_Math" alttext="\Diamond\bar{A}" display="inline"><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mover accent="true"><mi>A</mi><mo>¯</mo></mover></mrow></math> in the premise and therefore
makes a proper polarity assignment possible: <math id="S3.p3.m2" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math> appears once, and it can be
assigned to one side of any split. This restores the
applicability of the Maehara method.</p>
</div>
<div id="S3.p4" class="ltx_para">
<p class="ltx_p">However, rule (<a href="#S3.E2" title="In 3. Replacing □_GL with a Simpler Rule: The Price of Infinity ‣ A Companion to Shamkanov’s Circular Proofs for the Gödel–Löb Provability Logic Understanding how Proof System Transformations, Circularity, and Fixed-point Theorems, give Interpolation in GL" class="ltx_ref"><span class="ltx_text ltx_ref_tag">2</span></a>) is strictly weaker than <math id="S3.p4.m1" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math>: meaning it cannot prove Löb’s axiom by itself. There is a missing piece that must come from
somewhere.</p>
</div>
<section id="S3.SS1" class="ltx_subsection">
<h3 class="ltx_title ltx_font_bold ltx_title_subsection" style="--ltx-fg-color:#0F3773;">3.1. Where the infinity comes from</h3>

<div id="S3.SS1.p1" class="ltx_para">
<p class="ltx_p">The three-way equivalence <math id="S3.SS1.p1.m1" class="ltx_Math" alttext="\mathbf{GL}_{\mathbf{Seq}}\equiv\mathbf{GL}_{\infty}\equiv\mathbf{GL}_{\mathrm%
{circ}}" display="inline"><mrow><msub><mi>𝐆𝐋</mi><mi>𝐒𝐞𝐪</mi></msub><mo>≡</mo><msub><mi>𝐆𝐋</mi><mi mathvariant="normal">∞</mi></msub><mo>≡</mo><msub><mi>𝐆𝐋</mi><mi>circ</mi></msub></mrow></math>
(Theorem 3.2 of <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib1" title="" class="ltx_ref">1</a>]</cite>) is proved in one direction by
Lemma 3.3: given a finite <math id="S3.SS1.p1.m2" class="ltx_Math" alttext="\mathbf{GL}_{\mathbf{Seq}}" display="inline"><msub><mi>𝐆𝐋</mi><mi>𝐒𝐞𝐪</mi></msub></math>-proof <math id="S3.SS1.p1.m3" class="ltx_Math" alttext="\pi" display="inline"><mi>π</mi></math>, construct a
(possibly infinite) <math id="S3.SS1.p1.m4" class="ltx_Math" alttext="\mathbf{GL}_{\infty}" display="inline"><msub><mi>𝐆𝐋</mi><mi mathvariant="normal">∞</mi></msub></math>-proof. The construction replaces each
application of <math id="S3.SS1.p1.m5" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math> with simpler rule (<a href="#S3.E2" title="In 3. Replacing □_GL with a Simpler Rule: The Price of Infinity ‣ A Companion to Shamkanov’s Circular Proofs for the Gödel–Löb Provability Logic Understanding how Proof System Transformations, Circularity, and Fixed-point Theorems, give Interpolation in GL" class="ltx_ref"><span class="ltx_text ltx_ref_tag">2</span></a>), but first
must be drop the <math id="S3.SS1.p1.m6" class="ltx_Math" alttext="\Diamond\bar{A}" display="inline"><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mover accent="true"><mi>A</mi><mo>¯</mo></mover></mrow></math> from the premise. This is taken care of by applying
the admissible <em class="ltx_emph ltx_font_italic">Löb rule</em> (Proposition 2.1 of <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib1" title="" class="ltx_ref">1</a>]</cite>):</p>
</div>
<div id="S3.SS1.p2" class="ltx_para">
<table id="S3.Ex2" class="ltx_equation ltx_eqn_table">

<tbody><tr class="ltx_equation ltx_eqn_row ltx_align_baseline">
<td class="ltx_eqn_cell ltx_eqn_center_padleft"></td>
<td class="ltx_eqn_cell ltx_align_center"><math id="S3.Ex2.m1" class="ltx_Math" alttext="\dfrac{\displaystyle\Gamma,\Diamond\Gamma,\Diamond\bar{A},A}{\displaystyle%
\Gamma,\Diamond\Gamma,A}\;[\mathrm{\mathrm{L\ddot{o}b}}]" display="block"><mrow><mfrac><mrow><mi mathvariant="normal">Γ</mi><mo>,</mo><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mi mathvariant="normal">Γ</mi></mrow><mo>,</mo><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mover accent="true"><mi>A</mi><mo>¯</mo></mover></mrow><mo>,</mo><mi>A</mi></mrow><mrow><mi mathvariant="normal">Γ</mi><mo>,</mo><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mi mathvariant="normal">Γ</mi></mrow><mo>,</mo><mi>A</mi></mrow></mfrac><mo lspace="0.280em">⁢</mo><mrow><mo stretchy="false">[</mo><mrow><mi mathvariant="normal">L</mi><mo>⁢</mo><mover accent="true"><mi mathvariant="normal">o</mi><mo>¨</mo></mover><mo>⁢</mo><mi mathvariant="normal">b</mi></mrow><mo stretchy="false">]</mo></mrow></mrow></math></td>
<td class="ltx_eqn_cell ltx_eqn_center_padright"></td>
</tr></tbody>
</table>
</div>
<div id="S3.SS1.p3" class="ltx_para">
<p class="ltx_p">The Löb rule is admissible in <math id="S3.SS1.p3.m1" class="ltx_Math" alttext="\mathbf{GL}_{\mathbf{Seq}}" display="inline"><msub><mi>𝐆𝐋</mi><mi>𝐒𝐞𝐪</mi></msub></math> (though this is not entirely trivial with the popping of infinity, hence leading to some confusion): whenever its
premise is provable, so is its conclusion. Applying it to the premise <math id="S3.SS1.p3.m2" class="ltx_Math" alttext="\tau" display="inline"><mi>τ</mi></math>
of a <math id="S3.SS1.p3.m3" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math> step produces a new proof <math id="S3.SS1.p3.m4" class="ltx_Math" alttext="f(\tau)" display="inline"><mrow><mi>f</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>τ</mi><mo stretchy="false">)</mo></mrow></mrow></math> of <math id="S3.SS1.p3.m5" class="ltx_Math" alttext="\Gamma,\Diamond\Gamma,A" display="inline"><mrow><mi mathvariant="normal">Γ</mi><mo>,</mo><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mi mathvariant="normal">Γ</mi></mrow><mo>,</mo><mi>A</mi></mrow></math>.
This transformation <math id="S3.SS1.p3.m6" class="ltx_Math" alttext="h" display="inline"><mi>h</mi></math> then applies itself recursively to <math id="S3.SS1.p3.m7" class="ltx_Math" alttext="f(\tau)" display="inline"><mrow><mi>f</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>τ</mi><mo stretchy="false">)</mo></mrow></mrow></math> as the new proof itself may contain the <math id="S3.SS1.p3.m8" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math> rule, needing a new proof from its premises to conclusion and so on.</p>
</div>
<div id="S3.SS1.p4" class="ltx_para">
<p class="ltx_p">The key observation to note here is that the
admissibility proof for the Löb rule uses <math id="S3.SS1.p4.m1" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math> applied to <math id="S3.SS1.p4.m2" class="ltx_Math" alttext="\tau" display="inline"><mi>τ</mi></math>,
embedding <math id="S3.SS1.p4.m3" class="ltx_Math" alttext="\tau" display="inline"><mi>τ</mi></math> inside a larger proof. So <math id="S3.SS1.p4.m4" class="ltx_Math" alttext="f(\tau)" display="inline"><mrow><mi>f</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>τ</mi><mo stretchy="false">)</mo></mrow></mrow></math> contains all the
<math id="S3.SS1.p4.m5" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math> rules that <math id="S3.SS1.p4.m6" class="ltx_Math" alttext="\tau" display="inline"><mi>τ</mi></math> contained, plus at least one new one.
When <math id="S3.SS1.p4.m7" class="ltx_Math" alttext="h" display="inline"><mi>h</mi></math> processes <math id="S3.SS1.p4.m8" class="ltx_Math" alttext="f(\tau)" display="inline"><mrow><mi>f</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>τ</mi><mo stretchy="false">)</mo></mrow></mrow></math>, it again meets <math id="S3.SS1.p4.m9" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math> rules, applies the
Löb rule again, producing proofs of yet greater complexity, and so on
without bound. The output is possibly an infinite tree.</p>
</div>
<div id="S3.SS1.p5" class="ltx_para">
<p class="ltx_p">Also, observe that the transformation <math id="S3.SS1.p5.m1" class="ltx_Math" alttext="h" display="inline"><mi>h</mi></math> is defined by <em class="ltx_emph ltx_font_italic">corecursion</em>: (not by
induction on some decreasing measure), but as the unique fixed point of a
contractive operator <math id="S3.SS1.p5.m2" class="ltx_Math" alttext="F" display="inline"><mi>F</mi></math> on the complete metric space <math id="S3.SS1.p5.m3" class="ltx_Math" alttext="\mathcal{C}" display="inline"><mi class="ltx_font_mathcaligraphic">𝒞</mi></math> of
all “colourings” of the infinite binary tree, and a metric defined by
<math id="S3.SS1.p5.m4" class="ltx_Math" alttext="d(u,v)=2^{-\delta(u,v)}" display="inline"><mrow><mrow><mi>d</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>u</mi><mo>,</mo><mi>v</mi><mo stretchy="false">)</mo></mrow></mrow><mo>=</mo><msup><mn>2</mn><mrow><mo>−</mo><mrow><mi>δ</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>u</mi><mo>,</mo><mi>v</mi><mo stretchy="false">)</mo></mrow></mrow></mrow></msup></mrow></math> where <math id="S3.SS1.p5.m5" class="ltx_Math" alttext="\delta(u,v)" display="inline"><mrow><mi>δ</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>u</mi><mo>,</mo><mi>v</mi><mo stretchy="false">)</mo></mrow></mrow></math> is the depth of the
shallowest node at which <math id="S3.SS1.p5.m6" class="ltx_Math" alttext="u" display="inline"><mi>u</mi></math> and <math id="S3.SS1.p5.m7" class="ltx_Math" alttext="v" display="inline"><mi>v</mi></math> differ. Since <math id="S3.SS1.p5.m8" class="ltx_Math" alttext="F(h)(c)" display="inline"><mrow><mi>F</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>h</mi><mo stretchy="false">)</mo></mrow><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>c</mi><mo stretchy="false">)</mo></mrow></mrow></math> depends on
<math id="S3.SS1.p5.m9" class="ltx_Math" alttext="h" display="inline"><mi>h</mi></math> only at immediate subtrees of <math id="S3.SS1.p5.m10" class="ltx_Math" alttext="c" display="inline"><mi>c</mi></math> (one level deeper), <math id="S3.SS1.p5.m11" class="ltx_Math" alttext="F" display="inline"><mi>F</mi></math> is a
contraction with factor <math id="S3.SS1.p5.m12" class="ltx_Math" alttext="\tfrac{1}{2}" display="inline"><mfrac><mn>1</mn><mn>2</mn></mfrac></math>, and the Banach fixed-point theorem
guarantees a unique <math id="S3.SS1.p5.m13" class="ltx_Math" alttext="h" display="inline"><mi>h</mi></math> <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib1" title="" class="ltx_ref">1</a>, Sec. 3]</cite>.</p>
</div>
<div id="S3.SS1.p6" class="ltx_para">
<span class="ltx_ERROR undefined">{graybox}</span>
<p class="ltx_p"><span class="ltx_text ltx_font_bold">TL;DR:</span> Switching from <math id="S3.SS1.p6.m1" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math> to the simpler <math id="S3.SS1.p6.m2" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math> removes the
polarity obstacle by discarding the Löb portion of the rule. Lemma 3.3
recovers that via the admissible Löb rule, at the cost of producing
a proof that may be infinite. Infinite proofs are legitimate in <math id="S3.SS1.p6.m3" class="ltx_Math" alttext="\mathbf{GL}_{\infty}" display="inline"><msub><mi>𝐆𝐋</mi><mi mathvariant="normal">∞</mi></msub></math>;
Lemma 3.6 then compresses them back into finite circular proofs via the
subformula property and a pigeonhole argument.</p>
</div>
</section>
</section>
<section id="S4" class="ltx_section">
<h2 class="ltx_title ltx_font_bold ltx_title_section" style="font-size:120%;--ltx-fg-color:#0F3773;">4.  Admissibility of the Löb Rule, Circularity, and the
Proof of <math id="S4.m1" class="ltx_Math" alttext="\mathbf{GL}_{\mathrm{circ}}\Rightarrow\mathbf{GL}_{\mathbf{Seq}}" display="inline"><mrow><msub><mi style="--ltx-fg-color:#0F3773;" mathcolor="#0F3773">𝐆𝐋</mi><mi style="--ltx-fg-color:#0F3773;" mathcolor="#0F3773">circ</mi></msub><mo style="--ltx-fg-color:#0F3773;" mathcolor="#0F3773" stretchy="false">⇒</mo><msub><mi style="--ltx-fg-color:#0F3773;" mathcolor="#0F3773">𝐆𝐋</mi><mi style="--ltx-fg-color:#0F3773;" mathcolor="#0F3773">𝐒𝐞𝐪</mi></msub></mrow></math>
</h2>

<div id="S4.p1" class="ltx_para">
<p class="ltx_p">The most interesting, but confusing part of Theorem 3.2 is Lemma 3.7: every sequent provable
in <math id="S4.p1.m1" class="ltx_Math" alttext="\mathbf{GL}_{\mathrm{circ}}" display="inline"><msub><mi>𝐆𝐋</mi><mi>circ</mi></msub></math> is provable in <math id="S4.p1.m2" class="ltx_Math" alttext="\mathbf{GL}_{\mathbf{Seq}}" display="inline"><msub><mi>𝐆𝐋</mi><mi>𝐒𝐞𝐪</mi></msub></math>. This is the direction that shows
circular proofs are sound i.e, they do not prove anything illegitimate as circular argumentation is usually associated with.</p>
</div>
<section id="S4.SS1" class="ltx_subsection">
<h3 class="ltx_title ltx_font_bold ltx_title_subsection" style="--ltx-fg-color:#0F3773;">4.1. The main claim and its induction</h3>

<div id="S4.SS1.p1" class="ltx_para">
<p class="ltx_p">Let <math id="S4.SS1.p1.m1" class="ltx_Math" alttext="\pi=(\kappa,d)" display="inline"><mrow><mi>π</mi><mo>=</mo><mrow><mo stretchy="false">(</mo><mi>κ</mi><mo>,</mo><mi>d</mi><mo stretchy="false">)</mo></mrow></mrow></math> be a circular derivation of <math id="S4.SS1.p1.m2" class="ltx_Math" alttext="\Gamma" display="inline"><mi mathvariant="normal">Γ</mi></math>.
Note: <math id="S4.SS1.p1.m3" class="ltx_Math" alttext="H(\pi)" display="inline"><mrow><mi>H</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>π</mi><mo stretchy="false">)</mo></mrow></mrow></math> denotes the non-axiom leaves of <math id="S4.SS1.p1.m4" class="ltx_Math" alttext="\kappa" display="inline"><mi>κ</mi></math> that have
no back-link and no application of <math id="S4.SS1.p1.m5" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math> on the path from the leaf to
the root, and <math id="S4.SS1.p1.m6" class="ltx_Math" alttext="BH(\pi)" display="inline"><mrow><mi>B</mi><mo>⁢</mo><mi>H</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>π</mi><mo stretchy="false">)</mo></mrow></mrow></math> denotes those with no back-link but with at
least one <math id="S4.SS1.p1.m7" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math> on that path.
<math id="S4.SS1.p1.m8" class="ltx_Math" alttext="\overline{\square}\,A=A\wedge\Box A" display="inline"><mrow><mrow><mover accent="true"><mi mathvariant="normal">□</mi><mo stretchy="true">¯</mo></mover><mo lspace="0.170em">⁢</mo><mi>A</mi></mrow><mo>=</mo><mrow><mi>A</mi><mo>∧</mo><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow></mrow></mrow></math> is the notation used.</p>
</div>
<div id="S4.SS1.p2" class="ltx_para">
<p class="ltx_p">The claim proved by induction on the structure of <math id="S4.SS1.p2.m1" class="ltx_Math" alttext="\kappa" display="inline"><mi>κ</mi></math> is:</p>
</div>
<div id="S4.SS1.p3" class="ltx_para">
<table id="S4.E3" class="ltx_equation ltx_eqn_table">

<tbody><tr class="ltx_equation ltx_eqn_row ltx_align_baseline">
<td class="ltx_eqn_cell ltx_eqn_center_padleft"></td>
<td class="ltx_eqn_cell ltx_align_center"><math id="S4.E3.m1" class="ltx_Math" alttext="\mathbf{GL}\;\vdash\;\Bigl(\bigwedge_{a\in H(\pi)}\overline{\square}\,\Delta_{%
a}^{\sharp}\Bigr)\wedge\Bigl(\bigwedge_{a\in BH(\pi)}\Box\Delta_{a}^{\sharp}%
\Bigr)\;\longrightarrow\;\Gamma^{\sharp}." display="block"><mrow><mrow><mi>𝐆𝐋</mi><mo lspace="0.558em" rspace="0.558em">⊢</mo><mrow><mrow><mrow><mo maxsize="1.600em" minsize="1.600em">(</mo><mrow><munder><mo lspace="0em" movablelimits="false">⋀</mo><mrow><mi>a</mi><mo>∈</mo><mrow><mi>H</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>π</mi><mo stretchy="false">)</mo></mrow></mrow></mrow></munder><mrow><mover accent="true"><mi mathvariant="normal">□</mi><mo stretchy="true">¯</mo></mover><mo>⁢</mo><msubsup><mi mathvariant="normal">Δ</mi><mi>a</mi><mi mathvariant="normal">♯</mi></msubsup></mrow></mrow><mo maxsize="1.600em" minsize="1.600em">)</mo></mrow><mo>∧</mo><mrow><mo maxsize="1.600em" minsize="1.600em">(</mo><mrow><munder><mo lspace="0em" movablelimits="false">⋀</mo><mrow><mi>a</mi><mo>∈</mo><mrow><mi>B</mi><mo>⁢</mo><mi>H</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>π</mi><mo stretchy="false">)</mo></mrow></mrow></mrow></munder><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><msubsup><mi mathvariant="normal">Δ</mi><mi>a</mi><mi mathvariant="normal">♯</mi></msubsup></mrow></mrow><mo maxsize="1.600em" minsize="1.600em" rspace="0.280em">)</mo></mrow></mrow><mo rspace="0.558em" stretchy="false">⟶</mo><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup></mrow></mrow><mo lspace="0em">.</mo></mrow></math></td>
<td class="ltx_eqn_cell ltx_eqn_center_padright"></td>
<td rowspan="1" class="ltx_eqn_cell ltx_eqn_eqno ltx_align_middle ltx_align_right"><span class="ltx_tag ltx_tag_equation ltx_align_right">(3)</span></td>
</tr></tbody>
</table>
</div>
<div id="S4.SS1.p4" class="ltx_para">
<p class="ltx_p">The hypothesis says that all open-assumption sequents hold, with with respect to their modal positioning, that is, a leaf in <math id="S4.SS1.p4.m1" class="ltx_Math" alttext="H" display="inline"><mi>H</mi></math> contributes both the actual
truth <math id="S4.SS1.p4.m2" class="ltx_Math" alttext="\Delta_{a}^{\sharp}" display="inline"><msubsup><mi mathvariant="normal">Δ</mi><mi>a</mi><mi mathvariant="normal">♯</mi></msubsup></math> and its provability <math id="S4.SS1.p4.m3" class="ltx_Math" alttext="\Box\Delta_{a}^{\sharp}" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><msubsup><mi mathvariant="normal">Δ</mi><mi>a</mi><mi mathvariant="normal">♯</mi></msubsup></mrow></math>; a leaf in
<math id="S4.SS1.p4.m4" class="ltx_Math" alttext="BH" display="inline"><mrow><mi>B</mi><mo>⁢</mo><mi>H</mi></mrow></math> contributes only <math id="S4.SS1.p4.m5" class="ltx_Math" alttext="\Box\Delta_{a}^{\sharp}" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><msubsup><mi mathvariant="normal">Δ</mi><mi>a</mi><mi mathvariant="normal">♯</mi></msubsup></mrow></math>, because the intervening <math id="S4.SS1.p4.m6" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math>
rule strips away the truth from the conclusion. For a complete
circular proof <math id="S4.SS1.p4.m7" class="ltx_Math" alttext="H(\pi)=BH(\pi)=\emptyset" display="inline"><mrow><mrow><mi>H</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>π</mi><mo stretchy="false">)</mo></mrow></mrow><mo>=</mo><mrow><mi>B</mi><mo>⁢</mo><mi>H</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>π</mi><mo stretchy="false">)</mo></mrow></mrow><mo>=</mo><mi mathvariant="normal">∅</mi></mrow></math>, so (<a href="#S4.E3" title="In 4.1. The main claim and its induction ‣ 4. Admissibility of the Löb Rule, Circularity, and the Proof of GL_circ⇒GL_Seq ‣ A Companion to Shamkanov’s Circular Proofs for the Gödel–Löb Provability Logic Understanding how Proof System Transformations, Circularity, and Fixed-point Theorems, give Interpolation in GL" class="ltx_ref"><span class="ltx_text ltx_ref_tag">3</span></a>) giving
<math id="S4.SS1.p4.m8" class="ltx_Math" alttext="\mathbf{GL}\vdash\Gamma^{\sharp}" display="inline"><mrow><mi>𝐆𝐋</mi><mo>⊢</mo><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup></mrow></math> directly.</p>
</div>
<div id="S4.SS1.p5" class="ltx_para">
<p class="ltx_p">The base cases and propositional rule cases are taken care of without hassle. The <math id="S4.SS1.p5.m1" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math> rule
case transfers <math id="S4.SS1.p5.m2" class="ltx_Math" alttext="H" display="inline"><mi>H</mi></math>-assumptions into <math id="S4.SS1.p5.m3" class="ltx_Math" alttext="BH" display="inline"><mrow><mi>B</mi><mo>⁢</mo><mi>H</mi></mrow></math>-assumptions (they become “boxed”
after crossing the <math id="S4.SS1.p5.m4" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math> rule) and uses the GL-valid
<math id="S4.SS1.p5.m5" class="ltx_Math" alttext="\Box(\Gamma,\Diamond\Gamma,A)^{\sharp}\to(\Diamond\Gamma,\Box A,\Sigma)^{\sharp}" display="inline"><mrow><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><msup><mrow><mo stretchy="false">(</mo><mi mathvariant="normal">Γ</mi><mo>,</mo><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mi mathvariant="normal">Γ</mi></mrow><mo>,</mo><mi>A</mi><mo stretchy="false">)</mo></mrow><mi mathvariant="normal">♯</mi></msup></mrow><mo stretchy="false">→</mo><msup><mrow><mo stretchy="false">(</mo><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mi mathvariant="normal">Γ</mi></mrow><mo>,</mo><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow><mo>,</mo><mi mathvariant="normal">Σ</mi><mo stretchy="false">)</mo></mrow><mi mathvariant="normal">♯</mi></msup></mrow></math>.</p>
</div>
</section>
<section id="S4.SS2" class="ltx_subsection">
<h3 class="ltx_title ltx_font_bold ltx_title_subsection" style="--ltx-fg-color:#0F3773;">4.2. The back-link case and the Löb rule</h3>

<div id="S4.SS2.p1" class="ltx_para">
<p class="ltx_p">The critical case in the case distinction is when some leaf <math id="S4.SS2.p1.m1" class="ltx_Math" alttext="b" display="inline"><mi>b</mi></math> is connected by a back-link to the
root, so <math id="S4.SS2.p1.m2" class="ltx_Math" alttext="\Delta_{b}=\Gamma" display="inline"><mrow><msub><mi mathvariant="normal">Δ</mi><mi>b</mi></msub><mo>=</mo><mi mathvariant="normal">Γ</mi></mrow></math>. The argument has three steps.</p>
</div>
<div id="S4.SS2.p2" class="ltx_para ltx_noindent">
<p class="ltx_p"><span class="ltx_text ltx_font_bold">Step 1.</span> Erase the back-link to obtain <math id="S4.SS2.p2.m1" class="ltx_Math" alttext="\pi_{0}" display="inline"><msub><mi>π</mi><mn>0</mn></msub></math>. Now <math id="S4.SS2.p2.m2" class="ltx_Math" alttext="b" display="inline"><mi>b</mi></math> is an open
assumption. Since the back-link must pass through a <math id="S4.SS2.p2.m3" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math> rule
(applies for all back links according to Definition 3.3 in <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib1" title="" class="ltx_ref">1</a>]</cite>), <math id="S4.SS2.p2.m4" class="ltx_Math" alttext="b\in BH(\pi_{0})" display="inline"><mrow><mi>b</mi><mo>∈</mo><mrow><mi>B</mi><mo>⁢</mo><mi>H</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><msub><mi>π</mi><mn>0</mn></msub><mo stretchy="false">)</mo></mrow></mrow></mrow></math>.</p>
</div>
<div id="S4.SS2.p3" class="ltx_para ltx_noindent">
<p class="ltx_p"><span class="ltx_text ltx_font_bold">Step 2.</span> Apply the induction hypothesis to <math id="S4.SS2.p3.m1" class="ltx_Math" alttext="\pi_{0}" display="inline"><msub><mi>π</mi><mn>0</mn></msub></math>; which has one
fewer back-link making <math id="S4.SS2.p3.m2" class="ltx_Math" alttext="BH(\pi_{0})=BH(\pi)\cup\{b\}" display="inline"><mrow><mrow><mi>B</mi><mo>⁢</mo><mi>H</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><msub><mi>π</mi><mn>0</mn></msub><mo stretchy="false">)</mo></mrow></mrow><mo>=</mo><mrow><mrow><mi>B</mi><mo>⁢</mo><mi>H</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>π</mi><mo stretchy="false">)</mo></mrow></mrow><mo>∪</mo><mrow><mo stretchy="false">{</mo><mi>b</mi><mo stretchy="false">}</mo></mrow></mrow></mrow></math> and
<math id="S4.SS2.p3.m3" class="ltx_Math" alttext="\Delta_{b}=\Gamma" display="inline"><mrow><msub><mi mathvariant="normal">Δ</mi><mi>b</mi></msub><mo>=</mo><mi mathvariant="normal">Γ</mi></mrow></math>, the conclusion is:</p>
<table id="S4.Ex3" class="ltx_equation ltx_eqn_table">

<tbody><tr class="ltx_equation ltx_eqn_row ltx_align_baseline">
<td class="ltx_eqn_cell ltx_eqn_center_padleft"></td>
<td class="ltx_eqn_cell ltx_align_center"><math id="S4.Ex3.m1" class="ltx_Math" alttext="\mathbf{GL}\;\vdash\;(\text{assumptions of }\pi)\;\wedge\;\underbrace{\Box\,%
\Gamma^{\sharp}}_{\text{from }b}\;\to\;\Gamma^{\sharp}." display="block"><mrow><mrow><mi>𝐆𝐋</mi><mo lspace="0.558em" rspace="0.558em">⊢</mo><mrow><mrow><mrow><mo stretchy="false">(</mo><mrow><mtext>assumptions of </mtext><mo>⁢</mo><mi>π</mi></mrow><mo rspace="0.280em" stretchy="false">)</mo></mrow><mo rspace="0.502em">∧</mo><munder><munder accentunder="true"><mrow><mi mathvariant="normal">□</mi><mo lspace="0.170em">⁢</mo><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup></mrow><mo stretchy="true">⏟</mo></munder><mrow><mtext>from </mtext><mo>⁢</mo><mi>b</mi></mrow></munder></mrow><mo rspace="0.558em" stretchy="false">→</mo><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup></mrow></mrow><mo lspace="0em">.</mo></mrow></math></td>
<td class="ltx_eqn_cell ltx_eqn_center_padright"></td>
</tr></tbody>
</table>
</div>
<div id="S4.SS2.p4" class="ltx_para ltx_noindent">
<p class="ltx_p"><span class="ltx_text ltx_font_bold">Step 3.</span> The formula <math id="S4.SS2.p4.m1" class="ltx_Math" alttext="\Box\,\Gamma^{\sharp}\to\Gamma^{\sharp}" display="inline"><mrow><mrow><mi mathvariant="normal">□</mi><mo lspace="0.170em">⁢</mo><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup></mrow><mo stretchy="false">→</mo><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup></mrow></math>
is exactly a Löb-hypothesis type pattern. The admissible Löb in <math id="S4.SS2.p4.m2" class="ltx_Math" alttext="\mathbf{GL}_{\mathbf{Seq}}" display="inline"><msub><mi>𝐆𝐋</mi><mi>𝐒𝐞𝐪</mi></msub></math> means
<math id="S4.SS2.p4.m3" class="ltx_Math" alttext="\Box\,\Gamma^{\sharp}" display="inline"><mrow><mi mathvariant="normal">□</mi><mo lspace="0.170em">⁢</mo><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup></mrow></math> can be dropped, yielding
<math id="S4.SS2.p4.m4" class="ltx_Math" alttext="\mathbf{GL}\vdash(\text{assumptions of }\pi)\to\Gamma^{\sharp}" display="inline"><mrow><mi>𝐆𝐋</mi><mo>⊢</mo><mrow><mrow><mo stretchy="false">(</mo><mrow><mtext>assumptions of </mtext><mo>⁢</mo><mi>π</mi></mrow><mo stretchy="false">)</mo></mrow><mo stretchy="false">→</mo><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup></mrow></mrow></math>,
which is exactly (<a href="#S4.E3" title="In 4.1. The main claim and its induction ‣ 4. Admissibility of the Löb Rule, Circularity, and the Proof of GL_circ⇒GL_Seq ‣ A Companion to Shamkanov’s Circular Proofs for the Gödel–Löb Provability Logic Understanding how Proof System Transformations, Circularity, and Fixed-point Theorems, give Interpolation in GL" class="ltx_ref"><span class="ltx_text ltx_ref_tag">3</span></a>) for <math id="S4.SS2.p4.m5" class="ltx_Math" alttext="\pi" display="inline"><mi>π</mi></math>.</p>
</div>
<div id="S4.SS2.p5" class="ltx_para">
<span class="ltx_ERROR undefined">{keybox}</span>
<p class="ltx_p"><span class="ltx_text ltx_font_bold">TL;DR: What the Löb rule is doing.</span>
The back-link says: “I will prove <math id="S4.SS2.p5.m1" class="ltx_Math" alttext="\Gamma^{\sharp}" display="inline"><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup></math> by assuming it is already
provable.” This is a circular provability assumption, which is precisely the
pattern that Löb’s theorem is designed to discharge. Löb’s axiom encodes the
well-foundedness of provability in <math id="S4.SS2.p5.m2" class="ltx_Math" alttext="\mathbf{PA}" display="inline"><mi>𝐏𝐀</mi></math>: there are no infinite relapse of the form
“provably provably provably…”. The admissible Löb rule makes this well-foundedness available at the
syntactic level. Correspondingly, <em class="ltx_emph ltx_font_italic">back-links of the form in quesiton are Löb’s theorem structural form</em>: the Löb principle is transfered from the <math id="S4.SS2.p5.m3" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math> inference
rule in <math id="S4.SS2.p5.m4" class="ltx_Math" alttext="\mathbf{GL}_{\mathbf{Seq}}" display="inline"><msub><mi>𝐆𝐋</mi><mi>𝐒𝐞𝐪</mi></msub></math> into the back-link structure of <math id="S4.SS2.p5.m5" class="ltx_Math" alttext="\mathbf{GL}_{\mathrm{circ}}" display="inline"><msub><mi>𝐆𝐋</mi><mi>circ</mi></msub></math>, and the
admissible Löb rule resolves the circulairty when going the other way around.</p>
</div>
</section>
</section>
<section id="S5" class="ltx_section">
<h2 class="ltx_title ltx_font_bold ltx_title_section" style="font-size:120%;--ltx-fg-color:#0F3773;">5.  Twofold Self-Reference in Interpolant Construction
and Its Resolution</h2>

<div id="S5.p1" class="ltx_para">
<p class="ltx_p">In Section 4 of <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib1" title="" class="ltx_ref">1</a>]</cite>, Theorem 4.1
(Lyndon interpolation) is proved. The structure of the argument follows
the same back-link pattern as Lemma 3.7, but with an additional level
of self-reference that requires a second tool to come to the rescue.</p>
</div>
<section id="S5.SS1" class="ltx_subsection">
<h3 class="ltx_title ltx_font_bold ltx_title_subsection" style="--ltx-fg-color:#0F3773;">5.1. The background: Interpolant construction from split circular proofs</h3>

<div id="S5.SS1.p1" class="ltx_para">
<p class="ltx_p">A <em class="ltx_emph ltx_font_italic">splitting</em> <math id="S5.SS1.p1.m1" class="ltx_Math" alttext="\Gamma_{1}\mid\Gamma_{2}" display="inline"><mrow><msub><mi mathvariant="normal">Γ</mi><mn>1</mn></msub><mo>∣</mo><msub><mi mathvariant="normal">Γ</mi><mn>2</mn></msub></mrow></math> of a provable sequent
<math id="S5.SS1.p1.m2" class="ltx_Math" alttext="\Gamma_{1},\Gamma_{2}" display="inline"><mrow><msub><mi mathvariant="normal">Γ</mi><mn>1</mn></msub><mo>,</mo><msub><mi mathvariant="normal">Γ</mi><mn>2</mn></msub></mrow></math> assigns each formula to a left or right side. An
<em class="ltx_emph ltx_font_italic">interpolant of <math id="S5.SS1.p1.m3" class="ltx_Math" alttext="\Gamma_{1}\mid\Gamma_{2}" display="inline"><mrow><msub><mi mathvariant="normal">Γ</mi><mn>1</mn></msub><mo>∣</mo><msub><mi mathvariant="normal">Γ</mi><mn>2</mn></msub></mrow></math></em> is a formula <math id="S5.SS1.p1.m4" class="ltx_Math" alttext="C" display="inline"><mi>C</mi></math> with
<math id="S5.SS1.p1.m5" class="ltx_Math" alttext="w(C)\subseteq w(\bar{\Gamma}_{1})\cap w(\Gamma_{2})" display="inline"><mrow><mrow><mi>w</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>C</mi><mo stretchy="false">)</mo></mrow></mrow><mo>⊆</mo><mrow><mrow><mi>w</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><msub><mover accent="true"><mi mathvariant="normal">Γ</mi><mo>¯</mo></mover><mn>1</mn></msub><mo stretchy="false">)</mo></mrow></mrow><mo>∩</mo><mrow><mi>w</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><msub><mi mathvariant="normal">Γ</mi><mn>2</mn></msub><mo stretchy="false">)</mo></mrow></mrow></mrow></mrow></math>,
<math id="S5.SS1.p1.m6" class="ltx_Math" alttext="\mathbf{GL}\vdash\bar{\Gamma}_{1}^{\sharp}\to C" display="inline"><mrow><mi>𝐆𝐋</mi><mo>⊢</mo><mrow><msubsup><mover accent="true"><mi mathvariant="normal">Γ</mi><mo>¯</mo></mover><mn>1</mn><mi mathvariant="normal">♯</mi></msubsup><mo stretchy="false">→</mo><mi>C</mi></mrow></mrow></math>, and <math id="S5.SS1.p1.m7" class="ltx_Math" alttext="\mathbf{GL}\vdash C\to\Gamma_{2}^{\sharp}" display="inline"><mrow><mi>𝐆𝐋</mi><mo>⊢</mo><mrow><mi>C</mi><mo stretchy="false">→</mo><msubsup><mi mathvariant="normal">Γ</mi><mn>2</mn><mi mathvariant="normal">♯</mi></msubsup></mrow></mrow></math>.
By Lemma 4.2 of <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib1" title="" class="ltx_ref">1</a>]</cite>, every circular proof of
<math id="S5.SS1.p1.m8" class="ltx_Math" alttext="\Gamma_{1},\Gamma_{2}" display="inline"><mrow><msub><mi mathvariant="normal">Γ</mi><mn>1</mn></msub><mo>,</mo><msub><mi mathvariant="normal">Γ</mi><mn>2</mn></msub></mrow></math> yields a <em class="ltx_emph ltx_font_italic">split circular proof</em> of
<math id="S5.SS1.p1.m9" class="ltx_Math" alttext="\Gamma_{1}\mid\Gamma_{2}" display="inline"><mrow><msub><mi mathvariant="normal">Γ</mi><mn>1</mn></msub><mo>∣</mo><msub><mi mathvariant="normal">Γ</mi><mn>2</mn></msub></mrow></math>.</p>
</div>
<div id="S5.SS1.p2" class="ltx_para">
<p class="ltx_p">The <em class="ltx_emph ltx_font_italic">split inference rules</em> (equation (1) in <cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib1" title="" class="ltx_ref">1</a>]</cite>)
tell us, for each rule of <math id="S5.SS1.p2.m1" class="ltx_Math" alttext="\mathbf{GL}_{\mathrm{circ}}" display="inline"><msub><mi>𝐆𝐋</mi><mi>circ</mi></msub></math>, how the split propagates from
conclusion to premises and what the interpolant at the conclusion is in
terms of the interpolants at the premises. For propositional rules this is
once again dealt with rather smoothly. For the modal rule there are two cases depending on
which side <math id="S5.SS1.p2.m2" class="ltx_Math" alttext="\Box A" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow></math> lands:</p>
<ul id="S5.I1" class="ltx_itemize">
<li id="S5.I1.i1" class="ltx_item" style="list-style-type:none;">
<span class="ltx_tag ltx_tag_item">•</span> 
<div id="S5.I1.i1.p1" class="ltx_para">
<p class="ltx_p"><math id="S5.I1.i1.p1.m1" class="ltx_Math" alttext="\Box A" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow></math> on the <em class="ltx_emph ltx_font_italic">left</em>: premise has <math id="S5.I1.i1.p1.m2" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math> on the left;
interpolant becomes <math id="S5.I1.i1.p1.m3" class="ltx_Math" alttext="\Diamond C" display="inline"><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mi>C</mi></mrow></math>.</p>
</div>
</li>
<li id="S5.I1.i2" class="ltx_item" style="list-style-type:none;">
<span class="ltx_tag ltx_tag_item">•</span> 
<div id="S5.I1.i2.p1" class="ltx_para">
<p class="ltx_p"><math id="S5.I1.i2.p1.m1" class="ltx_Math" alttext="\Box A" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>A</mi></mrow></math> on the <em class="ltx_emph ltx_font_italic">right</em>: premise has <math id="S5.I1.i2.p1.m2" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math> on the right;
interpolant becomes <math id="S5.I1.i2.p1.m3" class="ltx_Math" alttext="\Box C" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><mi>C</mi></mrow></math>.</p>
</div>
</li>
</ul>
<p class="ltx_p">These are exactly the cases where the K4 <math id="S5.SS1.p2.m3" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math> rule (rule
(<a href="#S3.E2" title="In 3. Replacing □_GL with a Simpler Rule: The Price of Infinity ‣ A Companion to Shamkanov’s Circular Proofs for the Gödel–Löb Provability Logic Understanding how Proof System Transformations, Circularity, and Fixed-point Theorems, give Interpolation in GL" class="ltx_ref"><span class="ltx_text ltx_ref_tag">2</span></a>)) comes in handy: since <math id="S5.SS1.p2.m4" class="ltx_Math" alttext="A" display="inline"><mi>A</mi></math> appears only once in the
premise, it can be assigned unambiguously to one side.</p>
</div>
</section>
<section id="S5.SS2" class="ltx_subsection">
<h3 class="ltx_title ltx_font_bold ltx_title_subsection" style="--ltx-fg-color:#0F3773;">5.2. The twofold circularity</h3>

<div id="S5.SS2.p1" class="ltx_para">
<p class="ltx_p">The inductive construction assigns concrete interpolants to all non-bud
nodes. The obstruction arises, rather unsurprisingly, at the back-links. Suppose leaf <math id="S5.SS2.p1.m1" class="ltx_Math" alttext="b" display="inline"><mi>b</mi></math> is connected
to the root, meaning they carry the same split sequent <math id="S5.SS2.p1.m2" class="ltx_Math" alttext="\Gamma_{1}\mid\Gamma_{2}" display="inline"><mrow><msub><mi mathvariant="normal">Γ</mi><mn>1</mn></msub><mo>∣</mo><msub><mi mathvariant="normal">Γ</mi><mn>2</mn></msub></mrow></math>.</p>
</div>
<div id="S5.SS2.p2" class="ltx_para">
<p class="ltx_p">Just like before, erase the back-link to get <math id="S5.SS2.p2.m1" class="ltx_Math" alttext="\pi_{0}" display="inline"><msub><mi>π</mi><mn>0</mn></msub></math>; now <math id="S5.SS2.p2.m2" class="ltx_Math" alttext="b" display="inline"><mi>b</mi></math> is an open assumption.
Introduce a placeholder variable <math id="S5.SS2.p2.m3" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math> for the (unknown) interpolant at <math id="S5.SS2.p2.m4" class="ltx_Math" alttext="b" display="inline"><mi>b</mi></math>.
Proceeding inductively through <math id="S5.SS2.p2.m5" class="ltx_Math" alttext="\pi_{0}" display="inline"><msub><mi>π</mi><mn>0</mn></msub></math> yields a formula <math id="S5.SS2.p2.m6" class="ltx_Math" alttext="C_{0}" display="inline"><msub><mi>C</mi><mn>0</mn></msub></math>, possibly
containing <math id="S5.SS2.p2.m7" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math>, satisfying (for suitable assumptions of <math id="S5.SS2.p2.m8" class="ltx_Math" alttext="\pi_{0}" display="inline"><msub><mi>π</mi><mn>0</mn></msub></math>):</p>
<table id="S5.E4" class="ltx_equation ltx_eqn_table">

<tbody><tr class="ltx_equation ltx_eqn_row ltx_align_baseline">
<td class="ltx_eqn_cell ltx_eqn_center_padleft"></td>
<td class="ltx_eqn_cell ltx_align_center"><math id="S5.E4.m1" class="ltx_Math" alttext="\mathbf{GL}\vdash(\text{assumptions})\wedge\Box I_{b}\;\to\;\bigl((\bar{\Gamma%
}_{1}^{\sharp}\to C_{0})\wedge(C_{0}\to\Gamma_{2}^{\sharp})\bigr)," display="block"><mrow><mrow><mi>𝐆𝐋</mi><mo>⊢</mo><mrow><mrow><mrow><mo stretchy="false">(</mo><mtext>assumptions</mtext><mo stretchy="false">)</mo></mrow><mo>∧</mo><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><msub><mi>I</mi><mi>b</mi></msub></mrow></mrow><mo rspace="0.558em" stretchy="false">→</mo><mrow><mo maxsize="1.200em" minsize="1.200em">(</mo><mrow><mrow><mo stretchy="false">(</mo><mrow><msubsup><mover accent="true"><mi mathvariant="normal">Γ</mi><mo>¯</mo></mover><mn>1</mn><mi mathvariant="normal">♯</mi></msubsup><mo stretchy="false">→</mo><msub><mi>C</mi><mn>0</mn></msub></mrow><mo stretchy="false">)</mo></mrow><mo>∧</mo><mrow><mo stretchy="false">(</mo><mrow><msub><mi>C</mi><mn>0</mn></msub><mo stretchy="false">→</mo><msubsup><mi mathvariant="normal">Γ</mi><mn>2</mn><mi mathvariant="normal">♯</mi></msubsup></mrow><mo stretchy="false">)</mo></mrow></mrow><mo maxsize="1.200em" minsize="1.200em">)</mo></mrow></mrow></mrow><mo>,</mo></mrow></math></td>
<td class="ltx_eqn_cell ltx_eqn_center_padright"></td>
<td rowspan="1" class="ltx_eqn_cell ltx_eqn_eqno ltx_align_middle ltx_align_right"><span class="ltx_tag ltx_tag_equation ltx_align_right">(4)</span></td>
</tr></tbody>
</table>
<p class="ltx_p">where <math id="S5.SS2.p2.m9" class="ltx_Math" alttext="I_{b}=(\bar{\Gamma}_{1}^{\sharp}\to X_{b})\wedge(X_{b}\to\Gamma_{2}^{\sharp})" display="inline"><mrow><msub><mi>I</mi><mi>b</mi></msub><mo>=</mo><mrow><mrow><mo stretchy="false">(</mo><mrow><msubsup><mover accent="true"><mi mathvariant="normal">Γ</mi><mo>¯</mo></mover><mn>1</mn><mi mathvariant="normal">♯</mi></msubsup><mo stretchy="false">→</mo><msub><mi>X</mi><mi>b</mi></msub></mrow><mo stretchy="false">)</mo></mrow><mo>∧</mo><mrow><mo stretchy="false">(</mo><mrow><msub><mi>X</mi><mi>b</mi></msub><mo stretchy="false">→</mo><msubsup><mi mathvariant="normal">Γ</mi><mn>2</mn><mi mathvariant="normal">♯</mi></msubsup></mrow><mo stretchy="false">)</mo></mrow></mrow></mrow></math>
is the statement that <math id="S5.SS2.p2.m10" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math> is itself an interpolant for <math id="S5.SS2.p2.m11" class="ltx_Math" alttext="\Gamma_{1}\mid\Gamma_{2}" display="inline"><mrow><msub><mi mathvariant="normal">Γ</mi><mn>1</mn></msub><mo>∣</mo><msub><mi mathvariant="normal">Γ</mi><mn>2</mn></msub></mrow></math>.</p>
</div>
<div id="S5.SS2.p3" class="ltx_para">
<p class="ltx_p">It is possible to observe that two levels of self-reference are now present:</p>
<ol id="S5.I2" class="ltx_enumerate">
<li id="S5.I2.i1" class="ltx_item" style="list-style-type:none;">
<span class="ltx_tag ltx_tag_item">(i)</span> 
<div id="S5.I2.i1.p1" class="ltx_para">
<p class="ltx_p"><span class="ltx_text ltx_font_bold">Formula level.</span> The variable <math id="S5.I2.i1.p1.m1" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math> appears in <math id="S5.I2.i1.p1.m2" class="ltx_Math" alttext="C_{0}" display="inline"><msub><mi>C</mi><mn>0</mn></msub></math>, and
<math id="S5.I2.i1.p1.m3" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math> is supposed to equal the interpolant at the root: which is
<math id="S5.I2.i1.p1.m4" class="ltx_Math" alttext="C_{0}" display="inline"><msub><mi>C</mi><mn>0</mn></msub></math> itself! (since <math id="S5.I2.i1.p1.m5" class="ltx_Math" alttext="b" display="inline"><mi>b</mi></math> and the root carry the same sequent). So
<math id="S5.I2.i1.p1.m6" class="ltx_Math" alttext="C_{0}" display="inline"><msub><mi>C</mi><mn>0</mn></msub></math> contains itself as a component.</p>
</div>
</li>
<li id="S5.I2.i2" class="ltx_item" style="list-style-type:none;">
<span class="ltx_tag ltx_tag_item">(ii)</span> 
<div id="S5.I2.i2.p1" class="ltx_para">
<p class="ltx_p"><span class="ltx_text ltx_font_bold">Provability level.</span> The hypothesis <math id="S5.I2.i2.p1.m1" class="ltx_Math" alttext="\Box I_{b}" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><msub><mi>I</mi><mi>b</mi></msub></mrow></math> in
(<a href="#S5.E4" title="In 5.2. The twofold circularity ‣ 5. Twofold Self-Reference in Interpolant Construction and Its Resolution ‣ A Companion to Shamkanov’s Circular Proofs for the Gödel–Löb Provability Logic Understanding how Proof System Transformations, Circularity, and Fixed-point Theorems, give Interpolation in GL" class="ltx_ref"><span class="ltx_text ltx_ref_tag">4</span></a>) asserting the <em class="ltx_emph ltx_font_italic">provability</em> of “<math id="S5.I2.i2.p1.m2" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math> is an
interpolant” : a circular provability assumption of the same
kind as <math id="S5.I2.i2.p1.m3" class="ltx_Math" alttext="\Box\Gamma^{\sharp}" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup></mrow></math> in Lemma 3.7.</p>
</div>
</li>
</ol>
</div>
</section>
<section id="S5.SS3" class="ltx_subsection">
<h3 class="ltx_title ltx_font_bold ltx_title_subsection" style="--ltx-fg-color:#0F3773;">5.3. Resolution by the fixed-point theorem and the Löb rule</h3>

<div id="S5.SS3.p1" class="ltx_para ltx_noindent">
<p class="ltx_p"><span class="ltx_text ltx_font_bold">Level (i): the GL fixed-point theorem.</span>
Since the back-link passes through a <math id="S5.SS3.p1.m1" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math> rule, the variable <math id="S5.SS3.p1.m2" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math>
appears in <math id="S5.SS3.p1.m3" class="ltx_Math" alttext="C_{0}" display="inline"><msub><mi>C</mi><mn>0</mn></msub></math> only inside modal operators. Upon this observation, Theorem 4.3 of
<cite class="ltx_cite ltx_citemacro_cite">[<a href="#bib.bib1" title="" class="ltx_ref">1</a>]</cite> (the GL fixed-point theorem) then comes to one’s rescue: for any
formula <math id="S5.SS3.p1.m4" class="ltx_Math" alttext="A(P)" display="inline"><mrow><mi>A</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>P</mi><mo stretchy="false">)</mo></mrow></mrow></math> in which <math id="S5.SS3.p1.m5" class="ltx_Math" alttext="P" display="inline"><mi>P</mi></math> occurs only under <math id="S5.SS3.p1.m6" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math>, there exists a
<math id="S5.SS3.p1.m7" class="ltx_Math" alttext="P" display="inline"><mi>P</mi></math>-free formula <math id="S5.SS3.p1.m8" class="ltx_Math" alttext="F" display="inline"><mi>F</mi></math> with <math id="S5.SS3.p1.m9" class="ltx_Math" alttext="w(F)\subseteq w^{*}(A)\setminus\{P^{\circ}\}" display="inline"><mrow><mrow><mi>w</mi><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>F</mi><mo stretchy="false">)</mo></mrow></mrow><mo>⊆</mo><mrow><mrow><msup><mi>w</mi><mo>∗</mo></msup><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>A</mi><mo stretchy="false">)</mo></mrow></mrow><mo>∖</mo><mrow><mo stretchy="false">{</mo><msup><mi>P</mi><mo>∘</mo></msup><mo stretchy="false">}</mo></mrow></mrow></mrow></math>
and <math id="S5.SS3.p1.m10" class="ltx_math_unparsed" alttext="\mathbf{GL}\vdash\overline{\square}\,(P\leftrightarrow A)\leftrightarrow%
\overline{\square}\,(P\leftrightarrow F)" display="inline"><mrow><mi>𝐆𝐋</mi><mo>⊢</mo><mover accent="true"><mi mathvariant="normal">□</mi><mo stretchy="true">¯</mo></mover><mrow><mo stretchy="false">(</mo><mi>P</mi><mo stretchy="false">↔</mo><mi>A</mi><mo stretchy="false">)</mo></mrow><mo stretchy="false">↔</mo><mover accent="true"><mi mathvariant="normal">□</mi><mo stretchy="true">¯</mo></mover><mrow><mo stretchy="false">(</mo><mi>P</mi><mo stretchy="false">↔</mo><mi>F</mi><mo stretchy="false">)</mo></mrow></mrow></math>.
Applying this to <math id="S5.SS3.p1.m11" class="ltx_Math" alttext="X_{b}\leftrightarrow C_{0}(X_{b})" display="inline"><mrow><msub><mi>X</mi><mi>b</mi></msub><mo stretchy="false">↔</mo><mrow><msub><mi>C</mi><mn>0</mn></msub><mo>⁢</mo><mrow><mo stretchy="false">(</mo><msub><mi>X</mi><mi>b</mi></msub><mo stretchy="false">)</mo></mrow></mrow></mrow></math> gives a concrete formula
<math id="S5.SS3.p1.m12" class="ltx_Math" alttext="F" display="inline"><mi>F</mi></math> eliminating <math id="S5.SS3.p1.m13" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math>. Obtained by setting <math id="S5.SS3.p1.m14" class="ltx_Math" alttext="C:=C_{0}[X_{b}\mapsto F]" display="inline"><mrow><mi>C</mi><mo>:=</mo><mrow><msub><mi>C</mi><mn>0</mn></msub><mo>⁢</mo><mrow><mo stretchy="false">[</mo><mrow><msub><mi>X</mi><mi>b</mi></msub><mo stretchy="false">↦</mo><mi>F</mi></mrow><mo stretchy="false">]</mo></mrow></mrow></mrow></math>.</p>
</div>
<div id="S5.SS3.p2" class="ltx_para">
<p class="ltx_p">The GL fixed-point theorem can be used to resolve this circulairty because <math id="S5.SS3.p2.m1" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math>’s Löb axiom makes any
“modalized” self-referential equation well-founded: the self-reference is always
shielded by <math id="S5.SS3.p2.m2" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math>, so it concerns provability of <math id="S5.SS3.p2.m3" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math> rather than
<math id="S5.SS3.p2.m4" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math>’s truth directly, and this well-foundedness of provability guarantees
a unique solution.</p>
</div>
<div id="S5.SS3.p3" class="ltx_para ltx_noindent">
<p class="ltx_p"><span class="ltx_text ltx_font_bold">Level (ii): the Löb rule.</span>
After substituting <math id="S5.SS3.p3.m1" class="ltx_Math" alttext="F" display="inline"><mi>F</mi></math> for <math id="S5.SS3.p3.m2" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math>, condition (<a href="#S5.E4" title="In 5.2. The twofold circularity ‣ 5. Twofold Self-Reference in Interpolant Construction and Its Resolution ‣ A Companion to Shamkanov’s Circular Proofs for the Gödel–Löb Provability Logic Understanding how Proof System Transformations, Circularity, and Fixed-point Theorems, give Interpolation in GL" class="ltx_ref"><span class="ltx_text ltx_ref_tag">4</span></a>) becomes:</p>
<table id="S5.Ex4" class="ltx_equation ltx_eqn_table">

<tbody><tr class="ltx_equation ltx_eqn_row ltx_align_baseline">
<td class="ltx_eqn_cell ltx_eqn_center_padleft"></td>
<td class="ltx_eqn_cell ltx_align_center"><math id="S5.Ex4.m1" class="ltx_Math" alttext="\mathbf{GL}\vdash(\text{assumptions of }\pi)\wedge\Box I_{b}(F)\;\to\;\bigl((%
\bar{\Gamma}_{1}^{\sharp}\to C)\wedge(C\to\Gamma_{2}^{\sharp})\bigr)." display="block"><mrow><mrow><mi>𝐆𝐋</mi><mo>⊢</mo><mrow><mrow><mrow><mo stretchy="false">(</mo><mrow><mtext>assumptions of </mtext><mo>⁢</mo><mi>π</mi></mrow><mo stretchy="false">)</mo></mrow><mo>∧</mo><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><msub><mi>I</mi><mi>b</mi></msub><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>F</mi><mo rspace="0.280em" stretchy="false">)</mo></mrow></mrow></mrow><mo rspace="0.558em" stretchy="false">→</mo><mrow><mo maxsize="1.200em" minsize="1.200em">(</mo><mrow><mrow><mo stretchy="false">(</mo><mrow><msubsup><mover accent="true"><mi mathvariant="normal">Γ</mi><mo>¯</mo></mover><mn>1</mn><mi mathvariant="normal">♯</mi></msubsup><mo stretchy="false">→</mo><mi>C</mi></mrow><mo stretchy="false">)</mo></mrow><mo>∧</mo><mrow><mo stretchy="false">(</mo><mrow><mi>C</mi><mo stretchy="false">→</mo><msubsup><mi mathvariant="normal">Γ</mi><mn>2</mn><mi mathvariant="normal">♯</mi></msubsup></mrow><mo stretchy="false">)</mo></mrow></mrow><mo maxsize="1.200em" minsize="1.200em">)</mo></mrow></mrow></mrow><mo lspace="0em">.</mo></mrow></math></td>
<td class="ltx_eqn_cell ltx_eqn_center_padright"></td>
</tr></tbody>
</table>
<p class="ltx_p">Now <math id="S5.SS3.p3.m3" class="ltx_Math" alttext="I_{b}(F)" display="inline"><mrow><msub><mi>I</mi><mi>b</mi></msub><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>F</mi><mo stretchy="false">)</mo></mrow></mrow></math> is exactly the statement that <math id="S5.SS3.p3.m4" class="ltx_Math" alttext="C" display="inline"><mi>C</mi></math> is an interpolant for the
root split sequent. So the hypothesis <math id="S5.SS3.p3.m5" class="ltx_Math" alttext="\Box I_{b}(F)" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><msub><mi>I</mi><mi>b</mi></msub><mo>⁢</mo><mrow><mo stretchy="false">(</mo><mi>F</mi><mo stretchy="false">)</mo></mrow></mrow></math> asserts the provability
of the very conclusion we are trying to establish, a Löb-pattern
circular provability assumption. The admissible Löb rule drops it, giving:</p>
<table id="S5.Ex5" class="ltx_equation ltx_eqn_table">

<tbody><tr class="ltx_equation ltx_eqn_row ltx_align_baseline">
<td class="ltx_eqn_cell ltx_eqn_center_padleft"></td>
<td class="ltx_eqn_cell ltx_align_center"><math id="S5.Ex5.m1" class="ltx_Math" alttext="\mathbf{GL}\vdash(\text{assumptions of }\pi)\;\to\;\bigl((\bar{\Gamma}_{1}^{%
\sharp}\to C)\wedge(C\to\Gamma_{2}^{\sharp})\bigr)." display="block"><mrow><mrow><mi>𝐆𝐋</mi><mo>⊢</mo><mrow><mrow><mo stretchy="false">(</mo><mrow><mtext>assumptions of </mtext><mo>⁢</mo><mi>π</mi></mrow><mo rspace="0.280em" stretchy="false">)</mo></mrow><mo rspace="0.558em" stretchy="false">→</mo><mrow><mo maxsize="1.200em" minsize="1.200em">(</mo><mrow><mrow><mo stretchy="false">(</mo><mrow><msubsup><mover accent="true"><mi mathvariant="normal">Γ</mi><mo>¯</mo></mover><mn>1</mn><mi mathvariant="normal">♯</mi></msubsup><mo stretchy="false">→</mo><mi>C</mi></mrow><mo stretchy="false">)</mo></mrow><mo>∧</mo><mrow><mo stretchy="false">(</mo><mrow><mi>C</mi><mo stretchy="false">→</mo><msubsup><mi mathvariant="normal">Γ</mi><mn>2</mn><mi mathvariant="normal">♯</mi></msubsup></mrow><mo stretchy="false">)</mo></mrow></mrow><mo maxsize="1.200em" minsize="1.200em">)</mo></mrow></mrow></mrow><mo lspace="0em">.</mo></mrow></math></td>
<td class="ltx_eqn_cell ltx_eqn_center_padright"></td>
</tr></tbody>
</table>
<p class="ltx_p">For a complete split circular proof (withno open assumptions), <math id="S5.SS3.p3.m6" class="ltx_Math" alttext="C" display="inline"><mi>C</mi></math> is the
desired Lyndon interpolant.</p>
</div>
<div id="S5.SS3.p4" class="ltx_para">
<span class="ltx_ERROR undefined">{keybox}</span>
<p class="ltx_p"><span class="ltx_text ltx_font_bold">TL;DR: Why two tools are needed.</span>
In Lemma 3.7 only the Löb rule was needed because the induction tracked
the sequent <math id="S5.SS3.p4.m1" class="ltx_Math" alttext="\Gamma^{\sharp}" display="inline"><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup></math> directly: the back-link created one level of
self-reference (the circular provability assumption <math id="S5.SS3.p4.m2" class="ltx_Math" alttext="\Box\Gamma^{\sharp}" display="inline"><mrow><mi mathvariant="normal">□</mi><mo>⁢</mo><msup><mi mathvariant="normal">Γ</mi><mi mathvariant="normal">♯</mi></msup></mrow></math>),
which the Löb rule dissolved. In Theorem 4.1 the induction tracks a
<em class="ltx_emph ltx_font_italic">formula to be constructed</em>, i.e, the interpolant. The back-link
creates a self-referential formula placeholder <math id="S5.SS3.p4.m3" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math> in addition to a
circular provability assumption. The placeholder must be eliminated first,
by the fixed-point theorem, which is applicable because the placeholder <math id="S5.SS3.p4.m4" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math> only appears inside the modal operator in <math id="S5.SS3.p4.m5" class="ltx_Math" alttext="C_{0}" display="inline"><msub><mi>C</mi><mn>0</mn></msub></math>, allowing for its elimination, there-by resolving the first self reference. Then the usual argumentation from before applies.</p>
</div>
</section>
</section>
<section id="Sx1" class="ltx_section">
<h2 class="ltx_title ltx_font_bold ltx_title_section" style="font-size:120%;--ltx-fg-color:#0F3773;">Concluding Remarks: From GL to the Modal <math id="Sx1.m1" class="ltx_Math" alttext="\mu" display="inline"><mi style="--ltx-fg-color:#0F3773;" mathcolor="#0F3773">μ</mi></math>-Calculus</h2>

<div id="Sx1.p1" class="ltx_para">
<p class="ltx_p">The four difficulties addressed in this companion are not independent, nor are they merely to be understood as quirks.
They form the core of the proof and point us toward a possible generalization: the <math id="Sx1.p1.m1" class="ltx_Math" alttext="\Diamond\bar{A}" display="inline"><mrow><mi mathvariant="normal">◇</mi><mo>⁢</mo><mover accent="true"><mi>A</mi><mo>¯</mo></mover></mrow></math> in <math id="Sx1.p1.m2" class="ltx_Math" alttext="\Box_{\mathbf{GL}}" display="inline"><msub><mi mathvariant="normal">□</mi><mi>𝐆𝐋</mi></msub></math> encodes Löb’s theorem
inside an inference rule; removing it forces infinite proofs; those
infinite proofs compress into circular proofs because of the subformula
property; circular proofs are sound precisely because back-links generate
Löb-pattern hypotheses that the admissible Löb rule can discharge; and
the same discharge, lifted one level to the interpolant formula rather
than the sequent, requires the additional mediation of the GL
fixed-point theorem. Shamkanov’s paper, in some sense, almost hints that the self-referential content of <math id="Sx1.p1.m3" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math> is best handled
by proof-theoretic tools that are themselves self-referential.</p>
</div>
<div id="Sx1.p2" class="ltx_para">
<p class="ltx_p">What makes these observations quite interesting is the fact that each feature
of Shamkanov’s argument can be understood as what is possibly an instance of a general set of conditions for such proofs and tools, a notion that enables the generalisation carried
out by Afshari and Leigh <cite class="ltx_cite ltx_citemacro_cite">[<span class="ltx_ref ltx_missing_citation ltx_ref_self">afshari2022</span>, <span class="ltx_ref ltx_missing_citation ltx_ref_self">afshari2021</span>]</cite>.</p>
</div>
<section id="Sx1.SS3.SSS0.Px1" class="ltx_paragraph">
<h4 class="ltx_title ltx_title_paragraph">Well-foundedness becomes the global trace condition.</h4>

<div id="Sx1.SS3.SSS0.Px1.p1" class="ltx_para">
<p class="ltx_p">In <math id="Sx1.SS3.SSS0.Px1.p1.m1" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math>, the requirement that every back-link pass through a <math id="Sx1.SS3.SSS0.Px1.p1.m2" class="ltx_Math" alttext="\Box" display="inline"><mi mathvariant="normal">□</mi></math> rule
is a local, checkable condition, justified by the well-foundedness
of provability in <math id="Sx1.SS3.SSS0.Px1.p1.m3" class="ltx_Math" alttext="\mathbf{PA}" display="inline"><mi>𝐏𝐀</mi></math>. In the <math id="Sx1.SS3.SSS0.Px1.p1.m4" class="ltx_Math" alttext="\mu" display="inline"><mi>μ</mi></math>-calculus, where one reasons about
arbitrary inductive and coinductive definitions, this localises into a
global condition on infinite paths: a cyclic proof is sound when every
infinite path carries a <em class="ltx_emph ltx_font_italic">good trace</em>, meaning the formula thread
along that path eventually stabilises on a <math id="Sx1.SS3.SSS0.Px1.p1.m5" class="ltx_Math" alttext="\mu" display="inline"><mi>μ</mi></math>-formula (for a left
trace) or a <math id="Sx1.SS3.SSS0.Px1.p1.m6" class="ltx_Math" alttext="\nu" display="inline"><mi>ν</mi></math>-formula (for a right trace). The admissible Löb rule,
which discharges circular provability assumptions one back-link at a time,
is replaced by the <em class="ltx_emph ltx_font_italic">Normal Form Theorem</em>, which rearranges any cyclic proof so that a global
marking <math id="Sx1.SS3.SSS0.Px1.p1.m7" class="ltx_Math" alttext="\sigma" display="inline"><mi>σ</mi></math> assigns <math id="Sx1.SS3.SSS0.Px1.p1.m8" class="ltx_Math" alttext="\mu" display="inline"><mi>μ</mi></math> or <math id="Sx1.SS3.SSS0.Px1.p1.m9" class="ltx_Math" alttext="\nu" display="inline"><mi>ν</mi></math> to each companion consistently
with the trace condition. This reinforces the notion that some well-foundedness condition may always be necessary when dealing with circular proof systems for a logic.</p>
</div>
</section>
<section id="Sx1.SS3.SSS0.Px2" class="ltx_paragraph">
<h4 class="ltx_title ltx_title_paragraph">The fixed-point theorem becomes an internal quantifier.</h4>

<div id="Sx1.SS3.SSS0.Px2.p1" class="ltx_para">
<p class="ltx_p">In Shamkanov’s proof, the self-referential placeholder <math id="Sx1.SS3.SSS0.Px2.p1.m1" class="ltx_Math" alttext="X_{b}" display="inline"><msub><mi>X</mi><mi>b</mi></msub></math> in the
interpolant formula is eliminated by invoking the GL fixed-point theorem
as a tool: the modalized equation <math id="Sx1.SS3.SSS0.Px2.p1.m2" class="ltx_Math" alttext="X_{b}\leftrightarrow C_{0}(X_{b})" display="inline"><mrow><msub><mi>X</mi><mi>b</mi></msub><mo stretchy="false">↔</mo><mrow><msub><mi>C</mi><mn>0</mn></msub><mo>⁢</mo><mrow><mo stretchy="false">(</mo><msub><mi>X</mi><mi>b</mi></msub><mo stretchy="false">)</mo></mrow></mrow></mrow></math>
has a canonical solution <math id="Sx1.SS3.SSS0.Px2.p1.m3" class="ltx_Math" alttext="F" display="inline"><mi>F</mi></math>, owing to Löb’s axiom, and one sets
<math id="Sx1.SS3.SSS0.Px2.p1.m4" class="ltx_Math" alttext="C:=C_{0}[X_{b}\mapsto F]" display="inline"><mrow><mi>C</mi><mo>:=</mo><mrow><msub><mi>C</mi><mn>0</mn></msub><mo>⁢</mo><mrow><mo stretchy="false">[</mo><mrow><msub><mi>X</mi><mi>b</mi></msub><mo stretchy="false">↦</mo><mi>F</mi></mrow><mo stretchy="false">]</mo></mrow></mrow></mrow></math>. In the <math id="Sx1.SS3.SSS0.Px2.p1.m5" class="ltx_Math" alttext="\mu" display="inline"><mi>μ</mi></math>-calculus, this step disappears as a
separate argument because the language already contains fixed-point
quantifiers: the interpolant at a companion is simply <math id="Sx1.SS3.SSS0.Px2.p1.m6" class="ltx_Math" alttext="\mu x_{b}\,C_{0}(x_{b})" display="inline"><mrow><mi>μ</mi><mo>⁢</mo><msub><mi>x</mi><mi>b</mi></msub><mo>⁢</mo><msub><mi>C</mi><mn>0</mn></msub><mo>⁢</mo><mrow><mo stretchy="false">(</mo><msub><mi>x</mi><mi>b</mi></msub><mo stretchy="false">)</mo></mrow></mrow></math>
or <math id="Sx1.SS3.SSS0.Px2.p1.m7" class="ltx_Math" alttext="\nu x_{b}\,C_{0}(x_{b})" display="inline"><mrow><mi>ν</mi><mo>⁢</mo><msub><mi>x</mi><mi>b</mi></msub><mo>⁢</mo><msub><mi>C</mi><mn>0</mn></msub><mo>⁢</mo><mrow><mo stretchy="false">(</mo><msub><mi>x</mi><mi>b</mi></msub><mo stretchy="false">)</mo></mrow></mrow></math>, with the choice of quantifier given by the
marking <math id="Sx1.SS3.SSS0.Px2.p1.m8" class="ltx_Math" alttext="\sigma" display="inline"><mi>σ</mi></math>. This emphasises the necessity of some fix-point properties in logics where one seeks to generalize the method.</p>
</div>
<div id="Sx1.SS3.SSS0.Px2.p2" class="ltx_para">
<p class="ltx_p">Similar points can be made for the existence of other notions like obtaining of <em class="ltx_emph ltx_font_italic">Subformula Property</em>, and so on</p>
</div>
</section>
<section id="Sx1.SS3.SSS0.Px3" class="ltx_paragraph">
<h4 class="ltx_title ltx_title_paragraph">A final TL;DR:</h4>

<div id="Sx1.SS3.SSS0.Px3.p1" class="ltx_para">
<p class="ltx_p">The apparent peculiarities of <math id="Sx1.SS3.SSS0.Px3.p1.m1" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math> :
the Löb axiom, the fixed-point theorem, the well-foundedness condition
, seem less to be some special quriks of provability logic that happen to make
the proof work and more like they are instances of the general structure of any
logic where such a method can be applied: a soundness
condition on cyclic proofs, a fixed-point mechanism for resolving
self-referential interpolants, and a combinatorial bound on formula
complexity, etc. Hence, understanding why each step in that proof is
necessary, the questions this companion has tried to address, helps one draw further conclusions and ideas for a more
general programme of applicability. The hope is, this work, would have served as a useful companion along the journey through the work that started it all.</p>
</div>
</section>
</section>
<section id="bib" class="ltx_bibliography">
<h2 class="ltx_title ltx_title_bibliography">References</h2>

<ul class="ltx_biblist">
<li id="bib.bib1" class="ltx_bibitem">
<span class="ltx_tag ltx_tag_bibitem">[1]</span>
<span class="ltx_bibblock">
D. S. Shamkanov,
“Circular proofs for the Gödel–Löb provability logic,”
<span class="ltx_text ltx_font_italic">Mathematical Notes</span> <span class="ltx_text ltx_font_bold">96</span>(4), 575–585, 2014.

</span>
</li>
<li id="bib.bib2" class="ltx_bibitem">
<span class="ltx_tag ltx_tag_bibitem">[2]</span>
<span class="ltx_bibblock">
D. S. Shamkanov,
“Interpolation properties for provability logics <math id="bib.bib2.m1" class="ltx_Math" alttext="\mathbf{GL}" display="inline"><mi>𝐆𝐋</mi></math> and <span class="ltx_text ltx_font_bold">GLP</span>,”
<span class="ltx_text ltx_font_italic">Proc. Steklov Inst. Math.</span> <span class="ltx_text ltx_font_bold">274</span>, 303–316, 2011.

</span>
</li>
<li id="bib.bib3" class="ltx_bibitem">
<span class="ltx_tag ltx_tag_bibitem">[3]</span>
<span class="ltx_bibblock">
M. H. Löb,
“Solution of a problem of Leon Henkin,”
<span class="ltx_text ltx_font_italic">J. Symbolic Logic</span> <span class="ltx_text ltx_font_bold">20</span>(2), 115–118, 1955.

</span>
</li>
<li id="bib.bib4" class="ltx_bibitem">
<span class="ltx_tag ltx_tag_bibitem">[4]</span>
<span class="ltx_bibblock">
R. M. Solovay,
“Provability interpretations of modal logic,”
<span class="ltx_text ltx_font_italic">Israel J. Math.</span> <span class="ltx_text ltx_font_bold">25</span>, 287–304, 1976.

</span>
</li>
<li id="bib.bib5" class="ltx_bibitem">
<span class="ltx_tag ltx_tag_bibitem">[5]</span>
<span class="ltx_bibblock">
K. Segerberg,
<span class="ltx_text ltx_font_italic">An Essay in Classical Modal Logic</span>,
Uppsala University, 1971.

</span>
</li>
<li id="bib.bib6" class="ltx_bibitem">
<span class="ltx_tag ltx_tag_bibitem">[6]</span>
<span class="ltx_bibblock">
S. Valentini,
“The modal logic of provability: cut-elimination,”
<span class="ltx_text ltx_font_italic">J. Philos. Logic</span> <span class="ltx_text ltx_font_bold">12</span>(4), 471–476, 1983.

</span>
</li>
<li id="bib.bib7" class="ltx_bibitem">
<span class="ltx_tag ltx_tag_bibitem">[7]</span>
<span class="ltx_bibblock">
R. Goré and R. Ramanayake,
“Valentini’s cut-elimination for provability logic resolved,”
<span class="ltx_text ltx_font_italic">Rev. Symb. Log.</span> <span class="ltx_text ltx_font_bold">5</span>(2), 212–238, 2012.

</span>
</li>
<li id="bib.bib8" class="ltx_bibitem">
<span class="ltx_tag ltx_tag_bibitem">[8]</span>
<span class="ltx_bibblock">
J. Brotherston,
<span class="ltx_text ltx_font_italic">Sequent Calculus Proof Systems for Inductive Definitions</span>,
PhD Thesis, University of Edinburgh, 2006.

</span>
</li>
</ul>
</section><div class="ltx_rdf" about="" property="dcterms:title" content="A Companion to Shamkanov’s Circular Proofs for GL"></div>

</article>
</div>
<footer class="ltx_page_footer">
<div class="ltx_page_logo">Generated  on Fri Apr 10 18:38:38 2026 by <a href="http://dlmf.nist.gov/LaTeXML/" class="ltx_LaTeXML_logo"><span style="letter-spacing:-0.2em; margin-right:0.1em;">L<span class="ltx_font_smallcaps" style="position:relative; bottom:2.2pt;">a</span>T<span class="ltx_font_smallcaps" style="font-size:120%;position:relative; bottom:-0.2ex;">e</span></span><span style="font-size:90%; position:relative; bottom:-0.2ex;">XML</span><img src="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAsAAAAOCAYAAAD5YeaVAAAAAXNSR0IArs4c6QAAAAZiS0dEAP8A/wD/oL2nkwAAAAlwSFlzAAALEwAACxMBAJqcGAAAAAd0SU1FB9wKExQZLWTEaOUAAAAddEVYdENvbW1lbnQAQ3JlYXRlZCB3aXRoIFRoZSBHSU1Q72QlbgAAAdpJREFUKM9tkL+L2nAARz9fPZNCKFapUn8kyI0e4iRHSR1Kb8ng0lJw6FYHFwv2LwhOpcWxTjeUunYqOmqd6hEoRDhtDWdA8ApRYsSUCDHNt5ul13vz4w0vWCgUnnEc975arX6ORqN3VqtVZbfbTQC4uEHANM3jSqXymFI6yWazP2KxWAXAL9zCUa1Wy2tXVxheKA9YNoR8Pt+aTqe4FVVVvz05O6MBhqUIBGk8Hn8HAOVy+T+XLJfLS4ZhTiRJgqIoVBRFIoric47jPnmeB1mW/9rr9ZpSSn3Lsmir1fJZlqWlUonKsvwWwD8ymc/nXwVBeLjf7xEKhdBut9Hr9WgmkyGEkJwsy5eHG5vN5g0AKIoCAEgkEkin0wQAfN9/cXPdheu6P33fBwB4ngcAcByHJpPJl+fn54mD3Gg0NrquXxeLRQAAwzAYj8cwTZPwPH9/sVg8PXweDAauqqr2cDjEer1GJBLBZDJBs9mE4zjwfZ85lAGg2+06hmGgXq+j3+/DsixYlgVN03a9Xu8jgCNCyIegIAgx13Vfd7vdu+FweG8YRkjXdWy329+dTgeSJD3ieZ7RNO0VAXAPwDEAO5VKndi2fWrb9jWl9Esul6PZbDY9Go1OZ7PZ9z/lyuD3OozU2wAAAABJRU5ErkJggg==" alt="Mascot Sammy"></a>
</div></footer>
</div>
</body>
</html>
