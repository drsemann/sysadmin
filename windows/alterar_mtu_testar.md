# Testando e alterando o mtu no Windows

## Testando o mtu
```# ping hostouip -f -l tamanhomtu ```

## Verificando mtu da interface de rede
```# netsh interface ipv4 show subinterfaces ```

## Alterando mtu da interface de rede
```# netsh interface ipv4 set subinterface “nomedainterface” mtu=tamanhomtu store=persistent```