# Guide to Install Joomla on Debian 8


## Install the dependencies:

```bash
$ sudo apt install apache2 libapache2-mod-php5 php5 php5-curl php5-intl php5-mcrypt php5-mysql php5-sqlite php5-xmlrpc mysql-server mysql-client
```

### Position on ```/var/www/html```:

```bash
$ cd /var/www/html
```

### Create a directory

```bash
$ mkdir joomla
```
### Position 

```bash
$ cd /var/www/html/joomla
```

### Download Joomla:

```bash
$ sudo wget https://downloads.joomla.org/cms/joomla3/3-6-5/joomla_3-6-5-stable-full_package-zip?format=zip
``` 

### Decompress the zip

```bash
$ unzip joomla_3-6-5-stable-full_package-zip?format=zip
``` 

### Delete the zip

```bash
$ rm -r joomla_3-6-5-stable-full_package-zip?format=zip
``` 

### Change owner


```bash
$ chown www-data: -R joomla/
``` 

## Now in mysql


### Create a user to ```Joomla```

Enter the console of mysql

```bash
$ mysql -u root -p
```

Create user:

```sql
$ CREATE USER 'joomlauser'@'localhost' IDENTIFIED BY 'userpassword';
```


### Create database


```sql
$ CREATE DATABASE joomladb;
``` 

On the basis of newly created data, we assign the user:

```sql
$ GRANT ALL PRIVILEGES ON joomladb.* TO 'joomlauser'@'localhost';
``` 
 
Refresh the database:

```sql
$ FLUSH PRIVILEGES;
```

And exit

```sql
$ exit;
```

> Now go to the next path ```https://localhost/joomla``` in your browser and finish the installation


