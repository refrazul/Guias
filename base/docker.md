## Instalar Docker

### Instalación Ubuntu
Primero, actualice su lista de paquetes existente:

Una vez dentro ingresar el comando para cambiar al usuario de aplicación

```bash
sudo apt update
```

Rquerimientos previos

```bash
sudo apt install apt-transport-https ca-certificates curl software-properties-common

```

Cargamos la llave GPG oficial de docker
```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
```

Actualizamos la base 

```bash
sudo apt update
```

Aseguramos que se a instalar Docker de los repos oficiales

```bash
apt-cache policy docker-ce
```

Instalamos Docker

```bash
sudo apt install docker-ce
```

Verificamos que docker este corriendo
```bash
sudo systemctl status docker
```

Si esta corriendo vemos el mensaje

```bash
sudo systemctl status docker
```

```
[sudo] contraseña para refrazul: 
● docker.service - Docker Application Container Engine
   Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2019-11-07 17:28:55 CST; 55min ago
     Docs: https://docs.docker.com
 Main PID: 7284 (dockerd)
    Tasks: 11
   CGroup: /system.slice/docker.service
           └─7284 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
```

### Ejecutando Docker sin sudo

Agregue su nombre de usuario al grupo docker si quiere evitar escribir sudo siempre que deba ejecutar el comando docker:

```bash
sudo usermod -aG docker ${USER}
```

Para aplicar la nueva membresía de grupo, debe cerrar sesión en el servidor y volver a iniciarla, o puede escribir lo siguiente:

```bash
su - ${USER}
```
Se le pedirá que ingrese la contraseña de su usuario para poder continuar.

Confirme que se haya agregado su usuario al grupo de docker escribiendo:

```bash
id -nG
```