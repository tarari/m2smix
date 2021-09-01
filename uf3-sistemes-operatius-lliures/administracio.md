# Administració

L’administració del sistema consisteix a dur a terme tasques de **manteniment i configuració** perquè el sistema funcioni de manera fiable. Bàsicament, el que es busca és garantir que el temps d’activitat, el rendiment, els recursos i la seguretat de l’equip satisfacin les necessitats de l’usuari o els usuaris del sistema.

Entre les **tasques més habituals** d’administració del sistema hi ha:

* La gestió dels usuaris i els grups.
* La gestió del sistema d’arxius.
* La gestió dels processos.
* La gestió de la memòria.
* La gestió dels dispositius d’emmagatzematge.
* L’optimització del rendiment.
* La supervisió dels registres del sistema.
* L’automatització de tasques rutinàries com les còpies de seguretat, etc.

### Creació i gestió d'usuaris i grups

Els sistemes GNU/Linux són sistemes operatius **multiusuari**, és a dir, sistemes on molts usuaris poden estar treballant al mateix temps, normalment connectats a través d’una xarxa d’ordinadors. Perquè un usuari pugui utilitzar el sistema operatiu ha de tenir un compte d’usuari. Aquests comptes d’usuari són estructures de dades que s’utilitzen per identificar un usuari concret en un sistema informàtic. Cada persona que utilitza el sistema informàtic ha de tenir un compte d’usuari diferent, ja que això li permetrà mantenir els seus arxius al seu directori de treball i tenir la seva pròpia configuració.

Un **compte d’usuari** permet a un usuari iniciar sessió en un sistema informàtic. El compte d’usuari determina a quins arxius i directoris podrà accedir i les seves preferències personals.

Els usuaris es poden agrupar en grups, de manera que un usuari pot pertànyer a tants grups d’usuaris com sigui necessari per satisfer les necessitats de funcionament del sistema.

Als sistemes Linux hi ha tres tipus de comptes d’usuari: el compte de l’usuari root, els comptes estàndards o locals i els comptes de sistema o associats a serveis.

* **Compte de l’usuari root**. Aquest és el compte de l’usuari administrador del sistema operatiu. Aquest compte es crea de forma automàtica durant la instal·lació del sistema operatiu i té accés a tots els arxius i aplicacions del sistema operatiu. Està destinat a l’administració del sistema i només l’hem d’utilitzar amb aquesta finalitat. Aquest compte no es pot eliminar però sí desactivar. Depenent de la política de seguretat del sistema operatiu aquest compte d’usuari estarà desactivat per defecte, com passa amb els sistemes operatius Ubuntu i les seves derivacions. En altres distribucions, com Debian, aquest usuari està totalment operatiu.
* **Comptes d’usuaris estàndard**. Aquest és el tipus de compte que utilitzen els usuaris que fan servir el sistema operatiu. Durant la instal·lació, el sistema operatiu demana les dades a l’usuari per crear un compte d’usuari estàndard. Després de la instal·lació podem crear més comptes d’usuaris estàndard si els necessitem.
* **Comptes de sistema**. Aquest tipus de comptes no poden iniciar sessió al sistema operatiu però algunes aplicacions que s’executen al sistema operatiu necessiten aquests comptes per poder funcionar correctament. Aquests comptes es creen automàticament quan instal·lem aquestes aplicacions.

Identificador d'usuari i grup

Els sistemes operatius GNU/Linux defineixen els usuaris i els grups d’usuaris amb números anomenats _**identificador d’usuari**_ **\(UID\)** i _**identificador de grup**_ **\(GID\)** respectivament. Els primers cent números d’identificadors d’usuaris i grups es reserven per a l’ús del sistema. El més important és el 0, que es correspon amb l’usuari i grup de root. Normalment, a partir del 1000, els identificadors d’usuari i grup es troben disponibles per als usuaris i grups personals. Quan creem nous comptes d’usuari, el sistema els assignarà com a identificador d’usuari i grup el següent número més alt sense utilitzar.

#### Utilització de les ordre 'su' i 'sudo'

Només el compte d’usuari root té accés a tots els arxius i aplicacions del sistema operatiu, és a dir que posseeix tots els privilegis i permisos per fer operacions al sistema operatiu. Quan utilitzem aquest compte d’usuari hem de tenir els coneixements adequats sobre les operacions que estem realitzant ja que un error podria deixar inservible el sistema operatiu.

L’usuari **root** és aquell que té tots els permisos en un sistema operatiu. Pot accedir a qualsevol arxiu i executar qualsevol ordre. Aquest usuari no té el seu directori personal dins del directori _/home_ sinó que normalment el té en un directori separat que penja directament de l’arrel i s’anomena _/root_.

No hem d’acostumar-nos a utilitzar aquest compte d’usuari de forma permanent ja que, si sempre tenim privilegis administratius, podem canviar accidentalment algun fitxer o executar una aplicació que canviï part del sistema operatiu i fer que el sistema operatiu deixi de funcionar. Si adquirim els privilegis administratius només quan són necessaris, reduirem el risc de cometre aquests errors.

Quan treballem al **mode ordre**, les ordres `sudo` i `su` ens permetran utilitzar el compte d’usuari root i els seus privilegis.

Per accedir al sistema operatiu amb el compte d’usuari root podem utilitzar l’ordre **`su`**. L’ordre `su` permet utilitzar l’intèrpret d’ordres d’un altre usuari sense tancar la sessió. Si no indiquem cap usuari o utilitzem el símbol “-”, estem indicant que volem treballar al sistema utilitzant el compte d’usuari root. Un cop acabem de treballar amb aquest compte d’usuari podem tancar la sessió utilitzant l’ordre `exit` o `logout`.

L’ordre **`sudo`**, de l’anglès _super user do_, és una utilitat que permet als usuaris executar ordres amb els privilegis administratius d’un altre usuari sota certes restriccions en la delegació de privilegis. Aquestes restriccions es troben a l’arxiu _/etc/sudoers_, i és on es defineix quins usuaris poden executar quines ordres i amb quins permisos. Si volem obtenir els privilegis administratius de l’usuari root cal que utilitzem l’ordre sense especificar cap nom d’usuari seguida del nom de l’ordre que volem executar.

A la [figura.1](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig1) i [figura.2](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig2) podeu observar les ordres per instal·lar un paquet anomenat _sl_ fent servir `su` i `sudo` respectivament. Podeu observar que quan utilitzem l’ordre `sudo`, només s’executa l’ordre indicada amb els privilegis de l’usuari root sense que es faci un canvi d’usuari, com passa amb l’ordre `su`.FiguraUtilització de l’ordre ‘su’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/su.png)FiguraUtilització de l’ordre ‘sudo’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/su2.png)

Quan treballem al **mode gràfic**, si una operació necessita privilegis administratius, el sistema ens demanarà la nostra contrasenya per assignar-nos els privilegis. Un cop acabem l’operació, el sistema operatiu ens retirarà els privilegis administratius.

#### Gestió d'usuaris a Ubuntu 20.04

La gestió d’usuaris consisteix a dur a terme la creació, modificació o esborrat dels comptes d’usuari del sistema. Com gairebé totes les tasques de gestió del sistema, la gestió dels usuaris es pot fer des del mode gràfic utilitzant aplicacions específiques per a aquestes tasques, o bé des del mode d’ordres del sistema.

Al sistema operatiu Ubuntu 20.04, es pot fer la gestió dels comptes d’usuari del sistema des del **mode gràfic** obrint la vista general d’_Activitats_ i cercant _Usuaris_. A la finestra de configuració que apareix, el primer que cal fer és prémer el botó _Desbloqueja_ a l’extrem superior dret i escriure la nostra contrasenya per obtenir privilegis d’administrador. A partir d’aquí ja podem fer les tasques de gestió d’usuaris.

Per afegir un nou compte d’usuari hem de prémer el botó _Afegeix usuari_. Si volem que el nou usuari tingui privilegis d’administrador cal que seleccionem _Administrador_ al tipus de compte. Cal que introduïm el nom complet de l’usuari, el nom del compte d’usuari i la contrasenya, tot i que podem seleccionar l’opció _Permet a l’usuari establir la contrasenya a l’entrada següent_ perquè el mateix usuari pugui configurar la seva contrasenya al primer inici de sessió. Podeu observar la finestra de creació d’usuaris a la [figura.3](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig3).FiguraCreació d’un usuari![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/crearusuari.png)

En aquesta finestra d’_Usuaris_ podem modificar els paràmetres dels comptes d’usuari creats en qualsevol moment. Si seleccionem l’opció _Entrada automàtica_ en un usuari, permetrem que es connecti automàticament quan iniciem l’equip informàtic, és a dir, no caldrà introduir una contrasenya per iniciar la sessió al compte. Ara bé, per seguretat, és preferible que tots els usuaris tinguin contrasenya i no és aconsellable activar aquesta opció.

Per eliminar un usuari, hem de prémer el botó _Suprimeix l’usuari_ que trobem a la part dreta de la finestra d’_Usuaris_. Cada usuari té el seu directori de treball personal i una configuració pròpia. Podem triar mantenir o eliminar aquests documents i configuració si estem segurs que ja no són necessaris i volem alliberar espai al disc dur. Per fer-ho seleccionem l’opció _Suprimeix els fitxers_ al quadre de diàleg que apareix quan eliminem un usuari. Aquests arxius s’eliminen de forma permanent i no es podran recuperar. Si els volem conservar, seleccionem l’opció _Conserva els fitxers_.

Al **mode ordre**, els usuaris es poden afegir utilitzant l’ordre `useradd`. La seva sintaxi és:

* `useradd [opcions] compte_usuari`

En la seva forma més simple podem utilitzar l’ordre `useardd nom_usuari`, on nom\_usuari és el nom de l’usuari que volem crear. En aquesta ordre les opcions principals que trobem són:

* **-d**. Aquesta opció permet crear el directori _home_ de l’usuari. El valor per defecte si no especifiquem res és /home/nom\_usuari.
* **-g**. Aquesta opció defineix el grup per defecte.
* **-G**. Aquesta opció defineix els noms o els GID dels grup als que pertany l’usuari.
* **-u**. Aquesta opció defineix el valor de l’identificador d’usuari.
* **-s**. Aquesta opció defineix el terminal per defecte. De forma predeterminada a la majoria de sistemes és _bash_.

L’ordre `useradd` permet definir una contrasenya amb l’opció _-p_ però cal que aquesta contrasenya estigui encriptada. Per tant, és més fàcil crear un usuari amb l’ordre `useradd` sense contrasenya i definir la contrasenya després amb l’ordre `passwd` que té la següent sintaxi:

* `passwd [opcions] [compte_usuari]`

Aquesta ordre no només permet assignar una contrasenya a un usuari, també permet gestionar la validesa de la contrasenya. Algunes de les seves opcions són:

* **-l**. Permet desactivar comptes d’usuari de forma temporal.
* **-x**. Determina el termini màxim vàlid d’una contrasenya.
* **-e**. Fa que la contrasenya caduqui quan l’usuari inicia sessió, obligant-lo a canviar-la.
* **-S**. Mostra la configuració de la contrasenya d’un usuari en concret.

Si un cop creat un compte d’usuari volem modificar-lo, podem utilitzar l’odre `usermod`. La sintaxi d’aquesta ordre és:

* `usermod [opcions] compte_usuari`

Algunes de les opcions que podem utilitzar són:

* **-c**. Permet especificar dades personals de l’usuari.
* **-d**. Assigna un nou directori personal a l’usuari.
* **-g**. Canvia el grup de l’usuari.

Finalment, per eliminar un compte podem utilitzar l’ordre `userdel`, que elimina l’usuari del sistema. Aquesta ordre té la següent sintaxi:

* `userdel [opcions] [compte_usuari]`

En aquesta ordre les opcions principals que trobem són:

* **-r, –remove**. Aquesta opció elimina el directori _/home_ de l’usuari i tots els arxius que conté.
* **-f, –force**. Aquesta opció força l’eliminació del compte encara que l’usuari estigui dins del sistema.

Els arxius de configuració d’usuaris _/etc/passwd_ i _/etc/shadow_ proporcionen informació sobre els comptes d’usuari. Els dos fitxers estan formats per un conjunt de línies, en què cada línia es refereix a un compte d’usuari. Cada línia està formada per un conjunt de camps delimitats per dos punts \(:\) com podeu observar a la [figura.4](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig4) i [figura.5](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig5), respectivament.FiguraArxiu '/etc/passwd’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/etcpasswd.jpg)FiguraArxiu '/etc/shadow’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/etcshadow.jpg)

El significat de cada camp a l’arxiu _/etc/passwd_ és:

* **Nom d’usuari**. El primer camp de cada línia és el nom del compte d’usuari.
* **Contrasenya**. El segon camp es reserva per la contrasenya. A la majoria de distribucions en aquest camp es mostra una “x”, que indica que la contrasenya està oculta i s’emmagatzema a l’arxiu _/etc/shadow_. Si ens trobem en una distribució on no s’utilitzen contrasenyes ocultes, en aquest camp podrem observar la contrasenya encriptada.
* **UID**. Al tercer camp trobem l’identificador de l’usuari.
* **GID per defecte**. Al quart camp trobem l’identificador del grup per defecte.
* **Informació**. Segons la distribució podem trobar en aquest camp diferent informació de l’usuari, com el nom complet, número de telèfon, etc.
* **Directori personal**. Al sisè camp trobem la ruta al directori _/home_ de l’usuari.
* **Terminal per defecte**. A l’últim camp trobem el terminal que utilitza l’usuari per defecte.

Tal com passa amb l’arxiu _/etc/passwd_, els camps de les línies de l’arxiu _/etc/shadow_ també tenen un significat determinat:

* **Nom d’usuari**. El primer camp és el nom de l’usuari.
* **Contrasenya**. La contrasenya s’emmagatzema de forma encriptada. Un asterisc \(\*\) o un signe d’admiració \(!\) indica que el compte està bloquejat perquè no té contrasenya.
* **Últim canvi de contrasenya**. El tercer camp indica la data de l’últim canvi de contrasenya. Aquesta data s’emmagatzema en dies des de l’1 de gener de 1970.
* **Dies fins a permetre un canvi**. Aquest camp indica el nombre de dies que han de passar perquè es pugui canviar la contrasenya.
* **Dies fins a demanar un canvi**. Aquest camp indica el nombre de dies que passaran des de l’últim canvi de contrasenya fins que el sistema ens demani un nou canvi de contrasenya.
* **Dies d’avís previs a l’expiració de la contrasenya**. Aquest camp indica quants dies abans de l’expiració de la contrasenya el sistema avisarà l’usuari.
* **Dies entre l’expiració i la desactivació**. Aquest camp indica els dies que poden passar entre l’expiració d’un compte d’usuari i la seva desactivació.
* **Data d’expiració**. Aquest camp mostra la data d’expiració del compte. La data s’expressa com el nombre de dies que han passat des de l’1 de gener de 1970.
* **Indicador especial**. Aquest és un camp reservat que actualment no s’utilitza.

Si als camps relacionats amb el recompte de dies trobem un valor de -1 o 99999 significa que la funcionalitat en qüestió es troba desactivada.

#### Gestió de grups a Ubuntu 20.04

Els usuaris s’acostumen a organitzar en grups d’usuaris. Un usuari pot pertànyer a tots els grups necessaris i adquirirà els privilegis de tots ells. Als sistemes GNU/Linux, tots els usuaris han de pertànyer a un grup dins del sistema operatiu com a mínim, per això durant el procés de creació d’un compte d’usuari també se li assigna un grup per defecte amb el mateix nom.

La pertinença als grups es controla amb l’arxiu _/etc/group_. Aquest arxiu conté una llista amb tots els grups del sistema operatiu i els usuaris que pertanyen a cadascun d’ells.

L’arxiu _/etc/group_ està format per un conjunt de línies encapçalades pel nom del grup, com podeu observar a la [figura.6](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig6).FiguraArxiu '/etc/group’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/etcgroup.jpg)

Cada camp està separat dels altres per dos punts \(:\). El significat de cada camp és el següent:

* **Nom del grup**. El primer camp indica el nom del grup.
* **Contrasenya**. El segon camp indica la contrasenya del grup. Si la distribució oculta la contrasenya en aquest camp podem observar una “x”; si no veurem la contrasenya encriptada. Els sistemes amb contrasenyes ocultes utilitzen l’arxiu _/etc/gshadow_, per emmagatzemar la informació de les contrasenyes ocultes dels grups.
* **GID**. Aquest camp indica l’identificador del grup.
* **Llista d’usuaris**. L’últim camp és una llista separada per comes que conté els membres del grup.

Si volem gestionar els grups utilitzant el **mode gràfic** cal instal·lar una aplicació específica per al treball amb usuaris i grups ja que l’eina _Usuaris_ no permet la gestió dels grups.

Al **mode ordre**, per afegir un nou grup utilitzem l’ordre `groupadd`. La seva sintaxi és la següent:

* `groupadd [opcions] nom_grup`

En aquesta ordre la principal opció que trobem és “-g” ja que normalment creem els grups sense especificar opcions:

* **-g**. Aquesta opció indica l’identificador que volem utilitzar per al grup. Si no utilitzem aquesta opció, el sistema assigna el primer GID disponible.

Per modificar els paràmetres d’un grup existent podem utilitzar l’ordre `groupmod`. La seva sintaxi és la següent:

* `groupmod [opcions] nom_grup`

En aquesta ordre les opcions principals que trobem són:

* **-g**. Aquesta opció permet especificar l’identificador de grup.
* **-n**. Aquesta opció permet especificar un nou nom de grup.

Si volem afegir un usuari a un grup utilitzem l’ordre `gpasswd`. Aquesta ordre també permet modificar altres característiques dels grups i assignar-los administradors. Els administradors són usuaris que poden realitzar algunes funcions administratives als grups, com afegir, eliminar membres i canviar la contrasenya del grup. La sintaxi bàsica d’aquesta ordre és:

* `gpasswd [opcions] nom_grup`

En aquesta ordre les opcions principals que trobem són:

* **-a usuari**. Aquesta opció permet afegir l’usuari especificat al grup especificat.
* **-d usuari**. Aquesta opció permet eliminar l’usuari especificat del grup especificat.

Si utilitzem aquesta ordre sense cap opció, `gpasswd` canvia la contrasenya del grup. La contrasenya del grup permet controlar de forma temporal qui n’és membre.

Si volem eliminar un grup podem utilitzar l’ordre `groupdel`. La seva sintaxi és la següent:

* `groupdel nom_grup`

Tot i que aquesta ordre té algunes opcions, s’acostuma a utilitzar sense cap d’elles.

Altres ordres molt utilitzades per a la gestió d’usuaris i grups d’usuaris són les següents:

* `whoami`. Indica quin és el nom del nostre compte d’usuari.
* `groups`. Mostra en quin grups l’usuari està actiu o qualsevol usuari si indiquem el nom de l’usuari després de l’ordre.
* `id`. Mostra l’UID i els grups als quals pertany l’usuari amb els seus GID.
* `login`. Permet canviar d’usuari.
* `whoami`. Indica quin és el nom del nostre compte d’usuari.
* `who`. Llista els usuaris que hi ha al sistema.
* `chage`. Canvia la caducitat de la contrasenya de l’usuari.
* `chsh`. Canvia la terminal de l’usuari.
* `chfn`. Permet editar les dades personals de l’usuari.

#### Gestió de perfils

Quan un usuari inicia sessió a un sistema informàtic, el sistema operatiu executa una sèrie de tasques per inicialitzar i configurar un entorn de treball personalitzat.

Quan es crea un usuari als sistemes GNU/Linux se li ha d’assignar un directori de connexió. Aquest directori de connexió conegut com a directori d’inici o també **directori** _**home**_ \(de l’anglès _home directory_\) conté els arxius i directoris personals de l’usuari. Per facilitar un comportament homogeni de tots els usuaris, podem definir les opcions comunes que tindran els usuaris creats a un sistema determinat amb l’ús del directori _/etc/skel_. Aquest directori conté l’estructura mínima que tindran tots els directoris de connexió de tots els usuaris creats al sistema.

_Skel_ és una abreviatura d’esquelet \(_skeleton_ en anglès\)

En el moment en què creem un nou usuari amb l’ordre `useradd`, es crearà el seu directori d’inici. Tot el contingut, tant arxius com carpetes, del directori _/etc/skel_ es copiarà a aquest directori que s’acaba de crear.

El directori _/etc/skel_ conté els arxius i directoris que es copien al directori d’inici d’un nou usuari quan es crea, tant si utilitzem el mode ordre com l’entorn gràfic.

Com podeu observar a la [figura.7](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig7), a Ubuntu 20.04 el contingut per defecte del directori _/etc/skel_ conté els arxius que permeten configurar l’entorn de l’usuari _.bash\_logout_, _.bashrc_ i _.profile_. L’arxiu _.profile_ és consultat pel sistema cada vegada que l’usuari hi accedeix; l’arxiu _.bashrc_ és consultat quan un usuari inicia un _shell_, mentre que l’arxiu _.bash\_logout_ és l’arxiu que consulta el sistema quan l’usuari en surt.FiguraContingut del directori '/etc/skel’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/skel.png)

El directori _skel_ per defecte el podem canviar al fitxer _/etc/default/useradd_. Podem fer servir qualsevol altre directori del sistema perquè sigui l’origen de la informació que es copiarà al directori d’inici dels nous usuaris. La línia del fitxer _/etc/default/useradd_ que controla aquesta configuració és la línia _/etc/skel_.

### Gestió del sistema d'arxius

En l’administració d’un sistema GNU/Linux, la gestió del sistema d’arxius és bàsica. Les tasques més elementals de gestió són les de:

* muntar o desmuntar sistemes d’arxius,
* revisar el seu estat,
* reparar sistemes d’arxius defectuosos i
* gestionar la quantitat d’espai de disc que pot utilitzar un usuari.

#### Muntatge i desmuntatge de particions

Els sistemes operatius GNU/Linux utilitzen una estructura jeràrquica d’arxius en forma d’arbre invertit. El sistema operatiu necessita alguna manera d’accedir a les dades ubicades als dispositius d’emmagatzematge i les seves particions. Als sistemes Windows això es fa assignant una lletra al dispositiu d’emmagatzematge, com C:, mentre que els sistemes GNU/Linux munten cada dispositiu d’emmagatzematge o partició a l’arbre de directoris. Quan ens referim a muntar, parlem de fer accessible el sistema d’arxius a partir d’un directori de l’arbre de directoris que s’anomena _**punt de muntatge**_.

Un **punt de muntatge** és un directori que s’utilitza com un mitjà per accedir al sistema d’arxius.

Un dels avantatges d’aquest sistema de punts de muntatge és la seva flexibilitat per localitzar els arxius. Els dispositius d’emmagatzematge es munten com si fossin un altre directori més a l’arbre de directoris del sistema.

Quan treballem al **mode gràfic** i fem doble clic sobre una de les icones que representa un dispositiu d’emmagatzematge, l’escriptori el munta de forma automàtica i mostra el seu contingut utilitzant l’aplicació de gestió d’arxius del sistema operatiu.

Si ens trobem al **mode ordre**, els sistemes GNU/Linux disposen de l’eina `mount` per muntar, una única vegada, un sistema d’arxius en un punt de muntatge. L’ordre `umount` reverteix el procés i l’edició de l’arxiu _/etc/fstab_ permet el muntatge de forma permanent.

La sintaxi de l’ordre `mount` és:

* `mount [opcions] [dispositiu] [punt de muntatge]`

Les opcions més comunes de `mount` són:

* **-a**. Aquesta opció fa que l’ordre munti tots els sistemes d’arxius llistats a l’arxiu `/etc/fstab`.
* **-r**. Aquesta opció munta el sistema d’arxius només en mode lectura.
* **-t**. Aquesta opció permet especificar el tipus de sistema d’arxius. Si s’omet aquesta opció, el sistema intentarà detectar el sistema d’arxius automàticament.

El **dispositiu** és el nom de l’arxiu associat al dispositiu d’emmagatzematge o partició, com /dev/sda4 o /dev/cdrom.

El **punt de muntatge** és el directori on volem associar el contingut del dispositiu.

Els dispositius d’emmagatzematge es poden muntar en pràcticament qualsevol part de l’arbre de directoris, i els més habituals són _/mnt_ i _/media_. Si utilitzem com a punt de muntatge un directori que conté informació, aquesta deixarà d’estar disponible fins que desmuntem el dispositiu.

Quan es munta un sistema d’arxius, es registra el muntatge a l’arxiu _/etc/mtab_. Aquest arxiu posseeix un format similar a l’arxiu de _/etc/fstab_/ i el podem examinar per veure quins sistemes d’arxius tenim muntats.

Els sistemes operatius GNU/Linux acostumen a fer un bon treball de detecció del tipus de sistema d’arxius i moltes vegades no cal utilitzar cap opció. Per tant, un dels exemples més clàssics podria ser `mount /dev/cdrom /media/cdrom`. Aquesta ordre munta el contingut del lector de CD al directori /media/cdrom. Normalment calen permisos d’administrador per executar aquesta ordre.

L’ordre `umount` té la següent sintaxi:

* `umount [opcions] [dispositiu | punt de muntatge]`

Amb aquesta ordre només s’ha d’especificar el dispositiu o el punt de muntatge, no els dos.

Les majoria d’opcions són similars a les de l’ordre `mount` però hi ha algunes excepcions com:

* **-a**. Aquesta opció fa que l’ordre desmunti tots els sistemes d’arxius llistats a l’arxiu _/etc/mtab_, l’arxiu que conté la informació sobre els sistemes d’arxius muntats al sistema. És possible que aquesta ordre no pugui desmuntar alguns dels sistemes d’arxius clau, com el directori _arrel_.
* **-r**. Aquesta opció indica que si no es pot desmuntar un sistema d’arxius, es torni a muntar en mode de només lectura.

Per exemple, per desmuntar el punt de muntatge /media/cdrom farem servir l’ordre `umount /media/cdrom` o `umount /dev/cdrom`.

L’arxiu _/etc/fstab_ agrupa la informació sobre els sistemes d’arxius i és llegit quan iniciem el sistema operatiu. El nom _fstab_ és una abreviatura de _filesystem table_, ‘taula del sistema d’arxius’ en català. Aquest arxiu conté un conjunt de línies amb sis camps cadascuna, separats per un espai, com podeu observar a la [figura.8](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig8).FiguraArxiu '/etc/fstab’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/etcfstab.jpg)

El significat dels camps és el següent:

UUID

UUID són les sigles d’_universally unique identifier_, en català ‘identificador únic universal’. És un número que s’expressa amb 32 dígits hexadecimals dividits en cinc grups separats per guions que serveix per identificar de forma unívoca qualsevol dispositiu.

* **Dispositiu**. El primer camp especifica el dispositiu de muntatge. Habitualment s’especifica fent servir el seu UUID, però també es pot fer servir el nom del dispositiu \(per exemple, /dev/sda1\).
* **Punt de muntatge**. El segon camp especifica el punt de muntatge, és a dir, on es muntarà el dispositiu d’emmagatzematge o partició.
* **Tipus de sistema d’arxius**. Aquest camp especifica el tipus de sistema d’arxius amb la mateixa nomenclatura que fan servir les ordres `mount` i `umount`.
* **Opcions de muntatge**. Aquest camp especifica les opcions de muntatge que modifiquen la forma en què el nucli tractarà el sistema d’arxius. Les opcions més utilitzades són:
  * **auto / noauto**. Especifica si la partició ha de muntar-se automàticament durant l’arrencada.
  * **exec / noexec**. Indica si la partició pot executar programes binaris compilats.
  * **ro / rw**. Especifica si la partició ha de muntar-se en mode de només lectura \(ro\) o en mode de lectura i escriptura \(rw\).
  * **user / nouser**. Permet a un usuari tenir privilegis per muntar i desmuntar.
  * **sync / async**. Determina si l’escriptura es produeix just després de l’ordre \(sync\) o si es permet que passi un temps entre l’ordre i la seva execució \(async\).
* **Còpia de seguretat**. Aquest camp conté un 1 si el sistema ha de fer una còpia de seguretat de la partició o un 0 en cas contrari.
* **Revisió del sistema d’arxius**. Aquest camp indica si s’ha de revisar la integritat del sistema d’arxius a l’inici. Un 0 indica que no s’ha de revisar el sistema d’arxius. Un número més gran indica l’ordre de revisió. La partició arrel ha de tenir el valor 1.

#### Revisió i reparació del sistema d'arxius

En algun moment pot donar-se un error als sistemes d’arxius del nostre sistema que provoqui la pèrdua de dades. Per comprovar i reparar els sistemes d’arxius a Ubuntu 20.04 disposem d’una eina anomenada `fsck`, de l’anglès _file system consistency check_.

Aquesta eina s’inicia automàticament sobre les particions marcades per a revisió a l’arxiu _/etc/fstab_, però podem executar-la manualment en qualsevol moment.

Podem utilitzar aquesta eina només amb el nom del dispositiu que volem comprovar. Tot i això, hi ha unes opcions amb les quals podem complementar l’execució. La sintaxi d’aquesta ordre és:

És recomanable executar `fsck` als sistemes d’arxius que no estan muntats, ja que els canvis escrits al dispositiu durant l’execució de l’eina poden danyar el sistema d’arxius.

* `fsck [opcions] [element]`

I les seves opcions més comunes són:

* **-A**. Aquesta opció verifica tots els sistemes d’arxius marcats per revisió a l’arxiu _/etc/fstab_.
* **-C**. Aquesta opció mostra un indicador del procés de revisió.
* **-V**. Aquesta opció permet visualitzar un resum de les accions realitzades.
* **-N**. Aquesta opció mostra el que faria l’eina però no arribar a fer-ho realment.
* **-t**. Aquest opció permet indicar els tipus de sistemes d’arxius per verificar.
* **-r**. Aquesta opció permet visualitzar algunes estadístiques sobre el dispositiu que s’està comprovant.
* **-y**. Aquesta opció accepta automàticament la correcció de qualsevol error detectat.

Al camp **element** podem utilitzar el nom del dispositiu \(/dev/sda6\), un punt de muntatge \(/home\), una etiqueta \(LABEL=ROOT\) o l’UUID del dispositiu.

#### Quotes de disc

Si un o més usuaris del sistema consumeixen massa espai dels dispositius d’emmagatzematge, poden impedir que altres usuaris utilitzin l’espai que necessiten. Per poder controlar aquesta situació existeixen les quotes de disc, que són els límits que venen determinats pel sistema operatiu sobre la **quantitat d’espai de disc que pot consumir un usuari**.

Alguns sistemes d’arxius que admeten quotes de disc són XFS, ReiserFS i ext4. Quan assignem quotes de disc, aquesta serà específica per al sistema d’arxius i per a l’usuari especificat.

Per utilitzar les quotes d’usuari cal que instal·lem el paquet _quota_ al sistema operatiu. Ho podem fer amb l’ordre `apt install quota`. Per poder utilitzar les quotes cal que les particions on volem executar-les tinguin el suport necessari. Per fer-ho, cal muntar les particions amb les opcions _usrquota_ i _grpquota_ per activar el suport de quota d’usuari i grup respectivament. Per canviar les opcions de muntatge de les particions hem d’editar l’arxiu _/etc/fstab_ i després tornar a muntar el sistema o sistemes d’arxius modificats. Les **particions** que es configurin per a l’ús de quotes tindran un aspecte com aquest:

* `/dev/sda5 /home/ ext4 usrquota,groquota 0 0`

Per definir les quotes dels usuaris utilitzem l’ordre `edquota`, que ens permetrà accedir a l’arxiu de configuració. La seva sintaxis és:

* `edquota [opcions] [usuari|grup]`

Les opcions més comunes són:

* **-u**. Amb aquesta opció indiquem a quin usuari configurarem la quota.
* **-g**. Amb aquesta opció configurarem la quota per a un grup.
* **-f**. Amb aquesta opció realitzem les operacions sobre un sistema d’arxius concret.
* **-p**. Aquesta opció permet copiar la configuració de la quota d’un usuari a altres usuaris.

Hi ha altres ordres per gestionar quotes que són:

* `quotacheck`. Aquesta ordre verifica la integritat de les quotes definides.
* `quotaon/quotaoff`. Aquesta opció activa o desactiva les quotes de disc.
* `repquota`. Aquesta ordre genera un informe de l’ús de les quotes.
* `quota`. Aquesta ordre permet a un usuari veure l’estat de les seves quotes.

### Gestió dels processos i serveis del sistema

El terme procés fa referència a un programa en execució. Està format per les instruccions del programa i per les dades necessàries per a la seva execució. Tots els processos als sistemes GNU/Linux inclouen un propietari \(l’usuari que executa el procés\) i un identificador de procés \(PID\), que és un número identificador únic per cada procés que hi ha en execució.

Per tal de poder complir amb la tasca encomanada, un procés tindrà la necessitat d’utilitzar una sèrie de recursos, com temps de CPU i memòria tant principal com secundària. Serà el sistema operatiu l’encarregat d’assignar aquests recursos als diferents processos per tal d’optimitzar el rendiment del sistema.

Un servei és un programa en execució en segon pla. Tradicionalment als sistemes Linux els serveis també s’anomenen dimonis, _daemons_ en anglès. Són processos amb els quals no acostumem a interactuar però que són molt necessaris per al funcionament del sistema. A nivell d’administració del sistema el que acostumem a fer amb els serveis és parar-los o reiniciar-los, en cas de necessitat.

#### Identificar els processos en sistemes GNU/Linux

Al **mode gràfic** d’Ubuntu 20.04 per administrar els processos podem utilitzar l’eina _Monitor del sistema_. Podem cercar aquesta eina des del quadre de cerca de la barra superior de l’escriptori.

Si premem la pestanya _Processos_ accedim a una finestra on podem veure tots els processos que s’estan executant al sistema i els seus estats. Si seleccionem un procés, i amb el botó dret del ratolí obrim el menú contextual, podem fer una sèrie d’operacions en funció de l’estat en què es trobi el procés inicialment. Aquestes operacions són:

* **Aturar el procés**. Podem aturar l’execució del procés sense que aquest acabi.
* **Continuar procés**. Podem reprendre l’execució d’un procés si estava aturat.
* **Finalitzar procés**. Podem finalitzar totalment un procés. El procés tancarà els seus arxius oberts i els recursos utilitzats.
* **Matar procés**. Podem utilitzar aquesta opció per acabar amb un procés que ha quedat bloquejat.
* **Canviar la prioritat**. Amb aquesta opció podem indiciar la prioritat del procés, en què 19 és la més baixa i -20 la més alta.

Al **mode ordre** es poden llistar els processos que s’estan executant al sistema fent servir l’ordre `ps`. Aquesta ordre, per defecte, mostra la llista de processos en execució de l’usuari que executa l’ordre. La seva sintaxi és:

* `ps [opcions]`

Les diferents opcions de l’ordre `ps` es poden consultar amb l’ordre `man`, però algunes de les més utilitzades són:

* **-a**. Llista els processos de tots els usuaris.
* **-u**. Mostra informació sobre el procés, com ara l’usuari propietari, el consum de CPU i memòria i l’estat, entre altres dades.
* **-x**. Mostra els processos de tots els terminals i usuaris.
* **-l**. Mostra informació del procés afegint la seva prioritat.
* **-f**. Mostra l’arxiu executable del procés.
* **–forest**. Mostra la llista de processos en format d’arbre per poder veure com es relacionen entre ells.

A la [figura.9](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig9) podeu veure l’ús de l’orde `ps` utilitzant tres de les seves opcions: a, u i x.FiguraOrdre ‘ps’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/ps.png)

La sortida de l’ordre `ps` mostra un encapçalament amb el significat de cada columna. Els camps més comuns són:

* **User**. Mostra el nom de l’usuari que executa el programa.
* **PID**. Mostra l’identificador del procés.
* **%CPU**. Mostra el percentatge d’ús de CPU que utilitza el procés quan s’executa l’ordre `ps`.
* **%MEM**. Mostra el percentatge d’ús de memòria.
* **TTY**. Identifica el terminal. Els dimonis, per exemple, no tenen cap.
* **Command**. Mostra l’ordre que inicia el procés.

Si només volem obtenir el PID d’un procés ho podem fer amb l’ordre `pidof` seguit del nom del procés.

Tot i que `ps` és una de les ordres més importants per a l’administració de processos, pot ser una mica difícil interpretar la seva sortida de dades. Per això també disposem d’altres ordres com `top` i `htop`, que són també utilitzades per administrar els processos. Per executar l’ordre `top` tan sols cal escriure “top” a l’intèrpret d’ordres. Aquesta ordre mostra a la pantalla diverses estadístiques del sistema, com són el nombre de tasques en execució i el consum total de CPU o memòria. Posteriorment apareix la llista de processos en execució ordenada segons les preferències de l’usuari, que es va refrescant constantment. `htop` és una alternativa a `top` més amigable per a l’usuari final, que tot i que no està instal·lada per defecte a moltes distribucions és interessant utilitzar-la.

A la [figura.10](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig10) podeu veure l’ús de l’ordre `top`.FiguraOrdre ‘top’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/top.jpg)

Com altres ordres del sistema operatiu, l’ordre `top` pot anar acompanyada d’una sèrie d’opcions. Les més usuals són:

* **-d**. Aquesta opció especifica el retard entre actualitzacions.
* **-p**. Amb aquesta opció podem monitorar processos específics indicant el seu PID.
* **-n**. Aquesta ordre no es tanca fins que nosaltres tanquem el programa, amb aquesta opció podem indicar a `top` que es tanqui després de mostrar un nombre concret d’actualitzacions.

En aquesta ordre, a més de veure les dades que mostra, podem introduir algunes opcions que ens mostraran informació addicional. Les més utilitzades són:

* **h**. Mostra l’ajuda.
* **k**. Amb aquesta opció podem destruir un procés.
* **r**. Amb aquesta opció podem canviar la prioritat d’un procés.
* **P**. Aquesta opció ordena les dades mostrades per ús de CPU.
* **M**. Aquesta opció ordena les dades mostrades per ús de CPU.
* **q**. Aquesta opció permet sortir del programa.

#### Tipus de processos

Als sistemes operatius GNU/Linux hi ha fonamentalment dos tipus de processos:

* **Processos interactius**: són aquells que s’han iniciat i són controlats des d’una sessió. Aquesta inicialització ha estat realitzada per un usuari connectat al sistema.
* **Processos en segon pla o no interactius**: són aquells que no esperen cap interacció per part de l’usuari.

Existeix, a més, un tipus especial de procés anomenat _dimoni_ \(_daemon_ en anglès\). Aquests processos dimoni s’inicien juntament amb l’inici del sistema i es mantenen en execució mentre el sistema està en ús. Poden considerar-se un tipus especial de processos no interactius.

Al sistema operatiu podem controlar si un procés s’executarà en primer o en segon pla, és a dir, si aquest procés està ocupant l’ús del terminal des del qual es va iniciar impedint realitzar altres tasques. Quan un programa està en execució el podem pausar amb la combinació de tecles Ctrl+Z per tornar a tenir el control del terminal. Aquesta combinació de tecles envia el procés a segon pla i ens permet tornar a treballar amb el terminal, si volem que el procés torni a executar-se en primer pla, caldrà utilitzar l’ordre `fg`.

Si volem executar un procés en segon pla directament, farem servir el modificador “&” al final de la línia que executa l’ordre. Podem utilitzar aquesta opció si volem executar un procés que no requereix la nostra interacció mentre fem una altra tasca.

Si hem enviat a segon pla diferents processos, cadascun tindrà un identificar de treball assignat. Per obtenir aquests identificadors utilitzem l’ordre `jobs`. Amb l’odre `jobs` podem observar els processos associats a la sessió actual, incloent tots els processos que s’estan executant en segon pla. Aquesta ordre mostrarà l’identificador del treball, l’estat del procés i l’ordre que s’ha executat.

L’identificador de treball és un número similar al PID però amb un concepte diferent. Les tasques estan numerades per cada sessió començant pel número 1. Algunes eines utilitzen aquests identificadors de treball en comptes del PID, per exemple, `fg` i `bg`.

De la mateixa manera que podem utilitzar l’ordre `fg` per portar a primer pla un procés, podem utilitzar l’ordre `bg` per enviar-lo a segon pla. L’ordre `bg [id_treball]` serveix per enviar un procés a segon pla. L’ordre `fg [id_treball]` permet per enviar un procés a primer pla i que torni a tenir el control interactiu.

Processos en segon pla

`$ sleep 300 &`. Amb l’ordre `sleep 300` podem temporitzar un interval de temps de 300 segons \(5 minuts\). El sistema esperarà 300 segons i després retornarà el control a l’usuari. Com que al final de l’ordre hem col·locat el modificador “&”, l’intèrpret d’ordres tornarà immediatament el control a l’usuari i executarà el procés _sleep_ en segon pla. Si executem l’ordre `jobs` podem observar que el procés s’està executant en segon pla i que el seu identificador de treball és 1. Per enviar-lo a primer pla utilitzem l’ordre `fg`. Podeu observar l’ús d’aquestes ordres a la [figura.11](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig11).FiguraProcés ‘sleep’ en segon pla![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/sleep.png)

#### Estats dels processos

Els processos poden estar en execució, aturats, pausats o fins i tot morts \(eliminats\). El sistema operatiu i l’usuari poden interactuar amb els processos utilitzant senyals. Per enviar un senyal a un procés cal fer servir l’ordre `kill`. Aquest senyal el pot enviar el nucli, l’usuari o una aplicació.

Per enviar un senyal, la sintaxi de l’ordre `kill` és la següent:

* `kill - s senyal PID`

L’opció “-s senyal” envia el senyal especificat al procés. Es pot especificar el senyal utilitzant un número o un nom. Podem veure tots els senyals disponibles escrivint l’ordre `kill -l`. Alguns dels senyals més utilitzats són els que permeten finalitzar processos que són:

Si no especifiquem cap senyal, el valor per defecte serà SIGTERM.

* **SIGKILL, 9**. Serveix per finalitzar un procés sense fer-ne les tasques de finalització. Aquest senyal no pot ser ignorat per cap procés, excepte pel procés systemd \(o el procés init\).
* **SIGTERM, 15**. Finalitza un procés però li permet fer les tasques de finalització com tancar els arxius oberts, etc.

Aquests senyals només destruiran els processos de l’usuari que envia el senyal.

Una variant d’aquesta ordre és `killall`, que té la següent sintaxi:

* `killall [opcions] nom`

Aquesta ordre permet destruir un procés sense conèixer el seu PID utilitzant-ne només el nom.

#### Prioritat dels processos

Un procés en execució als sistemes operatius GNU/Linux necessita una sèrie de recursos, entre ells temps de CPU. La prioritat per assignar temps de CPU als diferents processos en execució pot ser diferent per cada procés. Habitualment els processos executats per l’usuari root tenen una prioritat més alta.

Als sistemes GNU/Linux la prioritat dels processos s’anomena _nice_ i té un nivell entre -20 i 19. _Nice_ és ‘amable’ en anglès, per tant, com menys amable és un procés \(valor de prioritat més petit\) més prioritari serà, ja que tindrà tendència a no cedir temps de CPU a la resta de processos \(serà menys amable\). Com més alt sigui el valor de prioritat d’un procés, menys prioritari serà.

Si ens interessa prioritzar l’ús de CPU dels nostres programes podem utilitzar les ordres `nice` i `renice`. Per iniciar un programa amb un nivell de prioritat concret, farem servir l’ordre `nice`. La seva sintaxi és:

* `nice -n prioritat procés`

Per exemple, si volem iniciar un procés amb prioritat 12, utilitzem l’ordre `nice -n 12 procés`. Si volem canviar la prioritat d’un procés, es pot fer servir l’ordre `renice`.

* `renice -n prioritat PID`

Un usuari estàndard no pot assignar un valor de prioritat inferior al valor per defecte \(el valor per defecte és 0\) i tampoc pot canviar el valor de prioritat d’un procés a un valor inferior. Aquestes accions només les podrem realitzar amb privilegis administratius.

#### Comunicació entre processos

Cada procés en execució en la línia d’ordres té tres fluxos d’informació oberts per defecte que permeten la comunicació amb l’usuari. Són l’entrada estàndard \(STDIN\) associada al número 0, la sortida estàndard \(STDOUT\) associada al número 1 i la sortida d’error \(STDERR\) associada al número 2.

L’entrada estàndard \(STDIN\) és on l’usuari introdueix la informació que li vol donar al procés. Per defecte està associada al teclat. La sortida estàndard \(STDOUT\) és on el procés mostra les respostes a l’usuari. Per defecte està associada al terminal on s’està executant el programa. La sortida d’error \(STDERR\) és on el procés mostra els missatges d’error. Per defecte coincideix amb la sortida estàndard i està associada al terminal on s’està executant la sortida estàndard.

Els sistemes operatius GNU/Linux permeten canviar aquests fluxos per altres, permetent d’aquesta forma que la sortida d’un procés passi a ser l’entrada d’un altre procés o canviar els llocs des d’on s’agafen o es deixen les dades.

En aquells casos en què l’usuari no desitja que la sortida d’un procés es mostri per pantalla, es pot fer servir la redirecció de sortida “&gt;” i tot el que abans es mostrava per la sortida estàndard ara es podrà, per exemple, guardar a un fitxer. En el cas de voler rebre la informació des d’un fitxer en comptes del teclat es pot fer servir l’operador “&lt;” i substituirà l’entrada estàndard. Les redireccions d’entrada i sortida es poden combinar en una sola ordre.

També hi ha la possibilitat de redirigir el flux d’informació entre diferents processos mitjançant l’operador “\|”. El funcionament és que la sortida del programa executat a l’esquerra de l’operador s’envia com a entrada estàndard del programa de la dreta.

Comunicació entre processos

A continuació podeu observar alguns exemples de comunicació entre processos:

* `ls > sortida.txt`. Aquesta ordre emmagatzema la sortida del programa `ls` \(llista el contingut del directori actual\) a l’arxiu anomenat _sortida.txt_. Si el fitxer no existeix, es crearà i, si existeix, se’n substituirà el contingut. En cas que l’usuari no desitgi substituir el fitxer sinó afegir informació al final, ho pot fer mitjançant l’operador \(»\) de la següent forma: `ls » sortida.txt`. En aquest cas, no se substituirà el contingut del fitxer _sortida.txt_ sinó que la nova informació s’afegirà al final. En cas que el fitxer no existeixi, es crearà.
* `wc -l < entrada.txt`. En aquest cas l’ordre `wc` \(compta paraules o línies\) llegirà la informació del fitxer _entrada.txt_ en comptes de fer-ho del teclat.
* Les redireccions d’entrada i sortida es poden combinar en una sola ordre, per exemple: `wc -l < entrada.txt > sortida.txt`
* `cat /etc/passwd | head -5`. Aquesta ordre utilitza l’operador “\|” per llistar els 5 primers usuaris d’un sistema.

#### Gestió dels serveis del sistema

Als sistemes GNU/Linux podem trobar un tipus de processos anomenats _dimonis_. Aquests processos s’executen en segon pla i no permeten la interacció de l’usuari. Un tipus particular d’aquests processos són els serveis. Un servei és un dimoni que està esperant una petició per part d’un altre procés amb la intenció d’oferir-li una resposta. Els sistemes GNU/Linux inclouen per defecte multitud de serveis que s’inicien amb l’arrencada del sistema i serveixen per oferir diferents funcionalitats. Per exemple, hi ha serveis per permetre l’accés remot al sistema, per gestionar les cues d’impressió o per servir una pàgina web.

Per gestionar els serveis del sistema en els sistemes GNU/Linux basats en systemd, fem servir `systemctl`, que és la utilitat per defecte. L’ordre `systemctl` té la sintaxi següent:

* `systemctl [opcions] servei`

Les opcions fan referència a com s’executa o modifica el comportament del servei. Alguns exemples de les opcions d’aquesta ordre són:

* **start**. Permet iniciar un servei.
* **stop**. Permet aturar un servei.
* **restart**. Permet reiniciar un servei apagant i reiniciant el servei.
* **reload**. Permet recarregar un servei tornant a carregar els arxius de configuració.
* **status**. Permet consultar l’estat d’un servei.

Per exemple, per saber en quin estat es troba un servei anomenat _cron_ executem l’ordre `sudo systemctl status cron.service`, que donarà una resposta informant de si el servei està actiu _\(active \(running\)\)_ o aturat _\(inactive \(dead\)\)_. Els serveis han d’estar iniciats per poder contestar a les peticions que reben. Si cal que iniciem el servei cron executem l’ordre `sudo systemctl start cron.service`. Si desitgem aturar-lo fem servir l’ordre `sudo systemctl stop cron.service`. En certes ocasions pot ser necessari reiniciar un servei. Això implica aturar-lo i tornar-lo a iniciar. Per exemple, per reiniciar el servei cron fem servir l’ordre `sudo systemctl restart cron.service`. Hi ha alguns serveis en els quals, si n’hem modificat la configuració, cal carregar-la per aplicar el nou funcionament. Per exemple, per aplicar la nova configuració al servei cron executem l’ordre `sudo systemctl reload cron.service`.

### Gestió de la memòria

La memòria és un dels recursos més importants en el funcionament d’un sistema operatiu. El sistema operatiu s’encarrega d’assignar la memòria necessària a les aplicacions que ho necessiten. Quan iniciem l’equip informàtic només el sistema operatiu està consumint memòria, però a mesura que anem obrint altres aplicacions, com un editor de text o un navegador, la memòria es va ocupant. Si continuem obrint aplicacions fins al punt d’ocupar tota la memòria, el sistema informàtic es tornarà inestable i el sistema operatiu mantindrà en memòria les aplicacions bàsiques per al seu funcionament i en tancarà altres de menys prioritàries.

Per solucionar aquest problema, els sistemes GNU/Linux utilitzen un concepte anomenat _memòria virtual_ o _memòria swap_ \(‘memòria d’intercanvi’ en anglès\). La memòria virtual utilitza un espai d’emmagatzematge reservat al disc dur que juntament amb la memòria principal permet ampliar la capacitat de la memòria del sistema informàtic.

Tot i que l’escriptura de dades en el disc és més lenta que l’escriptura en el dispositiu de memòria principal i l’ús d’aquesta alentirà el sistema, és molt útil per evitar que el sistema hagi de tancar aplicacions en ús.

Als sistemes operatius GNU/Linux per utilitzar aquesta memòria es pot configurar una partició al disc dur dedicada per utilitzar-la com a memòria virtual, un dispositiu independent o un arxiu d’intercanvi reservat en el sistema operatiu. Tant la partició com el dispositiu i l’arxiu permeten que el sistema operatiu faci un emmagatzematge temporal de les dades que no caben a la memòria principal.

Normalment els sistemes GNU/Linux acostumen a utilitzar la memòria virtual quan el 60% de la memòria principal està en ús, però aquest valor es pot configurar a l’arxiu /proc/sys/vm/swappiness.

Podem comprovar la memòria principal i virtual total, en ús i disponible del nostre sistema operatiu utilitzant tant l’entorn gràfic com el mode text.

Al **mode gràfic** podem utilitzar l’eina _Monitor del sistema_. A la pestanya _Recursos_ podem veure una gràfica amb l’historial d’ús de la memòria principal i virtual i visualitzar els percentatges d’ús. Podeu veure aquesta gràfica a la [figura.12](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig12).FiguraÚs de la memòria principal i virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/memoria.jpg)

Al **mode text**, per comprovar quanta memòria està utilitzant el sistema operatiu podem utilitzar l’ordre `free`.

Amb l’ordre `free -h` \(podem utilitzar l’opció -h perquè s’ajusti la unitat de mesura automàticament\), podem visualitzar informació sobre la memòria principal i la memòria virtual que es troba en ús.

Una altra ordre `vmstat` també ens permet obtenir informació sobre l’ús de memòria, però a més també ens proporciona informació sobre els processos, la paginació, l’activitat de la CPU i de més paràmetres.

L’ordre `top`, una de les ordres clau per monitorar els processos del sistema operatiu, també mostra informació sobre la memòria principal i virtual utilitzada.

### Gestió dels dispositius d'emmagatzematge

Una de les tasques de l’administració de sistemes operatius és la gestió dels dispositius d’emmagatzematge, tant interns com externs. Les eines de gestió ens permeten crear particions, donar format, establir els punts de muntatge i altres tasques. Al sistema operatiu Ubuntu 20.04 podem utilitzar tant l’entorn gràfic com el mode text per fer aquesta gestió dels dispositius.

Si utilitzem el **mode gràfic** del sistema operatiu Ubuntu 20.04 podem utilitzar l’eina _Discs_ que ve integrada al sistema. L’eina _Discs_ ens permet muntar i desmuntar qualsevol dispositiu, comprovar el sistema d’arxius, donar format al dispositiu d’emmagatzematge i fer proves de rendiment.

Amb l’eina _Discs_ podem gestionar els volums i les particions. Al tauler esquerra de la finestra, on trobem els dispositius físics, hem de seleccionar el dispositiu que volem gestionar.

Partició

Quan parlem de partició ens referim a una àrea física d’emmagatzematge en un dispositiu d’emmagatzematge. Una vegada la partició s’ha muntat al sistema, s’anomena _volum_.

Al tauler dret podem visualitzar el model, la mida, el número de sèrie i un desglossament visual dels volums i particions presents al dispositiu d’emmagatzematge seleccionat.

Podem clicar en una de les particions o volums per veure més informació, com la mida, el nom, el número de sèrie o el tipus de partició o volum. Podeu observar la informació sobre un volum a la [figura.13](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig13).FiguraInformació d’un volum![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/discs.jpg)

Si tenim un nou dispositiu d’emmagatzematge i hi volem crear particions, el primer pas és crear una taula de particions per afegir-hi les noves. Per fer-ho cliquem al menú de la part superior dreta de la finestra i seleccionem l’opció _Formata el disc_. Podem seleccionar un esquema de partició GPT o MBR al menú que apareix. Després seleccionem _Formata_. Per continuar donant format caldrà que introduïm la nostra contrasenya per obtenir els privilegis d’administrador.

Un cop hem creat la taula de particions podem crear tantes particions com desitgem clicant el botó “+”. Podem seleccionar la ubicació de la partició, la mida i el nom. Per crear-la hem de polsar el botó _Crear_ i introduir la nostra contrasenya. Podem crear més particions seguint el mateix procés.

Per poder utilitzar la partició cal muntar-la, i ho fem seleccionant el botó _Reproduir_ \(Munta la partició seleccionada\). Per desmuntar-la caldria pressionar el botó _Stop_ \(Desmunta la partició seleccionada\).

Per eliminar la partició cal seleccionar-la i clicar al botó “-”.

Per donar format a una partició cal seleccionar-la, clicar el botó amb l’engranatge _Opció de la partició addicionals_ i seleccionar _Formata la partició_.

Aquesta mateixa eina _Discs_ ens ofereix altres opcions interessants per gestionar els dispositius d’emmagatzematge. Aquestes opcions són modificar algunes dades de les particions, comprovar el sistema d’arxius buscant errors, reparar els errors del sistema d’arxius, canviar les opcions de muntatge de les particions, etc.

Una eina també interessant que trobem a l’entorn gràfic és l’_Analitzador de l’ús dels discs_ que mostra gràfiques amb l’ocupació dels dispositius d’emmagatzematge. Podeu observar una imatge a la [figura.14](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig14).FiguraAnalitzador de l’ús dels discs![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/analitzador.jpg)

A més de l’eina _Discs_ a Ubuntu 20.04 també podem trobar _Gparted_. Gparted és un editor de particions per a l’escriptori GNOME. Amb aquesta aplicació podem crear, eliminar, redimensionar i copiar particions i els seus sistemes d’arxius d’un forma molt intuïtiva. Si volem utilitzar GParted en altres distribucions caldrà instal·lar l’aplicació, ja que en algunes no l’hi trobarem per defecte.

Quan executem _GParted_ s’obre una finestra que podeu observar a la [figura.15](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig15).FiguraGParted![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/gparted.jpg)

En aquesta finestra podem observar un menú superior amb alguns accessos ràpids i el menú de l’aplicació. A sota dels accessos ràpids trobem una barra dividida en diferents requadres que simbolitzen les particions del dispositiu d’emmagatzematge seleccionat.

Per treballar amb aquesta aplicació cal que seleccionem el dispositiu d’emmagatzematge que volem gestionar per veure les seves particions. Si cliquem amb el botó dret del ratolí sobre la partició o un espai buit, veurem les accions que podem dur a terme. Aquestes accions són:

* **Nova**. Aquesta opció crea una nova partició.
* **Suprimeix**. Aquesta opció elimina una partició.
* **Redimensiona/Mou**. Aquesta opció serveix per canviar la mida d’una partició o moure-la a una altra ubicació.
* **Copia/Enganxa** Aquesta opció permet copiar i enganxar una partició en una altra ubicació. La partició enganxada tindrà el mateix UUID i format que la copiada.
* **Formata a**. Aquesta opció dona format a la partició assignant un sistema d’arxius.
* **Munta/Desmunta**. Aquesta opció permet muntar o desmuntar la partició.
* **Comprova**. Permet buscar problemes a la partició i reparar-los.
* **Etiqueta del sistema d’arxius**. Aquesta opció permet posar una etiqueta al volum.
* **UUID nou**. Aquesta opció permet canviar l’identificador únic universal.
* **Informació**. Ens proporciona informació de la partició o volum, com el sistema d’arxius, el punt de muntatge, l’etiqueta, l’UUID, l’estat, l’espai lliure i utilitzat, etc.

Si ens trobem al **mode ordre** podem utilitzar l’ordre `fdisk` per gestionar i administrar els dispositius d’emmagatzematge. Aquesta eina permet llistar totes les particions, crear, editar i eliminar particions.

Per utilitzar l’ordre `fdisk` cal escriure el nom de l’ordre seguit del nom del dispositiu que volem gestionar. L’execució d’aquesta ordre mostra una línia d’ordres on podrem introduir l’opció per realitzar la tasca desitjada. Les opcions més utilitzades de `fdisk` són:

* **p**. Aquesta opció mostra la taula de particions. Si volem veure la taula de particions d’un dispositiu d’emmagatzematge no cal accedir a la línia d’ordres de `fdisk`, podem executar l’ordre `fdisk -l /dev/hda` des del terminal.
* **n**. Aquesta opció crea una partició. Per fer-ho haurem de respondre unes preguntes sobre el tipus de partició \(primària, estesa o lògica\), el cilindre d’inici i la mida. `fdisk` mesura els punts d’inici i finalització de les particions en cilindre i no en bytes. Això no suposa un problema perquè podem escollir el punt d’inici per defecte i especificar la mida de la partició en múltiples del byte i `fdisk` calcularà el cilindre final.
* **d**. Aquesta opció elimina una partició.
* **t**. Aquesta opció permet canviar el sistema d’arxius de la partició. Podem llistar els tipus de sistemes d’arxius admesos amb l’opció “-l”.
* **a**. Aquesta opció permet especificar que és una partició d’arrencada.
* **m**. Aquesta opció proporciona ajuda sobre les opcions.
* **w**. Aquesta opció permet sortir de `fdisk` guardant els canvis fets. Si volem sortir sense guardar els canvis podem fer servir l’opció “q”.

Podeu observar l’ajuda de l’ordre `fdisk` a la [figura.16](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig16).FiguraAjuda de l’eina ‘fdisk’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/fdisk.jpg)

Amb l’ordre `mkfs` podem donar format a un dispositiu d’emmagatzematge amb un determinat sistema d’arxius. La seva sintaxi és:

* `mkfs -t sistema_arxius dispositiu`.

Després d’utilitzar `fdisk` podem utilitzar aquesta ordre per crear el sistema d’arxius.

Al sistema operatiu Ubuntu 20.04 també podem trobar l’eina `cfdisk` una eina que permet la gestió dels dispositius d’emmagatzematge amb una interfície més amigable que `fdisk` i amb unes opcions molt similars. `cdifsk` a més de presentar una millor interfície a l’usuari també permet ampliar les particions esteses quan hi ha espai lliure a continuació, cosa que no és possible amb `fdisk`.

#### Ús dels dispositius d'emmagatzematge

Els dispositius d’emmagatzematge acostumen a omplir-se ràpidament, per la qual cosa és necessari comprovar periòdicament l’espai disponible al sistema. Per fer-ho podem utilitzar les eines `df` i `du` que permeten observar l’ús del disc per particions o per directoris.

L’ordre `df` ens permet visualitzar informació sobre l’espai total, ocupat i lliure al nostre sistema informàtic. Si utilitzem l’ordre sense paràmetres, ens dona informació en KB sobre la quantitat total d’espai del sistema d’arxius, l’espai utilitzat, l’espai lliure, el percentatge d’espai en ús i el punt de muntatge. La seva sintaxi és:

* `df [opcions] [particions]`

Podem canviar la sortida de l’ordre utilitzant algunes opcions. Les més usuals són:

* **-h, –human**. Si volem que la unitat s’ajusti de forma automàtica caldrà utilitzar aquesta opció.
* **-a, –all**. Inclou tots els sistemes d’arxius.
* **-t**. Mostra només informació sobre un sistema d’arxius en concret.
* **-T, –print**. Afegeix a la llista d’informació el tipus de sistema d’arxius.

L’eina `du` busca els directoris especificats i mostra quant ocupa cadascun i els seus subdirectoris. La sintaxi de l’ordre és com la `df`:

* `du [opcions] [directoris]`

Algunes de les seves opcions més conegudes són:

* **-a, –all**. Amb aquesta opció també obtindrem informació sobre els arxius continguts al directori.
* **-c, –total**. Aquesta opció afegeix la suma total al final de la sortida de l’ordre.
* **-h, –human**. Per ajustar de forma automàtica la unitat de mesura caldrà utilitzar aquesta opció.
* **–max-depth**. Aquesta opció limita la sortida al nombre de nivells que especifiquem.

A la [figura.17](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig17) podeu observar el resultat de les ordres `df` i `du` del directori personal de l’usuari.FiguraResultat de les ordres ‘df’ i ‘du’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/dfdu.jpg)

### Rendiment del sistema i eines de seguiment i monitoratge

La mesura del rendiment del nostre sistema depèn de molts factors, com el nombre d’aplicacions que poden funcionar simultàniament, la quantitat de memòria disponible, l’espai disponible als dispositius d’emmagatzematge, etc. Un cop tinguem recollides totes aquestes dades podrem fer una valoració del rendiment del sistema.

Per recollir la majoria de les dades que necessitem, al **mode gràfic** d’Ubuntu 20.04 disposen de l’eina _Monitor de sistema_, que ens permet mesurar el rendiment del sistema en temps real.

Aquesta aplicació disposa de tres pestanyes. A la primera, anomenada _Processos_, podem visualitzar una llista amb tots els processos en execució. Els podem ordenar per nom, usuari que l’executa, consum de CPU o memòria, prioritat, etc. Si seleccionem un procés el podem aturar, finalitzar, matar o permetre que continuï la seva execució utilitzant el botó dret del ratolí. També és possible canviar-ne la prioritat clicant sobre el procés i seleccionant _Canvia la prioritat_. Podeu observar el contingut d’aquesta pestanya a la [figura.18](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig18).FiguraProcessos en execució![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/processos.jpg)

La segona pestanya s’anomena _Recursos_ i hi podem observar un gràfic en temps real amb la utilització de la CPU, la memòria i la xarxa.

A la tercera pestanya anomenada _Sistema d’arxius_ podem veure quant espai tenim ocupat i disponible als nostres dispositius d’emmagatzematge, els directoris on estan muntats i el seu sistema d’arxius. Podeu observar aquesta pestanya a la [figura.19](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig19).FiguraInformació dels sistemes d’arxius![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/sistemafitxers.png)

A més de l’eina _Monitor del sistema_ disposem d’altres eines de tercers amb les quals podem monitorar l’ús del sistema. Una de les més conegudes és _Conky_, un monitor de sistema lliure i de codi obert per als sistemes Linux i BSD. Aquestes eines de tercers poden donar més informació que la que inicialment podem obtenir amb el _Monitor del sistema_, com informació relacionada amb la temperatura dels dispositius i amb els perifèrics.

Al **mode ordre**, utilitzarem les eines adequades per monitorar cadascun dels conceptes que ens permetran valorar el rendiment. Principalment aquests conceptes són:

* **Utilització de la CPU**. Podem comprovar si la CPU acostuma a treballar al 100% normalment. Si la CPU es manté per sota del 100% independentment del que el sistema informàtic estigui processant, encara podem afegir més càrrega de treball. Si no, caldria valorar-ne el rendiment. Per monitorar l’ús de la CPU podem utilitzar les ordres `ps`, `top`, `vmstat`, entre altres.
* **Utilització de la memòria**. Podem verificar l’ús de memòria del sistema o la memòria disponible tant per la memòria principal com per la memòria virtual. Les ordres que ho permeten són `free`, `top`, `vmstat`, entre altres.
* **Dispositius d’emmagatzematge**. Amb les ordres `fdisk`, `fsck`, `df` i `du` podem detectar problemes d’espai als dispositius d’emmagatzematge o fer estadístiques relacionades amb el sistema d’arxius, com el nombre d’arxius, la mida, etc.

### Ús compartit simple de recursos en xarxa

Els usuaris de la xarxa poden accedir als recursos compartits al nostre sistema. Quan estem en una mateixa xarxa els recursos com directoris i impressores es poden posar a disposició d’altres usuaris. Quan es comparteixen els recursos s’acostuma a fer de manera que la resta d’usuaris els puguin utilitzar amb algunes restriccions d’accés que ha determinat l’usuari que els comparteix.

Per compartir un directori utilitzant l’entorn gràfic caldrà seleccionar el directori i, amb el botó dret del ratolí seccionem l’opció _Compartició de xarxa local_. Això ens mostrarà un quadre de diàleg anomenat _Recursos compartits_ que podeu observar a la [figura.20](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig20).FiguraCompartició d’un directori![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/compartirdirectori.jpg)

En aquest quadre marquem la casella _Comparteix aquesta carpeta_ si volem compartir el directori seleccionat i dins del quadre _Nom del recurs compartit_ indiquem el nom amb el qual la resta d’usuaris de la xarxa veuran aquest recurs.

Perquè els usuaris puguin crear i suprimir arxius en aquest directori cal marcar la casella corresponent. Si no els usuaris de la xarxa només podran veure el contingut del directori. Podem donar accés al directori a usuaris convidats que no disposin de compte d’usuari per accedir al directori compartit, marcant l’última casella.

Per compartir el recurs, cliquem al botó _Crea un recurs compartit_. Si tot ha anat bé, a la carpeta es mostrarà una imatge amb un símbol de compartició.

És possible que al moment de compartir un recurs, el sistema operatiu ens indiqui que el servei de compartició no està instal·lat i que cal instal·lar-lo per compartir els recursos. El programari que s’instal·larà si acceptem la instal·lació és el paquet **samba**. _Samba_ és un conjunt d’eines que permeten la comunicació entre equips Unix, Windows i OS X.

Les definicions de les carpetes compartides pels diferents usuaris del sistema estan situades en fitxers de text situats dins del directori _/var/lib/samba/usershares_. Per cada recurs compartit per tots els usuaris del sistema es crearà un fitxer amb les opcions de compartició.

Per explorar els equips de la xarxa i accedir als recursos compartits, ho podem fer des de qualsevol sistema informàtic independentment del seu sistema operatiu. Si ho fem des d’un sistema operatiu Windows, hem d’accedir a l’equip que conté el recurs compartit des de l’_explorador d’arxius_. Si ho fem des d’un equip Linux podem utilitzar l’eina _Fitxers_ per cercar l’equip que disposa del recurs compartit i es muntarà de forma automàtica.

#### Impressores en xarxa

Per fer la compartició d’una impressora cal compartir-la en un dels equips de la xarxa per després configurar-la des dels altres equips.

A Ubuntu 20.04, per compartir una impressora cal accedir als seus paràmetres. Ho fem cercant al quadre de cerca de la barra superior _Impressores_ o obrint l’aplicació _Paràmetres_ i seleccionant _Impressores_. En aquesta finestra cal seleccionar el botó _Paràmetres addicionals d’impressió_ i s’obrirà una nova finestra amb les impressores disponibles al sistema.

Una vegada localitzada la impressora que es vol compartir, amb el botó dret hem de seleccionar l’opció _Compartida_ i en aquesta mateixa aplicació, seleccionar el menú _Servidor &gt; Ajusts_ per seleccionar _Publica les impressores compartides connectades a aquest sistema_. A partir d’aquest moment la impressora serà detectable i utilitzable per altres sistemes. Si a més es selecciona l’opció _Permet la impressió per Internet_ quedarà habilitat el protocol d’impressió IPP.

Es pot controlar l’accés a la impressora compartida per uns determinats usuaris. Per fer-ho cal fer clic amb el botó dret sobre la impressora i seleccionar _Propietats_. Dins de les propietats de la impressora, l’opció que interessa és _Control d’accés_. Aquesta opció permet configurar l’accés a partir d’una llista d’usuaris permesos o a partir de la llista d’usuaris sense permís. Aquests usuaris han d’existir al sistema on està connectada la impressora.

Per connectar la impressora compartida a un altre equip cal anar a _Paràmetres &gt; Impressores_ i clicar al botó _Afegeix_. Apareixerà una nova finestra per afegir una nova impressora que podeu observar a la [figura.21](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig21). Si la impressora ha estat publicada per l’equip que la tenia compartida, és possible que aparegui directament com a disponible fins i tot abans de cercar-la, gràcies al servei d’instal·lació automàtica d’impressores anomenat _cups-browsed_.FiguraCompartició d’una impressora![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/impressores.jpg)

Si el procés de cercar la impressora no la troba, podem utilitzar altres opcions com _Impressora Windows a través de SAMBA_ o _Protocol d’impressió per Internet \(ipp\)_.

Que seleccionem l’opció _Impressora Windows a través de SAMBA_ no significa que estiguem connectant una impressora a un equip Windows necessàriament, sinó que utilitzarem Samba per accedir a un altre equip Linux. Samba normalment s’utilitza perquè equips Windows i Linux puguin compartir recursos entre ells, però si dos equips Linux utilitzen Samba també es poden comunicar entre ells.

Si utilitzem l’opció _Protocol d’impressió per Internet \(ipp\)_ podrem accedir de forma remota a qualsevol impressora de la xarxa que estigui compartida amb el protocol d’impressió d’internet ipp.

### Automatització de tasques

L’automatització de tasques en un sistema informàtic ens permet agilitzar l’execució de tasques repetitives que consumeixen gran part del nostre temps. Algunes de les tasques repetitives més usuals que trobem al món informàtic són la creació de còpies de seguretat, l’actualització de les aplicacions, el monitoratge del sistema, etc.

Als sistemes Linux l’automatització de tasques se sol fer des del **mode ordre** i s’utilitzen les eines **Cron** i **Anacron**.

Cron és una eina que permet executar tasques a intervals regulars de temps i és molt útil per automatitzar tasques relacionades amb el manteniment del sistema informàtic. Les tasques que es volen executar i el moment de l’execució s’especifiquen en un arxiu anomenat _**crontab**_. Cada usuari del sistema té el seu propi arxiu _crontab_ per programar tasques, que s’emmagatzema al directori _/var/spool/cron/crontabs_. A més d’aquests arxius _crontab_ dels usuaris hi ha un altre arxiu anomenat _/etc/crontab_ que s’aplica a tot el sistema i que disposa d’un camp addicional per indiciar l’usuari que ha d’executar cada tasca. Aquest arxiu cal editar-lo manualment. Podeu observar un arxiu _contrab_ d’un usuari i l’arxiu general _/etc/crontab_ a la [figura.22](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig22) i [figura.23](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig23), respectivament.FiguraArxiu ‘crontab’ d’un usuari![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/crontabusuari.jpg)FiguraArxiu '/etc/crontab’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/crontab.jpg)

Els arxius _crontab_ d’usuari estan formats per una sèrie de línies que s’anomenen expressions de Cron i tenen la següent sintaxi:

* `minut hora dia_mes mes dia_setmana ordre`

El significat de cada camp a una expressió de Cron és el següent:

* **minut**. Aquest camp permet indicar en quin minut volem executar la tasca. Pot ser un número enter comprès entre 0 i 59 i alguns caràcters especials.
* **hora**. Aquest camp indica a quina hora volem executar la tasca. Podem utilitzar un número enter entre 0 i 23 i caràcters especials.
* **dia\_mes**. Aquest camp especifica quin dia del mes volem executar la tasca. Podem utilitzar un número enter entre 1 i 31 i els caràcters especials.
* **mes**. Aquest camp serveix per indicar el mes. Podem utilitzar un número enter entre 1 i 12 i caràcters especials.
* **dia\_setmana**. Aquest camp serveix per especificar quin dia de la setmana s’executarà la tasca. Podem introduir un 1 pel dilluns, 2 pel dimarts fins al 7, que representa el diumenge, tot i que el diumenge també es pot representar amb el número 0. També podem introduir les tres primeres lletres del nom del dia en anglès \(mon, tue, wed, thu, fri, sat i sun\). En aquest camp també podem fer servir caràcters especials.
* **ordre**. En aquest camp especifiquem la tasca que volem executar.

Els caràcters especials que podem utilitzar a les expressions de Cron són:

* **“\*”**. Aquest caràcter significa ‘tot’. Si posem l’asterisc al camp minut i al camp hora significa cada minut de cada hora.
* **,**. Aquest caràcter serveix per crear una llista. Si volem executar un tasca al minut zero i al minut 45, podem posar 0,45 al camp minut i no crear dues tasques separades.
* **-**. Aquest caràcter representa un rang de valor. Si volem executar una tasca cada minut entre el minut 0 i el minut 30, podem posar al camp minut el valor 0-30.
* **/**. Aquest caràcter serveix per expressar un valor de període. Si volem executar una ordre cada 2 dies podem escriure /2 al camp dia.

Hi ha algunes expressions que es poden utilitzar a l’arxiu _crontab_ per abreviar alguns caràcters especials que són:

* **@hourly**. Abrevia 0 \* \* \* \* \(Cada hora\)
* **@daily**. Abrevia 0 0 \* \* \* \(Cada dia\)
* **@weekly**. Abrevia 0 0 \* \* 0 \(Cada setmana\)
* **@monthly**. Abrevia 0 0 1 \* \* \(Cada mes\)
* **@yearly**. Abrevia 0 0 1 1 \* \(Cada any\)

Els usuaris no han d’editar els arxius _crontab_ d’usuari de forma manual. Es recomana utilitzar l’ordre `crontab`, que permet editar l’arxiu del nostre perfil. Podem editar l’arxiu amb l’ordre `crontab -e`. La primera vegada que utilitzem aquesta ordre ens demanarà seleccionar un editor de text que ens servirà per editar l’arxiu de forma predeterminada.

Aquesta mateix ordre `crontab` admet altres opcions com:

* **-l**. Permet veure el contingut de l’arxiu _crontab_ de l’usuari que ha iniciat sessió però no editar-lo.
* **-r**. Aquesta opció elimina l’arxiu _crontab_ sense demanar confirmació.
* **-i**. Aquesta opció, utilitzada conjuntament amb -r, sol·licita confirmació per eliminar l’arxiu.
* **-u**. Si tenim privilegis d’administrador i utilitzem l’ordre `sudo` podrem editar el _crontab_ de qualsevol usuari amb aquesta opció.

Podem administrar els permisos dels usuaris per utilitzar l’ordre `crontab` utilitzant els arxius _/etc/cron.allow_ i _/etc/cron.deny_. Els usuaris inclosos a l’arxiu _cron.deny_ no podran editar el seu crontab i només ho podran fer els usuaris inclosos a l’arxiu _cron.allow_. En cas que un mateix usuari estigui present als dos arxius, _cron.deny_ i _cron.allow_, l’usuari si podrà editar el seu _crontab_.

Després de comprovar quines tasques cal executar a l’arxiu _/etc/crontab_, també es comproven tots els arxius emmagatzemats al directori _/etc/cron.d_. Cadascun d’aquests arxius especifica una tasca programada. Aquests arxius poden editar-se manualment i utilitzen les mateixes expressions de Cron que els arxius _crontab_. Només els usuaris amb privilegis d’administrador poden programar tasques en aquest directori.

Cron és una eina que permet executar tasques de forma automàtica en un moment concret. Si en el moment d’iniciar la tasca, el sistema informàtic està apagat, la tasca no s’executarà. És una eina pensada per a equips que es troben constantment encesos, com els servidors. Si volem utilitzar un programador de tasques per a equips personals que s’encenen i s’apaguen amb més freqüència, és millor utilitzar Anacron.

Anacron és una eina que complementa Cron i executa les tasques que han quedat pendents. Si quan Cron vol realitzar la tasca programada, el sistema informàtic està apagat, la tasca es realitzarà per Anacron quan sigui possible.

Les tasques que executa Anacron es defineixen a l’arxiu _/etc/anacrontab_. Aquest arxiu el podem editar directament. Per afegir una tasca cal escriure-la amb una expressió que té la següent sintaxi:

* `període retard identificador_tasca ordre`
* **període**. Aquest camp indica amb quina periodicitat s’executa la tasca. Alguns dels caràcters que podem escriure en aquest camp són:
  * **1 o @daily**. Si volem que l’ordre s’executi cada dia.
  * **7 o @weekly**. L’ordre s’executarà setmanalment.
  * **30 o @monthly**. Si volem que l’execució sigui mensualment.
  * **Número enter**. Especifica cada quants dies s’executarà l’odre. Per exemple, un 5 significa que l’odre s’executarà cada 5 dies.
* **retard**. Aquest camp especifica quants minuts passen des de que Anacron detecta que ha d’executar la tasca fins que l’executa. Pot ser útil per evitar sobrecarregar el sistema fent totes les tasques al mateix temps.
* **identificador\_tasca**. Aquest nom identifica la tasca que s’executarà.
* **ordre**. En aquest camp especifiquem la tasca que volem executar.

Altres opcions utilitzades de l’ordre `anacron` són:

* **-f**. Executa totes les tasques al moment, ignorant els temps establerts.
* **-T**. Comprova que l’arxiu _/etc/anacrontab_ no té errors i és vàlid.
* **-n**. Permet executar les tasques immediatament ignorant el temps de retard.

Les eines Cron i Anacron, a més de l’execució de tasques emmagatzemades als arxius _crontab_ i _anacrontab_, també podem executar tasques que es trobin emmagatzemades en arxius en uns directoris concrets. Aquests directoris són:

* _**/etc/cron.daily**_. Aquests guions administratius s’executaran una vegada al dia.
* _**/etc/cron.weekly**_. De la mateixa manera, els guions administratius emmagatzemats en aquest directori, s’executaran una vegada a la setmana.
* _**/etc/cron.monthly**_. En aquest directori s’emmagatzemen els guions administratius que s’executaran una vegada al mes.
* _**/etc/cron.hourly**_. Tots els guions administratius emmagatzemats en aquest directori s’executaran cada hora. Només Cron pot executar els guions ubicats en aquest directori.

Cron i Anacron poden executar els guions administratius ubicats als directoris _/etc/cron.daily_, _/etc/cron.weekly_ i _/etc/cron.monthly_. Qui els executarà dependrà de si tenim les dues eines instal·lades al sistema operatiu i de si l’equip es troba encès o apagat.

Expressions de Cron

A continuació podeu observar alguns exemples d’expressions de Cron:

* **“\* \* \* \* \* ordre”**. Executa l’ordre cada minut de cada hora de cada dia de cada mes.
* **/15 \* \* \* \* ordre**. Executa l’ordre cada 15 minuts de cada dia de cada mes.
* **0 2 \* \* 1 ordre**. Executa l’ordre cada dilluns a les dues de la matinada.
* **15,35 \* \* 1 \* ordre**. Executa l’ordre als minuts 15 i 35 de cada hora tots els dies del primer més de l’any:
* **45 18 \* \* 5 ordre**. Executa l’ordre cada divendres a les 18.45pm.

A continuació podeu observar alguns exemples d’expressions de Anacron:

* **1 5 Tasca1 ordre**. Executa l’ordre cada dia amb un retard de 5 minuts. La tasca s’anomena Tasca1.
* **@monthly 10 Tasca2 ordre**. Executa l’ordre cada mes amb un retard de 10 minuts. La tasca s’anomena Tasca2.

#### Execució de programes i guions administratius

Moltes de les tasques que fan els administradors de sistema són repetitives. Si, per exemple, necessitem afegir 100 usuaris a un sistema, utilitzar l’odre `useradd` cent vegades pot resultar esgotador. Per fer tasques repetitives que no necessàriament han de tenir una freqüència de realització concreta disposem dels **guions administratius**.

Els **guions administratius** són programes escrits en un llenguatge que pot interpretar el sistema operatiu i on podem utilitzar les ordres del mateix sistema operatiu, variables i expressions condicionals. També es coneixen com _scripts_.

En un guió administratiu, la primera línia identifica el _shell_ que s’ha de fer servir per executar-lo. Si volem utilitzar _bash_ per executar-lo la primera línia serà:

`#!/bin/bash`

Els dos primers caràcters són un codi especial que indica al nucli de Linux que està davant d’un guió administratiu i que utilitzi la resta de la línia com a ruta al programa que executarà el guió. Aquesta línia és coneguda com _shebang_.

Una de les característiques dels guions administratius és que poden executar ordres del sistema operatiu, de manera que les ordres que podem fer servir al mode ordre també les podem utilitzar per escriure el guió.

Un guió administratiu és un arxiu de text que es pot escriure amb qualsevol editor de text pla. Poden tenir qualsevol nom, que normalment fa referència a la utilitat del guió, i habitualment tenen extensió “.sh”. Quan el guió administratiu està escrit, hem de modificar l’arxiu perquè es pugui executar. Per fer-ho podem fer servir l’ordre `chmod`. En concret podem fer servir `chmod a+x nom_guió.sh` per afegir els permisos d’execució per a tots els usuaris.

Per executar el guió administratiu escriurem la seva ruta completa o el nom del _shell_ seguit del nom del guió administratiu, per exemple `bash guio.sh`. En cas que el guió administratiu estigui ubicat al directori actual podem escriure “./” seguit del nom del guió administratiu.

Es pot programar l’execució dels guions administratius amb les eines Cron i Anacron, ja que aquestes eines poden executar tant ordres del sistema operatiu com guions administratius.

A continuació podeu observar un petit guió administratiu que mostra per pantalla el nom de l’usuari connectat al sistema informàtic i el directori de treball en el qual està situat.

Guió administratiu

\#!/bin/bash

\# Un primer guió administratiu

echo “Hola”

echo “Soc l’usuari:”

whoami

echo “El meu directori de treball actual és:”

pwd

### Mètodes per a la recuperació del sistema operatiu

En cas que un sistema deixi de funcionar de forma correcta pot arribar a ser necessari recuperar les dades dels usuaris, el sistema operatiu o tota la informació del sistema.

#### Accés al mode de recuperació

Si tenim algun problema amb el sistema operatiu podem iniciar el sistema en mode de recuperació. Amb aquesta opció podem realitzar algunes opcions que poden permetre recuperar el sistema si aquest no funciona correctament o no podem iniciar-lo. Algunes de les tasques que podem dur a terme en aquest mode són:

* Resoldre problemes relacionats amb l’arrencada del sistema i GRUB.
* Reparar o desinstal·lar paquets que estan causant problemes al sistema operatiu.
* Solucionar problemes de maquinari.
* Gestionar guions administratius d’inici.
* Solucionar problemes amb els comptes d’usuari.
* Gestionar processos en execució.
* Investigar problemes amb tasques programades.

Per iniciar el mode de recuperació, quan iniciem el sistema operatiu a la pantalla d’inici hem de seleccionar _Opcions avançades d’Ubuntu_ i a la pantalla següent l’opció _Recovery mode_. En aquest moment podrem veure el menú de recuperació que podeu observar a la [figura.24](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig24).FiguraMode de recuperació d’Ubuntu 20.04![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/recuperacio.png)

En aquest menú trobem les opcions següents:

* **resume**. Aquesta opció permet continuar amb l’arrencada normal del sistema.
* **clean**. Aquesta opció permet alliberar espai als dispositius d’emmagatzematge. Quan seleccionem aquesta opció ens demanarà permís per muntar els sistemes d’arxius definits a _/etc/fstab_ i cercarà els paquets que ja no són necessaris per al sistema per eliminar-los.
* **dpkg**. Aquesta opció permet reparar qualsevol paquet de programari que pugui estar causant problemes al sistema operatiu. Per això, primer es llegeix la llista de paquets, es verifiquen les dependències i s’actualitza el sistema.
* **fsck**. Aquesta opció permet utilitzar l’ordre `fsck` per comprovar i reparar els sistemes d’arxius dels dispositius d’emmagatzematge. Quan utilitzem aquesta ordre, el sistema comprova i repara el sistema d’arxius automàticament.
* **grub**. Aquesta opció permet actualitzar el carregador d’arrencada automàticament ja que és possible que a l’instal·lar algun altre sistema operatiu o modificar la configuració aquest no funcioni correctament.
* **network**. Aquesta opció activa la xarxa. És interessant activar la xarxa si volem executar tasques que requereixen connexió a Internet.
* **root**. Aquesta opció permet accedir al terminal com a usuari root, fet que ens permetrà solucionar problemes amb aquest usuari, que té control total sobre el sistema. Podem sortir de la sessió del terminal escrivint l’ordre `exit`.
* **system-summary**. Aquesta opció presenta un resum del sistema que conté informació sobre la CPU, la connectivitat de xarxa i la utilització dels dispositius d’emmagatzematge.

#### Creació de còpies de seguretat

Hi ha molts factors que poden provocar la pèrdua de dades en un sistema informàtic. Els dispositius d’emmagatzematge poden fallar o podem eliminar informació per accident. Per evitar perdre les dades quan succeeixen aquests problemes hem de fer còpies de seguretat.

Una **còpia de seguretat** és l’emmagatzematge de les dades originals que estan al sistema per poder-les recuperar en cas de pèrdua.

Els sistemes GNU/Linux disposen de moltes eines per fer còpies de seguretat. En el cas del sistema Ubuntu GNU/Linux, una de les aplicacions més utilitzades per fer còpies de seguretat al **mode gràfic**, ja que és l’aplicació instal·lada per defecte, és _Còpies de seguretat_ també anomenada _Déjà Dup_. Aquesta aplicació permet fer còpies de seguretat de les dades de l’usuari de forma manual i automàtica, i també restaurar-les. Podeu observar la finestra de l’eina a la [figura.25](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig25).FiguraCòpies de seguretat![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/copies.png)

Per executar l’eina, anem al quadre de cerca de la barra superior i busquem l’aplicació pel nom _Còpies de seguretat_. Quan l’obrim podem veure un tauler a l’esquerra amb diferents opcions:

* **Resum**. Aquesta opció ens proporciona les opcions per crear i restaurar les còpies de seguretat.
* **Carpetes que cal desar**. En aquesta finestra podem seleccionar els directoris que volem incloure a la còpia de seguretat. El directori _/home_ de l’usuari ja es troba seleccionat per defecte. Per seleccionar altres directoris cal clicar el botó “+” i per eliminar-los el botó “-”.
* **Carpetes que cal ignorar**. En aquesta finestra podem seleccionar els directoris que no volem que s’incloguin a la còpia de seguretat. Per defecte, els directoris Paperera i Baixades ja es troben a la llista. Si volem ometre la còpia d’algun directori més, cliquem el botó “+”. Si alguna de les carpetes de la llista no volem que sigui ignorada, cliquem el botó “-”.
* **Ubicació de l’emmagatzematge**. Les còpies de seguretat es poden guardar en un directori d’un dispositiu d’emmagatzematge, de forma remota o fins i tot utilitzant serveis de tercers al núvol, com Google Drive. En els tres casos cal que indiquem el nom del directori de destí. Si triem l’opció _Servidor de xarxa_ per guardar el directori remotament també caldrà indicar les dades referents a la ubicació del servidor.
* **Planificació**. Aquesta opció permet planificar la realització de les còpies de seguretat. En aquesta finestra podem activar o desactivar l’opció de còpia de seguretat automàtica. Si activem l’opció podem seleccionar amb quina freqüència volem que es facin les còpies \(diàriament o setmanalment\) i quant de temps les volem mantenir \(sempre, un any o sis mesos\).

Per crear una còpia de seguretat anem a l’opció _Resum_ i seleccionem _Fes la còpia de seguretat ara_ i podrem veure una finestra amb una barra de progrés on es mostra l’estat de la còpia.

Per restaurar una còpia de seguretat cal anar a _Resum_ i clicar al botó _Restaura_. A continuació hem d’introduir des d’on volem restaurar la còpia de seguretat i seleccionar la còpia desitjada. En aquest cas també veurem una barra de progrés que ens indicarà l’estat de la restauració.

Al **mode ordre** trobem moltes utilitats que permeten fer còpies de seguretat, com ara les ordres `tar`, `cpio`, `dd`, `cp`, etc. Una de les ordres més utilitzades és la `tar`, que permet emmagatzemar una gran quantitat d’arxius en un únic arxiu.

Per a més informació sobre la utilització de l’ordre `tar` podeu consultar el punt “Compressió i descompressió d’arxius”, dins de l’apartat “Configuració de sistemes operatius lliures”, d’aquesta mateixa unitat.

Una altra ordre que s’utilitza força per copiar sistemes d’arxius complets és `dd`. Aquesta ordre permet fer i recuperar còpies de seguretat utilitzant un arxiu d’imatge. La seva sintaxi bàsica amb les opcions més utilitzades és:

* `dd if=origen of=destí`

On:

* **if=**. Significa arxiu d’entrada, en anglès _input file_, i especifica l’arxiu d’origen.
* **of=**. Significa arxiu de sortida, en anglès _output file_, i especifica l’arxiu de destí.

Per exemple, per fer una còpia de seguretat del dispositiu /dev/sda2 en un dispositiu extern que estigui muntat en /media/disc, l’ordre és: `dd if=/dev/sda2 of=/media/disc/arxiu.img` Si volem restaurar aquesta còpia de seguretat, farem servir l’ordre: `dd if=/media/disc/arxiu.img of=/dev/sda2`

Amb l’ordre `dd` només hem de realitzar còpies de seguretat de sistemes d’arxius desmuntats. Fer la còpia de seguretat d’un sistema d’arxius muntat pot donar com a resultat un sistema d’arxius inconsistent i restaurar-lo pot provocar la pèrdua de dades al dispositiu d’emmagatzematge.

### Registres del sistema i del programari d'aplicació

Els sistemes operatius GNU/Linux deixen constància de totes les activitats que es duen a terme durant el seu funcionament. Aquesta informació és guarda en un registre. L’encarregat de dur a terme aquesta tasca és un dimoni que s’executa en segon pla i rep la informació des dels programes que estan configurats per utilitzar-lo.

A Ubuntu 20.04, _systemd-jounarld_ és el dimoni encarregat d’escriure els registres referents al funcionament del sistema informàtic. La informació de registre recopilada s’emmagatzema en un arxiu binari. Aquestes dades no són accessibles amb un editor de text i és per aquest motiu que hem de fer servir les aplicacions o ordres corresponents per interactuar amb els registres. Aquest arxiu està situat al directori _/var/log/journal_.

Al **mode gràfic** podem fer servir l’eina _Registres_ per consultar els registres emmagatzemats. Podeu observar aquesta eina a la [figura.26](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig26).FiguraEina ‘Registres’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/registres.jpg)

En aquesta aplicació trobem dos taulers. El tauler de l’esquerra permet consultar els missatges referents a una categoria específica, mentre que el de la dreta permet visualitzar-los.

Les categories principals que trobem al tauler esquerre són aplicacions, sistema, seguretat i maquinari, tot i que també podem veure els missatges classificats com a importants o tots sense categoritzar.

Al tauler dret podem observar que en alguns missatges hi ha un número al final de la línia que indica que hi ha altres missatges relacionats amb aquests i que, de fet, el que té el número és l’últim de la llista.

Si cliquem sobre un dels missatge podem observar-ne més informació, com l’hora, la prioritat, l’aplicació que el genera, etc.

A la part superior dreta de la pantalla podem localitzar un missatge concret utilitzant la lupa. La mateixa barra de cerca que s’obre quan cliquem la lupa ens ofereix la possibilitat de filtrar la informació que volem cercar per camp com PID, UIC, GID, nom del procés, etc. o per temps, on podem indicar un interval de temps concret o els dies i hores on volem cercar el missatge.

Al costat de la lupa trobem una icona de descàrrega que ens serveix per guardar els missatges seleccionats en un arxiu per si necessitem consultar-los més endavant.

La mida del fitxer de registre, que si no es controla podria créixer indefinidament, es configura editant els arxius de configuració de systemd-journald amb un editor de text, i es pot definir com un percentatge de la mida del volum on està situat. Quan el fitxer de registre arriba a la seva mida màxima, les entrades de registre més antigues són eliminades i se’n creen de noves.

La configuració es fa al fitxer _**/etc/systemd/journald.conf**_ tot i que en alguns casos es poden crear també directoris de configuració. A _/etc/systemd/journald.conf.d_/ es poden trobar fitxers de configuració amb l’extensió .conf creats per paquets de programari instal·lats al sistema i que desitgen registrar canvis. Podeu observa l’arxiu de configuració a la [figura.27](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a3/continguts.html#fig27).FiguraArxiu de configuració ‘journald.conf’![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/journald.jpg)

Alguns dels paràmetres de configuració que podem trobar al fitxer són:

'Syslog'

_Syslog_ era el dimoni encarregat d’escriure els registres del sistema abans de la implementació de Systemd com a gestor de sistema i de serveis en algunes distribucions.

* **Storage**. Pot rebre els valors de “none” per desactivar l’emmagatzematge de registres, “volatile” per emmagatzemar els registres únicament en memòria i que estiguin accessibles temporalment a la ruta _/run/log/journal_; “persistent”, que emmagatzemarà els registres a la ruta _/var/log/journal_, i finalment “auto”, que funcionarà com a “persistent” si existeix el directori _/var/log/journal_ i en cas contrari actuarà com a “volatile”.
* **Compress**. Aquesta opció activa la compressió de les dades del registre amb “auto”, que comprimirà les dades de més de 512 bytes o es pot especificar una mida concreta a partir de la qual es comprimiran aquestes dades.
* **SystemKeepFree**. És un dels paràmetres que serveix per definir la mida del registre. Per defecte, systemd-journald deixarà lliure un 15% de la mida del volum on està situat el directori _/var/log/journal_ si no especifiquem un altre valor.
* **RuntimeKeepFree**. Serveix per definir la mida del registre. En cas que el registre estigui activat en mode “volatile” les dades no s’emmagatzemen definitivament.
* **ForwardToSyslog**. Permet redirigir els missatges que arriben a systemd-journald cap al dimoni syslog, i aquesta opció està activada per defecte.
* **MaxLevelStore**. Especifica el nivell dels registres que s’emmagatzemen al disc. Només s’emmagatzemaran els missatges d’un nivell igual o inferior a l’especificat. Els nivells estan ordenats de més greu \(“0” o “emerg”\) a menys greu \(7 o “debug”\). El valor per defecte és 7.

En el **mode ordre**, podem utilitzar l’ordre `journalctl` per visualitzar els registres. Si executem aquesta ordre sense cap paràmetre podem visualitzar tots els registres ordenats de més antic a més nou. Aquests registres constaran de milers i milers de línies, i les primeres columnes són les que mostren el dia i l’hora de l’esdeveniment. Aquesta hora sempre és l’hora local del sistema de quan es va registrar l’esdeveniment.

És evident que l’ús de l’ordre `journalctl` sense cap paràmetre no resulta còmoda, perquè en el moment de consultar els registres normalment busquem unes dades concretes. Les opcions més utilitzades són:

* **–since i -–until**. Permet mostrar els registres en unes dates i hores concretes.
* **-u**. Permet mostrar els registres d’un servei en concret.
* **\_PID i \_UID**. Permet mostrar els registres associats a un procés o un identificador d’usuari.
* **-k**. Mostra els registres del nucli.
* **-p**. Mostra els registres d’un nivell concret.

Ús de l'ordre 'journalctl'

A continuació podeu observar alguns exemples amb l’ordre `journalctl`:

* `journalctl /bin/login`. Mostra els registres de l’ordre `login`.
* `journalctl –since “2020-01-01” –until “2020-01-31 20:30”`. Permet obtenir tots els registres del mes de gener de 2020.
* `journalctl -u cron.service`. Aquesta ordre mostra únicament els registres de Cron.
* `journalctl _PID=3328`. Mostra els registres associats al procés 3328.
* `journalctl _UID=87`. Mostra els registres associats a l’usuari 87.
* `journalctl -p emerg`. Mostra els registres de nivell 0

### Verificació i documentació del procés d'administració d'un sistema operatiu

Després de tot el procés d’instal·lació, configuració i administració cal que verifiquem que el sistema funciona correctament i que documentem els processos que encara no ho estan.

Quan arribem al punt de documentar el procés d’administració segurament ja disposarem de la documentació dels processos anteriors, el d’instal·lació i configuració. Sempre es recomana anar documentant al llarg dels processos i no deixar tota la documentació per al final ja que podríem oblidar part de la informació.

Per a més informació sobre la gestió de la documentació podeu consultar els punts “Documentació del procés d’instal·lació i incidències” i “Verificació i documentació del procés de configuració d’un sistema operatiu”, dins dels apartats “Instal·lació de sistemes operatius lliures” i “Configuració de sistemes operatius lliures”, respectivament, d’aquesta mateixa unitat.

A la documentació que ja tenim sobre la instal·lació i configuració cal afegir la referent als usuaris i grups creats, els recursos compartits \(com directoris o impressores\) especificant quins són els permisos sobre els recursos i quina és la seva finalitat, les dades referents al manteniment del sistema i les incidències aparegudes durant el procés d’administració i la seva solució.

