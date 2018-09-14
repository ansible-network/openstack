# Provision initiator
The `cloud_vpn/provision_initiator` function will provision a VPN initiator
on OpenStack.
It is performed by calling the `cloud_vpn/provision_initiator` task from the role.
The task will process variables needed for provisioning a VM and call OpenStack Heat.

Below is an example to provision a VM that will be the initiator of the VPN on OpenStack.

```
- hosts: localhost

  tasks:
    - name: Provision initiator
      include_role:
        name: ansible-network.openstack
        tasks_from: cloud_vpn/provision_initiator
      vars:
        cloud_vpn_name: myvpn
        cloud_vpn_initiator_provision: openstack
        cloud_vpn_initiator_vpc_cidr: 10.0.0.0/24
        cloud_vpn_initiator_private_ip: 10.0.0.10
        cloud_vpn_initiator_key_name: mykey
        cloud_vpn_initiator_instance_size: m1.small
        cloud_vpn_initiator_image_id: vyos
        cloud_vpn_initiator_openstack_cloud: mycloudfromcloudsyaml
        cloud_vpn_initiator_openstack_external_network: ext-net
```

## Notes
None
