===================
``mc admin update``
===================

.. default-domain:: minio

.. contents:: Table of Contents
   :local:
   :depth: 1

.. mc:: mc admin update

Description
-----------

.. start-mc-admin-update-desc

The :mc-cmd:`mc admin update` command updates all MinIO servers in the
deployment. The command also supports using a private mirror server for
environments where the deployment does not have public internet access.

.. end-mc-admin-update-desc

.. admonition:: Use ``mc admin`` on MinIO Deployments Only
   :class: note

   .. include:: /includes/facts-mc-admin.rst
      :start-after: start-minio-only
      :end-before: end-minio-only


Considerations
--------------

Updates are Non-Disruptive
~~~~~~~~~~~~~~~~~~~~~~~~~~

:mc-cmd:`mc admin update` updates the binary and restarts all MinIO servers in
the deployment simultaneously. MinIO operations are atomic and strictly
consistent and as such the restart process is non-disruptive to applications.

MinIO strongly recommends only performing simultaneous upgrade-and-restart
procedures. Do not perform "rolling" (e.g one node at a time) upgrade 
procedures.

Examples
--------

Use :mc-cmd:`mc admin update` to update each :mc:`minio` server process in the
MinIO deployment:

.. code-block:: shell
   :class: copyable

   mc admin update ALIAS

Replace :mc-cmd:`ALIAS <mc admin update ALIAS>` with the 
:mc-cmd:`alias <mc alias>` of the MinIO deployment.

Syntax
------

:mc-cmd:`mc admin update` has the following syntax:

.. code-block:: shell
   :class: copyable

   mc admin update ALIAS [MIRROR_URL]

:mc-cmd:`mc admin update` supports the following arguments:

.. mc-cmd:: ALIAS

   The :mc-cmd:`alias <mc alias>` of the MinIO deployment to update. 

   If the specified ``ALIAS`` corresponds to a distributed MinIO
   deployment, :mc-cmd:`mc admin update` updates *all* MinIO servers
   in the deployment at the same time. 

   Use :mc:`mc alias list` to review the configured aliases and their
   corresponding MinIO deployment endpoints.

.. mc-cmd:: MIRROR_URL
   
   The mirror URL of the ``minio`` server binary to use for updating MinIO
   servers in the :mc-cmd:`~mc admin update ALIAS` deployment.

