Getting started
===============

.. contents::
   :local:


Example inventory
-----------------

To set/unset file attributes on host given in
``ypid_service_file_attributes`` Ansible inventory group:

.. code:: ini

    [ypid_service_file_attributes]
    hostname

Example playbook
----------------

Here's an example playbook that can be used to manage file_attributes::

    ---
    - name: Set file attributes, configurable via Ansible’s inventory
      hosts: 'ypid_service_file_attributes'
      become: True

      roles:

        - role: ypid.file_attributes
          tags: [ 'role::file_attributes' ]

Ansible tags
------------

You can use Ansible ``--tags`` or ``--skip-tags`` parameters to limit what
tasks are performed during Ansible run. This can be used after host is first
configured to speed up playbook execution, when you are sure that most of the
configuration has not been changed.

Available role tags:

``role::file_attributes``
  Main role tag, should be used in the playbook to execute all of the role
  tasks as well as role dependencies.
