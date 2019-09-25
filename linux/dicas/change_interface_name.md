### Alterar nome da interface para formato antigo ###

#### Editar o arquivo do grub ###
`# nano /etc/default/grub`

#### Adicionar em GRUB_CMDLINE_LINUX ####
` GRUB_CMDLINE_LINUX="net.ifnames=0 biosdevname=0"`

#### Atualizar grub ####
`# grub-mkconfig -o /boot/grub/grub.cfg`