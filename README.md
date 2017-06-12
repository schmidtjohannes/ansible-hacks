# ansible-hacks
bunch of ansible hacks I found useful when I started learning ansible
## extract ports
To extract to ansible_port of another group first you have to get the list of the group by using
    {{ groups['clients'] }}
Then you use the item name to lookup the whole host-configuration in the hostvars - dictionary. All attributes are present in json format.
To get the port you use
    hostvars[item].ansible_port
That means although you are in a different host-list of your playbook you can easily access

## skip task by flag
I needed a possiblity to controll the configuration and restart of a firewall on centos 7
so I check if a certain flag is defined in the variable list of a host, in this case skip_client_firewall
