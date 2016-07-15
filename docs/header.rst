Built-in Functions
======

Array manipulation
------------------

.. js:function:: map(fn, xs)

   Returns an array where ``fn`` has been applied to each element in ``xs``.

   ::

      map(function(x){return x * 2}, [1, 2, 3]) // => [2, 4, 6]

.. js:function:: map2(fn, xs, ys)

   Returns an array where ``fn`` has been applied to each element in ``xs`` and ``ys``.

   ::

      map(function(x, y){return x * y}, [1, 2, 3], [4, 5, 6]) // => [ 4, 10, 18 ]

.. js:function:: mapN(fn, n)

   Returns an array where ``fn`` has been applied to an array of integers in the interval [0, ``n``-1].

   ::

      mapN(function(x){return x * 2}, 3) // => [0, 2, 4]

.. js:function:: mapIndexed(fn, xs)

   Returns an array where ``fn`` has been applied to each element in ``xs``. ``fn`` is given two parameters: the index of the element, and the element itself.

   ::

      mapIndexed(function(i, x){return [i, x]}, ['a', 'b', 'c'])
        // => [[0, 'a'], [1, 'b'], [2, 'c']]

.. js:function:: reduce(fn, init, xs)

   Reduces ``xs`` to a single value. ``fn`` is applied to each element in ``xs`` and an accumulated value. ``init`` is the initial value of the acculumlation.

   ::

      reduce(function(accumulation, x){
        return accumulation + x 
      }, 0, [1, 2, 3])
        // => 6

.. js:function:: append(a, b)
   
   * ``a``: array
   * ``b``: array or real

   Returns an array with the contents of ``a`` followed by the contents of ``b``. 

   ::

      append([1, 2, 3], [4, 5, 6]); // => [1, 2, 3, 4, 5, 6]
      append([1, 2, 3], 4) // => [1, 2, 3, 4]

.. js:function:: cons(a, b)

   * ``a``: array or real
   * ``b``: array or real

   Returns an array with ``a`` followed by the contents of ``b``.

   ::

      cons([1, 2, 3], 4); // => [[1, 2, 3], 4]
      cons(1, [2, 3, 4]); // => [1, 2, 3, 4]
      cons(1, 2) // => [1, 2]
      cons([1, 2, 3], [4, 5, 6]) // => [[1, 2, 3], 4, 5, 6]

.. js:function:: snoc(a, b)

   Returns an array with the contents of ``a`` followed by ``b``.

   ::

      snoc([1, 2, 3], 4) // => [1, 2, 3, 4]
      snoc([1, 2, 3], [4, 5, 6]) // => [1, 2, 3, [4, 5, 6]]

.. js:function:: first(xs)

   Returns the first value of ``xs``.

   ::

      first([10, 20, 30]) // => 10

.. js:function:: second(xs)

   Returns the second value of ``xs``.

.. js:function:: third(xs)

   Returns the third value of ``xs``.

.. js:function:: fourth(xs)

   Returns the fourth value of ``xs``.
 
.. js:function:: secondLast(xs)

   Returns the second-to-last value of ``xs``.

.. js:function:: last(xs)

   Returns the last value of ``xs``.

.. js:function:: most(xs)

   Returns an array containing all but the last value of ``xs``.

   ::

      most([1, 2, 3, 4]) // => [1, 2, 3]

.. js:function:: rest(xs)

   Returns an array containing all but the first value of ``xs``.

   ::

      rest([1, 2, 3, 4]) // => [2, 3, 4]

Math
----

.. js:function:: sum(xs)

   Returns the sum of all the values of ``xs``.

   ::

      sum([5, 5]) // => 10

.. js:function:: product(xs)

   Returns the product of all the values of ``xs``.

   ::

      product([5, 10]) // => 50

.. js:function:: listMean(xs)

   Returns the mean of ``xs``.

.. js:function:: listVar(xs [, mu])

   Returns the variance of ``xs`` from ``mu``.

.. js:function:: normalize(xs)

   Returns each value in ``xs`` divided by ``sum(xs)``. The resulting array sums to 1.

Probability
-----------

.. js:function:: expectation(dist[, fn])

   Computes the expectation of a function ``fn`` under the
   :ref:`distribution <distributions>` given by ``dist``. The
   distribution ``dist`` must have finite support.

   ``fn`` defaults to the identity function when omitted.

   ::

      expectation(Categorical({ps: [.2, .8], vs: [0, 1]})); // => 0.8

Miscellaneous
-------------

.. js:function:: isEven(x)

   Returns ``true`` if ``x`` is even, ``false`` otherwise.

.. js:function:: isOdd(x)

   Returns ``true`` if ``x`` the number is odd, ``false`` otherwise.

.. js:function:: idF(x)

   The identity function. Returns ``x``.

.. js:function:: falseF()

   Returns ``false``.

.. js:function:: trueF()

   Returns ``true``.

.. js:function:: display(val)

   Prints a representation of ``val`` to the console.

.. js:function:: mapObject(fn, obj)

   Returns the object obtained by mapping the function ``fn`` over the
   values of the object ``obj``. Each application of ``fn`` has a
   property name as its first argument and the corresponding value as
   its second argument.

   ::

      var pair = function(x, y) { return [x, y]; };
      mapObject(pair, {a: 1, b: 2}); // => {a: ['a', 1], b: ['b', 2]}
