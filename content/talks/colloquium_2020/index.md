---
title: A new interpolation algorithm for the theory of Equality with Uninterpreted Functions

event: Computer Science Colloquium Series, University of New Mexico
event_url: https://www.cs.unm.edu/about/colloquium.html

location: Online
#address:
#  street: 450 Serra Mall
#  city: Stanford
#  region: CA
#  postcode: '94305'
#  country: United States

summary: Computer Science Colloquium Series, University of New Mexico

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: '2020-09-09T14:00:00Z'
date_end: '2020-09-09T14:50:00Z'
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: '2020-09-09T00:00:00Z'

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
url_slides: 'presentations/unm_colloquium_talk_2020.html'
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

An interpolant for a pair (A, B) of inconsistent formulas 
is a formula C such that: A implies C; B is inconsistent 
with C; and C  only contains common symbols between A and B. 
Modern techniques for interpolant generation rely on special 
deductive calculus and unsatisfiability proofs.  In this talk, 
we will discuss a new algorithm to compute the interpolation 
formula for the theory of Equality with Uninterpreted Functions 
(EUF) that does not require unsatisfiability proofs.  We will 
discuss an observation made during the implementation of the 
algorithm, introducing a new Horn-unsatisfiability algorithm 
that uses a congruence closure with explanations as the mechanism 
for equality propagation.
