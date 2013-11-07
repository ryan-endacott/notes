# Disjoint-set Operations

## Operations:
- Make-set
- Find-set(u)
  - Finds the set that u belongs to
- union(x, y)
  - Merges set containing x with set containing y

## Linked-List Representation

Suppose we have a set {a, b, c}
It is represented in arbitrary order by a linked list of the elements.

Empty head/tail is included. Each element has a pointer back to the empty head/tail.

Empty -> A -> B -> C -> Empty loop

Find-set(c) will return Empty head/tail

Suppose two sets {a, b}, and {c}

union(a, c)
Append one list to the other then get rid of the appended list's empty head node.
Resetting all of the back pointers in the second list takes k time.

Union is O(k), where k is length of shortest set.
So we must append the smaller set to the bigger one.
Figure out which one is smaller by storing size in empty head.

O(nlogn) for all unions.
Two sets of size i, j.  i > j
union i and j.
i + j is resulting size.  i + j > 2j
Everytime you reset the back pointer of an element, its size will double.


m find-set, make-set, and union operations take O(m + nlgn)


Easily check if two vertexes are in same connected component (slower than DFS):
```
for v in V:
  make-set(v)
for u-v in E:
  if find-set(u) != find-set(v):
    union(u, v)
```


## Disjoint-Forest (Reverse-Tree) Representation

{a, b, c}

a points to itself
b points to a
c points to a
   a
 b   c

or

a points to itself
b points to a
c points to b
    a
  b
c


find-set(b) returns a
find-set(x) returns root of its tree.

make-set(d) creates d node that points to itself

union(b, g) makes one root point to another.

find-set(a) can also use path-compression heuristic to make the tree more efficient.

With full compression, m operations can be done in O(m * alpha(n)) for all practical purposes, alpha(n) < 4
So usually linear, constant time.
