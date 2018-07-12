#########
Functions
#########

.. code-links:: clear

Have already seen functions in action, such as ``len`` and ``max``.

These are functions that Python provides for us.

We can also use functions in modules. One is example is the ``random``
function from the ``random`` module.  This returns random number between 0 and
1.

.. nbplot::

    >>> import random

.. nbplot::
    :hide-from: all
    :show-to: doctest

    >>> random.seed(1966)

.. nbplot::

    >>> random.random()
    0.88990060071...

.. nbplot::

    >>> random.random()
    0.96023181107...

We can also write our own functions.

We will use a function to contain the logic for deciding whether the next
chlild is a boy or a girl.  Call our new function ``girl_or_boy``.  Like
``random.random`` our function ``girl_or_boy`` will accept no arguments.  It
will return a ``G`` 50% of the time and a ``B`` 50% of the time.

Remember, we have already imported ``random``.

We make a function like this:

.. nbplot::

    >>> def girl_or_boy():
    ...     # Make a random number between 0 and 1
    ...     random_no = random.random()
    ...     if random_no < 0.5:
    ...         our_result = 'G'
    ...     else:
    ...         our_result = 'B'
    ...     return our_result

The function starts with the word ``def`` which tells Python we are defining a
function.  Next follows the name of the function, followed by, in our case,
parentheses.  You specify what arguments the function should have, in the
parentheses. In our case, our function as no arguments, so there is nothing
between the parentheses.

Next there follows a series of statements that are indented.  These statements
are the *body* of the function.  They are the code that gets run when the
function gets called.

We return the result with the ``return`` statement.  Here we are returning
``"G"`` if a random number was < 0.5, and a ``"B"`` otherwise.

Let's call the function a few times to see if the results are plausible:

.. nbplot::

    >>> # Notice, we pass no arguments
    >>> girl_or_boy()
    'B'

.. nbplot::

    >>> girl_or_boy()
    'B'

.. nbplot::

    >>> girl_or_boy()
    'G'

********
Exercise
********

Up until now, we've assumed that the chance that a child is a boy is 0.5.  Now
assume the proportion of boys born in the UK is 0.513 [#male-births]_.

Make a copy of the ``girl_or_boy`` function gove.  Modify the function to
return ``"B"`` (for a boy) 51.3% of the time, and ``"G"`` (for a girl) 48.7%
of the time:

You can try your function out a few times with the cell below:

.. nbplot::

    >>> girl_or_boy()
    'B'

If you've got that done, use a ``for`` loop to run this function 10000 times,
and record what proportion of times it returns ``"G"``.  Is the answer close
to 0.487?  It should be ...

.. [#male-births] `Official UK government statistics
   <https://www.gov.uk/government/statistics/gender-ratios-at-birth-in-great-britain-2010-to-2014>`_
   give the birth ratio as 105.3. This the number of boys born for every 100
   girls.
