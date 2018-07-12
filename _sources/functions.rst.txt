#########
Functions
#########

.. code-links:: clear

Have already seen functions in action, such as ``len`` and ``max``.

These are functions that Python provides for us.

We can also write our own functions.

We're going to wrap up our logic for the coin toss into a function, and call
the function ``coin_toss``.  Like ``random.random`` our function ``coin_toss``
will accept no arguments.  It will return a 0 50% of the time and a 1 50% of
the time.

We make a function like this:

.. nbplot::

    >>> def coin_toss():
    ...     random_no = random.random()
    ...     if random_no < 0.5:
    ...         our_result = 0
    ...     else:
    ...         our_result = 1
    ...     return our_result

The function starts with the word ``def`` which tells Python we are defining a
function.  Next follows the name of the function, followed by, in our case,
parentheses.  You specify what arguments the function should have, in the
parentheses. In our case, our function as no arguments, so there is nothing
between the parentheses.

Next there follows a series of statements that are indented.  These statements
are the *body* of the function.  They are the code that gets run when the
function gets called.

We return the result with the ``return`` statement.  Here we are returning a 0
if a random number was < 0.5, and a 1 otherwise.

Let's call the function a few times to see if the results are plausible:

.. nbplot::

    >>> # Notice, we pass no arguments
    >>> coin_toss()
    0

.. nbplot::

    >>> coin_toss()
    1

.. nbplot::

    >>> coin_toss()
    0

********
Exercise
********

Up until now, we've assumed that the chance that a child is a boy is 0.5.  Now
assume the proportion of boys born in the UK is 0.513 [#male-births]_.

Here is a new copy of the ``coin_toss`` function, but renamed.  Like the
``coin_toss`` function, it returns 0 50% of the time, and 1 the rest of the
time.  Modify the function to return 0 (for a boy) 51.3% of the time, and 1
(for a girl) 48.7% of the time:

.. nbplot::

    >>> def girl_or_boy():
    ...     # Return 1 for a girl, 0 for a boy
    ...     random_no = random.random()
    ...     if random_no < 0.5:
    ...         our_result = 0
    ...     else:
    ...         our_result = 1
    ...     return our_result

You can try your function out a few times with the cell below:

.. nbplot::

    >>> girl_or_boy()
    0
