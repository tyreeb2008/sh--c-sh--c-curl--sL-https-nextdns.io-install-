# sh--c-sh--c-curl--sL-https-nextdns.io-install-
> nextdns start
> nextdns stop
> nextdns restart
> > nextdns activate
> nextdns deactivate
> > > nextdns log
> > > > nextdns help
> > > > no-resolv
bogus-priv
strict-order
server=2a07:a8c1::
server=45.90.30.0
server=2a07:a8c0::
server=45.90.28.0
add-cpe-id=6d34f2
> > > > round_robin_upstreams: 1
upstream_recursive_servers:
  - address_data: 45.90.28.0
    tls_auth_name: "6d34f2.dns.nextdns.io"
  - address_data: 2a07:a8c0::0
    tls_auth_name: "6d34f2.dns.nextdns.io"
  - address_data: 45.90.30.0
    tls_auth_name: "6d34f2.dns.nextdns.io"
  - address_data: 2a07:a8c1::0
    tls_auth_name: "6d34f2.dns.nextdns.io"
    server:
  forward-zone:
    name: "."
    forward-tls-upstream: yes
    forward-addr: 45.90.28.0#6d34f2.dns.nextdns.io
    forward-addr: 2a07:a8c0::#6d34f2.dns.nextdns.io
    forward-addr: 45.90.30.0#6d34f2.dns.nextdns.io
    forward-addr: 2a07:a8c1::#6d34f2.dns.nextdns.io
    server_names = ['NextDNS-6d34f2']

[static]
  [static.'NextDNS-6d34f2']
  stamp = 'sdns://AgEAAAAAAAAAAAAOZG5zLm5leHRkbnMuaW8HLzZkMzRmMg'
  policy.add(policy.all(policy.TLS_FORWARD({
  {'45.90.28.0', hostname='6d34f2.dns.nextdns.io'},
  {'2a07:a8c0::', hostname='6d34f2.dns.nextdns.io'},
  {'45.90.30.0', hostname='6d34f2.dns.nextdns.io'},
  {'2a07:a8c1::', hostname='6d34f2.dns.nextdns.io'}
})))
