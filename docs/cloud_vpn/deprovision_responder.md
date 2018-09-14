# Deprovision responder
The `cloud_vpn/deprovision_responder` function will deprovision a VPN responder
on OpenStack.
It is performed by calling the `cloud_vpn/deprovision_responder` task from the role.
The task will process variables needed for deprovisioning a VM and call OpenStack Heat.

Below is an example to deprovision a VPN responder VM on OpenStack.

```
- hosts: localhost

  tasks:
    - name: Deprovision responder
      include_role:
        name: ansible-network.openstack
        tasks_from: cloud_vpn/deprovision_responder
      vars:
        cloud_vpn_name: myvpn
        cloud_vpn_responder_provisioner: openstack
        cloud_vpn_responder_openstack_cloud: mycloudfromcloudsyaml
```

## Notes
None
