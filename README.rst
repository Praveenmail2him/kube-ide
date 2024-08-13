kube-shell
==============

|Build Status| |PyPI version| |PyPI pyversions| |License| |Gitter chat|

Kube-shell: An integrated shell for working with the Kubernetes CLI

Under the hood kube-shell still calls kubectl. Kube-shell aims to
provide ease-of-use of kubectl and increasing productivity.

kube-shell features
-------------------

Auto Completion of Commands and Options with in-line documentation
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. figure:: http://i.imgur.com/dfelkKr.gif
   :alt: 

Fish-Style Auto Suggestions
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. figure:: http://i.imgur.com/7VciOuR.png
   :alt: 

Command History
^^^^^^^^^^^^^^^

You can use up-arrow and down-arrow to walk through the history of
commands executed. Also up-arrow partial string matching is possible.
For e.g. enter 'kubectl get' and use up-arrow and down-arrow to browse
through all kubectl get commands. You could also use CTRL+r to search
from the history of commands.

.. figure:: http://i.imgur.com/xsIM3QV.png
   :alt: 

Fuzzy Searching
^^^^^^^^^^^^^^^

.. figure:: http://i.imgur.com/tW9oAUO.png
   :alt: 

Server Side Auto Completion
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. figure:: http://i.imgur.com/RAfHXjx.gif
   :alt: 

Context information
^^^^^^^^^^^^^^^^^^^

Details of current context from kubeconfig is always readily displayed
on the bottom toolbar. By pressing F4 button you can switch between the
clusters and using F5 can switch between namespaces.

.. figure:: http://i.imgur.com/MJLgcj3.png
   :alt: 

vi editing mode
^^^^^^^^^^^^^^^

Press ESC you have all key bindings (w: next word, b: prev word) to move
across the words.

Installation
------------

The kube-shell requires python and
`pip <https://pypi.python.org/pypi/pip>`__ to install. You can
install the kube-shell using ``pip``:

.. code:: bash

        $ pip install kube-shell

Usage
-----

After installing kube-shell through pip, just run kube-shell to bring up
shell.

At the kube-shell command prompt you can run exit or press F10 to exit
the shell. You can clear the screen by running clear command.

By default drop-down suggestion list also displays in-line
documentation, you can turn on/off inline documnetation by pressing F4
button.

You can run any shell command by prefixing command with "!". For e.g.
!ls would list from the current directory.

At the background
-----------------

Other than generation of suggestions all heavy lifting is done by
Python's `prompt
toolkit <https://github.com/jonathanslenders/python-prompt-toolkit>`__,
`Pygments <http://pygments.org>`__ libraries.

A GO `program <misc/python_eats_cobra.go>`__ is used to generate
kubectl's commands, subcommands, arguments, global options and local
options in `json <kubeshell/data/cli.json>`__ format. Kube-shell uses
generated json file to suggest commands, subcommands, options and args.
For server side completion kube-shell uses
`client-python <https://github.com/kubernetes-incubator/client-python>`__
libray to fetch the resources.


Future Plans
-------------

Kube-shell will be updated for every K8s (kubectl) release version.

Will be extended for OpenShift (oc) version.