Installing Vumi with VirtualBox and Vagrant
===========================================

The easiest way to get Vumi up & running is by using VirtualBox_ and Vagrant_:

    1. Install VirtualBox_
    2. Install Vagrant_, make sure you follow the `OS specific instructions`_.
    3. Clone Vumi with `git clone https://github.com/praekelt/vumi.git`
    4. Execute `cd vumi`
    5. Datawinner configuration
        1. Clone datawinner vumi scripts with `git://github.com/mangroveorg/vumiscripts.git` in some other directory
        2. copy vumiscripts/vumi.pp to vumi/puppet/manifests/vumi.pp
        3. copy vumiscripts/supervisord.datawinner.conf to vumi/supervisord.datawinner.conf
        4. copy datawinner_airtel_mad_1_smpp.yaml and datawinner_airtel_mad_2_smpp.yaml to vumi/config directory
    6. Execute `vagrant up`, this will take some time to complete as it
        1. Downloads a 480MB Ubuntu 10.04 server VM
        2. Downloads ~ 40MB worth of Python packages
        3. Downloads ~ 100MB worth of packages with `apt-get`
    7. Go to http://localhost:7000/admin and log in with username `vumi` and password `vumi` for the Django based webapp.
    8. Go to http://localhost:7010 for the Supervisord web based management
    9. Go to http://localhost:7011 for the SMSC simulator console.

.. note::
    Ubuntu 10.04 only provides version 1.3.5 of RubyGems while Vagrant requires version 1.3.6. You'll need to get an upstream version or install from source as per the `OS specific instructions`_.

.. note::
    Ubuntu doesn't put `vagrant` on your $PATH, you'll need to manually symlink it with `sudo ln -s /var/lib/gems/1.8/bin/vagrant /usr/bin/`


.. _Vagrant: http://www.vagrantup.com
.. _VirtualBox: http://www.virtualbox.org
.. _OS specific instructions: http://vagrantup.com/docs/getting-started/index.html
