# Creació de les màquines virtuals

Per a crear una màquina virtual el primer que necessitem és instal·lar un software que ens permeti aplicar la virtualització. Aquest software és el que ens permetrà virtualitzar i gestionar les diferents màquines.

En el mercat hi ha múltiples alternatives de visualització: VirtualBox, VMWare, ... Algunes aplicacions de virtualització són gratuïtes, altres són gratuïtes si s'utilitzen per a certes finalitats mentre que altres són de pagament. En el nostre cas utilitzarem VirtualBox com a aplicació de virtualització.

## Instal·lació software VirtualBox <a id="instal&#xB7;laci&#xF3;-software-virtualbox"></a>

El primer que haurem de fer és la instal·lació del programa VirtualBox en el nostre sistema. Per a fer-ho ens haurem de descarregar el programa de la pàgina oficial.



## Creació de la màquina virtual <a id="creaci&#xF3;-de-la-m&#xE0;quina-virtual"></a>

L'aplicació de virtualització ens permet crear tantes màquines com siguin necessàries: l'única limitació serà en la capacitat d'emmagatzematge que disposem i la capacitat de l'ordinador per executar-les concurrentment: al mateix temps.

La creació de la màquina virtual consisteix en associar alguns dels recursos \(memòria, espai d'emmagatzematge, ...\) de la màquina física \(host\) a la màquina virtual. Per tant, aquests recursos deixen d'estar a disposició de la màquina host.

Nota: cal anar en compte quan s'assigna sobretot la memòria RAM a la màquina virtual de deixar un marge de memòria suficient per a la màquina física, en cas contrari la màquina virtual i la màquina física tindràn un rendiment molt baix. Val més assignar menys memòria a la màquina virtual i deixar més memòria per a la màquina física.

## Instal·lació sistema operatiu <a id="instal&#xB7;laci&#xF3;-sistema-operatiu"></a>

Ja disposem d'una màquina amb unes determinades característiques tècniques: memòria, processador,... Cal instal·lar el sistema operatiu per tal que aquesta màquina pugui funcionar. El primer que haurem de fer és decidir quin sistema operatiu i versió volem instal·lar. En el nostre cas instal·larem el sistema operatiu Linux Debian versió 9 en una màquina i Windows 7 en una altra màquina.

### Obtenir el CD <a id="obtenir-el-cd"></a>

El software del sistema operatiu Debian ens el podem descarregar d'Internet. Per a descarregar el programa de sistema operatiu accedim a l'adreça [https://www.debian.org/CD/http-ftp/\#stable](https://www.debian.org/CD/http-ftp/#stable) i fem la descarrega segons el processador de la nostra màquina física.



#### Fitxers ISO <a id="fitxers-iso"></a>

Un fitxer ISO és una imatge d'un CD o DVD. El fitxer que ens descarreguem conté tots els fitxers "comprimits" necessaris per a instal·lar el sistema operatiu en la màquina virtual.

#### Insertar el CD <a id="insertar-el-cd"></a>

Amb el fitxer ISO descarregat podem insertar el nostre CD a la nostra màquina virtual. Aquesta operació consisteix en associar al lector de CDs de la nostra màquina virtual el fitxer ISO descarregat.

