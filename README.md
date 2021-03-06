# orderedmultidict

### omdict is an ordered multivalue dictionary that retains method parity with [dict](http://docs.python.org/library/stdtypes.html#dict).

A multivalue dictionary is a dictionary that can store multiple values per
key. An ordered multivalue dictionary is a multivalue dictionary that retains
the order of insertions and deletions.

orderedmultidict is [Unlicensed](http://unlicense.org/) in the public domain so
you can build amazing things.

omdict can store multiple values per key.

```pycon
>>> from orderedmultidict import omdict
>>> omd = omdict()
>>> omd[1] = 1
>>> omd[1]
1
>>> omd.add(1, 11)
>>> omd.getlist(1)
[1, 11]
>>> omd.addlist(1, [111, 1111])
>>> omd.getlist(1)
[1, 11, 111, 1111]
>>> omd.allitems()
[(1, 1), (1, 11), (1, 111), (1, 1111)]
```

omdict retains insertion and deletion order.

```pycon
>>> omd = omdict()
>>> omd[2] = 2
>>> omd[1] = 1
>>> omd.items()
[(2, 2), (1, 1)]
>>> omd[2] = 'sup'
>>> omd.items()
[(2, 'sup'), (1, 1)]
```

Method parity with dict is retained. omdict can be a drop-in replacement.

```pycon
>>> d, omd = dict(), omdict()
>>> d.update([(1,1), (1,11), (2,2), (2,22)])
>>> omd.update([(1,1), (1,11), (2,2), (2,22)])
>>> d[1], omd[1]
(11, 11)
>>> d[3] = 3
>>> omd[3] = 3
>>> d.get(3), omd.get(3)
(3, 3)
>>> d.items() == omd.items()
True
```


### API

See all of omdict's methods, with examples, in omdict's API document,
[API.md](https://github.com/gruns/orderedmultidict/blob/master/API.md).


### Installation

Installing orderedmultidict with pip is easy.

```
$ pip install orderedmultidict
```
