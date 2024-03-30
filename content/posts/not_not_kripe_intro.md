+++
title = "A not not Brief Introduction to Kripke Semantics for Propositional Intuitionistic Logic"
author = ["Jose Abel Castellanos Joo"]
date = 2022-08-16
draft = false
+++

## Abstract {#abstract}

In this paper we motivate the study of Kripke semantics for propositional
intuitionistic logic by showing fundamental properties at the proof theory level
using $n+1$-valued logics. Some non-theorems of propositional intuitionistic
logic (like the excludded middle principle) are discussed using this approach.


## Introduction {#introduction}

With the discovery of non-Euclidean geometries
in the middle of the nineteenth century \cite{Trudeau2001},
mathematicians questioned
the logical foundations of mathematics.
In fact, the latter culminated in the
fragmentation of the mathematical community
resulting in three main schools
of thought:


### Platonism: {#platonism}

The practicioners
consider the subject at study to be
independent of the epistemic knowledge
of mathematical objects
and their relations. Instead, these were
regarded as abstract
entities which can only be accessed
through meaningful propositions.


### Formalism: {#formalism}

This trend considers
the linguistic approach an essential
aspect for the discussion of the mathematical
theories using axiomatic systems and
precise rules to understand and communicate
mathematical truth. Formalism is quite often
critized by its opponents to reduce mathematical investigations
to a simple manipulation of symbols. Regardless
of this unintended byproduct, formalism's
main point is to provide a suitable
framework to understand the consistency
of mathematics, a program heavely supported
by the mathematician David Hilbert at the beginning of
the 20th century.
It was not until logician Kurt G\\"odel with his
Incompleteness Theorems that showed the limitations
of this program.


### Intuitionism: {#intuitionism}

This school was initiated
by the ideas of L.E.J. Brouwer, a Dutch
mathematician who worked in several
mathematical subjects ranging from topology
to foundations of mathematics.
He was a critic of the Formalism approach.
The crucial missing part was the lack of
involvement of the knowledge-subject.
The thinking activity is of huge
importance for him. Such activity grounds
on our \emph{Ur-intuition} of the flow
of time \cite{https://doi.org/10.1002/sdr.462}.
Thus, mathematical work accounts to \`mental
constructions' in the intuitionistic sense.

In this light, an intuitionistic assertion
constitutes complete knowlege on the subject.
To say that something is true in the intuitionisc
sense accounts to having a proof of it. Notice
that the intention here is radically different
in the negation. Knowing that something
is false accounts to having a proof of the
impossibility of the fact, contrary to the
position of not having a proof of it.

A typical example in intuitionistic mathematics
is to discuss the excludded middle principle
\\(\neg A \lor A\\).
Such statement \emph{cannot be accepted}
intuitioniscally since it contributes more
to an undecided moment rather
than knowledge about the statement.
In the rest of this paper we will discuss
axiomatic systems and models which allows
us to understand intuitionistic ideas.


## A formal system \\(J\\) for propositional intuitionistic logic {#a-formal-system-j-for-propositional-intuitionistic-logic}

The following axioms were extract from \cite{hodel2013introduction}:

-   **Language**: The symbols of the language are:
    -   \\(p\_1, p\_2, p\_3, \dots\\): An infinite list of propositional variables
    -   \\(\neg, \rightarrow, \land, \lor\\): negation, implication, conjunction, and disjunction symbol
    -   \\((, )\\): left and right parenthesis for punctuation
-   **Axioms**:
    -   J1: \\(A \rightarrow (B \rightarrow A)\\)
    -   J2: \\((A \rightarrow (B \rightarrow C)) \rightarrow ((A \rightarrow B) \rightarrow (A \rightarrow C))\\)
    -   J3: \\(A \land B \rightarrow A\\)
    -   J4: \\(A \land B \rightarrow B\\)
    -   J5: \\(A \rightarrow (B \rightarrow (A \land B))\\)
    -   J6: \\(A \rightarrow (A \lor B)\\)
    -   J7: \\(B \rightarrow (A \lor B)\\)
    -   J8: \\((A \rightarrow C) \rightarrow ( ( B \rightarrow C) \rightarrow (( A \lor B) \rightarrow C))\\)
    -   J9: \\((A \rightarrow B) \rightarrow (( A \rightarrow \neg B) \rightarrow \neg A)\\)
    -   J10: \\(\neg A \rightarrow (A \rightarrow B)\\)
-   **Rules of Inference**:
    -   Modus Ponens

As in classical logic \\(A \leftrightarrow B\\) is abbreviated
as \\((A \rightarrow B) \land (B \rightarrow A)\\). It is important to mention that the other connective symbols do not
share similar abbreviations as in the classical counterpart.
Since \\(J\\) as a formal system contains \\(J1\\) and Modus
Ponens as unique rule of inference, by the comment on Theorem 3
in Section 3.5 of \cite{hodel2013introduction} we have that
\\(J\\) satisfies the Deduction theorem. A proof of the above is
shown in the next theorem:

Theorem:

<div class="theorem">

<span class="org-target" id="org-target--theorem1"></span> (Deduction theoreom for \\(J\\))
  If \\(\Gamma \cup \\{ A \\} \vdash\_J B\\), then
  \\(\Gamma \vdash\_J A \rightarrow B\\)

</div>

Proof:

<div class="proof">

We proceed by induction on the number of steps in the proof of \\(B\\)
using \\(\Gamma \cup \\{A\\}\\). Assume \\(\Gamma \cup \\{A \\} \vdash\_J B\\),
to prove \\(\Gamma \vdash\_J A \rightarrow B\\). There are three cases:

-   \\(B\\) is an axiom of \\(J\\) or \\(B \in \Gamma\\):
    From this we have that \\(\vdash\_J B\\)
    Since \\(J\\) has \\(J1\\), we can conclude that
    \\(\Gamma \vdash\_J B \rightarrow (A \rightarrow B)\\). By Modus Ponens we
    obtain \\(\Gamma \vdash\_J A \rightarrow B\\)
-   \\(B\\) is in \\(A\\): In this case, the following is proof of
    \\(\Gamma \vdash\_J A \rightarrow A\\).
    1.  \\(A \rightarrow (A \rightarrow A)\\), Axiom \\(J1\\)
    2.  \\(A \rightarrow ((A \rightarrow A) \rightarrow A)\\), Axiom \\(J1\\)
    3.  \\((A \rightarrow ((A \rightarrow A) \rightarrow A)) \rightarrow ( (A \rightarrow (A \rightarrow A)) \rightarrow (A \rightarrow A))\\), Axiom \\(J2\\)
    4.  $ (A &rarr; (A &rarr; A)) &rarr; (A &rarr; A)$, Modus Ponens(2, 3)
    5.  \\(A \rightarrow A\\), Modus Ponens(1, 4)
-   \\(B\\) is obtained from \\(C\\) and \\(C \rightarrow B\\) by an application of Modus Ponens. By induction, we have from
    \\(\Gamma \cup \\{ A \\} \vdash\_J B\\) and
    \\(\Gamma \cup \\{ A \\} \vdash\_J C \rightarrow B\\) the following
    \\(\Gamma \vdash\_J A \rightarrow B\\) and
    \\(\Gamma \vdash\_J A \rightarrow (C \rightarrow B)\\). By \\(J2\\)
    we have that \\(\Gamma \vdash\_J (A \rightarrow (C \rightarrow B)) \rightarrow ((A \rightarrow B) \rightarrow (A \rightarrow C))\\). A double application of Modus Ponens, we obtain \\(\Gamma \vdash\_J A \rightarrow C\\).

</div>

Theorem:

<div class="theorem">

\\(\neg A \lor A\\) and \\(\neg \neg A \rightarrow A\\) are not
theorems of \\(J\\).

</div>

Proof:

<div class="proof">

Let us introduce an $n+1$-valued logic as follows:
A truth assignment is a function \\(\phi : PROP \rightarrow \\{0, 1, \dots, n\\}\\); such an assignment extends to
all formulas \\(FOR(\neg, \lor, \land, \rightarrow)\\) of \\(J\\)
according to these rules:

-   \\(\phi(A \lor B) = \min \\{ \phi(A), \phi(B) \\}\\)
-   \\(\phi(\neg A) =  \begin{cases}
          0 & \phi(A) = n \\\\
          n & \phi(A) < n
        \end{cases}\\)
-   \\(\phi(A \land B) = \max \\{ \phi(A), \phi(B) \\}\\)
-   \\(\phi(A \rightarrow B) =  \begin{cases}
          0 & \phi(A) \geq \phi(B) \\\\
          \phi(B) & \phi(A) < \phi(B)
        \end{cases}\\)

We will prove that for every theorem \\(A\\) in \\(J\\)
we have that \\(\phi(A) = 0\\) by induction on the
length of the proof:

-   Base case: Since the base case accounts to axioms in \\(J\\), we need to prove that every axiom in \\(J\\) evaluates to 0 under \\(\phi\\):
    \begin{itemize}
    -   Case \\(J1\\): Since \\(\phi(A) \geq \phi(A)\\) and \\(\phi(A) \geq 0\\) we have that \\(\phi(A) \geq \phi(B \rightarrow A)\\), so \\(\phi(A \rightarrow (B \rightarrow A)) = 0\\).
    -   Case \\(J2\\): To prove \\(\phi(( A \rightarrow (B \rightarrow C)) \rightarrow ((A \rightarrow B) \rightarrow (A \rightarrow C))) = 0\\).
        \begin{itemize}
        -   Case 1. \\(\phi(A) \geq \phi(B \rightarrow C)\\). This implies \\(\phi(A \rightarrow (B \rightarrow C)) = 0\\). Thus, it is enough to prove that \\(\phi((A \rightarrow B) \rightarrow (A \rightarrow C)) = 0\\), i.e. \\(\phi(A \rightarrow B) \geq \phi(A \rightarrow C)\\).
            -   Subcase 1. \\(\phi(A) \geq \phi(B)\\) and \\(\phi(A) \geq \phi( C)\\): This holds since \\(0 \geq 0\\).
            -   Subcase 2. \\(\phi(A) \geq \phi(B)\\) and \\(\phi(A) < \phi( C)\\): It is enough to prove \\(0 \geq \phi( C)\\), i.e. \\(\phi( C) = 0\\). Suppose by contradiction that \\(\phi( C) \neq 0\\). We have that \\(\phi( C) > \phi(A) \geq \phi(B)\\), so \\(\phi( C) > \phi(B)\\). This implies that \\(\phi(B \rightarrow C) = \phi( C)\\). Since \\(\phi(A) \geq \phi(B \rightarrow C)\\) we have that \\(\phi(A) \geq \phi( C)\\). Therefore, \\(\phi( C) > \phi(A) \geq \phi( C)\\), a contradiction.
            -   Subcase 3. \\(\phi(A) < \phi(B)\\) and \\(\phi(A) \geq \phi( C)\\): This holds since \\(\phi(B) \geq 0\\).
            -   Subcase 4. \\(\phi(A) < \phi(B)\\) and \\(\phi(A) < \phi( C)\\): To prove that \\(\phi(B) \geq \phi( C)\\). Suppose by contradiction that \\(\phi(B) < \phi( C)\\), thus \\(\phi(B \rightarrow C) = \phi( C)\\). Since \\(\phi(A) \geq \phi(B \rightarrow C)\\) we have that \\(\phi(A) \geq \phi( C)\\). Since \\(\phi( C) > \phi(A) \geq \phi( C)\\) we reach a contradiction.
        -   Case 2. \\(\phi(A) < \phi(B \rightarrow C)\\). The latter implies that \\(\phi(A \rightarrow (B \rightarrow C)) = \phi(B \rightarrow C)\\). Hence, it is enough to prove that \\(\phi(B \rightarrow C) \geq \phi((A \rightarrow B) \rightarrow (A \rightarrow C))\\).
            -   Subcase 1. \\(\phi(B) \geq \phi( C)\\): From the latter we have that \\(\phi(B \rightarrow C) = 0\\). Hence, \\(\phi(A) < 0\\), but \\(\phi(A) \geq 0\\), a contradiction.
            -   Subcase 2. \\(\phi(B) < \phi( C)\\): It is enough to prove that \\(\phi( C) \geq \phi((A \rightarrow B) \rightarrow (A \rightarrow C))\\). Since \\(\phi(B) < \phi( C)\\) we have that \\(\phi(B \rightarrow C) = \phi( C)\\). Since \\(\phi(A) < \phi(B \rightarrow C)\\) we can conclude that hence \\(\phi( C) > \phi(A)\\). Let us prove the following observation \label{observation}: For any two formulas \\(A, B \in FOR(\neg, \land, \lor, \rightarrow)\\), we have that \\(\phi(A) \geq \phi(B \rightarrow A)\\). This happens because \\(\phi(A) \geq 0\\) and \\(\phi(A) \geq 0\\) and by definition of we have that \\(\phi(B \rightarrow A)\\) is either \\(0\\) or \\(\phi(A)\\). From this observation we have that \\(\phi(A \rightarrow C) \leq \phi((A \rightarrow B) \rightarrow (A \rightarrow C))\\). Since \\(\phi(A \rightarrow C) = \phi( C)\\) we can conclude that \\(\phi( C) \geq \phi((A \rightarrow B) \rightarrow (A \rightarrow C))\\).
    -   Case \\(J3\\): This follows from \\(\max \\{ \phi(A), \phi(B) \\} \geq \phi(A)\\).
    -   Case \\(J4\\): This follows from \\(\max \\{ \phi(A), \phi(B) \\} \geq \phi(B)\\).
    -   Case \\(J5\\): We notice the following cases:

        -   Case \\(\phi(A) < \phi(B) = \max \\{ \phi(A), \phi(B) \\}\\):

        This reduces \\(\phi(A \rightarrow (B \rightarrow A \land B)) = 0\\) to check that
        \\(\phi(A) \geq 0\\), which is true.

        -   Case \\(\phi(B) < \phi(A) = \max \\{ \phi(A), \phi(B) \\}\\):

        This reduces \\(\phi(A \rightarrow (B \rightarrow A \land B)) = 0\\) to check that
        \\(\phi(A) \geq \max\\{ \phi(A), \phi(B) \\}\\), which is true since
        \\(\phi(A) = \max \\{ \phi(A), \phi(B) \\}\\).

        -   Case \\(\phi(A) = \phi(B) = \max \\{ \phi(A), \phi(B) \\}\\):

        This reduces \\(\phi(A \rightarrow (B \rightarrow A \land B)) = 0\\) to check that
        \\(\phi(A) \geq 0\\) which is true.
    -   Case \\(J6\\): This follows from \\(\min \\{ \phi(A), \phi(B) \\} \leq \phi(A)\\).
    -   Case \\(J7\\): This follows from \\(\min \\{ \phi(A), \phi(B) \\} \leq \phi(A)\\).
    -   Case \\(J8\\): To prove that \\(\phi((A \rightarrow C) \rightarrow ((B \rightarrow C) \rightarrow ((A \lor B) \rightarrow C))) = 0\\).
        -   Case 1. \\(\phi(A) \geq \phi( C)\\): It is enough to prove that \\(\phi((B \rightarrow C) \rightarrow ( ( A \lor B) \rightarrow C)) = 0\\), i.e. \\(\phi(B \rightarrow C) \geq \phi((A \lor B) \rightarrow C)\\).
            -   Subcase 1. \\(\phi(B) \geq \phi( C)\\). It is enough to prove that \\(\phi(A \lor B) \geq \phi( C)\\).
                Since \\(\phi(A) \geq \phi( C)\\) and \\(\phi(B) \geq \phi( C)\\) then \\(\phi(A \lor B) = \min \\{ \phi(A), \phi(B) \\} \geq \phi( C)\\).
            -   Subcase 2. \\(\phi(B) < \phi( C)\\). Since \\(\phi(A) \geq \phi( C) > \phi(B)\\) we conclude that
                \\(\phi(A \lor B) = \phi(B)\\). Because \\(\phi(B) < \phi( C)\\), we have that
                \\(\phi(B \rightarrow C) = \phi( C)\\). Using the previous observation \ref{observation} we have that
                \\(\phi( C) \geq \phi((A \lor B) \rightarrow C)\\), thus \\(\phi(B \rightarrow C) \geq \phi((A \lor B) \rightarrow C)\\).

        -   Case 2. \\(\phi(A) < \phi(B \rightarrow C)\\). We will prove the following observation \label{observation2}: \\(\phi((A \land B) \rightarrow C) = \phi(A \rightarrow (B \rightarrow C))\\).
            -   Subcase 1. \\(\phi(A) \geq \phi(B \rightarrow C)\\): This means that \\(\phi(A \rightarrow (B \rightarrow C)) = 0\\), hence we need to prove that \\(\phi((A \land B) \rightarrow C) = 0\\). We can see that \\(\phi(A \rightarrow (B \rightarrow C)) = 0\\) implies that \\(\phi(A) \geq \phi(B \rightarrow C)\\), which means that if \\(\phi(B) < \phi( C)\\) we have that \\(\phi(A) \geq \phi(B \rightarrow C) = \phi( C)\\). Suppose by contradiction that \\(\phi((A \land B) \rightarrow C) \neq 0\\), so \\(\phi(A \land B) < \phi( C) \neq 0\\). Thus, \\(\phi( C) > \phi(A)\\) and \\(\phi( C) > \phi(B)\\). The latter entails \\(\phi(A) \geq \phi( C) > \phi(A)\\), a contradiction.
            -   Subase 2. \\(\phi(A) < \phi(B \rightarrow C)\\): This implies that \\(\phi(A \rightarrow (B \rightarrow C)) = \phi(B \rightarrow C)\\). So we need to prove that \\(\phi((A \land B) \rightarrow C) = \phi(B \rightarrow C)\\). We notice that \\(\phi(B) < \phi( C)\\), otherwise \\(\phi(B \rightarrow C) = 0\\) so \\(\phi(A) < 0\\), a contradiction. From this, we conclude that \\(\phi(B \rightarrow C) = \phi( C)\\), which reduces proving \\(\phi(A \rightarrow (B \rightarrow C)) = \phi(B \rightarrow C)\\) to prove \\(\phi(A \rightarrow (B \rightarrow C)) = \phi( C)\\) instead. Since \\(\phi(A) < \phi(B \rightarrow C) = \phi( C)\\), we have that \\(\phi( C) > \max \\{\phi(A), \phi(B) \\}\\). Therefore, \\(\phi((A \land B) \rightarrow C) = \phi( C)\\) as desired.

Returning to our original problem, we have that \\(\phi(A) < \phi(B \rightarrow C)\\), hence
it is enough to prove \\(\phi(A) \geq \phi((B \rightarrow C) \rightarrow ((A \lor B) \rightarrow C))\\).
From our previous observation \ref{observation2}, we notive that
\\(\phi(A) \geq \phi(((B \rightarrow C) \land (A \lor B)) \rightarrow C)\\), so by
our first observation \ref{observation}
the latter is true.

-   Case \\(J9\\): To prove \\(\phi((A \rightarrow B) \rightarrow ((A \rightarrow \neg B) \rightarrow \neg A)) = 0\\), i.e \\(\phi(A \rightarrow B) \geq \phi((A \rightarrow \neg B) \rightarrow \neg A)\\).

    -   Case 1. \\(\phi(A) \geq \phi(B)\\): To prove \\(\phi((A \rightarrow \neg B) \rightarrow \neg A) = 0\\), i.e. \\(\phi(A \rightarrow \neg B) \geq \phi(\neg A)\\).
        -   Subcase 1. \\(\phi(A) \geq \phi(\neg B)\\): Since \\(\phi(A) \geq \phi(B)\\)
            and \\(\phi(A) \geq \phi(\neg B)\\) we conclude that \\(\phi(A) = n\\),
            thus \\(\phi(\neg A) = 0\\), so \\(\phi(A \rightarrow \neg B) \geq \phi(\neg A)\\) reduces
            to \\(0 \geq 0\\) which is true.
        -   Subcase 2. \\(\phi(A) < \phi(\neg B)\\): This reduces
            \\(\phi(A \rightarrow \neg B) \geq \phi(\neg A)\\)
            to prove \\(\phi(\neg B) \geq \phi(\neg A)\\). Since \\(\phi(A) \geq \phi(B)\\) we
            have that \\(\phi(\neg B) > \phi(B)\\). This implies that \\(\phi(\neg B) = n\\),
            otherwise \\(\phi(\neg B) = 0\\) and \\(\phi(B) = n\\), but it cannot
            be the case that \\(\phi(\neg B) > n\\). The latter reduces
            \\(\phi(\neg B) \geq \phi(\neg A)\\) to prove \\(n \geq \phi(\neg A)\\) which is true.
    -   Case 2. \\(\phi(A) < \phi(B)\\): This means that \\(\phi(A \rightarrow B) = \phi(B)\\). To prove that \\(\phi(B) \geq \phi((A \rightarrow \neg B) \rightarrow \neg A)\\).
        -   Subcase 1. \\(\phi(A \rightarrow \neg B) \geq \phi(\neg A)\\). This means that \\(\phi((A \rightarrow \neg B) \rightarrow \neg A) = 0\\), which reduces \\(\phi(B) \geq \phi((A \rightarrow \neg B) \rightarrow \neg A)\\) to \\(\phi(B) \geq 0\\) which is true.
        -   Subcase 2. \\(\phi(A \rightarrow \neg B) < \phi(\neg A)\\). The latter means that \\(\phi((A \rightarrow \neg B) \rightarrow \neg A) = \phi(\neg A)\\). To prove \\(\phi(B) \geq \phi(\neg A)\\).

    Suppose by contradiction that \\(\phi(B) < \phi(\neg A)\\). Since \\(\phi(A) \geq \phi(B)\\)
    we have that \\(\phi(\neg A) > \phi(A)\\). So \\(\phi(\neg A) = n\\), otherwise
    \\(\phi(A) = n\\) and \\(\phi(\neg A) > n\\), which is not possible. The latter also
    entails that \\(\phi(A) < n\\). Additionally, \\(\phi(B) < n\\), otherwise
    \\(n < \phi(\neg A)\\), which is not possible. From the latter \\(\phi(\neg B) = n\\).
    Since \\(\phi(A) < n = \phi(\neg B)\\), we have that \\(\phi(A \rightarrow \neg B) = \phi(\neg B) = n\\).
    But this implies that \\(n > n\\), a contradiction.

<!--listend-->

-   Case \\(J10\\): To prove that \\(\phi(\neg A \rightarrow (A \rightarrow B)) = 0\\), i.e. \\(\phi(\neg A) \geq \phi(A \rightarrow B)\\).

    -   \Subcase 1. \\(\phi(A) \geq \phi(B)\\): So \\(\phi(A \rightarrow B) = 0\\), so

    \\(\phi(\neg A) \geq \phi(A \rightarrow B)\\) reduces to \\(\phi(\neg A) \geq 0\\), which is true.

    -   Subcase 2. \\(\phi(A) < \phi(B)\\): This implies that \\(\phi(A) < n\\), otherwise

    \\(n < \phi(B)\\), which is not possible. Additionally, \\(\phi(A \rightarrow B) = \phi(B)\\).
    Since \\(\phi(A) < n\\) we have that \\(\phi(\neg A) = n\\), thus
    \\(\phi(\neg A) \geq \phi(A \rightarrow B)\\) reduces to \\(n > \phi(A \rightarrow B)\\) which is true.

<!--listend-->

-   Inductive case: Let \\(\langle A\_1, A\_2, \dots, A\_n, A\_{n+1} \rangle\\) be

proof in \\(J\\) of size \\(n+1\\). We notice that the
subproof \\(\langle A\_1, A\_2, \dots, A\_n \rangle\\)
satisfies the Inductive hypothesis, i.e. $&phi;(A_i) = $ for every \\(1 \leq i \leq n\\). We need to show
that \\(\phi(A\_{n+1}) = 0\\). Several cases are noticed:

-   \\(A\_{n+1}\\) is an axiom of \\(J\\). Then by the
    base case we have that \\(\phi(A\_{n+1}) = 0\\) as desired.
-   \\(A\_{n+1}\\) was obtained using Modus Ponens
    using some \\(A\_i, A\_j := A\_i \rightarrow A\_{n+1}\\) in the proof with
    \\(i, j \leq n\\). By the inductive hypothesis,
    we have that \\(\phi(A\_i) = 0\\) and \\(\phi(A\_i \rightarrow A\_{n+1}) = 0\\), which means that
    \\(0 = \phi(A\_i) \geq \phi(A\_{n+1})\\), thus \\(\phi(A\_{n+1}) = 0\\).

With this invariant we conclude that \\(\phi(A) = 0\\) for every \\(\vdash\_J A\\).

</div>

We notice that with an assignment \\(\phi : PROP \rightarrow \\{0, 1, 2\\}\\)
such that \\(\phi(A) = 1\\) we have that \\(\phi(\neg A \lor A) = \min \\{ \phi(\neg A), \phi(A) \\}
= \min \\{ 2 ,  1 \\} = 1\\). Additionally, \\(\phi(\neg \neg A) = 0\\) since \\(\phi(\neg A) = 2\\),
so \\(\phi(\neg \neg A \rightarrow A) = 1\\) since \\(0 = \phi(\neg \neg A) < \phi(A) = 1\\).

It is important to notice that the $n+1$-valued logic introduced in the previous
theorem can be considered and \emph{invariant} for the propositional intuitionisc
formal system. However, this truth assignment does not constitute a semantics
for the system \\(J\\). In fact, there are no finite smeantics
for intuitionistic logic as we will observe with the following theorem:

Lemma:

<div class="lemma">

<span class="org-target" id="org-target--wow"></span>
For \\(n \geq 2\\), let \\(D\_n\\) denote the formula:

\\((p\_1 \leftrightarrow p\_2) \lor (p\_1 \leftrightarrow p\_3) \lor \dots \lor (p\_1 \leftrightarrow p\_n) \lor \dots\\) <br />
\\(\lor (p\_2 \leftrightarrow p\_3) \lor \dots \lor (p\_2 \leftrightarrow p\_n) \lor \dots\\) <br />
\\(\lor (p\_{n-1} \leftrightarrow p\_n)\\)

We have that \\(\not \vdash\_J D\_n\\).

</div>

Proof:

<div class="proof">

We use the $n+1$-valued logic previously defined in theorem \ref{theorem1}.
We notice that \\(\phi(D\_n) = \min\_{1 \leq i<j \leq n} \\{ \phi(p\_i \leftrightarrow p\_j) \\}\\).
Let us suppose by contradiction that \\(\vdash\_J D\_n\\). Thus, by theorem \ref{theorem1}
we have that \\(\phi(D\_n) = 0\\), so there are \\(1 \leq i<j \leq n\\) such
that \\(\phi(p\_i \leftrightarrow p\_j) = 0\\). Since \\(p\_i \leftrightarrow p\_j\\) stands for
\\((p\_i \rightarrow p\_j) \land (p\_i \rightarrow p\_j)\\) we have that
\\(\max \\{ \phi(p\_i \rightarrow p\_j), \phi(p\_j \rightarrow p\_i) \\} = 0\\). The latter
implies that \\(\phi(p\_i \rightarrow p\_j) = 0\\) and
\\(\phi(p\_j \rightarrow p\_i) = 0\\), which entail that \\(\phi(p\_i) \geq \phi(p\_j)\\)
and \\(\phi(p\_j) \geq \phi(p\_i)\\). These inequalities can be combined into
\\(\phi(p\_i) = \phi(p\_j)\\). So if we pick a truth assignment such that
\\(\phi(p\_i) = i\\) we notice that \\(D\_n\\) does not hold for all truth assignments
in the $n+1$-valued logic.

</div>

Theorem:

<div class="theorem">

Consider the language with connectives \\(\neg, \lor, \land, \rightarrow\\). A \emph{matrix}
for this language is a 6-tuple \\(M =
\langle S, S\_0, H\_\neg, H\_\lor, H\_\land, H\_\rightarrow \rangle\\), where
\\(S\\) is a nonempty set whose elements are called \emph{truth values}, \\(S\_0\\)
is a subset of \\(S\\) whose elements are called \emph{designated values},
and \\(H\_\lor, H\_\land, H\_\rightarrow\\), and \\(H\_\neg\\) are truth functions
for \\(\lor, \land, \rightarrow\\), and \\(\neg\\). A \emph{truth assignment}
for \\(M\\) is a function \\(\phi : PROP \rightarrow S\\). Such an assignment extends
\\(FOR(\neg, \lor, \land, \rightarrow)\\) in the usual way.

There is no matrix \\(M\\) with \\(S\\) finite such that for every formula \\(A\\),
\\(\vdash\_J A \Leftrightarrow \phi(A) \in S\_0\\) for every truth assignment
\\(\phi\\) for \\(M\\).

</div>

Proof:

<div class="proof">

Let us assume by contradiction that such matrix \\(M\\) exists with
\\(n\\) elements. We realize that \\(D\_{n+1}\\) is not a theorem of \\(J\\)
from lemma \ref{wow}, so there is a truth assignment \\(\phi\\)
for \\(M\\) such that \\(\phi(D\_{n+1}) \not \in S\_0\\). By the pigeonhole
principle, there are \\(1 \leq j < k \leq n+1\\) such that
\\(\phi(p\_i) = \phi(p\_k)\\), i.e. more propositional variables than
truth values. Let \\(E\_{n+1} = D\_{n+1}\\) be obtained from \\(D\_{n+1}\\)
by replacing \\((p\_j \leftrightarrow p\_k)\\) with \\((p\_k \leftrightarrow p\_k)\\).
Since \\(\phi(p\_j \leftrightarrow p\_k) = H\_\leftrightarrow(\phi(p\_j), \phi(p\_k))\\)
and \\(H\_\leftrightarrow\\) is a truth function, we have that
\\(H\_\leftrightarrow(\phi(p\_j), \phi(p\_k)) = H\_\leftrightarrow(\phi(p\_k), \phi(p\_k))\\)
since \\(\phi(p\_k) = \phi(p\_j)\\). So \\(H\_\leftrightarrow(\phi(p\_k), \phi(p\_k)) = \phi(p\_k \leftrightarrow p\_k)\\).
Thus \\(\phi(D\_{n+1}) = \phi(E\_{n+1})\\).

Let us prove the following theorem in \\(J\\): \\(\vdash\_J p\_k \leftrightarrow p\_k\\).

1.  \\(p\_k \rightarrow (p\_k \rightarrow p\_k)\\), Axiom \\(J1\\)
2.  \\(p\_k \rightarrow ((p\_k \rightarrow p\_k) \rightarrow p\_k)\\), Axiom \\(J1\\)
3.  \\((p\_k \rightarrow ((p\_k \rightarrow p\_k) \rightarrow p\_k)) \rightarrow ( (p\_k \rightarrow (p\_k \rightarrow p\_k)) \rightarrow (p\_k \rightarrow p\_k))\\), Axiom \\(J2\\)
4.  $ (p_k &rarr; (p_k &rarr; p_k)) &rarr; (p_k &rarr; p_k)$, Modus Ponens(2, 3)
5.  \\(p\_k \rightarrow p\_k\\), Modus Ponens(1, 4)
6.  \\((p\_k \rightarrow p\_k) \rightarrow ( (p\_k \rightarrow p\_k) \rightarrow ( (p\_k \rightarrow p\_k) \land (p\_k \rightarrow p\_k)))\\), Axiom \\(J5\\)
7.  $ (p_k &rarr; p_k) &rarr; ( (p_k &rarr; p_k) &and; (p_k &rarr; p_k))$, Modus Ponens(5, 6)
8.  $ (p_k &rarr; p_k) &and; (p_k &rarr; p_k)$, Modus Ponens(5, 7)
9.  $ (p_k &harr; p_k)$, Definition of \\(\leftrightarrow\\) (8)

Using the Axiom \\(J6\\) (or \\(J7\\)) we can introduce any number of formulas to a theorem in \\(J\\). Hence, \\(\vdash E\_{n+1}\\), thus \\(\phi(E\_{n+1}) \in S\_0\\) according to our assumption of the existence of a matrix \\(M\\). This however, entails that \\(\phi(D\_{n+1}) \in S\_0\\) but that is a contradiction.

</div>


## Kripke Semantics for Propositional Intuitionistic Logic {#kripke-semantics-for-propositional-intuitionistic-logic}

Definition:

<div class="definition">

\cite{vanDalen2013}
A **Kripke model** is a tuple \\(\mathcal{K} = \langle K, \Sigma \rangle\\) such that
\\(K\\) ia a non-empty partially ordered set, \\(\Sigma : K \rightarrow 2^{PROP}\\) is a function on \\(K\\)
that assigns a collection of propositional
variables to each element \\(k\\) in \\(K\\) satisfying
the following:

-   \\(\bot \not \in \Sigma(k)\\) for all \\(k\\) in \\(K\\)
-   If \\(k \leq l\\) then \\(\Sigma(k) \subseteq \Sigma(l)\\)

</div>

Each element in \\(K\\) can be interpreted as the
states of the knowlege-subject, which progression
over time is captured by the partially order
relation \\(\leq\\) over \\(K\\). Additionally,
the map \\(\Sigma\\) can be understood as the
knowledge state of the knowlege-subject
at each time. The function \\(\Sigma\\) tells us
which atoms are \`true' in each state \\(k \in K\\).
We can extend \\(\Sigma\\) to all formulas.

Lemma:

<div class="lemma">

\\(\Sigma\\) has a unique extension to a function on \\(K\\)
satisfying the following:

1.  \\(\psi \lor \phi \in \Sigma(k)\\) if and only if \\(\psi \in \Sigma(k)\\)

or \\(\phi \in \Sigma(k)\\)

1.  \\(\psi \land \phi \in \Sigma(k)\\) if and only if \\(\psi \in \Sigma(k)\\)

and \\(\phi \in \Sigma(k)\\)

1.  \\(\psi \rightarrow \phi \in \Sigma(k)\\) if and only if for all \\(l \geq k\\)

if \\(\psi \in \Sigma(l)\\) then \\(\phi \in \Sigma(l)\\)

</div>

The negation connective here is abbreviated as \\(\neg A := A \rightarrow \bot\\).
We write \\(k \models \phi\\) for \\(\phi \in \Sigma(k)\\), pronouncing it as
\\(k\\) forces \\(\phi\\).

Lemma:

<div class="lemma">

(Monotonicity of \\(\models\\)) Let \\(k, l \in K\\) and \\(\phi \in
FORM(\neg, \lor, \land, \rightarrow)\\). If \\(k \leq l\\), then \\(k \models \phi\\) implies
\\(l \models \phi\\)

</div>

Proof:

<div class="proof">

Induction on \\(\phi\\).

-   \\(\phi\\) is atomic: Holds by definition of Kripke structure.
-   \\(\phi\\) is \\(\phi\_1 \lor \phi\_2\\): Let \\(k \models \phi\_1 \lor \phi\_2\\)

and \\(k \leq l\\). So \\(k \models \phi\_1 \lor \phi\_2\\) if and only if
\\(k \models \phi\_1\\) or \\(k \models \phi\_2\\). By induction, we have that
\\(l \models \phi\_1\\) or \\(l \models \phi\_2\\) so
\\(l \models \phi\_1 \lor \phi\_2\\).

-   \\(\phi\\) is \\(\phi\_1 \land \phi\_2\\): Similar to the previous case.
-   \\(\phi\\) is \\(\phi\_1 \rightarrow \phi\_2\\):

Let \\(k \models \phi\_1 \rightarrow \phi\_2\\) and \\(l \geq k\\).
Suppose \\(p \geq l\\) and \\(p \models \phi\_1\\).
Since \\(p \geq k\\), \\(p \models \phi\_2\\). Hence, \\(l \models \phi\_1 \rightarrow \phi\_2\\).

</div>

The last lemma captures the idea that knowlege is preserved
\`over time' of the knowlege-subject and as such it can only
be incremented.