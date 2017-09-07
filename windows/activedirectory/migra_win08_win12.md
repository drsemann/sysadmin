# Migração Active Directory do 2008 para 2012R2

1. Adicionar servidor no AD.
2. Instalar serviço do AD.
3. Promover o servidor.
4. Consultar FSMO
    
    ```# netdom query fsmo```

5. Executar o comando "adprep.exe /forestprep" aplicativo está na pasta support\adprep no cd de instalação.
6. Testando se o camando adprep anterior atualizou o domino   

    ```# adprep.exe /domainprep```

    ```# adprep.exe /rodcprep```

    ```# adprep.exe /domainprep /gpprep```

7. Transferindo as funções do AD do Windows 2008R2 para o Windows 2012R2
  7.1. No Windows 2008R2 abra o prompt e execute o comando 
    
    ```# ntdsutil ```

  7.1. Abrirá um console, nele execute o comando 
    
    ```# roles```

  - Execute o comando

    ```# connections```
    
  - connect to server "nome do AD novo"
     * q 
     * transfer schema master (Na janela que abrirá clique em SIM)
     * transfer PDC (Na janela que abrirá clique em SIM)
     *  transfer naming master (Na janela que abrirá clique em SIM)
     *  transfer RID master (Na janela que abrirá clique em SIM)
     *  transfer infrastructure master (Na janela que abrirá clique em SIM)
     *  sai do prompt de comando do ntdsutil.
     *  Testando se foram efetuada a transferencia com o comando "netdom query fsmo"

  * Migrar DHCP para servidor Novo
     * No Windows 2008R2 executar "netsh dhcp server export C:\dhcp.txt all".
     * Copiar arquivo dhcp.txt para no novo servidor.
     * No Windows 2012R2 executar o comando "netsh dhcp server import c:\dhcp.txt all".
     * Autorizar o novo servidor para atribuir o DHCP.
     * Desautorizar servidor antigo e para serviço DHCP.


1. Item 1
1. Item 2
1. Item 3
   1. Item 3a
   1. Item 3b