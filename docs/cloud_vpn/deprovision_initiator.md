# Deprovision initiator
The `cloud_vpn/deprovision_initiator` function will deprovision a VPN initiator
on OpenStack.
It is performed by calling the `cloud_vpn/deprovision_initiator` task from the role.
The task will process variables needed for deprovisioning a VM and call OpenStack Heat.

Below is an example to deprovision a VPN initiator VM on OpenStack.

```
- hosts: localhost

  tasks:
    - name: Deprovision initiator
      include_role:
        name: ansible-network.openstack
        tasks_from: cloud_vpn/deprovision_initiator
      vars:
        cloud_vpn_name: myvpn
        cloud_vpn_initiator_provisioner: openstack
        cloud_vpn_initiator_openstack_cloud: mycloudfromcloudsyaml
```

## Notes
None
