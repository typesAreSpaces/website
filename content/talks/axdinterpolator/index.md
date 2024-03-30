---
title: AXDInterpolator A Tool for Computing Interpolants for Arrays with MaxDiff

event: 19th International Workshop on Satisfiability Modulo Theories
event_url: https://smt-workshop.cs.uiowa.edu/2021/index.shtml

location: Online
#address:
#  street: 450 Serra Mall
#  city: Stanford
#  region: CA
#  postcode: '94305'
#  country: United States

summary: 19th International Workshop on Satisfiability Modulo Theories

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: '2021-07-18T13:00:00Z'
#date_end: '2021-07-19T15:00:00Z'
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: '2021-07-18T00:00:00Z'

authors: [Jose Abel Castellanos Joo, Silvio Ghilardi, Alessandro Gianola and Deepak Kapur ]
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
url_slides: 'presentations/smt21-paper15-full-presentation.pdf'
url_video: 'https://www.youtube.com/watch?v=Hq7IJZXZQbw'

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

Several approaches toward 
quantifier-free interpolation algorithms 
of theories involving arrays
have been proposed by extending the
language using a binary function skolemizing
the extensionality principle. 

In FoSSaCS 2021, 
the last three authors studied the enrichment of the
McCarthy's theory of extensional arrays 
with a maxdiff operation. 

This paper discusses the implementation of the  
interpolation algorithm  proposed in FoSSaCS 2021 
using the Z3 API. 
The implementation allows the user to choose
Z3, Mathsat, or SMTInterpol as interpolation
engines.

The tool returns a formula in SMTLIB2
format, which allows compatibility with
model checkers and
invariant generators using such a format.
We compare our algorithm with state-of-the-art 
interpolation engines.
Some examples reveal that our tool can handle some formulas
in our theory that other solvers cannot. Our 
experiments using unsatisfiable formulas extracted 
with the model checker UAutomizer 
show the feasibility of our tool. For that purpose,
we used C programs from the 
ReachSafety-Arrays and MemSafety-Arrays
tracks of the SV-COMP.
