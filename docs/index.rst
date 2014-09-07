####################################################
Trololio: Trollius and asyncio compatibility library
####################################################

.. module:: trololio
   :synopsis: Trollius and asyncio compatibility

Trololio provides a compatibility layer for Trollius and asyncio (aka Tulip).
It addresses the differences listed in `Trollius and Tulip
<http://trollius.readthedocs.org/asyncio.html>`_:

* Allows the use of Trollius' syntax with :mod:`py3:asyncio`.
* Provides missing objects and aliases for the others.
* Synchronizes debug environnement variables.

.. seealso::

   Documentation for `Trollius <http://trollius.readthedocs.org/>`_ and
   :mod:`py3:asyncio`.



******************
Indices and tables
******************

* :ref:`genindex`
* :ref:`search`



***************
Module contents
***************

.. data:: ASYNCIO

   A boolean indicating if :data:`asyncio` (:mod:`trololio`'s submodule) is
   :mod:`py3:asyncio`.

.. data:: TROLLIUS

   A boolean indicating if :mod:`asyncio` (:mod:`trololio`'s submodule) is
   :mod:`trollius:trollius`.

:data:`ASYNCIO` and :data:`TROLLIUS` are always of opposite value.


Trollius objects
================

The following objects are aliases for the :mod:`trollius:trollius` ones, or defined by
:mod:`trololio`.

.. function:: coroutine

   :func:`trollius:trollius.coroutine` or equivalent allowing ``yield From(x)``.

.. function:: From

   :func:`trollius:trollius.From` or equivalent.

.. exception:: Return

   :exc:`trollius:trollius.Return` or equivalent.

.. data:: BACKPORT_SSL_ERRORS

   :data:`trollius:trollius.BACKPORT_SSL_ERRORS` or ``False``.

.. data:: BACKPORT_SSL_CONTEXT

   :data:`trollius:trollius.BACKPORT_SSL_CONTEXT` or ``False``.


Standard library objects
========================

The following objects are aliases for the :mod:`trollius:trollius` ones, or aliases for
the standard library ones.

OSError and socket.error exceptions
-----------------------------------

.. exception:: BlockingIOError

   :exc:`trollius:trollius.BlockingIOError` or :exc:`py3:BlockingIOError`.

.. exception:: BrokenPipeError

   :exc:`trollius:trollius.BrokenPipeError` or :exc:`py3:BrokenPipeError`.

.. exception:: ChildProcessError

   :exc:`trollius:trollius.ChildProcessError` or :exc:`py3:ChildProcessError`.

.. exception:: ConnectionAbortedError

   :exc:`trollius:trollius.ConnectionAbortedError` or :exc:`py3:ConnectionAbortedError`.

.. exception:: ConnectionRefusedError

   :exc:`trollius:trollius.ConnectionRefusedError` or :exc:`py3:ConnectionRefusedError`.

.. exception:: ConnectionResetError

   :exc:`trollius:trollius.ConnectionResetError` or :exc:`py3:ConnectionResetError`.

.. exception:: FileNotFoundError

   :exc:`trollius:trollius.FileNotFoundError` or :exc:`py3:FileNotFoundError`.

.. exception:: InterruptedError

   :exc:`trollius:trollius.InterruptedError` or :exc:`py3:InterruptedError`.

.. exception:: PermissionError

   :exc:`trollius:trollius.PermissionError` or :exc:`py3:PermissionError`.


SSLError
--------

.. exception:: SSLEOFError

   :exc:`trollius:trollius.SSLEOFError` or :exc:`py3:ssl.SSLEOFError`.

.. exception:: SSLWantReadError

   :exc:`trollius:trollius.SSLWantReadError` or :exc:`py3:ssl.SSLWantReadError`.

.. exception:: SSLWantWriteError

   :exc:`trollius:trollius.SSLWantWriteError` or :exc:`py3:ssl.SSLWantWriteError`.


SSLContext
----------

.. class:: SSLContext

   :class:`trollius.SSLContext` or :class:`py3:ssl.SSLContext`.



asyncio submodule
=================

.. module:: asyncio
   :synopsis: Either Trollius or asyncio.

Trololio provides the :mod:`asyncio` submodule. It is either
:mod:`trollius:trollius` (first choice) or :mod:`py3:asyncio` (fallback).

:note: If neither module was found, an :exc:`ImportError` is raised.