---
title: Implementation of Uniform Interpolation Algorithms

event: Master Thesis Defense, University of New Mexico
event_url: 

location: Online
#address:
#  street: 450 Serra Mall
#  city: Stanford
#  region: CA
#  postcode: '94305'
#  country: United States

summary: Master Thesis Defense, University of New Mexico

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: '2020-10-20T13:00:00Z'
#date_end: '2021-07-19T15:00:00Z'
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: '2020-10-20T00:00:00Z'

authors: [Jose Abel Castellanos Joo]
tags: [formal methods, interpolation, verification]

# Is this a featured talk? (true/false)
featured: false

#image:
#  caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/bzdhc5b3Bxs)'
#  focal_point: Right

#links:
#  - icon: twitter
#    icon_pack: fab
#    name: Follow
#    url: https://twitter.com/georgecushen
url_code: ''
url_pdf: ''
url_slides: 'presentations/master_thesis_defense_2020.pdf'
url_video: ''

# Markdown Slides (optional).
#   Associate this talk with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides:

# Projects (optional).
#   Associate this post with one or more of your projects.
#   Simply enter your project's folder or file name without extension.
#   E.g. `projects = ["internal-project"]` references `content/project/deep-learning/index.md`.
#   Otherwise, set `projects = []`.
projects:
---

# Abstract

This thesis discusses algorithms for the uniform interpolation 
problem and presents their implementation for the following theories: 
(quantifier-free) equality with uninterpreted
functions (EUF), unit two variable per 
inequality (UTVPI), and theoretic aspects for the 
combination of the two previous theories. 
The uniform interpolation algorithms implemented in this thesis were 
originally proposed in \cite{KAPUR2017}.

Refutational proof-based solutions are the usual approach 
of many interpolation algorithms 
\cite{10.1007/978-3-642-00768-2_34, mcmillan2011interpolants, 10.1007/978-3-540-24730-2_2}. 
The approach taken in \cite{KAPUR2017} relies on quantifier-elimination heuristics 
to construct a uniform interpolant using one of the two formulas involved 
in the interpolation problem. The latter makes it 
possible to study the complexity 
of the algorithms obtained compared to refutational-based
solution which rely on the efficiency of 
SMT solvers.

It is not always possible to find a
uniform interpolant for every formula in 
the combined theory of EUF and UTVPI 
\cite{10.1007/978-3-030-51074-9_11}.
Hence, the thesis work implements an
algorithm for a subset of formulas in 
the combined theory which
the existence of uniform interpolants
is guaranteed.
Additionally, the thesis work implements
a Nelson-Oppen interpolation framework 
\cite{10.1007/11532231_26}
to combine the uniform 
interpolating
algorithms in previous sections.

The implementation uses Z3 
\cite{10.1007/978-3-540-78800-3_24} 
for parsing purposes and 
satisfiability checking in 
the combination component of the 
thesis. Minor modifications were applied 
to Z3's enode data structure 
in order to label and distinguish formulas 
efficiently (i.e. distinguish 
A-part, B-part). The project can easily be 
integrated into the Z3 solver 
to extend its functionality for 
verification purposes using the Z3 
plug-in module. 

The major results of the project are the 
following:

- Implementation of Kapur's uniform interpolating
algorithm for theories EUF and UTVPI.
- Modification and implementation 
of the Phase III in Kapur's
uniform interpolation algorithm for EUF. As
a byproduct, an application in 
membership testing in conjunction of Horn 
clauses is obtained.
- Experimental evidence
of uniform interpolants is provided as
well as performance results of the 
implemented systems.
- An partially sound uniform interpolation 
algorithm for the combined theory of EUF and UTVPI
is proposed and proven correct for a suitable 
fragment of the aforementioned combined theory.
