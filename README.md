compile-sysmon
=========

This role is intended to be run against one windows host to compile the sysmon config that is stored in a git repo.

Requirements
------------

This requires that the host have Powershell 5.1. If Git is not present, then it will install Git. This also requires a route to Git so it can download the latest copy of the sysmon config from the repo. Currently using the great work of olafhartong for the git repo.

Role Variables
--------------

Variables that can be set:

    git_exe: Git-2.25.1-64-bit.exe
    git_state: present
    git_install_args: /SILENT /COMPONENTS="icons,ext\reg\shellhere,assoc,assoc_sh"
    git_repo: https://github.com/olafhartong/sysmon-modular.git

Dependencies
------------

NA

Example Playbook
----------------

This example playbook calls both the compile and distribute roles:

     - name: Compile sysmon
       hosts: sysmon_compile
       roles:
         - compile-sysmon

     - name: Install sysmon
       hosts: windows
       roles:
         - sysmon

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
