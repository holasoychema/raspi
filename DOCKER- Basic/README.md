Instalación de docker 

1. Instalación de paquetes necesarios
     sudo apt-get install -y \
     apt-transport-https \
     ca-certificates \
     curl \
     gnupg2 \
     software-properties-common \
     vim \
     fail2ban \
     ntfs-3g

2. Instalar firmas del repo de docker
    curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add -
    sudo apt-key fingerprint 0EBFCD88

3. Agregar repositorio de docker
    echo "deb [arch=armhf] https://download.docker.com/linux/debian \
     $(lsb_release -cs) stable" | \
    sudo tee /etc/apt/sources.list.d/docker.list

    -----------
    Si da problemas:
    echo "Package: docker-ce
    Pin: version 18.06.1*
    Pin-Priority: 1000" > /etc/apt/preferences.d/docker-ce

4. Instalar Docker
    sudo apt-get update && sudo apt-get install -y --no-install-recommends docker-ce docker-compose

5. Agregar al usuario al grupo de docker
    sudo usermod -a -G docker <usuario>
    #(logout and login)