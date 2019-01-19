# Convex hull

An interactive animation of an alogithm to find the convex hull of a group of points. You can try it out here: https://mrtimuk.github.io/convhull/

The algorithm has two steps:

### 1. Create a hull containing the points

A simple polygon containing all the points. The simplest way to do this is to join all the points in radial order.

### 2. Remove points which make the hull concave

Imagine travelling along the edge of the hull clockwise. If the hull is convex then at each vertex one must make a right-turn to continue clockwise. A left-turn indicates that the vertex is causing the polygon to be convex, so that vertex should be removed.

We need a function that shows whether a turn is to the right or left. The cross product serves this purpose as it can be defined as:

> a &times; b = |a| . |b| . sin &theta;

Since |a| and |b| are non-negative, the sign of a &times; b is determined by the sign of sin &theta;, the internal angle of the polygon. sin &theta; is positive for 0&deg; &lt; &theta; &lt; 180&deg; and negative for 180&deg; &lt; &theta; &lt; 360&deg;, the latter being a reflex angle indicating concavity.
