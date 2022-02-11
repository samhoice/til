# namedtuple

This is not something new, but not something I've used often. I had opportunity to look at it today.

`namedtuple` from the `collections` library is a tuple that can be indexed by name. So instead of a normal python tuple: `t = (3, 6)` which can accessed by index as `t[0]`, a named tuple can be accessed by a name. The canonical example seems to be a cartesian coordinate.

`Coord = namedtuple('Coord', ['x', 'y'])`

Then it can be instantiated as:

`c = Coord(3, 6)`

`c[0] # ==3`

But the interesting part is the name:

`c.y # ==6`

But remember it's a tuple so it's immutable.
