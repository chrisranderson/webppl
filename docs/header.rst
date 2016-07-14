Built-in functions
======

Arrays
------

.. js:function:: append(a, b)


Probability
-----------

.. js:function:: MAP(dist)

.. js:function:: entropy(dist)

.. js:function:: expectation(dist[, func])


Miscellaneous
-------------

.. js:function:: isEven(x)

   Returns ``true`` if the number is even, ``false`` otherwise.

.. js:function:: isOdd(x)

   Returns ``true`` if the number is odd, ``false`` otherwise.

.. js:function:: idF(x)

   The identity function. Returns the argument it is passed.

.. js:function:: falseF()

   A function that returns ``false``.

.. js:function:: trueF()

   A function that returns ``true``.

.. js:function:: display(val)

   Prints a representation of the value ``val`` to the console.

.. js:function:: expectation(dist[, fn])

   Computes the expectation of a function ``fn`` under the
   :ref:`distribution <distributions>` given by ``dist``. The
   distribution ``dist`` must have finite support.

   ``fn`` defaults to the identity function when omitted.

   ::

      expectation(Categorical({ps: [.2, .8], vs: [0, 1]})); // => 0.8

.. js:function:: mapObject(fn, obj)

   Returns the object obtained by mapping the function ``fn`` over the
   values of the object ``obj``. Each application of ``fn`` has a
   property name as its first argument and the corresponding value as
   its second argument.

   ::

      var pair = function(x, y) { return [x, y]; };
      mapObject(pair, {a: 1, b: 2}); // => {a: ['a', 1], b: ['b', 2]}
