mtree
=====

A portable implementation of the BSD mtree_ utility.

mtree does two things: it builds a specification of a file hierarchy and can
take a specification and check that a file hierarchy fits that specification.

This implementation is intended to be used in circumstances where there it's
not feasible to build or install an implementation of mtree for a given
platform, but where Python is still available.

Alternatives
------------

If you're able to compile it for your system, mtree-port_ is a good alternative
and may be faster.

Some Linux distros package versions of mtree, but these tend to be very old and
thus lack useful features.

Requirements
------------

This paticular implementation targets Python 2.5+, mainly for pragmatic
reasons. If this seems bad, I'd vehemently ask you to get your OS of choice
to package or bundle a modern version of mtree.

Omissions
---------

The following flags are currently noops: ``-b`` (the default behaviour is to
not bother with the newlines), ``-C`` (outside of scope), ``-D`` (ditto),
``-j`` (ditto).

As hash support depends on what is supported in hashlib_ on your platform,
this may mean that hashes such as RIPEMD-160_, which isn't listed in
``hashlib.algorithms_guaranteed`` may not actually be available everywhere.

.. _mtree: https://www.freebsd.org/cgi/man.cgi?mtree(8)
.. _file format: https://www.freebsd.org/cgi/man.cgi?mtree(5)
.. _mtree-port: https://github.com/archiecobbs/mtree-port
.. _RIPEMD-160: https://en.wikipedia.org/wiki/RIPEMD
.. _hashlib: https://docs.python.org/2/library/hashlib.html
