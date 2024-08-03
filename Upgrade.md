## Upgrade Ahsay

## 1. No terminal shell, pare o serviço AhsayCBS.
```bash
cd /root/bin
sh shutdown.sh
```

## 2. - Se estiver personalizado, remova a pasta 

```bash
/usr/local/cbs/system/cbs/Installers
```

para limpar os binários antigos do cliente personalizado.

## 3. Pare o serviço NFS.

```bash
cd nfs/bin
sh shutdown.sh
```

## 4. Verifique se o serviço foi encerrado:

```bash
ps -ef | grep java
ps -ef | grep nfs
```

## 5. Renomeie a pasta de instalação existente, por exemplo:

/usr/local/cbs85486 (renomeie a pasta com o número da versão atual anexado; ou seja, v8.5.4.86) para que você tenha uma cópia de rollback em caso de problema de upgrade.
mv /usr/local/cbs /usr/local/cbs85486

## 6. Crie uma nova pasta CBS para substituir a pasta que você renomeou no passo anterior. O nome da pasta deve corresponder, caso contrário, o script do serviço AhsayCBS existente falhará ao iniciar.
```bash
# mkdir /usr/local/cbs
```

## 7. Copie o arquivo de instalação, cbs-nix.tar.gz, para /usr/local/cbs e descompacte-o.

```bash
# cp cbs-nix.tar.gz /usr/local/cbs
# cd /usr/local/cbs
# gunzip cbs-nix.tar.gz
# tar –xf cbs-nix.tar
```

## 8. Se houver espaço disponível, copie a pasta de configuração, a pasta de configurações do sistema, a pasta de logs e a pasta home padrão do usuário da antiga pasta CBS (por exemplo: cbs85486) para o caminho de instalação. (Se faltar espaço, você pode mover em vez de copiar)
Você pode omitir a movimentação da pasta “user” se o caminho da Home do Usuário não for um diretório dentro do caminho de instalação do CBS.
Exemplo:
```bash
# cd /usr/local/cbs/
# cp –rp /usr/local/cbs85486/conf .
# cp –rp /usr/local/cbs85486/system .
# cp –rp /usr/local/cbs85486/logs .
# cp –rp /usr/local/cbs85486/user .
```

## 9. Inicie o serviço AhsayCBS executando os seguintes comandos:
```bash
# cd /usr/local/cbs/bin
# sh startup.sh
```

```bash
cp -rp system/ /root/99160/
cp –rp logs/ /root/99160/
cp -rp logs/ /root/99160/
cp -rp user/ /root/99160/
```