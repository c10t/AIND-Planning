# Research Review

This is a review of
the important historical developments in the field of
AI planning and search.

## STRIPS [1]
This represents a world model as an arbitrary collection of first-order
predicate calculus formulas.
STRIPS describes the initial and goal states
as conjunctions of positive literals.
This is the first major AI planning system.

## PDDL [2]
PDDL, the Planning Domain Definition Language is a computer-parsable,
standardized syntax for representing STRIPS, ADL, and other languages.
PDDL is intended to express "physics" of a domain, that is,
what predicats there are, what actions are possible, and so on.
This language used for the AIPS planning competitions.

## HSP [3]
HSP, Heuristic Search Planner is the first to make state-space search
practical for large planning problems. Planner like HSP transform
problems into problems of heuristic search by automatically extracting
heuristics from STRIPS encodings. HSP showed that it chan be competitive
with state-of-the-art Graphplan and SAT planners in the AIPS98
Planning Contest.

## Citations
[1] Fikes and Nilsson, STRIPS: A New Approach to the
Application of Theorem Proving to Problem Solving, 1971

[2] Ghallab, et al., PDDL - The Planning Domain Definition Language, 1998

[3] Bonet and Geffner, Planning as heuristic search, 2001
