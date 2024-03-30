---
title: Computing certicates in compact quadratic modules in $\mathbb{R}[x]$

event: Thesis Proposal Defense
event_url: 

location: Online
#address:
#  street: 450 Serra Mall
#  city: Stanford
#  region: CA
#  postcode: '94305'
#  country: United States

summary: Thesis Proposal Defense

# Talk start and end times.
#   End time can optionally be hidden by prefixing the line with `#`.
date: '2023-09-13T13:00:00Z'
#date_end: '2021-07-19T15:00:00Z'
all_day: false

# Schedule page publish date (NOT talk date).
publishDate: '2023-09-13T00:00:00Z'

authors: [Jose Abel Castellanos Joo]
tags: [computational real algebraic geometry, verification]

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
url_slides: 'presentations/thesis-proposal-defense-v4.pdf'
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

This thesis will study algorithms to compute certificates for members in compact
quadratic modules in univariate polynomial rings and certificates for the
Archimedean polynomial in the bivariate case. Our current results compute exact
certificates (sums of squares multipliers) that certify the membership of a
polynomial in a compact monogenic quadratic module. Our method is constructive
and symbolic, thus exact. We provide bounds for the degree representation of our
sums of squares certificates. Additionally, we compare our method with existing
solutions involving numerical approaches. We plan to extend our methods to the
general case of compact quadratic modules by finding reductions of a general
compact quadratic module basis to a single generator that is included in the
original quadratic module in consideration.

Real algebraic geometry has recently received a lot of attention in the formal
methods community working with reasoning problems involving polynomial
equalities and inequalities. These constraints appear naturally in areas such as
software verification
\cite{10.1007/978-3-030-29436-6_11,10.1007/978-3-319-68167-2_26}, hybrid systems
\cite{WANG2022104965, 10.1007/978-3-540-24743-2_32}, and machine learning
\cite{NEURIPS2020_dea9ddb2,NEURIPS2021_e3b21256}. A fundamental aspect in
verification is the ability to provide useful information to users to validate
results, hence the need to provide checkable information in these algorithms.  A
characterization of the generator of compact monogenic quadratic modules in
$\mathbb{R}[X]$ was introduced in \cite{Augustin2008TheMP}. While the structure
of resulting polynomial provides information to decide membership, this
representation does not provide information to compute the sums of squares
multipliers of member of such quadratic modules.

Our current result for the univariate case allows us to find certificates in a
preorder structure for a basis with 2 generators introduced in
\cite{10.1145/3476446.3536176}. We plan to find certificates for the product of
the two generators in order to have certificates in the quadratic module
structure. For the bivariate case, we have solved the certificates problem for a
monogenic case satisfying certain properties. We plan to generalize this result
for more general cases.
