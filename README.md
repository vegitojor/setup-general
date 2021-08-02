##### SO -> Debian. Ubuntu. derivados

### SETING DEL .bashrc
~~~
#Configuracion de la terminal
parse_git_branch() {
     git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/'
}
PS1='\[\e[0;32m\]Vegitojor\$\W -> $(parse_git_branch) \[\e[1;37m\]'
~~~


### LAMP (linux, apache, php, mysql)
fuente: https://platzi.com/tutoriales/1154-wordpress/1634-instalar-lamp-stack-en-linux-ubuntu-1404/

fuente: https://askubuntu.com/questions/772397/mbstring-is-missing-for-phpmyadmin-in-ubuntu-16-04

`sudo apt-get install apache2 `


`sudo add-apt-repository ppa:ondrej/php `

`sudo apt-get update `

`sudo apt-get install php7.0 `

`sudo apt-get install mysql-server php7.0-mysql php7.0-mcrypt`

`sudo apt install php7.0-xmlrpc php7.0-cli php7.0-dev php7.0-common php7.0-json php7.0-mbstring php7.0-xml php7.0-curl php7.0-xsl php7.0-zip php7.0-pgsql php7.0-mcrypt libapache2-mod-php7.0 php7.0-mysql `


`sudo phpenmod mcrypt`

`sudo phpenmod mbstring`

`sudo apt-get install phpmyadmin`

`sudo systemctl restart apache2`

info (para listar los paquetes de php 7.0):

`apt-cache pkgnames | grep php7.0`


Para dar parmisos a phpMy-admin:

`sudo gedit /etc/apache2/apache2.conf`

agregar 
~~~
Include /etc/phpmyadmin/apache.conf
~~~

`sudo service apache2 restart`




# Programas requeridos

### **SDKMAN**
fuente: https://sdkman.io/install

`curl -s "https://get.sdkman.io" | bash` 

Instalar Java (desde sdkman)

`sdk list java`

`sdk install java <version de java elegida>`


### **Gradle**
fuente: https://gradle.org/install/

`sdk install gradle 5.6.4`

si falla:

`sudo rm -r .gradle`

### **Redis**
fuente: 

`sudo apt install redis-server`


# Programas necesarios (opcional)

### **Intellij Idea**
fuente: https://www.jetbrains.com/idea/download/?gclid=Cj0KCQjw3Nv3BRC8ARIsAPh8hgIcIrO9FnHJu-yd_p0sI5afb1pj8tHb3eirTRiEgtmGvs5_DPtbMKQaAuq2EALw_wcB#section=linux
              
`sudo snap install intellij-idea-community --classic`   
    
### **DBeaver**
fuente: https://dbeaver.io/download/

Descargar pakage .deb y ejecutar con:

`sudo dpkg -i xxxxxxxx.deb`

### **sublime text** 
fuente: https://www.sublimetext.com/docs/3/linux_repositories.html
https://easycloudsupport.zendesk.com/hc/en-us/articles/360006586972-Install-Sublime-Text-3-in-Ubuntu-16-04-Higher-The-Official-Way

`wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add -`

`sudo apt-get install apt-transport-https`

`echo "deb https://download.sublimetext.com/ apt/stable/" | sudo tee /etc/apt/sources.list.d/sublime-text.list`

`sudo apt-get update`

`sudo apt-get install sublime-text`

### **VS Code**
fuente: https://code.visualstudio.com/docs/?dv=linux64_deb

Descargar pakage .deb y ejecutar con:

`sudo dpkg -i xxxxxxxx.deb`

### **Zomm**
fuente: https://zoom.us/download?os=linux

### Postman
fuente: https://medium.com/@canoodle/adding-icon-launcher-for-postman-native-app-in-ubuntu-a48a3917c786

descargar de: https://www.postman.com/downloads/

descomprimir en  `/home/[ user  ]`

`cd `

`sudo gedit .local/share/applications/postman.desktop`

 agregar:
~~~
[Desktop Entry]
Encoding=UTF-8
Version=1.0
Type=Application
Name=Postman
Icon=/home/[  your username  ]/Postman/app/resources/app/assets/icon.png
Path=/home/[  your username  ]/Postman
Exec=/home/[  your username  ]/Postman/Postman
StartupNotify=false
StartupWMClass=Postman
OnlyShowIn=Unity;GNOME;
X-UnityGenerated=true
~~~


guardar
 

# Entorno Trabajo
##### repositorio inicial
https://github.com/redbeestudios/vigilant-guide/#docker


# Elementary OS

fusuma - para gestos del panel tactil
wingpanel - para barra superior
por problemas de bluetooth (respuesta 2) https://unix.stackexchange.com/questions/258074/error-when-trying-to-connect-to-bluetooth-speaker-org-bluez-error-failed

~~~
sudo bluetoothctl
[bluetooth]# power off
[bluetooth]# power on
[bluetooth]# scan on
(Cuando aparesca la direccion mack)
[bluetooth]# scan off
[bluetooth]# connect XX:XX:XX:XX:XX:XX (your bluetooth address)
[Arc Touch Mouse SE]# trust XX:XX:XX:XX:XX:XX 
[Arc Touch Mouse SE]# pair XX:XX:XX:XX:XX:XX 
[bluetooth]# quit


sudo bluetoothctl
[bluetooth]# power on
[bluetooth]# agent on
[bluetooth]# default-agent
[bluetooth]# scan on
[NEW] Device XX:XX:XX:XX:XX:XX David's AirPods
[bluetooth]# scan off
[bluetooth]# trust XX:XX:XX:XX:XX:XX
[bluetooth]# pair XX:XX:XX:XX:XX:XX
Attempting to pair with XX:XX:XX:XX:XX:XX
[CHG] Device XX:XX:XX:XX:XX:XX Connected: yes
[CHG] Device XX:XX:XX:XX:XX:XX UUIDs: ... 
[CHG] Device XX:XX:XX:XX:XX:XX UUIDs: ... 
[CHG] Device XX:XX:XX:XX:XX:XX UUIDs: ... 
[CHG] Device XX:XX:XX:XX:XX:XX UUIDs: ... 
[CHG] Device XX:XX:XX:XX:XX:XX UUIDs: ... 
[CHG] Device XX:XX:XX:XX:XX:XX UUIDs: ... 
[CHG] Device XX:XX:XX:XX:XX:XX UUIDs: ... 
[CHG] Device XX:XX:XX:XX:XX:XX UUIDs: ... 
[CHG] Device XX:XX:XX:XX:XX:XX Paired: yes
Pairing successful
[CHG] Device XX:XX:XX:XX:XX:XX Connected: no
[bluetooth]# connect XX:XX:XX:XX:XX:XX
Attempting to connect to XX:XX:XX:XX:XX:XX
[CHG] Device XX:XX:XX:XX:XX:XX Connected: yes
Connection successful
[bluetooth]# quit


~~~
