check_user
==========

PAM Check_user

## Instruction d'installation sous Centos 6.X

###Pré-requis

Installez les librairies PAM :

``` sh
yum install -y pam-devel
```

Installez les utilitaires de compilation:

``` sh
yum -y install binutils qt gcc make patch libgomp glibc-headers glibc-devel kernel-headers kernel-devel
```

### Récupérez les sources

Installez Git:

``` sh
yum -y install git
```

Clonez le dépôt

``` sh
git clone https://github.com/humboldtux/check_user.git
```

### Compilation

``` sh
cd check_user
gcc -o check_user -lpam -lpam_misc -ldl check_user.c
```

Un binaire check_user a été créé dans le dossier courant. Vous pouvez vérifier qu'il supporte bien PAM:
``` sh
ldd check_user
```

Vous pouvez ensuite copier le binaire dans un dossier de votre $PATH:
``` sh
mv check_user /usr/local/sbin/
```

Puis vérifier que le binaire est bien accessible:
``` sh
which check_user
```
