=========================
``mc license unregister``
=========================

.. default-domain:: minio

.. contents:: Table of Contents
   :local:
   :depth: 1

.. mc:: mc license unregister


Description
-----------

The :mc-cmd:`mc license unregister` command disconnects your deployment from your |SUBNET| account.

After unregistering, you can no longer use the :mc:`mc support` commands.


Examples
--------

Unregister a Deployment Using the Deployment's Name
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Remove the registration of the MinIO deployment at alias ``minio1`` from SUBNET.

.. code-block:: shell
   :class: copyable

   mc license unregister minio1

Syntax
------
      
The command has the following syntax:

.. code-block:: shell

   mc [GLOBALFLAGS] license unregister ALIAS

Parameters
~~~~~~~~~~

.. mc-cmd:: ALIAS
   :required:

   The :ref:`alias <alias>` of the MinIO deployment.


Global Flags
~~~~~~~~~~~~

.. include:: /includes/common-minio-mc.rst
   :start-after: start-minio-mc-globals
   :end-before: end-minio-mc-globals
