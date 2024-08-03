## Ahsay Backup 

INSTALAÇÃO AHSAYBACKUP

# Baixar diretamente do site Ahsay, arquivo zipado:

```bash
tar -xvzf ahsaybackup9.x.tar
```

# Após instalado configurar a ferramneta como serviço:
```bash
systemctl status cbs

systemctl status cbsnfs
```

Após estar em execução acesse via WebBrowser:

```bash
https://192.168.3.120:8001/cbs/

```

## CHECAGEM DA FERRAMENTA 

```bash
ps -ef|grep java

ps -ef|grep nfs

ps -ef|grep rotatelogs 

systemctl list-unit-files | grep cbs

systemctl status cbsnfs 

netstat -pan|more. 
```

## 1. Após instalar seu sistema operacional da qual irá executar a instalação do AhsayBackup, será necessário pegar algumas informações:

Pegar MAC - 00:50:56:91:34:5d  - 

```bash
ifconfig
```
Será necessário também liberar as seguintes portas para o perfeito funcionamento: 

```bash
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp
sudo ufw allow 8081/tcp
sudo ufw allow 25/tcp
sudo ufw allow 111/tcp
sudo ufw allow 1058/tcp
sudo ufw allow 2049/tcp
sudo ufw enable
sudo ufw status
```
Conforme imagem (description-ports.png) 

## 2. Configurações necessárias após a instalação para o TLS

WikiArticle - https://wiki.ahsay.com/doku.php?id=public:version_9:cbs:9304_how_to_improve_security_of_connection_to_cbs to change the TLS version of the CBS. 

(Será necessário reiniciar o serviço)

## 3. Para ajustar o Java Heap size, basta seguir esta documentação

Recomendação de 4GB

Para CBS: https://wiki.ahsay.com/doku.php?id=public:version_9:cbs:9311_how_to_modify_the_java_heap_size_of_ahsaycbs

Para OBM/ACB: https://wiki.ahsay.com/doku.php?id=public:version_9:client:9404_how_to_modify_the_java_heap_size_of_ahsayobc

Hadware necessário: https://wiki.ahsay.com/doku.php?id=public:version_9:start_here:9000_ahsay_hardware_requirement_list_hrl_for_version_9.1_or_above


