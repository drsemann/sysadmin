## Setando senha root

<code>SET PASSWORD FOR 'root'@'localhost' = PASSWORD('SENHA');</code>

## Trocando senha root

<code>UPDATE mysql.user SET authentication_string = PASSWORD('SENHA') WHERE User = 'root' AND Host = 'localhost';</code>