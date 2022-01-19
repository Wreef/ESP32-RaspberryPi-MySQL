![logo](https://i.ibb.co/YthtbLh/Giifff-mid.gif)
***
# Banco de Dados MySQL: Raspberry Pi 
Neste guia, iremos criar um banco de dados MySQL no Raspberry Pi.

## Instalando o banco de dados:

Acesse o promt de comando (CMD):

Atualize a Raspberry Pi:
```CMD
sudo apt update && sudo apt upgrade -y
```
> Esse processo pode demorar.

Após a atualização instale o Apache2:
```CMD
sudo apt install apache2 -y
```

Acesse a seguinte pasta:
```CMD
cd /var/www/html
```

Verifique os arquivo da pasta:
```CMD
ls -al
```

Note que na pasta haverá um arquivo chamado "index.html".

Verifique o IP da sua placa:
```CMD
hostname -I
```

Acesse em seu navegador o IP exibido.

> No meu caso: (http://192.168.1.106)
