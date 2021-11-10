## Remover erro no log do Squid "error:transaction-end-before-headers"

Adicionar no arquivo do squid a acl:

```acl hasRequest has request```

Adicionar ao final de seu log:

```access_log daemon:/var/log/squid/access.log squid hasRequest```

Reinicializar o squid

```# systemctl restart squid```
