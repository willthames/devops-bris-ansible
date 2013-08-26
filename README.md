About the examples
==================

The examples in this repository use two VMs based on a single vagrant
base box.

I created them using
https://github.com/okfn/ckan/wiki/How-to-Create-a-CentOS-Vagrant-Base-Box

This led to a vagrant box called centos64-64 (CentOS 6.4 for 64bit) 
which I then use in the included Vagrantfile. 

The ansible-hosts file can be used as an inventory for the two virtual box
VMs.

```
ansible -i ansible-hosts -m ping all 
acct | success >> {
    "changed": false, 
    "ping": "pong"
}

shop | success >> {
    "changed": false, 
    "ping": "pong"
}
```

References
----------
* [Vagrant](http://vagrantup.com/)
* [VirtualBox](http://www.virtualbox.org)
