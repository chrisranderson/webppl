Built-in Functions
======

Arrays
------

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
