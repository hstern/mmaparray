MMap Arrays: Fast, Disk-Backed Arrays for Python
================================================

.. |copy|   unicode:: U+000A9 .. COPYRIGHT SIGN

|copy| 2014 Farsight Security Inc.

|copy| 2010 Victor Ng

Released under the MIT license.  See license.txt.

About
-----

This library provides persistent, shared, disk-backed arrays with a similar
structure to the built-in array module.  You might want to use this if you
have a dataset that is larger than available physical memory, or if you want
to reduce startup time for your program by loading data on demand, or if you
want yet another way to share memory between processes.

Compatible with Python 2.7 and Python 3.x.  Supports locked pages on
Linux >= 2.5.37 with the ``want_lock`` parameter to ``mmaparray.array()`` and
``mmaparray.MMap<type>Array.__init__()``.

Usage
-----

.. code:: python

    import mmapfile

    a = mmapfile.array('example.array', 'I', 100)
    for i in range(0, len(a)):
        a[i] = i

    for i, val in enumerate(a):
        print ('a[{}] = {}'.format(i, val))

    a.flush()
    a.close()

