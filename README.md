check_user
==========

PAM Check_user

## Instruction d'installation sous Centos

###Pré-requis

Installez les librairies PAM :

``` sh
$ sudo yum install -y pam-devel
```

Installez les utilitaires de compilation:

``` sh
$ sudo yum groupinstall -y 'Development Tools'
```

### Récupérez les sources

Installez Git:

``` sh
$ sudo yum -y install git
```

Clonez ce dépôt

``` sh
$ git clone https://github.com/humboldtux/check_user.git
```

### Compilation

``` sh
$ cd check_user
$ gcc -o check_user -lpam -lpam_misc -ldl check_user.c
```

Un binaire *check_user* a été créé dans le dossier courant. Vous pouvez vérifier qu'il supporte bien PAM:
``` sh
$ ldd check_user
```

Vous pouvez ensuite copier le binaire dans un dossier de votre $PATH:
``` sh
$ sudo mv check_user /usr/local/sbin/
```

Puis vérifier que le binaire est bien accessible:
``` sh
$ command -v check_user
```
