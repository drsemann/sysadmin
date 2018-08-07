# Troubleshooting de conexão vpn IPsec

## Verificar se conexão está ativa

```# show vpn ipsec sa```

```# sudo ipsec statusall```

```# sudo swanctl --log```

## Verificar arquivos de configuração

```# sudo cat /etc/ipsec.conf```

```# sudo cat /etc/ipsec.secrets```

## Verificando conexões de entrada nas portas da VPN

```# sudo tcpdump -i eth0 -n udp dst port 4500 or port 500```

## Adicionando reconecção em caso de queda
```# set vpn ipsec ike-group FOO0 dead-peer-detection action restart```

```# set vpn ipsec ike-group FOO0 dead-peer-detection interval 30```

```# set vpn ipsec ike-group FOO0 dead-peer-detection timeout 60```