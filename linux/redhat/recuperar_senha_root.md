## Recuperar senha root RH8


### Adcionar o seguinte no final da linha

``` 
rd.break console=tty1
```

### Montar / como rw

```
mount -o remount,rw /sysroot
chroot /sysroot
passwd
touch /.autorelabel
```