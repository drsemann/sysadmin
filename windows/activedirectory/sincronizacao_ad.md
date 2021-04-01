# Comandos para verificar e forçar sincronização do AD

## Verificar sincronização

```# repadmin /showrepl```

```# dcdiag /test:replications```

## Forçar a sincronização do AD (Dever ser executado no AD que está com os registros antigos)

```# repadmin /syncall /APeD```