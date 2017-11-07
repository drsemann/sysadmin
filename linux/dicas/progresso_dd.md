#### Progresso comando dd ####

``` # sudo apt install pv ```

``` # pv xxxx.img | sudo dd of=/dev/xxxx bs=4MB conv=fsync ```

#### Usando o dcfldd ####

``` # sudo apt install dcfldd ```

``` # dcfldd if=/dev/xxxx of=xxxx.img ```