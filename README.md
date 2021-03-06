# Dispersive Flies Optimization

This is an implementation in Python (using numpy) of the swarm algorithm called _Dispersive Flies Optimization_.

The concept is based on the swarming behaviour of flies near food sources. It is a bare-bones swarm intelligence
algorithm (i.e. it has very few tunable parameters), where:

1. The exploratory phase is based on randomly altering a fly's coordinates (rather like mutation in a genetic
algorithm); and

2. The exploitative phase is based on a fly adjusting its
coordinates based on those of its closest neighbour of highest fitness and the fly with the overall best fitness.

The use of the fly with the best fitness has been criticized by some, since this information would not be available to
flies in real swarm intelligence; the authors of the article, however, have stated that it is unneccessary, and I will
be doing experiments where it can be disabled to see how performance compares.

The article for the Dispersive Flies Optimization can be found here:

https://annals-csis.org/Volume_2/pliks/142.pdf

It is also described on Wikipedia:

https://en.wikipedia.org/wiki/Dispersive_flies_optimisation

Along with the implementation are two programs to employ the algorithm:

1. An implementation that chases a mouse cursor around a window in two dimensions; and

2. An implementation to find _Steiner systems._

A `S(t, k, v)` Steiner system is a set of `k`-sets from a `v`-set such that every `t`-set appears in
exactly one `k`-set. A simple example is `S(2, 3, 7)`, the _Steiner triple system of order 7_, also denoted `STS(7)`.
Let `{0, ..., 6}` be the `v`-set. The `STS(7)` is thus, unique up to isomorphism, of the form:

```
{0, 1, 2}
{0, 3, 4}
{0, 5, 6}
{1, 3, 5}
{1, 4, 6}
{2, 3, 6}
{2, 4, 5}
```

This is also called the _Fano plane_ and is the _projective plane of order 2._

More on Steiner systems can be read at:

https://en.wikipedia.org/wiki/Steiner_system

The algorithm is able to find an STS of order 9 with relative ease:

```
(0, 1, 3)
(0, 2, 5)
(0, 4, 6)
(0, 7, 8)
(1, 2, 7)
(1, 4, 8)
(1, 5, 6)
(2, 3, 4)
(2, 6, 8)
(3, 5, 8)
(3, 6, 7)
(4, 5, 7)
```
