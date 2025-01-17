######
pyudev
######

.. image:: https://secure.travis-ci.org/pyudev/pyudev.png?branch=develop
   :target: http://travis-ci.org/pyudev/pyudev

http://pyudev.readthedocs.org

pyudev is a LGPL_ licensed, pure Python_ binding for libudev_, the device and
hardware management and information library for Linux.  It supports almost all
libudev_ functionality. You can enumerate devices, query device properties and
attributes or monitor devices, including asynchronous monitoring with threads,
or within the event loops of Qt, Glib or wxPython.

The binding supports CPython_ 3 and compatible versions of PyPy_.
It is tested against udev 151 or newer, earlier versions of udev
as found on dated Linux systems may work, but are not officially supported.


Usage
-----

Usage of pyudev is quite simply thanks to the power of the underlying udev
library. Getting the labels of all partitions just takes a few lines:

>>> import pyudev
>>> context = pyudev.Context()
>>> for device in context.list_devices(subsystem='block', DEVTYPE='partition'):
...     print(device.get('ID_FS_LABEL', 'unlabeled partition'))
...
boot
swap
system

The website_ provides a detailed `user guide`_ and a complete `API reference`_.


Support
-------

Please report issues and questions to the issue tracker, but respect the
following guidelines:

- Check that the issue has not already been reported.
- Check that the issue is not already fixed in the ``master`` branch.
- Open issues with clear title and a detailed description in grammatically
  correct, complete sentences.
- Include the Python version and the udev version (see ``udevadm --version``) in
  the description of your issue.


Development
-----------

The source code is hosted on GitHub_::

   git clone git://github.com/pyudev/pyudev.git

Please fork the repository and send pull requests with your fixes or new
features, but respect the following guidelines:

- Read `how to properly contribute to open source projects on GitHub
  <http://gun.io/blog/how-to-github-fork-branch-and-pull-request/>`_.
- Understand the `branching model
  <http://nvie.com/posts/a-successful-git-branching-model/>`_.
- Write `good commit messages
  <http://tbaggery.com/2008/04/19/a-note-about-git-commit-messages.html>`_.
- Add unit tests if possible (refer to the `testsuite documentation
  <http://pyudev.readthedocs.org/en/latest/tests/index.html>`_).
- Add API documentation in docstrings.
- Open a `pull request <https://help.github.com/articles/using-pull-requests>`_
  that relates to but one subject with a clear title and description in
  grammatically correct, complete sentences.


.. _LGPL: http://www.gnu.org/licenses/old-licenses/lgpl-2.1.html
.. _Python: http://www.python.org/
.. _CPython: http://www.python.org/
.. _PyPy: http://www.pypy.org/
.. _libudev: http://www.kernel.org/pub/linux/utils/kernel/hotplug/libudev/
.. _website: http://pyudev.readthedocs.org
.. _user guide: http://pyudev.readthedocs.org/en/latest/guide.html
.. _api reference: http://pyudev.readthedocs.org/en/latest/api/index.html
.. _issue tracker: http://github.com/pyudev/pyudev/issues
.. _GitHub: http://github.com/pyudev/pyudev
.. _git: http://www.git-scm.com/


Request a New Release
---------------------
I will be doing regular releases of this project every August and October,
shortly after Fedora releases are branched from rawhide.

If you believe an extra release would help you in some way, please file an
issue, explaining why you need the new release, and I expect I'll put one up.

Why should you explain why you need the new release? Well, it is helpful to me,
because pyudev is not at all part of my regular work, and I tend not to know
very much about how it is used these days.
