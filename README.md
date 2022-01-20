![logo](https://i.ibb.co/YthtbLh/Giifff-mid.gif)
***
# Banco de Dados MySQL: Raspberry Pi 
Neste guia, iremos criar um banco de dados MySQL no Raspberry Pi.

## Instalando o banco de dados:

Acesse o promt de comando (CMD):

<p align="center">
  <img src="https://i.ibb.co/0Z8btp1/mysql1.png" alt="5"/>
</p>

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

```CMD
sudo apt install php -y
```

Removendo o arquivo "index.html":

```CMD
sudo rm index.html
```
```CMD
sudo nano index.php
```

Escreva alguma mensagem para aparecer na página, aperte CTRL + X, aperte Y e por fim ENTER.

```php
<?php echo "Olá mundo!"; ?>
```

Dê um restart no apache2:

```CMD
sudo service apache2 restart
```

Acesse o IP em seu navegador mais uma vez.

<p align="center">
  <img src="https://i.ibb.co/Q8YgdmS/mysql5.png" alt="5"/>
</p>

Remova o arquivo "index.php":

```CMD
sudo rm index.php
```

Instalando Mariadb:

```CMD
sudo apt install mariadb-server php-mysql -y
```

Dê um restart no apache2:

```CMD
sudo service apache2 restart
```

Configurando mariadb:

```CMD
sudo mysql_secure_installation
```

> Insira a sua senha para o usuário root, aperte ENTER.

> Aperte Y e ENTER para definir a senha do usuário root. Digite a nova senha e aperte ENTER.

> Aperte Y para remover usuários anônimos.
 
> Aperte Y para desabilitar acesso remoto do root.

> Aperte Y para remover o teste.

> Aperte Y para recarregar os privilégios.

Instalando o phpMyAdmin:

```CMD
sudo apt install phpmyadmin -y
```

> Nas configurações escolha "dbconfig-common".

> Selecione Apache2 e aperte ENTER.

> Em configurações do phpmyadmin selecione "OK".

> Em configurações do phpmyadmin com  dbconfig-common selecione "Yes".

> Digite sua senha e selecione "OK".

Habilite o PHP MySQLi:

```CMD
sudo phpenmod mysqli
```

Dê um restart no apache2:

```CMD
sudo service apache2 restart
```

Agora tente acessar (com seu IP) "http://192.168.0.104/phpmyadmin".

<p align="center">
  <img src="https://i.ibb.co/FXTwjtY/mysql6.png" alt="5"/>
</p>

Para corrigir esse erro mova a pasta "phpmyadmin".

```CMD
sudo ln -s /usr/share/phpmyadmin /var/www/html/phpmyadmin
```

Agora tente acessar novamente (com seu IP) "http://192.168.0.104/phpmyadmin".

<p align="center">
  <img src="https://i.ibb.co/SRvY8BH/mysql67png.png" alt="5"/>
</p>

Acesse com o usuário "root" e a senha que você criou anteriormente.

<p align="center">
  <img src="https://i.ibb.co/LgyLkWn/mysql61.png" alt="5"/>
</p>

Pronto! Você criou seu banco de dados.

Somente um último ajuste. Use os seguintes códigos no CMD:

```CMD
ls -lh /var/www/
sudo chown -R pi:www-data /var/www/html/
sudo chmod -R 770 /var/www/html/
```

## Conclusão
Com seu banco de dados criado é possível desenvolver projetos de datalogger.

# Até mais!
