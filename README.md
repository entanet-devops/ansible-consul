Consul
=========

Install consul server or agents, based on other consul roles brianshumate.consul and cmacrae.consul (thanks!)

Is intended to be ran as part of a packer build, with a future terraform provisioning step to join servers to clusters.

Consul must be configured to use TLS.

dnsmasq is installed and configured to redirect DNS look ups to consul for consul domain. systemd-resolvd is configured to direct DNS lookups for .consul TLD to dnsmasq.

Only Ubuntu 18.04 is tested.

Role Variables
--------------

Agent config

consul_datacenter: dc1
consul_encrypt: *ENCRYPT-KEY*
consul_join:
  - consul-1.example.net
  - consul-2.example.net
  - consul-3.example.net

consul_copy_services_json: false


Example Playbook
----------------

    - hosts: servers
      roles:
         - entanet-devops.ansible-consul

License
-------

BSD
