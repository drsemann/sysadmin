### Verificar login falho postfix ###

#### Ver erro de senha pop3 e exibe IP ####
```# cat /var/log/maillog |grep "LOGIN FAILED"```

#### Ver erro SMTP ####
```# cat /var/log/messages |grep "PAM auth error"```
```# cat /var/log/messages |grep "IP"```
```# cat /var/log/messages |grep "itj-alexandre"```
