Solana RPC Haproxy
=========

Role for a sample HAproxy config to place in front of a Solana RPC node. HAproxy handles basic HTTP handling plus 

Requirements
------------

  * Ansible >= 2.8

Role Variables
--------------

  * `haproxy_log_level`: Log level for haproxy
  * `haproxy_certificate_path`: Specify a path to a certificate in case you want HAproxy to respond to SSL certificates. By default a self-signed certificate is installed.
  * `haproxy_lb_maxconn`: Maximum connections that the loadbalancer accepts. Default 3000.
  * `haproxy_rpc_maxconn`: Maximum RPC connections that get forwarded to the Solana RPC software. Default 1000.
  * `haproxy_rpc_maxconn_pubsub`: Maximum pubsub connections that get forwarded to the Solana RPC software. Default 500.
  * `haproxy_major_version`: The major version of haproxy to install. Default 2.2.
  * `haproxy_minor_version`: The minor version of haproxy to install. Default 10.
  * `haproxy_checksum`: Checksum for the haproxy install package (sha256sum).


For more specific configuration, you will want to customise the haproxy.cfg. A good introduction to customising haproxy for API use can be found [here](https://www.haproxy.com/blog/using-haproxy-as-an-api-gateway-part-1/).

Example Playbook
----------------

```
    - hosts: rpc_nodes
      roles:
         - { role: rpcpool.solana_rpc_haproxy }
```

License
-------

MIT

Author Information
------------------

This role was originally developed by [rpcpool](https://rpcpool.com). Patches, suggestions and improvements are always welcome.
