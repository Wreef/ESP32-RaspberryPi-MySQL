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

<p align="center">
  <img src="https://i.ibb.co/tPXJSHD/mysql1.png" alt="5"/>
</p>

> Esse processo pode demorar.

Após a atualização instale o Apache2:
```CMD
sudo apt install apache2 -y
```

Acesse a seguinte pasta (pelo CMD):
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

<p align="center">
  <img src="https://i.ibb.co/DKjPbFn/mysql3.png" alt="5"/>
</p>

Acesse em seu navegador o IP exibido.

> No meu caso: (http://192.168.0.104)

Você verá a seguinte página:

<p align="center">
  <img src="https://i.ibb.co/1KWSYZF/mysql4.png" alt="5"/>
</p>

Instalação do PHP:

```cmd
sudo apt install php -y
```

Removendo o arquivo "index.html":

```cmd
sudo rm index.html
```
```cmd
sudo nano index.php
```

Escreva alguma mensagem para aparecer na página, aperte CTRL + X, aperte Y e por fim ENTER.

```php
<?php echo "Olá mundo!"; ?>
```

Dê um restart no apache2:

```cmd
sudo service apache2 restart
```

Acesse o IP em seu navegador mais uma vez.

<p align="center">
  <img src="https://i.ibb.co/Q8YgdmS/mysql5.png" alt="5"/>
</p>


