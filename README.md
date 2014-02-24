griddy
======
SASS mixin to reset margins and floats when changing media queries. Available for Bourbon + Neat & Compass + Susy.

Problem
======
Largest media query has four columns, medium: three, small: two, etc. Styles applied to nth-child(4n) at large media query need removing when styles apply to nth-child(3n) or nth-child(2n).

Solution
======
Other solutions require that you specify the child to remove styles from. This requires you to remember that a change to one media query may need additional changes in another. This (Griddy) method simply resets values for nth-child('all less than current'). The rendered CSS is slightly more verbose, but simpler to manage.


Notes
======
Compass version tested and working. Based on what I learned writing the Compass version, I suspect there are some issues which need addressing for the Bourbon version. Will back fix on my next Bourbon-based project (or feel free to submit pull request).

In the loop which iterates up to and including $cols, $cols could be replaced with $grid-columns, where $grid-columns is the max columns used. This would make output more verbose and doesn't appear to be necessary as rules specificity seems to be  handling it just fine.
