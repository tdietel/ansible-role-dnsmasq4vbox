dnsmasq4vbox
============

Set up dnsmasq to serve a host-only network for VirtualBox.

Requirements
------------

This modules does not configure the VirtualBox host-only network. DHCP
on that network has to be disabled, because dnsmasq will serve DHCP
requests.

Role Variables
--------------

* **dnsmasq_conf_file**: location of the configuration file [default:
/usr/local/etc/dnsmasq.conf] 
* **dnsmasq_interfaces**: list of interfaces to listen on [default: vboxnet0]
* **dnsmasq_dhcp_range**: range of dynamic DHCP addresses [default: 192.168.100.101,192.168.100.150,255.255.255.0,12h]
* **dnsmasq_domain**: domainname for local host names [default: vboxnet]

Dependencies
------------

You must set up and configure VirtualBox.

Example Playbook
----------------

    - hosts: virtualboxhosts
      roles:
         - { role: dnsmasq4vbox, dnsmasq_domain: vbox.example.com }


License
-------

BSD

Author Information
------------------

Tom Dietel <tom@dietel.net>
