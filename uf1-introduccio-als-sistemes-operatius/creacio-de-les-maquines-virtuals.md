# Màquines virtuals i virtualització

## Configuració de màquines virtuals

La virtualització s’està convertint en una tecnologia molt popular al sector informàtic, ja que permet executar diversos sistemes operatius i/o aplicacions en un únic equip informàtic. Per fer-ho, és necessari utilitzar un programari específic que ens permeti crear màquines virtuals o contenidors, els quals permeten l’execució de diferents sistemes operatius i/o aplicacions de forma simultània sense la necessitat de crear escenaris d’arrencada dual.

### Introducció a la virtualització

La tecnologia de virtualització ja existia a la **dècada de 1960**, però ha estat sempre una tecnologia aplicada a casos molt concrets i no d’un ús generalitzat. A principis del 2000, amb noves necessitats en les empreses pel que fa a les tecnologies de la informació, els enginyers van rescatar aquesta tecnologia \(que en cap cas s’havia deixat de fer servir\) i li van donar gran popularitat. A inicis del **segle XXI**, la majoria de les empreses tenien servidors físics que no permetien l’execució de les seves aplicacions en maquinari d’altres fabricants i això suposava un problema.

A mesura que la virtualització anava evolucionant, les empreses van poder utilitzar les aplicacions en altres maquinaris simulant diversos tipus i versions de sistemes operatius, fins i tot van començar a utilitzar un mateix equip informàtic per executar diversos sistemes operatius. Amb l’aplicació de la virtualització, els servidors es van començar a utilitzar de forma més eficient o van quedar en desús i van permetre a les empreses reduir les despeses relacionades amb la compra, instal·lació, refrigeració i manteniment de servidors.

L’aplicació de la virtualització a les empreses ha reduït la dependència d’un únic proveïdor de maquinari o de sistema operatiu i és tan freqüent el seu ús que moltes d’elles ja disposen de programari específic per l’administració de la virtualització.

Actualment, donada la gran evolució del maquinari pel que fa a la seva capacitat de procés, utilitzar un sistema informàtic complet per executar un únic sistema operatiu i algunes poques aplicacions o serveis de forma simultània de ben segur suposa la infrautilització d’aquests equips; és a dir, s’està **malbaratant capacitat de procés**. Aquest problema es fa més evident quan es tracta de servidors, com pot ser un servidor web o un servidor de bases de dades, on les càrregues de treball són puntuals. Com solucionar aquesta infrautilització? La idea és crear sistemes virtuals, els quals contenen el sistema operatiu i les aplicacions o serveis necessaris per donar resposta a una necessitat, i que es poden moure entre diferents sistemes físics en el moment en què sigui necessari per maximitzar la utilització d’aquests sistemes.

### Exemple pràctic de virtualització

Podem imaginar que una empresa té tres servidors físics individuals, cadascun amb el seu propi propòsit. Cada servidor utilitza només el 20% dels seus recursos, és a dir, una petita part del seu potencial. La virtualització permet utilitzar un únic servidor per realitzar les tasques que tenien assignades els tres servidors físics de forma que aquest únic servidor consumirà el 60% dels seus recursos.

La virtualització permet crear una o més màquines virtuals a partir d’un equip informàtic real utilitzant un programari específic. D’aquesta forma podem executar diversos sistemes operatius i aplicacions de forma aïllada en un únic equip informàtic real.

La **virtualització** permet que diversos sistemes operatius virtuals es puguin executar simultàniament en un mateix equip informàtic compartint els recursos físics disponibles com el processador, la memòria, els discos durs i els dispositius d’entrada/sortida.

A la virtualització, els sistemes operatius que s’executen en una màquina virtual es comporten de la mateixa forma com ho farien a un equip físic real i creuen que tenen disponibles tots els recursos de maquinari, com ara processador, memòria RAM, discos durs i interfícies de xarxa. Durant el procés de configuració de la màquina virtual és possible definir quin maquinari serà ofert a la màquina virtual.

Per exemple, en un equip amb 4 processadors i 8 GB de memòria RAM, la màquina virtual es pot configurar per oferir únicament 2 processadors i 4 GB de memòria RAM. Una vegada instal·lat i configurat un sistema operatiu a una màquina virtual, les aplicacions en ell instal·lades i fins i tot altres equips informàtics que poden connectar-se a ell, no troben cap diferència entre aquest sistema operatiu virtual i un sistema operatiu real. En alguns tipus de virtualització, el sistema operatiu es modifica lleugerament perquè sigui conscient que es troba virtualitzat i es relacioni puntualment amb l’equip físic de forma directa. En aquest cas estem parlant de **paravirtualització**.

El concepte de la virtualització no només fa referència a equips físics que poden contenir diferents sistemes operatius, sinó que també pot referir-se a altres àmbits tecnològics, com l’emmagatzematge, les xarxes o les aplicacions. La virtualització es fa servir en diferents àmbits tecnològics i alguns exemples són els següents:

* **Virtualització de servidors**. Gràcies a la virtualització podem utilitzar diferents màquines virtuals \(cadascuna de les quals pot gestionar un servei\) en un únic equip físic en comptes d’utilitzar diferents equips físics per oferir cada servei. Això comporta un estalvi en maquinari, electricitat i recursos humans, ja que només caldrà gestionar un únic dispositiu on estaran virtualitzats els diferents servidors que una empresa pugui necessitar. Un altre avantatge de la virtualització de servidors és la facilitat per fer còpies de seguretat d’aquests servidors allotjats en màquines virtuals.
* **Virtualització d’escriptori**. Amb aquest tipus de virtualització podem emmagatzemar un un únic equip informàtic l’espai de treball personal de molts usuaris en comptes d’utilitzar diversos equips informàtics de forma local. Aquesta virtualització redueix costos i permet que els usuaris puguin treballar des de qualsevol lloc.
* **Virtualització de xarxes**. També coneguda com a virtualització de funcions de xarxa o NFV \(_Network Functions Virtualization_\). Amb aquesta virtualització podem utilitzar programari per fer les tasques que acostumen a fer els dispositius de xarxa reals. Aquesta virtualització permet desplegar elements de xarxa ràpidament quan l’empresa ho necessita sense dependre del maquinari.
* **Virtualització d’aplicacions.** Amb aquest tipus de virtualització podem executar aplicacions independentment de les característiques de l’entorn on s’executen. Aquestes aplicacions virtualitzades habitualment s’executen de forma remota en un servidor i l’usuari final obté la sensació que està fent-la servir de manera tradicional al seu dispositiu, sigui un sistema informàtic o un dispositiu mòbil.
* **Virtualització d’emmagatzematge.** Aquesta virtualització també es coneix com a emmagatzematge definit per programari o SDS \(_Software-Defined Storage_\). Aquest tipus de virtualització permet agrupar els elements d’emmagatzematge físics i lògics en un únic magatzem. Aquest fet millora la seva gestió que es pot dur a terme des d’un únic lloc central.

#### Màquina real, màquina virtual i contenidors

Les **màquines reals** són aquelles que tenen components físics \(processador, memòria RAM, dispositius d’emmagatzematge, etc.\) i on s’executa un programari base que permet la interacció amb aquests components físics. Si parlem d’una **màquina virtual**, estem parlant d’un entorn que funciona com un sistema informàtic virtual, amb els seus propis components virtuals \(processador, memòria RAM, dispositius d’emmagatzematge, etc.\) que es creen a partir dels components físics reals.

Per poder crear i utilitzar una màquina virtual utilitzem un programari específic que ha de trobar-se en execució a la màquina real. Aquest programari s’encarrega de gestionar els components físics de la màquina real perquè la màquina virtual els pugui utilitzar.

En un entorn de virtualització, la màquina real s’anomena _màquina amfitrió_ mentre que la màquina o màquines virtuals que creem s’anomenen _màquines hostes_.

La **màquina virtual o màquina hoste** \(_guest_ en anglès\) és la màquina que funciona fent servir els recursos de la **màquina real o màquina amfitrió** \(_host_ en anglès\).

Podem **classificar la virtualització** en tres tipus, en funció del programari específic que utilitzen per generar l’entorn de virtualització:

* Virtualització amb hipervisor de tipus 1.
* Virtualització amb hipervisor de tipus 2 o monitor de màquina virtual.
* Virtualització basada en contenidors.

L’**hipervisor** és el programari encarregat de crear una capa d’abstracció per comunicar la màquina real amb les màquines virtuals. La seva missió és assignar els recursos informàtics a les màquines virtuals a mesura que els van necessitant.

**Virtualització amb hipervisor de tipus 1**

En aquest cas, la virtualització es duu a terme utilitzant un programari anomenat **hipervisor de tipus 1 o hipervisor natiu**. En aquest cas, l’hipervisor s’executa directament sobre l’equip informàtic físic. Poder accedir directament al maquinari real sense la necessitat d’utilitzar un sistema operatiu ofereix un major rendiment, ja que les màquines virtuals podran accedir al maquinari d’una forma més ràpida.

Aquest tipus de virtualització és molt segura i estable, ja que els sistemes operatius virtuals són totalment independents uns d’altres i la fallada d’un sistema operatiu d’una de les màquines virtuals no afectarà la resta de sistemes operatius i els permetrà continuar funcionant. Per aquest motiu aquest tipus de virtualització està molt orientada a **entorns professionals** que necessiten aquesta estabilitat.

**Virtualització amb hipervisor de tipus 2 o monitor de màquina virtual**

En aquest cas, la virtualització es duu a terme amb un programari anomenat **hipervisor de tipus 2**, també conegut com a **hipervisor allotjat o monitor de màquina virtual**. Aquest programari s’instal·la i s’executa sobre el sistema operatiu de la mateixa forma que es podria fer amb qualsevol altra aplicació com Microsoft Word o Mozilla Firefox.

En aquests tipus d’hipervisor podem executar màquines virtuals que s’executaran un nivell per sobre de l’hipervisor. L’estabilitat i el rendiment són menors que la que proporciona l’hipervisor de tipus 1, ja que tota la càrrega la suporta un únic sistema operatiu, anomenat sistema operatiu amfitrió. Si falla aquest sistema operatiu amfitrió, fallaran tots els sistemes operatius convidats \(els sistemes operatius executats a les màquines virtuals\). Per una altra banda, aquest tipus de virtualització permet que el sistema operatiu amfitrió no es vegi afectat en el seu rendiment perquè té accés directe al maquinari.

Per aquests avantatges i inconvenients, aquest tipus de virtualització està més orientada a **entorns de prova, docència o domèstics**.

A la  figura podeu observar la diferència entre els hipervisors de tipus 1 i tipus 2

![Hipervisors](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/smx_m02_u1_007_n.png)

**Contenidors - containers**

Tant els hipervisors de tipus 1 com els de tipus 2 ofereixen a les màquines hostes un maquinari sobre el qual instal·lar els sistemes operatius convidats. És per això que podem veure aquest tipus de virtualització com una virtualització basada en maquinari.

En un possible escenari, amb una màquina amfitriona que pot contenir desenes o inclús centenars de màquines hostes on totes elles \(tant l’amfitriona com les hostes\) funcionen amb el mateix sistema operatiu, pot semblar un malbaratament de recursos realitzar desenes o centenars d’instal·lacions d’un mateix sistema operatiu a les màquines hostes. A partir d’aquest supòsit sorgeix un concepte similar que no necessita la instal·lació de sistemes operatius convidats, perquè les aplicacions utilitzen el mateix nucli del sistema operatiu amfitrió per no malbaratar recursos; aquesta tècnica és coneix com **virtualització basada en contenidors**.

Amb la virtualització basada en contenidors, no tenim un sistema operatiu completament instal·lat executant-se en cada màquina virtual sinó que únicament hi ha un únic sistema operatiu complet al sistema informàtic gestionant tot el maquinari i tan sols s’ofereixen les parts necessàries del sistema amfitrió per permetre una execució aïllada i segura de les diferents aplicacions. Tots aquests contenidors comparteixen el nucli del sistema operatiu així com les aplicacions del sistema i les llibreries necessàries per executar programes. Cal tenir en compte que en aquest tipus de virtualització, els components compartits entre els diferents contenidors són únicament de lectura.

A la figura podeu observar la diferència entre la virtualització amb hipervisor i la virtualització basada en contenidors.

![Hipervisors vs contenidors](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/smx_m02_u1_005.png)

Màquines virtuals de sistema vs. màquines virtuals de procés

En aquest mòdul quan parlem de màquines virtuals sempre ens referim a les màquines virtuals de sistema que són les que **simulen un equip informàtic complet**. Aquestes màquines disposen de tots els recursos virtuals i poden executar qualsevol sistema operatiu sempre que la màquina amfitriona on es troben allotjades ho suporti.

  
Cal tenir en compte que existeix un altre tipus de màquines virtuals anomenades **màquines virtuals de procés** que no simulen un equip informàtic sencer. Aquestes màquines només executen un procés en concret, com pot ser una aplicació. Com a exemple d’aquests tipus de màquines trobem les màquines virtuals Java o .NET. Aquestes màquines permeten als programadors desenvolupar aplicacions per diferents sistemes operatius, ja que és la màquina virtual de procés la que s’encarrega de la seva execució independentment del sistema operatiu de l’equip informàtic.

#### Avantatges i inconvenients

La virtualització és una tecnologia que està generant molt d’interès, sobretot a partir de l’aparició de la computació al núvol. Trobem una gran quantitat de beneficis en la utilització de la virtualització, però també una varietat de desavantatges que cal mencionar.

Entre els avantatges de les màquines virtuals podem destacar els següents:

* **Execució de diferents sistemes operatius de forma simultània**. La virtualització permet executar més d’un sistema operatiu a la vegada en un mateix equip informàtic.
* **Execució d’aplicacions pròpies d’un sistema operatiu en un sistema operatiu diferent**. Podem executar aplicacions natives d’un sistema operatiu en un altre sistema operatiu amfitrió amb característiques diferents.
* **Execució de sistemes operatius antics**. Podem instal·lar sistemes operatius antics, com MS-DOS, encara que el maquinari de l’equip real no sigui compatible amb aquest sistema.
* **Fer paquets de programari**. Podem empaquetar en màquines virtuals instal·lacions de programari complicades o excessivament llargues per tenir-les disponibles en qualsevol moment. Un cop instal·lada i configurada, una màquina virtual pot copiar-se o transportar-se entre diferents sistemes informàtics utilitzant el mateix hipervisor.
* **Recuperació i proves**. Gràcies a la virtualització podem guardar l’estat particular d’una màquina virtual i retornar a un estat anterior si cal. Gràcies a això, podem experimentar amb nous sistemes operatius sense por a equivocar-nos.
* **Reducció de costos**. La virtualització pot reduir els costos de maquinari i electricitat. Podem executar moltes màquines virtuals en un únic sistema informàtic en comptes d’executar molts sistemes informàtics físics independents.

Sobre els avantatges de la tecnologia de contenidors podem destacar:

* **Aïllament d’aplicacions**. Els contenidors empaqueten els recursos necessaris per al funcionament de les aplicacions. Aquests paquets es troben completament aïllats uns dels altres i les aplicacions funcionen independentment d’altres contenidors.
* **Facilitat d’instal·lació**. Els contenidors ja inclouen l’aplicació i tots els components necessaris com llibreries, dependències i arxius de configuració per compensar les diferències entre sistemes operatius. La seva instal·lació es pot fer utilitzant una única ordre.
* **Independència del sistema informàtic**. Els contenidors es poden transportar fàcilment entre sistemes informàtics sempre que el sistema operatiu tingui suport pel tipus de contenidor.
* **Pèrdues de virtualització mínimes**. Mentre que la virtualització basada en maquinari comporta una pèrdua de rendiment a causa de l’hipervisor, els contenidors, com que no l’utilitzen, redueixen aquesta pèrdua al mínim.
* **Administració unitària**. Existeix la possibilitat de gestionar diferents contenidors amb les mateixes eines automatitzant totes les aplicacions de forma centralitzada.

Els principals inconvenients de les màquines virtuals són:

* **Rendiment inestable**. Quan executem diverses màquines virtuals en una mateixa màquina amfitrió, el rendiment de cada màquina virtual dependrà de la càrrega de treball del sistema operatiu amfitrió i de les altres màquines virtuals en execució.
* **Disminució de l’eficiència**. Una màquina virtual no és tan eficient accedint als components físics com la mateixa màquina real.
* **Dependència de l’hipervisor**. Només és possible simular el maquinari que es trobi suportat per l’hipervisor de virtualització. A més, com cada hipervisor utilitza les seves pròpies tecnologies, no hi ha uniformitat en els formats i la portabilitat entre hipervisors és complicada.
* **Dependència de la màquina amfitrió**. Les màquines utilitzades per virtualitzar acostumen a ser més potents i per tant més cares. Per una altra banda, una fallada en un component físic d’una màquina amfitrió afecta a totes les màquines virtuals que allotja.

Als contenidors els principals inconvenients són:

* **Dependència del sistema operatiu amfitrió**. Només és possible utilitzar els contenidors suportats pel sistema operatiu amfitrió.
* **Consum de recursos**. Tot i que els contenidors consumeixen els recursos de forma més eficient que les màquines virtuals, encara estan per sota del rendiment d’una màquina real, ja que necessiten gestionar la interfície entre el contenidor i el sistema informàtic amfitrió.
* **Emmagatzematge de dades**. Per defecte, totes les dades dins d’un contenidor desapareixen quan s’apaga el contenidor. Actualment resulta difícil trobar una forma d’emmagatzemar les dades de forma persistent.
* **Aplicacions gràfiques**. Els contenidors van ser dissenyats per allotjar aplicacions de tipus servidor que no necessiten una interfície gràfica. Les aplicacions gràfiques poden no funcionar correctament.

### Programari per a la creació de màquines virtuals

El programari per a la creació de màquines virtuals, conegut com a **hipervisor**, permet executar diferents sistemes operatius en un mateix equip informàtic. Per exemple, podem executar Linux al nostre Windows o executar Windows en un equip Mac juntament amb totes les seves aplicacions existents. A la [figura.3](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig3) podem observar l’execució d’un sistema Windows a un equip amb sistema operatiu Linux.FiguraExecució de Windows 10 en un sistema operatiu Ubuntu![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/escriptori.png)

Els hipervisors de tipus 1 més coneguts són Microsoft Hyper-V, Citrix Hypervisor \(XenServer\) i WMware ESXi. Mentre que Oracle VirtualBox, VMware Workstation i Parallels Desktop són exemples d’hipervisors de tipus 2.

Hipervisors de tipus 1:

* **Microsoft Hyper-V**. És un programari de virtualització de Microsoft basat en un hipervisor de tipus 1 per sistemes informàtics basats en processadors AMD i Intel. A Windows 10 només trobem aquesta característica a les edicions Pro, Education i Enterprise. Aquest programari és una opció molt interessant pels usuaris de Windows gràcies a la seva integració amb el sistema operatiu.
* **Citrix Hypervisor \(XenServer\)**. És un programari de virtualització de Citrix Systems, Inc optimitzat per càrregues de treball d’escriptori i aplicacions virtuals basat en l’hipervisor de Xen Project, un hipervisor de codi obert desenvolupat per la Universitat de Cambridge.
* **WMware ESXi**. És un programari de virtualització produït per WMware Inc, una filial d’EMC Corporation. WMware ESXi és l’hipervisor de les diferents solucions de virtualització empresarial de Wmware Inc.

Hipervisors de tipus 2:

* **VMware Workstation**. VMware Workstation Pro és un hipervisor pels sistemes operatius Windows i Linux que permet als usuaris configurar màquines virtuals. Existeix una versió gratuïta anomenada VMware Workstation Player dirigida a l’ús personal.
* **Parallels Desktop**. És un programari de virtualització de maquinari per equips que funcionen amb sistema operatiu Mac OS X desenvolupat per l’empresa de programari Parallels.
* **Oracle VirtualBox**. Aquesta és una aplicació de virtualització multiplataforma. VirtualBox és una aplicació gratuïta i fàcil d’utilitzar. Podem instal·lar aquest programari en equips basats en Intel o AMD que executin qualsevol sistema operatiu, Windows, Linux, Mac OS X, Solaris, etc.

#### Instal·lació i configuració de VirtualBox

VirtualBox és una aplicació formada per dos paquets principals:

* **Paquet bàsic**. Aquest paquet està format per tots els components principals de VirtualBox. És de codi obert i té llicencia _GNU General Public License V2_.
* **Paquets d’extensió**. Aquests paquets amplien la funcionalitat del paquet base de VirtualBox. VirtualBox proporciona un paquet d’extensió únic disponible a la seva pàgina web. Actualment el paquet d’extensió de VirtualBox ofereix suport per USB 2.0 i 3.0, permet dur a terme el xifratge del disc dur i possibilita l’arrancada per xarxa del sistema informàtic, entre altres opcions.

Per instal·lar VirtualBox cal anar a la pàgina web oficial d’Oracle \([www.oracle.com](https://www.oracle.com/es/index.html)\) i triar la versió de VirtualBox que es correspongui al nostre sistema operatiu i equip informàtic, per exemple per un equip Windows 10 de 64 bits triem l’opció _Windows hosts_ com podeu observa a la [figura.4](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig4).

Llicència GNU GPL

La Llicència Pública General GNU és un tipus de llicència per a programari que permet la còpia, distribució \(comercial o no\) i modificació del codi, sempre que qualsevol modificació es continuï distribuint amb la mateixa llicència GPL. La llicència GPL no permet la distribució de programes executables sense el codi font corresponent o una oferta de com obtenir-lo gratuïtament. És la llicència lliure de programari més utilitzada.FiguraInstal·lació de VirtualBox![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vb1.png)

Caldrà anar seguint els passos que ens proposa l’assistent d’instal·lació, el primer pas de l’assistent ens informa que es procedirà a instal·lar VirtualBox al nostre sistema operatiu, el segon pas ens demana que seleccionem les característiques que volen instal·lar, per defecte deixem seleccionades les característiques bàsiques predeterminades i continuem avançant clicant el botó _Següent_, podeu observar aquests dos primers passos a la [figura.5](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig5) i [figura.6](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig6).FiguraAssistent d’instal·lació de VirtualBox \(I\)![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vb2.png)FiguraAssistent d’instal·lació de VirtualBox \(II\)![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vb3.png)

Al tercer pas de l’assistent d’instal·lació podem triar crear les icones i accessos directes que ens puguin ser útils, ho podeu observar a la [figura.7](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig7).FiguraAssistent d’instal·lació de VirtualBox \(III\)![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vb4.png)

Durant la instal·lació ens demanarà confirmació per instal·lar diferents controladors pels dispositius virtuals, a la [figura.8](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig8) i [figura.9](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig9) podeu observar com VirtualBox necessita reiniciar la connexió de xarxa de forma temporal i com sol·licita autorització per instal·lar un nou controlador, respectivament.FiguraAssistent d’instal·lació de VirtualBox \(IV\)![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vb5.png)FiguraAssistent d’instal·lació de VirtualBox \(V\)![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vb7.png)

Després d’instal·lar els arxius necessaris, l’assistent ens mostrarà una finestra on ens informa que la instal·lació està completa. Podeu observar aquesta finestra a la [figura.10](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig10).FiguraAssistent d’instal·lació de VirtualBox \(VI\)![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vb8.png)

**Especificitats de la instal·lació de VirtualBox en Ubuntu**

Per instal·lar VirtualBox a Ubuntu existeixen dues possibilitats. La primera és fer servir el programari disponible a la web de VirtualBox que Oracle, la companyia que desenvolupa l’hipervisor, posa a disposició dels internautes en la pàgina de descàrregues. En aquesta pàgina hi ha disponibles versions per les diferents distribucions de GNU/Linux, incloent-hi Ubuntu. En aquest cas cal descarregar el fitxer .deb i instal·lar-lo amb el gestor de paquets gràfic.

La segona possibilitat és fer servir el centre de programari d’Ubuntu anomenat Ubuntu Software. Aquest centre de programari, similar a la botiga d’aplicacions dels dispositius mòbils Android, o a la botiga d’aplicacions de Microsoft Windows, disposa de diferents programes que han estat testejats per funcionar amb el Sistema Operatiu. Al quadre de cerca simplement cal buscar VirtualBox i ens permetrà la instal·lació de l’aplicatiu fent clic al botó “Instal·lar”.

**Configuració de VirtualBox**

Per accedir a la finestra de configuració global de VirtualBox cal seleccionar _Fitxer &gt; Preferències_. En aquesta finestra, que podeu observar a la [figura.11](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig11), trobem la configuració global de VirtualBox que s’aplica a totes les màquines virtuals de l’usuari actual. Al cas de la secció _Extensions_, les noves funcionalitats que instal·lem amb els paquets d’extensió s’aplicaran tant a les màquines virtuals com a l’aplicació.FiguraConfiguració global de VirtualBox![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/general.png)

En aquesta finestra trobem disponibles les següents seccions:

* **General**. Permet a l’usuari especificar la carpeta per defecte pels arxius de les màquines virtuals i a la biblioteca d’autenticació VRDP.
* **Entrada**. Permet a l’usuari especificar la tecla especial _Host_. Aquesta és la tecla que permet gestionar si el punter es troba a la màquina virtual o a les finestres del sistema operatiu amfitrió. Aquesta tecla també s’utilitza per dur a terme determinades accions amb la màquina virtual.
* **Actualització**. Permet a l’usuari especificar les opcions de configuració de les actualitzacions.
* **Llengua**. Permet a l’usuari triar l’idioma desitjat per treballar amb la interfície gràfica de VirtualBox.
* **Pantalla**. Permet a l’usuari poder especificar la resolució \(amplada i alçada\) del monitor. Permet establir un factor d’escala predeterminat per tots els monitors dels sistemes operatius convidats i augmentar les finestres de les màquines virtuals quan el punter ratolí passi per sobre.
* **Xarxa**. Permet configurar els detalls de les xarxes NAT, com el nom, l’adreça ip, la màscara de la xarxa i el reenviament de ports entre altres opcions. A la dreta del quadre xarxes NAT trobem les opcions per crear, modificar o eliminar xarxes NAT.
* **Extensions**. Permet administrar i comprovar els paquets d’extensió instal·lats. Per instal·lar el paquet d’extensió cal descarregar-lo de la pàgina web oficial i clicar a la icona anomenada _Afegeix un paquet nou_. En aquesta mateixa finestra podem tant afegir com eliminar paquets d’extensió com podeu observar a la [figura.12](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig12).
* **Servidor intermediari**. Permet configurar un servidor proxy HTTP que farà d’intermediari entre les connexions del client i un servidor de destí.

FiguraAdministració d’extensions de VirtualBox![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/extension.png)

#### Creació de màquines virtuals

Un cop instal·lat el programari per a la creació de màquines virtuals i les extensions recomanades ja podem començar a crear les màquines virtuals. Per accedir al programari de creació de màquines virtuals, buscarem el programari al menú de programes o aplicacions en funció del sistema operatiu instal·lat al maquinari amfitrió.

Quan iniciem VirtualBox per primer cop veurem la finestra que podeu observar a la [figura.13](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig13).

Aquesta finestra es coneix com a finestra de gestió VirtualBox. Al tauler de l’esquerra trobem la llista amb totes les màquines virtuals que tenim creades, si encara no hem creat cap màquina virtual, aquesta llista estarà buida. El tauler de la dreta mostra les propietats de la màquina virtual seleccionada al tauler esquerre, mentre no tinguem màquines virtuals creades, aquest tauler mostrarà un missatge de benvinguda.FiguraFinestra de gestió de VirtualBox![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/benvinguda.png)

Per crear una nova màquina virtual, accedim a aquesta finestra de gestió i seleccionem l’opció _Nova_ per accedir a l’assistent de creació de màquina virtual. Durant totes les finestres que ens mostrarà aquest assistent introduirem les dades que necessitarà el programari per crear la màquina virtual.

Podeu observar la primera finestra de l’assistent a la [figura.14](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig14).FiguraCreació d’una nova màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/pas1.png)

En aquesta primera finestra, l’assistent ens demanarà les següents dades:

* **Nom**. El nom que triem per la màquina virtual també serà el nom que utilitzaran els arxius de la màquina virtual al disc dur de la màquina amfitrió.
* **Carpeta de màquines**. En aquesta opció seleccionem l’espai de disc on volem emmagatzemar els arxius necessaris per a la creació de la màquina virtual. Per defecte, es mostra la ruta predeterminada a les preferències del programa.
* **Tipus**. En aquest apartat seleccionem el tipus de sistema operatiu que volem instal·lar. Si volem instal·lar un sistema operatiu que no trobem a la llista, seleccionem l’opció _Altres_. Depenent del sistema operatiu que triem, VirtualBox farà una configuració inicial per complir amb els requisits del sistema operatiu convidat.
* **Versió**. En aquest apartat seleccionem la versió del sistema operatiu que volem instal·lar.

A la següent finestra de l’assistent seleccionem la memòria RAM que VirtualBox assignarà a la màquina virtual cada vegada que s’iniciï. La quantitat de memòria RAM seleccionada en aquesta opció s’agafarà de la màquina amfitrió i s’assignarà al sistema operatiu convidat, per tant hem de triar aquesta quantitat acuradament, ja que no estarà disponible pel sistema amfitrió. Podeu observar aquesta pantalla a la [figura.15](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig15).FiguraSelecció de memòria RAM per a la màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/pas2.png)

Assignació de memòria RAM a la màquina virtual

Si la màquina amfitrió disposa de 8 GB de memòria RAM i assignem 2 GB de memòria RAM a la màquina virtual, només disposarem de 6 GB de memòria RAM al nostre equip mentre s’estigui executant la màquina virtual. Si executem dues màquines virtuals iguals, de forma simultània, només disposarem de 4 GB de memòria RAM al sistema amfitrió. Sempre hem de comprovar que disposem de suficient memòria RAM al sistema operatiu amfitrió perquè el sistema pugui funcionar amb normalitat i de forma estable.

A la següent finestra, cal especificar si volem afegir un disc dur virtual a la nova màquina virtual creada. Ho podeu observar a la [figura.16](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig16).

Les opcions que trobem en aquesta finestra són les següents:

* **No afegir un disc dur virtual**. Aquesta opció crea la màquina virtual sense afegir cap disc dur. Si triem aquesta opció, VirtualBox ens avisarà que no podrem instal·lar cap sistema operatiu a la màquina fins que no afegim un disc dur. Només podem iniciar la màquina utilitzant un disc òptic virtual o des d’una xarxa.
* **Crear un disc dur virtual ara**. Aquesta opció permet crear un nou disc dur virtual buit. Aquesta és l’opció que seleccionem quan estem creant una màquina virtual per primer cop.
* **Utilitzar un disc dur virtual existent**. Amb aquesta opció podem triar un arxiu que ja contingui un disc dur virtual.

FiguraCreació d’un disc dur virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/pas3.png)

Si triem les opcions _No afegir un disc dur virtual_ o _Utilitzar un disc dur virtual existent_ només caldrà clicar al botó _Crear_ per crear la nova màquina virtual que a partir d’aquest moment, trobarem al tauler de l’esquerra de la finestra de gestió de VirtualBox amb el nom que li hem assignat.

Si seleccionem l’opció **Crear un disc dur virtual ara**, anirem a l’assistent de creació de nou disc dur virtual. Aquest assistent ens ajudarà a crear un nou arxiu de disc dur virtual com podeu observar a la [figura.17](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig17).FiguraElecció del format del disc dur virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/pas4.png)

En un primer pas, caldrà seleccionar el tipus d’arxiu de disc dur virtual que volem crear. Les opcions disponibles són:

* **VDI \(**_**VirtualBox Disk Image**_**\)** . Aquest és el format natiu que utilitza VirtualBox per crear el disc dur virtual.
* **VMDK \(**_**VirtualBox Machine Disk**_**\)** . Aquest és el format que utilitzen altres aplicacions de creació de màquines virtual, com per exemple VMWare. VirtualBox suporta aquest format i pot fer-ho servir. Podem escollir aquesta opció si volem canviar discos durs virtuals entre VirtualBox i VMWare.
* **VHD \(**_**Virtual Hard Disk**_**\)**. VirtualBox també suporta aquest format que és l’utilitzat pel programari de creació de màquines virtuals de Microsoft.

Podem seleccionar altres opcions si cliquem el botó _Mode expert_ que són:

* **HDD** \(_Parallels Hard Disk_\). Format propietari que utilitza l’empresa Parallels i que utilitzen els sistemes Mac OS X.
* **QCOW \(**_**QEMU Copy-On-Write**_**\)** i **QED \(**_**QEMU enhanced disk**_**\)** . Són els formats d’arxiu per arxius d’imatge de disc utilitzat per l’aplicació QEMU.

Al següent pas, veurem que VirtualBox ens permet decidir si volem que el fitxer de disc dur creixi a mesura que s’utilitza o bé que es creï amb una mida fixa, com podeu observar a la [figura.18](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig18).FiguraTipus d’ubicació del disc dur virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/pas5.png)

Les opcions disponibles en aquesta finestra de l’assistent són:

* **Ubicat de forma dinàmica**. En aquest cas, l’arxiu va augmentant la seva mida a mesura que es van introduint dades al disc dur virtual.
* **Mida fixa**. En aquest cas, es reserva tot l’espai assignat al disc dur virtual al disc dur amfitrió.

Al tercer pas, ens demanarà que introduïm el nom del disc dur virtual i seleccionem la seva mida com podeu observar a la [figura.19](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig19). Per evitar que el disc dur del sistema operatiu amfitrió es que quedi sense espai disponible, VirtualBox limita la mida de l’arxiu de disc dur virtual.FiguraAssignació de la mida del disc dur virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/pas6.png)

Per últim cal clicar al botó _Crear_ per crear la nova màquina virtual. A partir d’aquest moment, trobarem la màquina virtual al tauler de l’esquerra de la finestra de gestió de VirtualBox amb el nom que li hem assignat.

És possible utilitzar el mode expert per agilitzar el procés de creació de la màquina virtual, ja que ens permet fusionar diversos passos en un de sol.

**Instal·lació de 'Guest Additions'**

Les eines _Guest Additions_ de VirtualBox són un complement que podem instal·lar a les màquines virtuals que creem i que permet afegir noves funcionalitats i millorar el rendiment de la màquina virtual. Aquestes eines només es poden instal·lar després de la instal·lació del sistema operatiu convidat i no abans.

Aquestes eines ens permeten donar funcionalitats avançades per millorar la interacció entre la màquina virtual i la màquina amfitrió. Algunes d’aquestes funcions són:

* **Suport per carpetes compartides**. Podem compartir carpetes entre la màquina virtual i la màquina amfitrió que ens permetrà intercanviar arxius fàcilment.
* **Porta-retalls compartit**. El porta-retalls de la màquina virtual i de la màquina amfitrió poden compartir-se de forma que podrem fer servir les opcions de copiar i enganxar entre les màquines.
* **Arrossegar i deixar anar**. Podrem arrossegar i deixar anar elements des d’una màquina a una altra aprofitant que el porta-retalls es troba compartit.
* **Ratolí integrat**. Podrem desplaçar el punter del ratolí entre la màquina virtual i amfitrió sense la necessitat d’utilitzar tecles per entrar i sortir de les màquines virtuals.
* **Acceleració 2D i 3D**. Podrem utilitzar les característiques d’acceleració 2D i 3D a la màquina virtual.

La instal·lació de les Guest Additions pot variar segons el sistema operatiu convidat. En qualsevol cas, els **passos** que cal seguir per fer la instal·lació són els següents:

1. Inserim la imatge de CD de les _Guest Additions_, per fer-ho anem a _Dispositius &gt; Insereix la imatge de CD de les Guest Additions_.
2. Esperem que aparegui un missatge del sistema operatiu que indica que el sistema està preparat per executar aquestes eines. \(No en tots els sistemes operatius apareix aquest missatge\).
3. Utilitzem l’eina de gestió d’arxius del sistema operatiu per localitzar l’arxiu d’instal·lació de les Guest Additions i l’instal·lem.
4. Reiniciem la màquina virtual perquè VirtualBox faci efectius els canvis.

#### Configuració de màquines virtuals

La configuració del programari de creació de màquines virtuals i de les mateixes màquines virtuals permet millorar el seu rendiment. La configuració d’una màquina virtual de VirtualBox pot realitzar-se utilitzant la interfície gràfica o l’eina VBoxManage. La interfície gràfica permet dur a terme la configuració d’una forma més agradable i intuïtiva mentre que l’eina VBoxManage permetrà introduir la configuració en forma d’ordres de text utilitzant l’intèrpret d’ordres del sistema operatiu amfitrió.

A continuació, mostrem els passos per configurar els paràmetres d’una màquina virtual utilitzant la interfície gràfica de VirtualBox. Per anar a la finestra de configuració de la màquina virtual, cal seleccionar la màquina virtual i clicant amb el botó dret sobre ella, seleccionar l’opció _Paràmetres_. Els passos són els següents:

1. Configuració general
2. Configuració del sistema
3. Configuració de pantalla
4. Configuració d’emmagatzematge
5. Configuració d’àudio
6. Configuració de xarxa
7. Configuració de ports en sèrie
8. Configuració d’USB
9. Configuració de carpetes compartides
10. Configuració de la interfície d’usuari

**Configuració general**

A la finestra _Paràmetres_, a la secció _General_ podem configurar els paràmetres fonamentals de la màquina virtual. Les opcions que trobem estan organitzades en les pestanyes _Bàsic_, _Avançat_, _Descripció_ i _Xifratge de disc_ com podeu observar a la [figura.20](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig20).FiguraConfiguració general de la màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/generalmv.png)

A la secció _General_ podem trobar les següents opcions de configuració a les seves respectives pestanyes:

* **Bàsic**. En aquesta pestanya trobem el nom de la màquina virtual. Amb aquest mateix nom VirtualBox també guarda els arxius de configuració de la màquina virtual. Si canviem el nom de la màquina, també es canviarà el nom d’aquests arxius. A continuació, trobem el tipus de sistema operatiu convidat per la màquina virtual que defineix la configuració de la màquina. Canviar aquest valor després de la creació de la màquina virtual no afecta la configuració de la màquina que s’ha fet durant la creació d’aquesta. Per últim trobem la versió del sistema operatiu convidat seleccionat per instal·lar a la màquina virtual.
* **Avançat**. En aquesta pestanya trobem les següents opcions.
  * **Capeta de captures**. Aquí podem especificar el directori on volem emmagatzemar els arxius d’imatge de les captures de la màquina virtual.
  * **Porta-retalls compartit**. En aquesta opció podem seleccionar si volem compartir el porta-retalls entre el sistema operatiu amfitrió i el convidat. Si triem l’opció _Bidireccional_, VirtualBox mantindrà les mateixes dades als dos porta-retalls. Si seleccionem _De l’amfitrió al client_ o _Del client a l’amfitrió_, VirtualBox només copiarà les dades del porta-retalls en una única direcció que correspondrà a la selecció feta. Per motius de seguretat el porta-retalls està desactivat de forma predeterminada.
  * **Arrossega i deixar anar**. Aquesta opció activa l’opció de seleccionar i arrossegar un element directament entre el sistema operatiu amfitrió i el convidat. Si seleccionem _De l’amfitrió al client_ o _Del client a l’amfitrió_, VirtualBox només arrossegarà les dades en una única direcció que correspondrà a la selecció feta. Per motius de seguretat aquesta opció es troba desactivada de forma predeterminada.
* **Descripció**. Amb aquesta opció es pot introduir una descripció de la màquina virtual, resulta molt útil per no oblidar quina és la funció de la màquina virtual o quines aplicacions té instal·lades. Aquesta opció no té cap efecte en la funcionalitat de la màquina virtual.
* **Xifratge del disc**. Aquesta opció permet encriptar el disc dur vinculat a la màquina virtual. Per habilitar aquesta opció cal marcar la casella _Habilita el xifrat de disc_. Després podem seleccionar l’algorisme de xifrat i introduir la contrasenya desitjada.

**Configuració del sistema**

A la finestra _Paràmetres_, a la secció _Sistema_ podem configurar els paràmetres de maquinari de la màquina virtual, com la memòria i el processador. Les opcions que trobem estan organitzades en les pestanyes _Placa mare_, _Processador_ i _Acceleració_. Podeu observar les pestanyes _Placa mare_ i _Processador_ a la [figura.21](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig21) i [figura.22](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig22), respectivament.

Les opcions que trobem en aquesta finestra són:

* **Placa mare**. En aquesta pestanya podem establir la quantitat de **memòria RAM** que s’assigna a la màquina virtual quan s’està executant. Aquesta memòria ha d’estar disponible al moment d’iniciar la màquina virtual i no estarà disponible per la màquina amfitrió mentre la màquina virtual estigui en execució. Podem canviar la quantitat de memòria després d’instal·lar el sistema operatiu convidat però no és recomanable reduir la quantitat assignada per evitar el mal funcionament del sistema operatiu. Altres opcions que trobem en aquesta pestanya són:
  * **Ordre d’arrencada**. Aquesta opció determina l’ordre que farà servir el sistema operatiu convidat per arrencar des dels diferents dispositius d’emmagatzematge virtuals. VirtualBox pot iniciar el sistema operatiu des de disquet, unitat de CD/DVD, disc dur o xarxa.
  * **Xip**. Podem seleccionar quin xip utilitzarà la màquina virtual. PIIX3 és el xip més utilitzat per la majoria de sistemes operatius.
  * **Dispositiu del punter**. El dispositiu senyalador virtual pot ser el tradicional ratolí que utilitza el connector PS/2 o les tauletes USB per dispositius amb connexió USB.
  * **Funcions ampliades**. Com funcions ampliades trobem les següents:
    * **Habilita I/O APIC**. Amb aquesta opció podem habilitar els controladors d’interrupció programables avançats \(APIC\). Aquesta activació és necessària per sistemes operatius convidats de 64 bits o si volem utilitzar més d’una CPU virtual a la màquina virtual.
    * **Activa EFI**. Permet activar la interfície extensible de Firmware que reemplaça la BIOS i pot ser útil per alguns sistemes operatius.
    * **Rellotge de maquinari en hora UTC**. Si aquesta opció està seleccionada, VirtualBox informa de l’hora en format UTC al sistema operatiu convidat. És útil per sistemes operatius que utilitzen rellotge de maquinari en UTC com UNIX.
* **Processador**. En aquesta pestanya podem configurar els paràmetres relatius a la CPU de la màquina virtual. Disposem de les següents opcions:
  * **Processador**. Amb aquesta opció podem establir el nombre de nuclis de processador. No hem de configurar màquines virtuals que utilitzen més nuclis de processador que els que estan disponibles físicament a la màquina amfitriona.
  * **Límit d’execució**. Aquesta opció limita la quantitat de temps que el processador real dedica a emular un processador virtual. Per defecte, l’opció és 100% que significa que no hi ha limitació.
  * **Funcions ampliades**. Com funcions ampliades trobem les següents:
    * **Habilitar PAE/NX**. Aquesta opció permetrà que una CPU de 32 bits pugui accedir a més de 4 GB de memòria RAM afegint 4 bits extres a les adreces de memòria.
    * **Habilitar VT-x / AMD-V imbricat**. Aquesta opció permet activar la virtualització a nivell de BIOS/UEFI a la màquina hoste. L’opció VT-x es refereix a processadors Intel mentre que l’opció AMD-v fa referència a processador AMD. Només és possible activar-la forçant la seva habilitació des de VBoxManage.
* **Acceleració**. En aquesta pestanya podem configurar VirtualBox per utilitzar extensions de virtualització de maquinari si és suportada per la màquina amfitrió.
  * **Interfície de paravirtualització**. En aquesta opció disposem de diferents interfícies de paravirtualització que permeten millorar el rendiment dels sistemes operatius convidats.
  * **Virtualització de maquinari**. Permet configurar les funcions de virtualització de maquinari per cada màquina virtual. Si el processador admet les funcions de paginació imbricada, es pot millorar el rendiment amb l’activació d’aquestes opcions.

FiguraConfiguració de la placa mare de la màquina virtual \(I\)![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/sistemaplacamarepng.png)FiguraConfiguració del processador de la màquina virtual \(II\)![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/sistemaprocessador.png)

**Configuració de pantalla**

A la finestra _Paràmetres_, a la secció _Pantalla_ podem configurar els paràmetres relatius a la pantalla. Les opcions que trobem estan organitzades en les pestanyes _Pantalla_, _Pantalla remota_ i _Enregistrament_. Podeu observar les pestanyes _Pantalla_ i _Enregistrament_ a la [figura.23](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig23) i [figura.24](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig24), respectivament.FiguraConfiguració de la pantalla de la màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/pantalla.png)FiguraOpcions d’enregistrament de la màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/enregistrament.png)

Les opcions que trobem en aquesta finestra són:

'Remote Desktop Protocol' \(RDP\)

És un protocol que permet la comunicació durant l’execució d’una aplicació entre un intèrpret d’ordres i un servidor.

* **Pantalla**. En aquesta pestanya trobem les següents opcions:
  * **Memòria de vídeo**. Estableix la mida de la memòria de vídeo disponible per la màquina virtual convidada. Segons la quantitat de memòria assignada, podem trobar disponibles diferents resolucions i profunditats de colors.
  * **Nombre de monitors**. Podem simular que la màquina virtual tingui més d’un monitor. Les sortides dels diferents monitors es mostren a la màquina amfitrió en diferents finestres que s’executen en paral·lel. Si volem visualitzar el contingut d’aquests monitors en pantalla completa, necessitarem que la màquina amfitrió tingui tants monitors com la màquina convidada té assignats.
  * **Factor d’escala**. Aquesta opció permet escalar la mida de la pantalla. Si tenim diferents monitors podem establir el factor d’escala de forma individual o en conjunt per tots els monitors.
  * **Controlador gràfic**. Especifica el tipus d’adaptador utilitzat per la màquina virtual convidada. Entre totes les opcions disponibles, si triem VBoxSVGA o VMSVGA necessitarem tenir instal·lat les Guest Additions a la màquina virtual convidada.
  * **Acceleració**. Amb aquesta opció podem seleccionar si la màquina virtual utilitzarà les eines d’acceleració per gràfics 3D o 2D.
* **Pantalla remota**. En aquesta pestanya si tenim instal·lada l’extensió de pantalla remota de VirtualBox, podem activar i configurar el servidor VRDP que porta integrat VirtualBox i que permet connectar-se a la màquina virtual de forma remota amb qualsevol visor RDP estàndard.
* **Enregistrament**. Amb aquesta opció podem permetre l’enregistrament d’àudio i vídeo d’una màquina virtual. Per activar aquesta opció cal marcar la casella _Activa l’enregistrament_.
  * **Mode d’enregistrament**. Podem triar enregistrar només vídeo, només àudio o àudio i vídeo.
  * **Camí al fitxer**. Determina la ruta on es guardarà l’arxiu d’enregistrament.
  * **Mida del marc**. En aquesta opció podem triar la resolució del vídeo en píxels.
  * **Marcs per segon**. Podem establir el màxim nombre de fotogrames de vídeo per segon. L’augment d’aquest valor augmenta la mida de l’arxiu d’enregistrament.
  * **Qualitat del vídeo**. Podem establir la velocitat de bits per segon de la gravació. Si incrementem aquest valor millorarem l’aparença del vídeo, però augmentarem la mida de l’arxiu.
  * **Qualitat de l’àudio**. Podem triar quina qualitat tindrà l’àudio de l’enregistrament. Si incrementem aquest valor, també incrementarem la mida de l’arxiu.
  * **Pantalles**. Si tenim diverses pantalles configurades, podem seleccionar les pantalles que volem enregistrar.

**Configuració d’emmagatzematge**

La secció d’emmagatzematge permet connectar discos durs virtuals, CD o DVD, imatges i unitats de disquet virtuals de la mateixa forma que una màquina real ho faria amb els seus dispositius físics. Podeu observar la finestra de configuració a la [figura.25](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig25).FiguraConfiguració dels dispositius d’emmagatzematge de la màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/emmagatzematge.png)

En aquesta secció trobem els dispositius classificats en funció del seu controlador: IDE, SCSI, SAS, SATA, etc. Per afegir un nou controlador, cal clicar la icona que es troba a la part inferior de la finestra anomenada _Afegeix un mòdul nou d’emmagatzematge_. Segons els tipus de controlador seleccionat podrem modificar algunes de les seves característiques a la part dreta de la finestra.

Un cop tenim els controladors necessaris podem afegir una nova unitat òptica o disc dur utilitzant les icones _Afegeix unitat òptica_ o _Afegeix disc dur_ que podem trobar a la dreta del tipus de controlador. Als dos casos apareix un quadre de diàleg que permet seleccionar un arxiu d’imatge de disc existent o unitat òptica. També als dos casos tenim l’opció de crear-ne nous.

Si seleccionem un disc dur o unitat òptica podem veure els seus atributs a la part dreta de la finestra. Aquests atributs són els següents:

* **Ranura de dispositiu**. Podem veure la ranura de dispositiu del controlador on està connectat el disc dur virtual. Els controladors IDE tenen quatre ranures, conegudes com a primari mestre, primari esclau, secundari mestre i secundari esclau. Els controladors SATA i SCSI ofereixen fins a 30 ranures per connectar dispositius virtuals.
* **Dispositiu d’estat sòlid**. Per discos durs, aquesta opció permet simular un disc dur virtual a la màquina virtual com si fos un dispositiu d’estat sòlid.
* **CD/DVD live**. Per unitats de CD/DVD virtuals podem seleccionar aquesta opció per indicar que no volem treure el disc òptic virtual quan el sistema operatiu convidat l’expulsa.
* **Connexió en calent**. Aquesta opció permet simular un disc dur o unitat òptica virtual a la màquina virtual com si fos un dispositiu de connexió en calent.

Per eliminar un controlador, disc dur o unitat òptica, el seleccionem i cliquem l’opció _Eliminar_.

**Configuració d'àudio**

La secció Àudio permet que la màquina virtual pugui tenir una targeta d’àudio virtual connectada. Podeu observar les opcions d’aquesta secció a la [figura.26](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig26).FiguraConfiguració de l’àudio de la màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/audio.png)

En aquesta secció tenim disponibles les següents opcions:

* **Controlador d’àudio de l’amfitrió**. En aquesta opció podem seleccionar el controlador d’àudio que VirtualBox utilitzarà de la màquina amfitrió.
* **Controlador d’àudio**. En aquesta opció podem triar, entre diverses opcions, el controlador que simularà la màquina virtual.
* **Característiques ampliades**. Amb aquestes opcions esteses podem habilitar la sortida i entrada d’àudio de la màquina virtual.

**Configuració de xarxa**

La secció Xarxa permet configurar la forma en què VirtualBox presenta les interfícies de xarxa virtuals a la màquina virtual i el seu mode de funcionament. Una màquina virtual pot simular fins a vuit interfícies de xarxa de les quals només quatre poden configurar-se mitjançant la interfície gràfica, la resta cal configurar-les utilitzant l’eina VBoxManage. Podeu observar les opcions d’aquesta secció a la [figura.27](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig27).FiguraConfiguració de xarxa de la màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/xarxa.png)

Cadascuna de les interfícies de xarxa es connecten a una xarxa específica. Aquesta xarxa específica ens dona el seu mode de funcionament que pot ser diferent per cada interfície de xarxa. Podem trobar aquests modes de funcionament a l’opció **Connectat a**. Els modes de funcionament poden ser:

* **No està connectat**. Amb aquesta opció, la màquina virtual és conscient que hi ha una interfície de xarxa però que no està connectada. En comptes d’utilitzar aquest mode també podem utilitzar qualsevol altre mode sense marcar la casella _Cable connectat_.
* **NAT**. Quan creem una màquina virtual, VirtualBox habilita de forma predeterminada una interfície de xarxa virtual i selecciona el mode de traducció d’adreces de xarxa \(NAT\) per ella. D’aquesta forma, el sistema operatiu convidat pot connectar-se a Internet utilitzant la interfície de xarxa de la màquina amfitrió, però no podrà connectar-se a la màquina amfitrió ni a altres màquines. Tot i que en un principi l’amfitrió no podrà veure la màquina virtual, podem fer-la visible gràcies a la redirecció de ports.
* **Adaptador pont**. Amb aquest mode es crea un commutador virtual de forma que la màquina virtual es connecta a la mateixa xarxa que la màquina amfitrió. D’aquesta forma, la màquina virtual es comporta com un equip més de la xarxa real.
* **Xarxa interna**. Aquest mode podem utilitzar-lo per crear una xarxa virtual que serà visible per les màquines virtuals seleccionades però no per la màquina amfitrió o Internet.
* **Adaptador de només l’amfitrió**. Aquesta opció s’utilitza per crear una xarxa que contingui la màquina amfitrió i un conjunt de màquines virtuals sense la necessitat d’utilitzar la interfície de xarxa real de la màquina amfitrió.
* **Controlador genèric**. Aquest mode permet compartir la interfície de xarxa genèrica.
* **Xarxa NAT**. Aquest mode permet que els equips que es troben dins de la mateixa Xarxa NAT puguin comunicar-se entre ells a diferència del que passa al mode NAT on només hi ha un equip. Per utilitzar aquesta opció primer cal crear la xarxa. Per fer-ho anem a _Fitxer &gt; Preferències &gt; Xarxa_ per definir la xarxa NAT. Quan seleccionem la icona _Afegeix xarxa NAT nova_ situada a la part dreta de la finestra Xarxes NAT podem configurar el nom de la xarxa, la xarxa CIDR, la compatibilitat amb DHCP i IPv6 i el reenviament de ports com podeu observar a la [figura.28](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig28).

FiguraConfiguració de xarxes NAT de VirtualBox![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/xarxanat.png)

Després de seleccionar a quina xarxa es connecten les interfícies de xarxa, si despleguem les opcions que es troben a l’apartat _Avançat_ podem seleccionar el tipus d’adaptador de xarxa i altres opcions:

Adreça MAC

L’adreça MAC \(_Media Access Control_\) és un identificador que correspon de forma única a una interfície de xarxa. També és coneguda com a _adreça física_ i és única per cada dispositiu.

* **Tipus d’adaptador**. Per cada interfície podem seleccionar individualment quin tipus d’adaptador simularà la màquina virtual. VirtualBox pot virtualitzar sis tipus d’adaptadors virtuals.
* **Mode promiscu**. Si permetem aquesta opció podrem veure tot el tràfic de paquets de la xarxa. Aquesta opció és útil per fer proves de xarxa o auditories de seguretat.
* **Adreça MAC**. Permet canviar l’adreça MAC de la màquina virtual, ja que no podem tenir dues interfícies amb la mateixa adreça MAC en una xarxa.
* **Cable connectat**. Aquesta opció permet simular la connexió o desconnexió del cable de la interfície de xarxa de la màquina virtual.

**Configuració de ports en sèrie**

La secció _Ports en sèrie_ permet que VirtualBox pugui utilitzar ports en sèrie virtuals. Aquest tipus de port s’utilitzaven abans que el connector USB guanyés popularitat. Aquests ports permetien connectar mòdems i alguns ratolins. Tot i que aquest tipus de port ja no són tan comuns com abans encara poden ser d’utilitat pels programadors de sistemes operatius.

Si s’habilita un port en sèrie virtual, la màquina virtual i per tant el seu sistema operatiu, disposarà d’un port en sèrie virtual que admetrà tant la recepció com la transmissió de dades. És possible configurar fins a quatre ports en sèrie virtuals per màquina virtual. Podeu observar la finestra de configuració a la [figura.29](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig29).FiguraConfiguració ports en sèrie de la màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/ports.png)

Per cada port en sèrie podem configurar les següents opcions:

* **Número de port**. Determina el port en sèrie que simularà la màquina virtual.
* **Mode del port**. Determina si està desconnectat, si el port en sèrie virtual està connectat a un port sèrie real de la màquina amfitrió, si la sortida del port en sèrie s’envia a un arxiu i altres opcions.

**Configuració d'USB**

La secció USB permet configurar el suport USB per VirtualBox que permet a la màquina virtual accedir directament els dispositius USB connectats a la màquina amfitrió. Cal tenir en compte que quan la màquina virtual comenci a utilitzar un dispositiu USB, ja no estarà disponible en la màquina amfitrió per tant cal anar amb compte amb els dispositius USB que estan en ús a la màquina amfitrió perquè es desconnectaran sense un apagat adequat i això pot provocar la pèrdua de dades.

Per habilitar un USB per una màquina virtual, marquem la casella _Habilitar controlador USB_ per poder configurar les opcions com podeu observar a la [figura.30](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig30).FiguraConfiguració dels dispositius USB de la màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/usb.png)

En primer lloc cal seleccionar un controlador amb el nivell especificat de compatibilitat. Després podem configurar els filtres de dispositiu USB.

Els filtres de dispositiu USB permeten decidir quins dispositius USB es connectaran automàticament a la màquina virtual. Els dispositius USB amb filtre coincident passaran automàticament a la màquina virtual si estan connectats a la màquina amfitrió. Els dispositius USB que no tinguin un filtre coincident també poden passar-se de forma manual a la màquina virtual.

Per crear un nou filtre, cal clicar la icona _Crear un filtre USB nou_ a la dreta de la finestra de filtres de dispositius USB. Podem assignar un nom al filtre que ens ajudi a recordar els criteris del filtre per tenir una referència després. Com més criteris especifiquem més precisa serà la selecció del dispositiu. Podem seleccionar diferents criteris entre els quals tenim el fabricant, el producte, el número de sèrie o la ubicació del dispositiu USB, ja que el podem tenir connectat de forma local o remota.

Podem observar a la part dreta de la finestra de filtres de dispositius USB altres opcions com _Afegir un filtre USB nou amb tots els camps inicialment buits_ \(de forma que el filtre que coincidirà amb qualsevol dispositiu USB connectat\), _Editar el filtre USB seleccionat_ o _Suprimir el filtre USB seleccionat_.

La casella de verificació que es troba al costat del nom del filtre permet desactivar-lo sense eliminar-lo.

**Configuració de carpetes compartides**

La secció _Carpetes compartides_ permet intercanviar dades entre la màquina virtual i la màquina amfitrió. Aquesta funció requereix que les Guest Additions estiguin instal·lades a la màquina virtual. Les carpetes compartides es troben ubicades a la màquina amfitrió i es comparteixen amb la màquina virtual. Podeu observar aquesta secció a la [figura.31](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig31).FiguraConfiguració de les carpetes compartides entre la màquina virtual i la màquina amfitrió![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/carpetes.png)

Per compartir una carpeta de la màquina amfitrió amb la màquina virtual cal seleccionar la icona _Afegeix una compartició_ a la dreta de la finestra de _Carpetes compartides_. Això farà aparèixer una nova finestra on s’ha d’especificar la ruta de la carpeta i triar un nom compartit que la màquina virtual utilitzarà per accedir a la carpeta compartida.

A continuació podem seleccionar si volem que la carpeta sigui només de lectura. Si no activem la casella, la carpeta compartida serà de lectura i escriptura.

**Configuració de la interfície d'usuari**

La secció _Interfície d’usuari_ permet canviar aspectes de la interfície d’usuari de les màquines virtuals. Podeu observar aquesta secció a la [figura.32](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig32).

En aquesta secció trobem tres grans blocs:

* **Barra de menú**. Aquesta opció permet deshabilitar o habilitar opcions del menú desmarcant o marcant la casella corresponent. També és possible deshabilitar la barra de menú completa desseleccionant la casella de verificació que es troba a la dreta.
* **Barra d’eines petita**. En mode pantalla completa o integrat, VirtualBox mostra una petita barra d’eines que conté els principals elements que normalment estan disponibles a la barra de menú de la màquina virtual. Podem desactivar aquesta barra d’eina o mostrar-la a la part de dalt de la pantalla amb aquestes opcions.
* **Barra d’estat**. Aquesta opció permet deshabilitar les icones de la barra d’estat seleccionant la casella corresponent. També és possible reorganitzar les icones arrossegant i deixat anar la icona o deshabilitar la barra d’estat per complet desmarcant la casella de verificació que trobem a l’esquerra.

FiguraConfiguració de la interfície d’usuari de la màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/interficie.png)

#### Utilització de màquines virtuals

Un cop hem acabat la configuració de la màquina virtual podem iniciar-la de diferents formes. Podem fer doble clic a la màquina virtual desitjada a la llista disponible a la finestra de gestió de VirtualBox, podem seleccionar la màquina virtual a la llista de màquines a la finestra de gestió de VirtualBox i seleccionar l’opció _Iniciar_ a la part superior de la finestra o podem accedir directament des del directori on tenim emmagatzemades les màquines virtuals clicant a l’arxiu de dades de la màquina virtual amb extensió .vbox.

Quan iniciem la màquina virtual per primera vegada caldrà **seleccionar el mitjà d’instal·lació** del sistema operatiu convidat, per després procedir a instal·lar-lo. En aquest cas, tenim diferents opcions:

* Si disposem d’un mitjà físic, com un CD o DVD d’instal·lació, posem el CD o DVD al nostre equip amfitrió. A la llista que ens mostrarà la finestra d’arrancada seleccionem el dispositiu per permetre a la màquina virtual accedir al dispositiu de la màquina amfitrió.
* Si disposem d’un arxiu d’imatge ISO que hem descarregat d’Internet es pot muntar l’arxiu ISO directament. En aquest cas, cal seleccionar l’arxiu ISO a la llista de mitjans d’instal·lació.

Quan iniciem una màquina virtual després de la instal·lació del sistema operatiu, s’obrirà una finestra on arrancarà el sistema operatiu convidat. És aquest el millor moment per instal·lar les Guests Additions en cadascuna de les màquines virtuals que creem, quan tenim la màquina virtual creada i configurada amb el sistema operatiu convidat desitjat instal·lat.

A partir d’aquí podem fer servir el sistema operatiu virtual de la mateixa forma que utilitzem un sistema operatiu real, tot i que cal tenir en compte alguns conceptes que són diferents a l’utilitzar una màquina virtual i no una màquina real.

**La tecla Host**

Després d’instal·lar el sistema operatiu convidat si no hem instal·lat les Guest Additions encara, la màquina virtual i la màquina amfitrió no poden tenir el control del ratolí i el teclat al mateix temps.

Si no tenim les Guest Additions instal·lades al sistema operatiu convidat \(que permeten que les operacions del teclat i el ratolí siguin molt fluides entre la màquina virtual i la màquina amfitrió\), podem veure un segon punter del ratolí que es troba confinat dins de la finestra de la màquina virtual. Si volem treballar amb la màquina virtual, cal fer clic amb el ratolí dins de la finestra, però si volem retornar la propietat del teclat i el ratolí al sistema operatiu amfitrió, hem d’utilitzar una tecla especial anomenada **tecla Host**.

De forma predeterminada als sistemes GNU/Linux i Windows, és la tecla _Ctrl dreta_ del teclat. Als sistemes Mac, la tecla Host predeterminada és la tecla _cmd esquerra_. De totes maneres, la configuració de la tecla Host sempre es mostra a la part inferior dreta de la finestra de la màquina virtual, com podeu observar a la [figura.33](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig33), i és possible canviar aquesta tecla a la configuració de VirtualBox a _Fitxer &gt; Preferències &gt; Entrada_.FiguraTecla Host![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/ctrldreta.png)

**Introducció de caràcters especials**

Alguns sistemes operatius necessiten certes combinacions de tecles específiques per iniciar alguns procediments, com per exemple la combinació Ctrl + Alt + Supr que permet bloquejar l’equip, tancar sessió, canviar d’usuari, obrir administrador de tasques o apagar l’equip a Windows, la combinació de tecles Ctrl + Alt + Retrocés, que normalment restableix la interfície gràfica d’usuari als sistemes Linux, o la combinació Ctr+ Alt + Fx, on Fx és una de les tecles de funció que van de l’F1 a l’F12 i que permet canviar entre terminals virtuals. No podem utilitzar aquestes combinacions específiques per indicar al sistema operatiu convidat que faci la seva funció perquè aquestes combinacions de tecles les interpreta directament al sistema operatiu amfitrió.

Per enviar qualsevol d’aquestes combinacions al sistema operatiu convidat instal·lat a la màquina virtual cal utilitzar els elements del menú _Entrada &gt; Teclat_ de la finestra de la màquina virtual on també trobem l’accés directe a aquestes combinacions utilitzant la tecla Host. Per altres combinacions de teclats, com Alt + Tab que permet canviar entre finestres obertes, VirtualBox permet configurar si aquestes combinacions afectaran el sistema operatiu amfitrió o convidat utilitzant l’opció _Fitxer &gt; Preferències &gt; Entrada_.

**Tancament d'una màquina virtual**

Per apagar un sistema operatiu convidat instal·lat en una màquina virtual, ho fem exactament de la mateixa forma que com apaguem el sistema operatiu en una màquina real. És a dir, utilitzant l’opció _Apagar_ del mateix sistema operatiu.

Per una altra banda, VirtualBox permet apagar màquines virtuals fent servir l’opció _Fitxer &gt; Tanca_ a la mateixa màquina virtual. En aquest cas al tancar una màquina virtual, VirtualBox ens ofereix tres opcions que podeu observar a la [figura.34](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig34).FiguraTancament d’una màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/tancar.png)

Aquestes tres opcions són:

* **Guardar l’estat de la màquina**. Amb aquesta opció, VirtualBox guarda l’estat de la màquina virtual al disc dur local. Quan tornem a iniciar la màquina virtual més endavant, la màquina virtual continuarà la seva execució exactament on es va quedar.
* **Envia el senyal d’aturada**. Aquesta opció envia un senyal d’apagat a la màquina virtual que té el mateix efecte que pressionar el botó d’engegada d’un equip real.
* **Atura la màquina**. Amb aquesta opció, VirtualBox deixa d’executar la màquina virtual però sense guardar el seu estat. Aquesta opció equival a treure l’alimentació d’una màquina real sense apagar-la correctament i pot provocar la pèrdua de dades.

**Eliminació i canvi d'ubicació d'una màquina virtual**

És possible eliminar una màquina virtual de VirtualBox i tots els seus arxius associats. Per fer-ho cal seleccionar la màquina virtual a la finestra de gestió de VirtualBox i amb el botó dret del ratolí, seleccionar l’opció _Eliminar_. El quadre de diàleg de confirmació ens permetrà seleccionar si volem eliminar només la màquina virtual o també els arxius associats amb la màquina virtual. No és possible eliminar una màquina virtual si aquesta es troba en ús.

Per canviar d’ubicació els arxius associats a una màquina virtual cal clicar amb el botó dret la màquina virtual i seleccionar l’opció _Moure_. D’aquesta forma, podem seleccionar una nova ubicació per la màquina virtual. Tampoc és possible moure una màquina virtual si aquesta es troba en ús.

**Clonació d'una màquina virtual**

Podem crear una còpia completa o un enllaç a una màquina virtual existent. Aquest tipus de còpia es coneix com a **clonació**.

Per fer una clonació, cal clicar amb el botó dret a la màquina virtual al tauler esquerre de la finestra de gestió de VirtualBox i seleccionar l’opció _Clona_. Un cop hem seleccionat aquesta opció, hem d’omplir les opcions que ens apareix a la finestra de clonació de màquina virtual que podeu observar a la [figura.35](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig35).

En aquesta finestra cal especificar:

* **Nom**. Cal especificar el nom de la màquina virtual clonada.
* **Ruta**. Podem triar la ubicació de la màquina virtual clonada. Per defecte, trobarem la ruta que està especificada a les _Preferències_ de VirtualBox.
* **Política d’adreces MAC**. En aquest apartat trobem opcions com conservar les adreces MAC o generar noves adreces de la interfície de xarxa en clonar la màquina virtual.
* **Opcions addicionals**. En aquest apartat trobem opcions com mantenir els noms de les imatges de disc en clonar la màquina virtual i conservar els identificadors únics universals \(UUID\) de maquinari en clonar la màquina virtual.

FiguraClonació d’una màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/clonar.png)

Al següent pas d’aquest assistent hem de seleccionar el tipus de clonat que volem crear. En aquest pas especificarem si volem crear una còpia completa o un enllaç a la màquina virtual existent. L’opció _Clonació completa_ copiarà tots els arxius de la màquina virtual a un nou directori. Una còpia completa pot funcionar sense la màquina virtual original. L’opció _Clonació enllaçada_ crea una nova màquina virtual que depèn de la màquina virtual original. Ho podeu observar a la [figura.36](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig36).

UUID

UUID són les sigles de _Universally Unique Identifier_, que significa ‘identificador únic universal’. S’utilitza per crear identificadors únics que permetin reconèixer un element dins d’un sistema informàtic.FiguraClonació d’una màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/clonar2.png)

Si cliquem el botó _Clona_, es farà la clonació de la màquina virtual i podrem trobar la nova màquina al tauler de l’esquerra de la finestra de gestió de VirtualBox amb el nom que li hem assignat.

És possible utilitzar el mode expert per agilitzar el procés de clonació, ja que ens presentarà totes les opcions en una única finestra a més de donar-nos una opció més anomenada _Instantànies_ que ens permet especificar si volem crear la clonació de tota la màquina \(opció Tot\) o d’un estat actual de la mateixa \(opció Estat actual de la màquina\).

L’opció de clonació no estarà disponible si la màquina virtual es troba en funcionament.

**Importació i exportació de màquines virtuals**

VirtualBox pot importar i exportar màquines virtuals creades per diferents usuaris. Aquest programari pot utilitzar tant l’estàndard OVF \(Format de virtualització obert\) com OVA \(Dispositiu de virtualització oberta\). Els arxius d’importació i exportació els podem trobar amb extensió .ovf o .ova en funció de l’estàndard que utilitzen. Al cas de l’extensió .ova aquests arxius utilitzen una versió de l’estàndard OVF en format d’arxius Tar. VirtualBox també permet importar i exportar màquines virtuals en formats de serveis al núvol.

Extensió .tar

Tar és un format d’arxius molt utilitzat en entorns UNIX, identificat per l’extensió .tar. S’utilitza per emmagatzemar arxius i directoris, però no inclou la compressió d’aquests.

Aquests formats permeten generar un arxiu preparat pel seu ús que es poden importar i exportar entre hipervisors i que poden oferir paquets de programari complets i llestos per utilitzar.

Per **importar un arxiu en format OVF o OVA** cal seleccionar _Fitxer &gt; Importar una aplicació virtual_ a la finestra de gestió de VirtualBox. Al quadre de diàleg que apareix, seleccionem la font d’on importar la màquina virtual que pot ser tant un arxiu com un dels proveïdors de serveis al núvol disponibles. Si seleccionem un arxiu, caldrà seleccionar la ruta de l’arxiu al següent apartat. Si seleccionem un proveïdor de serveis al núvol caldrà seleccionar el compte d’usuari que volem utilitzar i la màquina virtual en concret que volem importar. Ho podeu observar a la [figura.37](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig37).FiguraImportació d’una màquina virtual \(I\)![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/import1.png)

Al següent pas, trobem la finestra de paràmetres de l’aplicació on es mostren els sistemes virtuals importats. En aquesta finestra podem canviar la configuració del sistema virtual, com podeu observar a la [figura.38](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig38).FiguraImportació d’una màquina virtual \(II\)![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/import2.png)

En aquesta mateixa finestra també podem seleccionar:

* **Carpeta de màquines bàsiques**. En aquest apartat podem seleccionar el directori on s’emmagatzemarà el sistema virtual a la màquina amfitrió. Si el sistema virtual està format per diferents màquines virtuals, es pot especificar un directori diferent per cada màquina virtual.
* **Política d’adreces MAC**. Permet reinicialitzar o conservar les adreces MAC de les interfícies de xarxa a les màquines virtuals abans de la importació.
* **Opcions addicionals**. En aquest apartat podem decidir importar els discos durs en format VDI en lloc del format de disc dur del sistema virtual importat.

Per últim, fem clic al botó _Importa_ per importar el sistema virtual.

Per **exportar una màquina virtual a un arxiu** cal seleccionar la màquina que volem exportar i seleccionar _Fitxer &gt; Exporta una aplicació virtual_ a la barra de menú. Al quadre de diàleg que apareix, només cal seleccionar la màquina virtual que volem exportar.

Al següent pas seleccionarem a quin format volem exportar la màquina virtual. Podem utilitzar les extensions .ovf i .ova. Si triem l’opció .ovf, els fitxers es guardaran per separat. Si triem l’opció .ova tots els fitxers es combinaran en un de sol. Si triem un proveïdor de serveis al núvol, s’exportarà la màquina virtual de forma remota i caldrà indiciar el compte d’usuari del servei al núvol on estiguem registrats per a exportar màquines virtuals.

Si triem el format de virtualització obert, en aquesta mateixa finestra, podem indiquem els següents paràmetres per fer l’exportació que podeu observar a la [figura.39](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig39).FiguraExportació d’una màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/export.png)

A la finestra d’exportació d’una màquina virtual disposem de les següents opcions:

* **Format**. En aquest apartat podem seleccionar el format dels arxius de sortida.
* **Fitxer**. Seleccionem la ubicació on s’emmagatzemaran els arxius exportats.
* **Política d’adreces MAC**. Especifica si s’han de mantenir o reassignar les adreces MAC de les interfícies de xarxa.
* **Opcions addicionals**. Trobem les opcions d’incloure un arxiu de manifest o arxius d’imatge ISO a l’arxiu d’emmagatzematge exportat. L’arxiu de manifest guardarà un arxiu amb la configuració original de la màquina exportada que ens permetrà comprovar la integritat de la importació si és necessari.

A continuació, cal clicar el botó _Següent_ per veure la informació descriptiva que s’afegirà a l’arxiu d’exportació, com el nom, informació i detalls del sistema virtual o la llicència.

Per últim polsem el botó _Exporta_ per començar el procés d’exportació.

**Creació d'instantànies**

Utilitzant les instantànies es pot guardar l’estat d’una màquina virtual per tornar a recuperar-lo més endavant si volem retornar l’estat de la màquina a un punt anterior. Podem fer totes les instantànies d’una màquina virtual que desitgem tenint en compte que ocuparan espai al disc dur de la màquina amfitrió.

Per veure les instantànies creades en una màquina virtual, cal seleccionar la màquina virtual i clicar a la icona _Llista_ que es troba al costat de la màquina virtual. Després seleccionem l’opció _Instantànies_. Si la llista està buida, significa que no s’ha guardat cap instantània de la màquina virtual i la llista només mostrà l’element _Estat actual_ que representa el punt actual de la màquina virtual. Podeu observar una màquina virtual amb dues instantànies a la [figura.40](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig40).FiguraInstantànies d’una màquina virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/instantanies.png)

Podem fer tres operacions amb les instantànies que són:

* **Fer una instantània**. Fa una còpia de l’estat actual de la màquina al que podrem tornar en qualsevol moment. Per fer una instantània amb la màquina virtual en execució, seleccionem _Màquina &gt; Fes una instantània_ al menú de la finestra de la màquina virtual. Si la màquina està apagada, fem clic al nom de la màquina virtual, després seleccionem la icona Llista que està al costat del nom de la màquina i seleccionem Instantànies. Després podem clicar la icona _Fes_. Al crear una instantània caldrà guardar-la amb un nom que ens servirà com a referència per ajudar-nos a recordar l’estat de la màquina virtual quan es va fer la instantània, com «Guest Additions instal·lades» o «Actualització del sistema feta».
* **Restaurar una instantània**. Per restaurar una instantània fem clic amb el botó dret en qualsevol instantània feta i seleccionem _Restaurar_. Quan restaurem una instantània, l’estat actual de la màquina es perd i retornem a l’estat que tenia la màquina virtual quan es va fer la instantània.
* **Eliminar una instantània**. Aquesta opció no afecta l’estat de la màquina virtual, només elimina els arxius que VirtualBox ha utilitzat per emmagatzemar la instantània alliberant l’espai al disc. Per eliminar una instantània fem clic al nom de la màquina virtual, després seleccionem la icona Llista que està al costat del nom de la màquina i seleccionem Instantànies. Després podem clicar la icona _Suprimeix_.

**Utilització del teclat virtual**

VirtualBox ens proporciona un teclat virtual que ens permet introduir caràcters al sistema operatiu convidat. Un teclat virtual és un teclat que visualitzem a la pantalla i que podem utilitzar com a alternativa al teclat físic.

Per poder utilitzar còmodament aquest teclat, cal que ens assegurem que la distribució d’idioma del teclat configurat en el sistema operatiu convidat coincideix amb la distribució del teclat utilitzada pel teclat virtual. Podeu observar el teclat virtual de VirtualBox a la [figura.41](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig41).FiguraTeclat virtual![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/teclatvirtual.png)

El teclat virtual es troba disponible per utilitzar-lo sobretot als següents **casos**:

* Quan el teclat físic de la màquina amfitriona no té la mateixa distribució que el teclat que volem utilitzar a la màquina virtual. Per exemple, si volem utilitzar un teclat anglès dels EUA a la màquina virtual, però el teclat de la màquina real és un teclat internacional.
* Per enviar combinacions de tecles especials al sistema operatiu convidat. Tot i que aquestes combinacions es poden introduir utilitzant les opcions disponibles a _Entrada &gt; Teclat_ al menú de la màquina virtual ens pot resultar útil utilitzar el teclat virtual.
* Per usuaris que executen el sistema operatiu en un dispositiu que no té accés a un teclat físic.

Per accedir al teclat virtual cliquem a _Entrada &gt; Teclat &gt; Teclat virtual_ a la barra de menú de la màquina virtual.

A la part inferior dreta de la finestra del teclat virtual trobem la configuració del teclat on podem modificar el disseny del teclat, canviar la distribució o desactivar totes les tecles pressionades, com Ctrl, Alt o Supr.

**Gestió de fitxers**

La gestió de fitxers permet copiar i moure fàcilment arxius entre un sistema operatiu convidat i el sistema operatiu amfitrió. A més, també permet crear noves carpetes i canviar el nom o eliminar arxius. Per poder fer-lo servir els usuaris convidats s’han d’autenticar i crear una sessió de convidat abans de poder transferir els arxius.

Per obrir el gestor de fitxers seleccionem _Màquina &gt; Gestor de fitxers_ a la màquina virtual. Si és la primera vegada que l’utilitzem, haurem de crear una sessió de convidat nova. Per fer-ho, introduïm l’usuari i la contrasenya de l’usuari del sistema operatiu convidat i cliquem al botó _Crear una sessió_. A partir d’aquí el contingut del sistema d’arxius de la màquina virtual apareix en el tauler dret del gestor de fitxers mentre que els arxius de la màquina amfitriona es mantenen al tauler de l’esquerra com podeu observar [figura.42](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig42).FiguraGestor de fitxers![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/gestorfitxers.png)

Amb aquesta eina podem transferir arxius entre la màquina virtual i la màquina amfitriona utilitzant les icones de transferència d’arxiu que trobem a la part central de la finestra del gestor de fitxers entre els dos taulers que representen les màquines.

Sobre els taulers que representen les màquines trobem altres accions disponibles com:

* **Anar un nivell amunt**. Permet anar al directori superior del directori on estem ubicats.
* **Ves a la carpeta d’inici**. Permet anar al directori personal de l’usuari.
* **Actualitza el contingut**. Actualitza el contingut de les finestres.
* **Elimina**. Permet eliminar els objectes seleccionats.
* **Canvia el nom**. Permet canviar el nom de l’objecte seleccionat.
* **Crea un directori nou**. Permet crear un nou directori.
* **Selecciona tots els objectes**. Permet seleccionar tots els objectes de la llista.
* **Inverteix la selecció**. Permet invertir la selecció dels objectes feta.
* **Propietats**. Mostra les propietats d’un objecte.

A la part superior de la finestra trobem quatre icones que ens permeten visualitzar més informació com:

* **Sessió**. Mostra l’usuari i la contrasenya i permet iniciar i tancar la sessió.
* **Opcions**. Mostra opcions disponibles com llistar els directoris a dalt, preguntar abans d’esborrar, veure les mides dels arxius i mostrar els objectes amagats.
* **Operacions**. Mostra el panell amb les operacions realitzades.
* **Registre**. Mostra un registre de les operacions realitzades i el seu resultat.

**Gestió de suports virtuals**

VirtualBox realitza un seguiment de totes les imatges de disc dur, unitat òptica i disquet que utilitzen les màquines virtuals. Aquestes imatges s’anomenen suports virtuals i s’agrupen en pestanyes separades pel tipus de format. Podeu observar el gestor de suports virtuals a la [figura.43](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig43).FiguraGestor de suports virtuals![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/gestorsuportvirtual.png)

Aquests tipus de format són els següents:

* **Imatges de disc dur**. Són arxius d’imatge en qualsevol dels formats admesos per VirtualBox, com VDI, VMDK, VHD, etc.
* **Imatges de CD/DVD**. Són arxius d’imatge en format ISO.
* **Imatges de disquet**. Són arxius en format RAW.

De cada imatge, el gestor de suports virtuals, mostra la seva ubicació al disc dur amfitrió i altra informació, com la màquina virtual que està associada a la imatge.

Les principals accions que podem dur a terme amb el gestor de suports virtuals les trobem en forma d’icona a la part superior de la finestra del gestor. Són les següents:

* **Afegeix**. Permet afegir una imatge.
* **Crea**. Amb aquesta opció podem crear una nova imatge de disc. Si creem una imatge de disc dur virtual, ho farem utilitzant l’assistent de creació de discos virtuals. Si creem una imatge d’ISO virtual, utilitzarem la finestra de creació d’ISO virtuals. Per les imatges de disquet es mostra una finestra específica per crear disquets.
* **Copia**. Amb aquesta opció podem fer una còpia d’una imatge. Si la fem d’un disc dur virtual, podem triar el tipus de format de destí entre VDI, VHD i VMDK.
* **Mou**. Permet moure una imatge a una altra ubicació. Quan utilitzem aquest gestor per moure una imatge, s’actualitzaran tots els arxius de configuració relacionats.
* **Elimina**. Permet eliminar una imatge de suport virtual. També dóna la possibilitat d’eliminar els arxius relacionats amb la imatge quan s’elimina la imatge.
* **Allibera**. Aquesta opció permet alliberar una imatge per separar-la d’una màquina virtual. Aquesta acció només es pot executar si la imatge està connectada a una màquina virtual com, per exemple, un disc dur virtual.
* **Cerca**. Permet cercar una imatge pel seu nom o UUID.
* **Propietats**. Amb aquesta opció podem veure les següents dades:
  * **Tipus**. Mostra el comportament del disc.
  * **Ubicació**. Especifica la ubicació de l’arxiu d’imatge al sistema amfitrió.
  * **Descripció**. Permet afegir una breu descripció de la imatge de disc.
  * **Mida**. Especifica la mida de la imatge de disc. Podem utilitzar el control lliscant per augmentar o disminuir la mida de la imatge de disc.
  * **Informació**. Aquesta opció la trobem a la pestanya d’Informació al costat de la pestanya Atributs i ens dona més informació sobre la imatge de disc, com el format, el xifrat, UUID, entre altres valors.
* **Actualitza**. Actualitza els valors de la imatge de disc.

#### Gestió de màquines virtuals des de la línia d'ordres

De vegades no és necessari fer servir una interfície gràfica per crear i gestionar màquines virtuals, sinó que resulta molt més còmode, una vegada estem acostumats a fer-les servir, crear-les i gestionar-les des d’un intèrpret d’ordres.

El mateix VirtualBox té una eina que permet gestionar màquines virtuals utilitzant l’ordre anomenada _VBoxManage_. A més, existeixen utilitats proporcionades per altres empreses que estan pensades per facilitar encara més la creació i gestió de les màquines Virtuals, sigui amb VirtualBox o amb altres hipervisors com Hyper-V. Una de les utilitats més conegudes i utilitzades és _Vagrant_.

**VBoxManage**

Amb VBoxManage és possible controlar per complet VirtualBox des de l’intèrpret d’ordres del nostre sistema operatiu amfitrió. VBoxManage a més de permetre executar totes les funcions que permet la interfície gràfica, ens dona la possibilitat d’executar altres opcions de configuració més avançades a les quals no podem accedir utilitzant la interfície gràfica.

Per utilitzar VBoxManage, cal fer servir l’ordre `VBoxManage`, seguida d’una subordre específica i, a vegades, de la màquina virtual a la qual volem aplicar l’ordre. Per executar aquesta ordre utilitzem l’intèrpret d’ordres del sistema operatiu amfitrió. Si el nostre sistema operatiu amfitrió és Windows, podem fer servir CMD o PowerShell, si el sistema operatiu és GNU/Linux o Mac OS X farem servir el Terminal.

Si executem l’ordre `VBoxManage` sense cap opció es mostra l’ajuda amb la llista de subordres que estan disponibles.

Per exemple, per poder llistar les màquines virtuals que tenim disponibles al nostre sistema operatiu amfitrió, podem fer servir l’ordre `VBoxManage list vms`. Per executar aquesta ordre cal que iniciem l’intèrpret d’ordres del sistema operatiu amfitrió \(per exemple, si el nostre sistema operatiu amfitrió és Windows, podem iniciar CMD\) i escrivim l’ordre. Podeu observar l’execució de l’ordre i la resposta a la [figura.44](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig44).

Com podeu observar a la resposta de l’ordre, ens mostra la llista de màquines virtuals creades amb els seus respectius noms i els seus UUID.

Una altra ordre interessant és la que ens permet veure tota la configuració d’una màquina virtual en particular. L’ordre que hem d’executar és `VBoxManage showvminfo` seguida del nom de la màquina virtual o del seu UUID. Podeu observar un exemple a la [figura.45](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig45) on l’ordre completa és `VBoxManage showvminfo “Ubuntu 20.04”`.FiguraLlistar les màquines virtuals amb VBoxManage![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vboxmanagelist.png)FiguraMostrar configuració d’una màquina virtual amb VBoxManage![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vboxmanageinfo.png)

Per últim, podem utilitzar una ordre per iniciar aquesta mateixa màquina virtual. En aquest cas l’ordre és `VBoxManage startvm` seguida del nom de la màquina. Per exemple, per iniciar la màquina virtual anomenada “Ubuntu 20.04” farem servir l’ordre `VBoxManage startvm “Ubuntu 20.04”`. Podeu comprovar que quan fem servir aquesta ordre, s’inicia la màquina virtual a la [figura.46](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig46).FiguraIniciar màquina virtual amb VBoxManage![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vboxmanagestart.png)

Algunes de les principals ordres que ens proporciona VBoxManage per interaccionar amb les màquines virtuals són:

* **VBoxManage list**. Mostra informació relacionada amb les màquines virtuals i sobre la configuració de VirtualBox.
* **VBoxManage showvminfo**. Mostra informació sobre una màquina virtual en particular.
* **VBoxManage createvm**. Permet crear una nova màquina virtual.
* **VBoxManage modifiedvm**. Aquesta ordre canvia les propietats d’una màquina virtual que no s’estigui executant. Amb aquesta ordre podem modificar tots els paràmetres de configuració de la màquina virtual que mostra la interfície gràfica d’usuari de VirtualBox i algunes configuracions més avançades.
* **VBoxManage movevm**. Aquesta ordre mou una màquina virtual a una nova ubicació dins de la màquina amfitrió. Els arxius associats a la màquina virtual es mouen també a la nova ubicació de disc.
* **VBoxManage import**. Amb aquesta ordre podem importar màquines virtuals.
* **VBoxManage export**. Aquesta ordre permet exportar màquines virtuals.
* **VBoxManage startvm**. Amb aquesta ordre podem iniciar una màquina virtual que es trobi inicialment als estats Apagada o Guardada.
* **VBoxManage controlvm**. Aquesta ordre permet canviar l’estat d’una màquina virtual que es troba en execució. Poden canviar entre diferents estats com màquina apagada, reiniciant-se, amb l’estat guardat, enviar-li un senyal d’apagat ACPI, etc.
* **VBoxManage discardstate**. En aquest cas podem descartar l’estat guardat de la màquina virtual que no s’està executant. Si descartem l’estat guardat de la màquina, farem que el sistema operatiu de la màquina virtual torni a arrencar la pròxima vegada que iniciï.
* **VBoxManage createmedium**. Amb aquesta ordre podem crear una nova imatge de disc dur, unitat òptica o disquet.
* **VBoxManage showmediuminfo**. Aquesta ordre mostra informació sobre una imatge de disc dur, unitat òptica o disquet, com la seva mida, el tipus i les màquines virtuals que l’utilitzen.
* **VBoxManage modifymedium**. Permet canviar les característiques d’una imatge de disc dur, unitat òptica o disquet creada.

**Vagrant**

Una altra eina que permet crear i gestionar màquines virtuals de forma ràpida i simplificada és Vagrant. Vagrant és una eina molt utilitzada per automatitzar el procés de creació i gestió de les màquines virtuals i està pensada tant per a desenvolupadors de programari, que necessiten tenir operatiu un entorn de treball de forma ràpida, com per a administradors de sistemes als quals permet crear i gestionar màquines virtuals amb funcions de servidor de forma ràpida.

Independentment de quin hipervisor fem servir, ja sigui VirtualBox, VMware, Hyper-V o altres, Vagrant permet gestionar les màquines virtuals utilitzant ordres mitjançant l’intèrpret d’ordres del sistema operatiu amfitrió. Tot i que Vagrant pot treballar amb diferents hipervisors, hem de tenir en compte que no és convenient que un sistema operatiu amfitrió tingui instal·lats diversos hipervisors \(per exemple Hyper-V i VirtualBox al mateix temps\).

En el cas concret de Microsoft Windows, si tenim VirtualBox i Hyper-V instal·lats de forma simultània, podem deshabilitar Hyper-V fent clic amb el botó de la dreta sobre el menú inici i seleccionant _Programes i característiques &gt; Activar o desactivar característiques de Windows_. En aquesta finestra hem de desmarcar Hyper-V i Acceptar.

Per instal·lar Vagrant, tan sols cal anar a la pàgina web oficial de descàrregues i descarregar el fitxer corresponent al nostre sistema operatiu. Les opcions disponibles actualment són Mac OS X, Windows, Linux \(per distribucions en general\), Debian i CentOS. En el cas de Microsoft Windows, la descàrrega és un arxiu amb extensió .msi. Podeu observar la pàgina web de descàrrega de Vagrant a la [figura.47](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig47).

Paquets MSI

Són arxius instal·ladors de programari per Windows que contenen tota la informació necessària per automatitzar la instal·lació.FiguraDescàrrega de Vagrant![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vagrant.png)

Les **caixes de Vagrant**, conegudes com a _Vagrant Boxes_ en anglès, és la forma en la qual Vagrant empaqueta un sistema informàtic virtual. Una caixa de Vagrant pot ser utilitzada per qualsevol usuari de Vagrant en pràcticament qualsevol hipervisor i sistema operatiu. Per exemple, un usuari pot utilitzar una caixa de Vagrant que contingui el sistema operatiu Ubuntu 20.04 LTS sobre un sistema amfitrió Windows 10 amb VMWare i un altre usuari pot utilitzar la mateixa caixa de Vagrant que executi mateix sistema operatiu convidat Ubuntu 20.04 LTS en un sistema operatiu amfitrió Debian executant VirtualBox com a hipervisor.

La forma més fàcil d’utilitzar les caixes de Vagrant és descarregar-les des del catàleg públic de Vagrant i executar-les. A més a més, aquest catàleg permet als usuaris compartir les seves pròpies caixes. A la [figura.48](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig48) podeu observar algunes de les caixes de Vagrant disponibles a la seva pàgina web oficial.FiguraCaixes de Vagrant![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/caixesvagrant.png)

Tota la interacció amb Vagrant es realitza mitjançant l’intèrpret d’ordres del sistema operatiu amfitrió utilitzant l’ordre `vagrant`. Si treballem en Windows, ho podem fer des de PowerShell o CMD; si estem en un sistema Linux o Mac OS, ho podem fer fent servir el Terminal. Si s’executa aquesta ordre sense cap opció, es mostra l’ajuda amb la llista de subordres que estan disponibles. L’ajuda de cadascuna de les subordres es pot consultar afegint «-h» després de l’ordre. Per exemple, per conèixer l’ajuda de la subordre “init” es pot escriure `vagrant init -h`.

A diferència de com s’utilitza la interfície gràfica de VirtualBox per crear una màquina virtual, la forma de **crear una màquina virtual amb Vagrant** és la següent:

1. En primer lloc cal crear un directori de treball, on guardarem la màquina virtual i el seu entorn de treball. Cal crear un directori diferent per cada màquina virtual que vulguem executar.
2. El segon pas és utilitzar l’intèrpret d’ordres per executar l’ordre `vagrant init` seguit del nom de la caixa de Vagrant des del directori de treball creat anteriorment. Aquest pas guarda l’arxiu de configuració de Vagrant dins del directori.
3. El tercer pas és iniciar la màquina virtual. Ho fem amb l’ordre `vagrant up`.

Després d’aquests passos, automàticament trobarem disponible la màquina virtual basada en la caixa de Vagrant seleccionada. Si estem fent servir VirtualBox com hipervisor i consultem la seva interfície gràfica, podem observar com ha aparegut una nova màquina virtual al sistema com podeu observar a la [figura.49](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig49). Si iniciem aquesta màquina virtual, podrem observar que ja té el sistema operatiu Ubuntu 20.04 instal·lat.FiguraCaixes de Vagrant![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vagrantup.png)

Podem crear totes les màquines virtuals que vulguem a partir d’una mateixa caixa de Vagrant. L’únic que hem de tenir en compte és que per cadascuna de les màquines virtuals creades els arxius han d’estar emmagatzemats en un directori propi de la màquina amfitriona.

Per eliminar una màquina virtual fem servir l’ordre `vagrant destroy`. Aquesta ordre cal confirmar-la explícitament per no eliminar una màquina virtual de forma accidental. Un cop executada aquesta ordre podem observar com la màquina virtual desapareix de la finestra de gestió de VirtualBox.

Si ara executem l’ordre `vagrant box list` seguirà apareixent la caixa de Vagrant utilitzada, ja que, tot i que hem eliminat la màquina virtual i ja no existeix, la caixa en la qual estava basada continua disponible en el nostre sistema amfitrió. Per eliminar la caixa del sistema i que deixi d’estar disponible cal executar l’ordre `vagrant box remove` seguida del nom de la caixa de Vagrant que volem eliminar i d’aquesta forma ja no ocuparà espai al disc de la màquina amfitriona. Podeu observar aquests passos a la [figura.50](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig50).FiguraCaixes de Vagrant![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/vagrantdestroy.png)

### Programari per a la creació de contenidors

Els contenidors i les màquines virtuals tenen **similituds i diferències**. Quant a l’usuari final, el comportament de les dues opcions és molt similar, ja que els contenidors estan pensats per aconseguir la mateixa funcionalitat que amb les màquines virtuals però sense la necessitat de sobrecarregar el sistema; però quant a l’administrador, sí que hi ha diferències, ja que cada tipus de programari s’haurà de gestionar de forma diferent.

Bàsicament, les **màquines virtuals** estan enfocades a virtualitzar tot un sistema informàtic mentre que els **contenidors** estan pensats per executar una aplicació de forma aïllada en un sistema informàtic.

Una màquina virtual executa un sistema operatiu complet, incloent-hi tot el nucli del sistema operatiu mentre que un contenidor comparteix el nucli del sistema operatiu amfitrió. El contenidor no té accés complet a aquest nucli, com tampoc té accés a tot el sistema informàtic, únicament té accés a una part que, a més a més, acostuma a estar virtualitzada.

El contenidor, a més d’accedir al nucli del sistema operatiu amfitrió, també necessita accedir a una sèrie de llibreries bàsiques del sistema operatiu per accedir a alguns serveis \(com l’accés al disc, a la interfície de xarxa, etc.\). Aquestes llibreries s’empaqueten en l’anomenada **imatge base** i és la base de tots els contenidors.

Les tecnologies més conegudes per crear i utilitzar contenidors són LXC \(Linux Container\) i Docker. Una gran diferència entre les dues tecnologies és que mentre que Docker és una solució dissenyada per contenir una única aplicació, com pot ser un servidor de bases de dades o un servidor web, LXC està dissenyat per contenir un sistema operatiu complet sense la necessitat de virtualitzar el maquinari, com fan els hipervisors de màquines virtuals:

* **LXC** és una tecnologia de virtualització en l’àmbit de sistema operatiu per GNU/Linux. LXC permet que un sistema informàtic executi diferents instàncies de sistemes operatius aïllats coneguts com a Entorns Virtuals \(EV\) sense la pèrdua de rendiment que produeixen els hipervisors, ja que la velocitat d’execució dels entorns virtuals és pràcticament nativa.
* **Docker** és un projecte de codi obert que permet desplegar aplicacions dins de contenidors i que pot funcionar amb sistemes operatius Linux, Windows i macOS.

Docker permet unir en un únic paquet l’aplicació i les seves dependències de manera que aquesta aplicació es pot moure de forma ràpida entre un entorn i un altre. Concretament, un contenidor de Docker inclou tot el necessari per executar una aplicació, és a dir, el codi, les llibreries necessàries, les utilitats i la configuració necessària. Com que Docker està disponible per macOS, Windows i Linux, el programari que s’ha situat en un contenidor s’executarà de forma indistinta en qualsevol sistema que tingui Docker instal·lat, independentment del sistema operatiu i del maquinari que utilitzi.

Podeu observar la representació gràfica de LXC i Docker a la [figura.51](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig51).FiguraLXC vs Docker![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/smx_m02_u1_006.png)

#### Instal·lació i configuració de Docker Desktop

Una de les aplicacions que podem tenir a la màquina amfitriona per poder crear contenidors en Docker és **Docker Desktop** i està disponible en la pàgina web oficial de Docker. Docker Desktop és una aplicació d’escriptori dissenyada per Docker per usuaris de Windows i Mac. Amb aquesta aplicació podem crear contenidors de forma fàcil i intuïtiva.

Per instal·lar l’aplicació, anem a la pàgina web de Docker i entre els seus productes seleccionem “Docker Desktop”. Si obrim el desplegable que ens permet triar el sistema operatiu, observem que tenim la possibilitat d’instal·lar dues versions diferents, una anomenada _Stable_ i l’altra _Edge_. En aquest cas, seleccionem la versió _Windows Stable_, com podeu observar a la [figura.52](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig52); ja que la versió _Windows Edge_ inclou característiques experimentals que potser no funcionen correctament o no han estat suficientment provades.FiguraDescàrrega de Docker Desktop per Microsoft Windows![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/docker1.png)

_Docker Desktop Stable per Windows_ és la versió de Docker per sistemes operatius Windows que es pot instal·lar en les versions Pro, Enterprise i Education, ja que necessita un hipervisor per funcionar. En el cas de voler instal·lar Docker en una versió Windows Home directament, com que aquesta versió de Windows no suporta HyperV, caldrà instal·lar WSL 2 i els contenidors creats estaran realment basats en GNU/Linux.

Després de descarregar l’aplicació, cal executar l’arxiu d’instal·lació i seguir les instruccions fins que finalitzi l’assistent d’instal·lació, moment en el qual és necessari reiniciar el sistema. El primer pas és acceptar que aquesta aplicació faci canvis en el sistema, com podeu observar a la [figura.53](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig53).

Subsistema Windows per a Linux \(WSL\)

El Subsistema Windows per a Linux WSL \(de l’anglès _Windows Subsystem for Linux_\) permet als desenvolupadors i als usuaris executar un entorn GNU/Linux, incloent-hi les utilitats del sistema, eines de la línia d’ordres i aplicacions, directament en Windows sense necessitat d’instal·lar una màquina virtual ni d’haver de tenir configurada una arrencada dual del sistema.FiguraAssistent d’instal·lació de Docker Desktop![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/docker2.png)

Al següent pas hem de seleccionar l’hipervisor sobre el qual farem servir l’aplicació, en aquest cas, serà Hiper-V. Ho podeu observar a la [figura.54](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig54).FiguraAssistent d’instal·lació de Docker Desktop![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/docker3.png)

Després comença la instal·lació de l’aplicació que finalitzarà demanant que reiniciem el sistema operatiu, com podeu observar a la [figura.55](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig55).FiguraAssistent d’instal·lació de Docker Desktop![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/docker5.png)

A partir d’aquest moment, apareix una nova icona de Docker Desktop a l’escriptori i a l’àrea de notificació, i l’aplicació es podrà executar.

És possible que quan iniciem el programa per primera vegada, el sistema ens mostri un missatge indicant que el servei no està funcionant com podeu observar a la [figura.56](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig56). Per continuar haurem d’iniciar el servei clicant el botó _Start_.FiguraIniciar Docker Desktop![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/docker6.png)

Aquest pas és necessari per poder crear i utilitzar els contenidors. A l’àrea de notificació de la barra de tasques de Windows 10 Pro \(el sistema operatiu amfitrió\), apareixerà una nova icona indicant l’estat del servei, en aquest cas podem observar que el Docker Desktop està funcionant.

Si executem directament l’aplicació Docker Desktop en Windows, apareix una finestra on podem crear contenidors i consultar els contenidors i imatges existents al sistema. Aquesta finestra es coneix com a **tauler de Docker** i la podeu observar a la [figura.57](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig57).

El tauler de Docker permet administrar els contenidors, aplicacions i imatges directament des del sistema informàtic amfitrió utilitzant una interfície gràfica que permet realitzar les accions principals.

Les dues seccions principals del tauler de Docker són:

Usuari a Docker Hub

Existeix la possibilitat d’iniciar sessió a Docker Hub, amb un identificador anomenat Docker ID i una contrasenya. Per donar-se d’alta cal anar a l’adreça [hub.docker.com](http://hub.docker.com/) i registrar-se. El fet de tenir un usuari a Docker Hub ens permet emmagatzemar les nostres pròpies imatges al núvol.

* **Containers/Apps**. La vista _Containers/Apps_ permet administrar i veure en temps d’execució tots els contenidors i aplicacions.
* **Images**. La vista _Images_ mostra una llista de les imatges Docker i ens permet administrar-les i executar-les com a contenidors. Si iniciem sessió, també podrem veure les imatges compartides en Docker Hub. Docker Hub és un repositori en línia de contenidors. Es tracta d’un lloc on persones i empreses han creat imatges de les seves aplicacions favorites o desenvolupades per ells i, després d’haver-les empaquetat en un contenidor, han creat una **imatge** d’aquest contenidor \(una mena de foto\) i l’han guardat en aquest repositori o magatzem perquè estigui a disposició de tothom.

FiguraTauler de Docker![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/dashboard1.png)

A més de les vistes de contenidors i imatges, el tauler de Docker també ens permet accedir a la configuració de l’aplicació, accedir al menú de solució de problemes i iniciar sessió a Docker Hub amb el nostre identificador Docker. Totes aquestes opcions les trobem a la part superior dreta del tauler de Docker.

Configuració de Docker Desktop

Per accedir a la finestra de configuració global de Docker Desktop cliquem la icona de configuració que trobem a la part dreta superior de la finestra. A la [figura.58](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig58) la podeu observar.FiguraConfiguració global de Docker Desktop![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/dockergeneral.png)

En aquesta finestra trobem disponibles les següents seccions:

* **General**. En aquesta secció podem configurar, entre altres opcions, si volem iniciar Docker al mateix temps que el sistema operatiu amfitrió, si volem activar les actualitzacions automàtiques i si volem enviar les nostres estadístiques per ajudar a Docker a millorar l’aplicació.
* **Resources**. Aquesta secció de Recursos permet configurar el processador, la memòria, els discos, _proxis_, xarxa i altres recursos. Les opcions seran diferents en funció de si utilitzen contenidors de Linux en mode WSL 2, contenidors de Linux en mode Hyper-V o contenidors de Windows.
* **Docker Engine**. La secció de Motor de Docker permet configurar el servei de Docker per determinar com s’executaran els contenidors. Aquesta configuració cal fer-la mitjançant un arxiu JSON, però la configuració per defecte és més que suficient per a la majoria de casos, tan sols caldrà modificar-la en algunes circumstàncies molt específiques. Una vegada escrita la configuració en format JSON cal fer clic en “Apply & Restart” per emmagatzemar la configuració i reiniciar Docker Desktop.
* **Command Line**. A la secció de Línia d’Ordres es poden habilitar o no característiques experimentals. Aquestes característiques permeten accedir a funcions que s’implementaran en futures versions de Docker Desktop però que encara no han estat suficientment provades i es considera que s’han d’utilitzar únicament amb intenció de provar-les i no per entorns en producció on l’estabilitat és necessària.

#### Creació de contenidors amb Docker Desktop

Per descarregar la primera imatge i començar a treballar amb contenidors, anem a la pàgina web oficial de Docker Hub [hub.docker.com](http://hub.docker.com/) i mirem les imatges que es troben disponibles per la seva descàrrega. En aquest cas descarreguem una imatge de Windows anomenada “mcr.microsoft.com/windows/nanoserver:1809”.

JSON

JSON són les sigles, en anglès, de _JavaScript Object Notation_ \(‘Notació d’Objectes de JavaScript’\); es tracta d’un format d’intercanvi de dades basat en fitxers de text que és fàcil de llegir i escriure tant pels usuaris com per les màquines.

Per ubicar la imatge al tauler de Docker cal utilitzar PowerShell de Windows. **Windows Powershell** és una interfície de línia d’ordres que facilita la configuració i administració del sistema operatiu. Per accedir cal anar a _Menú Inici &gt; Windows Powershell_ o podem accedir directament buscant PowerShell a la barra de cerca de programes.

Un cop hem accedit a PowerShell escrivim l’ordre `docker image pull mcr.microsoft.com/windows/nanoserver:1809` per descarregar la imatge, com podeu observar a la [figura.59](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig59).

Després d’executar aquesta ordre, podrem comprovar que tenim la imatge disponible al tauler de Docker. Amb una imatge podem fer diferents accions, com ara, executar-la com un contenidor, emmagatzemar-la, descarregar l’última versió de Docker Hub, inspeccionar-la o eliminar-la, com podeu observar a la [figura.60](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig60).FiguraDescàrrega d’una imatge Docker![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/powershell.png)FiguraAccions que es poden dur a terme a una imatge![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/images.png)

**Descarrega d’una imatge de Docker Hub**. Per descarregar l’última versió d’una imatge de Docker Hub, cal seleccionar la vista _Images_ al tauler de Docker. Aquesta vista mostra una llista de les imatges que es troben al nostre disc local. Seleccionem la imatge de la llista i cliquem la icona de més opcions. Per últim cliquem l’opció _Pull_ que descarregarà l’última versió de la imatge de Docker Hub.

**Emmagatzematge d’una imatge de Docker Hub**. Per emmagatzemar una imatge a Docker Hub, cal seleccionar la vista _Images_ al tauler de Docker. Després seleccionem la imatge desitjada de la llista i cliquem la icona de més opcions. En aquest cas, cliquem l’opció _Push to hub_.

**Inspecció d’una imatge**. Aquesta opció permet consultar informació detallada sobre la imatge, com la seva mida, quan va ser creada, el seu identificador, etc. Per inspeccionar una imatge seleccionem la vista _Images_ per veure la llista amb totes les imatges, seleccionem la desitjada i cliquem _Inspect_ a la icona de més opcions per consultar la informació de la imatge. En aquesta mateixa vista també trobem les opcions d’emmagatzemar i descarregar una nova versió d’una imatge, eliminar-la o executar-la com un contenidor.

Per fer servir les opcions de descàrrega i emmagatzemar una imatge de Docker Hub, cal tenir iniciada la sessió a Docker Hub.

**Eliminació d’una imatge**. La vista _Images_ permet eliminar imatges que ja no volen emmagatzemar al disc dur. En aquesta vista podem veure el nombre d’imatges i l’espai total de disc que utilitzen aquestes imatges. Per eliminar una imatge, cal seleccionar-la i seleccionar l’opció _Remove_ a la llista d’opcions de la icona més opcions.

**Execució d'una imatge com a contenidor**

Un cop ja tenim una imatge disponible a l’entorn virtual, per poder fer servir el contenidor caldrà executar la imatge. Per fer-ho, seleccionem la imatge i també la icona _RUN_ que apareix quan passem el ratolí per sobre la imatge, com podeu observar a la [figura.61](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig61).FiguraExecució d’una imatge com a contenidor![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/run.png)

Al clicar la icona _RUN_ observem un quadre de diàleg que ens permet executar el contenidor, com podeu observar a la [figura.62](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig62).FiguraOpcions addicionals per l’execució d’una imatge com a contenidor![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/run2.png)

En aquest quadre trobem la possibilitat d’introduir una configuració opcional de nom, port i volum. Per utilitzar els valors predeterminats, podem clicar directament el botó _Run_ sense especificar cap configuració. Això ens crea un nou contenidor a partir de la imatge que podem gestionar des de la vista _Container/App_.

Un cop el contenidor es troba en funcionament, a la vista _Containers/Apps_ podem observar **diferents opcions** quan passem el ratolí per sobre del contenidor, com podeu observar a la [figura.63](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig63). Les accions que ens dona l’opció de fer un contenidor són _CLI_, _Stop_, _Restart_ i _Delete_:FiguraAccions que es poden dur a terme amb un contenidor![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/clicontainer.png)

* **CLI**. Per accedir al contenidor utilitzant la interfície de línia d’ordres \(CLI\), només cal clicar sobre aquesta opció. D’aquesta forma, accedim al terminal des d’on podem introduir ordres al contenidor.
* **Stop, Restart i Delete**. Les opcions _Stop_, _Restart_ i _Delete_ permeten gestionar el cicle de vida del contenidor, aturant-lo, reiniciant-lo o eliminant-lo, respectivament.

Si seleccionem l’opció CLI, ja podrem començar a utilitzar el contenidor. A la [figura.64](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig64) podeu observar el contenidor de Windows en execució.

CLI

La interfície de línia d’ordres \(CLI, de l’anglès _Command-line Interface_\) és un mètode que permet als usuaris donar ordres a un programa informàtic utilitzant línies de text.FiguraExecució d’una imatge com a contenidor![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/execucio.png)

Per sortir de la sessió interactiva del contenidor es pot executar l’ordre `exit` al mateix terminal del contenidor.

Al tauler Docker també es pot observar el contenidor creat i el seu estat com podeu observar a la [figura.65](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig65) on podeu observar el contenidor en execució.FiguraContenidor en execució![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/clicontainer2.png)

**Execució d'una imatge d'un sistema operatiu diferent del sistema amfitrió com a contenidor**

El servei de Docker s’executa sobre Windows fent servir la tecnologia Hyper-V en Windows 10 Pro, Windows 10 Enterprise o Windows 10 per Educació. Amb aquesta tecnologia es permet executar contenidors amb el sistema operatiu Microsoft Windows.

Pot donar-se el cas que ens interessi executar un contenidor GNU/Linux en una màquina Microsoft Windows 10. És possible realitzar-ho canviant la tecnologia que fa servir Docker Desktop per crear i gestionar els contenidors, ja que Windows 10 inclou la possibilitat d’executar aplicacions GNU/Linux de forma directa fent servir el Subsistema Linux per Windows WSL \(de l’anglès _Windows Subsistem for Linux_\).

Per **canviar la tecnologia** sobre la que s’executen els contenidors, cal anar a la icona de Docker Desktop de la barra de notificacions i fer clic amb el botó de la dreta. En el menú contextual cal seleccionar _Switch to Linux containers…_ en el cas de voler crear i executar contenidors GNU/Linux fent servir WSL 2 o _Switch to Windows containers…_ en el cas de voler crear i executar contenidors Windows basats en Hyper-V, com podeu observar a la [figura.66](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig66). L’opció que apareixerà serà sempre la contrària a la que s’està fent servir en aquest moment.

Trobareu més informació sobre WSL al punt “Instal·lació i configuració de Docker Desktop”, d’aquest mateix contingut.

No disponible per a la versió Home

En el cas de Windows 10 Home Edition, Docker Desktop únicament podrà fer servir WSL 2 i no Hyper-V, ja que no està disponible per l’edició Home del sistema operatiu.FiguraCanvi a contenidors Linux![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/switchtolinuxcontainers.png)

En el moment de canviar la gestió entre contenidors Windows i Linux, Docker Desktop mostrarà una **advertència** pel fet que mentre que el sistema estigui gestionant contenidors Linux no podrà gestionar contenidors Windows \(i al contrari, si està gestionant contenidors Windows no podrà gestionar contenidors Linux\), tot i que es mantindran en execució i no es perdran les dades, com podeu observar a la [figura.67](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig67).FiguraCanvi a contenidors Linux![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/advertenciaswitchtolinuxcontainers.png)

**Inspecció del contenidor**

Si en comptes de passar el ratolí per sobre del contenidor, fem clic, trobem altres dades sobre el contenidor, com podeu observar a la [figura.68](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/a2/continguts.html#fig68). Aquestes dades que podem consultar són:

* **Logs**. En aquesta opció trobem els registres de l’execució del contenidor.
* **Inspect**. En aquesta opció trobem informació sobre el contenidor, com la versió de la imatge, el xifratge utilitzat i altres detalls.
* **Stats**. En aquesta opció podem consultar l’estadística d’ús de processador, memòria, velocitat de lectura/escriptura en disc i consum de xarxa.

A més, a la part superior de la finestra trobem els accessos ràpids a les opcions d’obrir la CLI per introduir ordres al contenidor i les opcions _Stop_, _Restart_ i _Delete_.FiguraInspecció del contenidor![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u1/media/stats.png)

### Realització de proves de rendiment del sistema

En els sistemes informàtics els **recursos** no són il·limitats. Habitualment el límit és definit pel pressupost disponible: una major inversió en maquinari implicarà més capacitat de procés, més velocitat i més memòria amb la qual executar aplicacions i poder emmagatzemar dades.

Si la inversió econòmica en el sistema informàtic és insuficient per cobrir les necessitats del programari que s’executa, el resultat serà un sistema amb problemes de rendiment. Si pel contrari el que es té és un sistema sobredimensionat, el resultat serà un malbaratament de recursos. Per aquest motiu és convenient dimensionar de forma correcta el sistema informàtic en funció de les necessitats.

En un sistema informàtic on els recursos no estan utilitzats al 100%, resulta convenient aprofitar la virtualització per afegir nous sistemes virtuals i aprofitar així el maquinari que no estava sent utilitzat de forma contínua. És evident que les màquines virtuals consumeixen recursos de la màquina amfitrió i es pot donar el cas que es consumeixen tants recursos que poden arribar a alentir la màquina amfitrió, així com la resta de màquines virtuals, i comprometre la seva estabilitat. Per **mesurar el rendiment del maquinari** podem efectuar una prova de rendiment també coneguda com a _benchmark_ en anglès.

Una **prova de rendiment o** _**benchmark**_ és una tècnica que s’utilitza per mesurar el rendiment dels components d’un sistema informàtic per poder comparar els resultats amb altres components similars.

Per realitzar una prova de rendiment cal tenir en compte alguns **factors importants**:

* Cal conèixer les especificacions dels components físics i lògics als quals es farà la prova de rendiment.
* No s’ha de realitzar cap acció extra amb els components que volem testejar, simplement realitzaran la seva funció bàsica.
* Per obtenir resultats fiables, cal utilitzar més d’un tipus de prova de rendiment.

Les **fases** que componen una prova de rendiment són les següents:

1. Planificació, en la que es decideixen quins paràmetres es mesuraran i comparar, així, com es recuperaran els resultats de la recopilació de la informació.
2. Captura de dades o realització de la prova de rendiment on, mitjançant diferents eines es realitza el test. Aquest test obtindrà unes dades de rendiment.
3. Anàlisi de la informació on es recopilen les diferents dades de la fase anterior i es mostren de forma comparativa.
4. Pla d’acció en el que es fan les propostes de millora necessàries per aconseguir millorar els resultats de la prova de rendiment en properes execucions. Per exemple, si es detecta que l’ús de la memòria RAM és del 100% caldria afegir més memòria RAM al sistema, si pel contrari l’ús de la memòria RAM es manté estable al voltant del 50%, queda clar que augmentar la memòria RAM no milloraria substancialment properes execucions de la prova de rendiment.
5. Millores addicionals en el cas que es detectin possibilitats de millora no contemplades a la fase de planificació. Un exemple seria si la prova de rendiment es planifica per saber si és necessari actualitzar els processadors del sistema, però durant les proves es detecta que el problema està en una connexió de xarxa insuficient.

En el cas particular de les màquines virtuals, una prova de rendiment pot servir per decidir la possibilitat d’afegir noves màquines o no a un sistema amfitrió o decidir quin hipervisor proporciona millor rendiment als sistemes que es pretenen virtualitzar. Com que un sistema virtualitzat sempre provoca una pèrdua de rendiment en comparació a un sistema amb les mateixes funcions, però no virtualitzat, la prova de rendiment també pot servir per **decidir si la virtualització és possible**, ja que aquesta pèrdua de rendiment és assumible o pel contrari no és una opció viable.

L’escalabilitat és la capacitat d’un sistema informàtic d’augmentar la càrrega de treball suportada sense perdre qualitat en el servei ofert.

Per fer una prova de rendiment en una màquina virtual cal utilitzar eines adequades, ja que no totes les aplicacions per efectuar les proves de rendiment que funcionen en una màquina real són compatibles amb les màquines virtuals. Algunes de les **eines de** _**benchmark**_ més populars són Geekbench, UserBenchmark, SiSoftware Sandra Lite, Phoronix Test Suite o PassMark.

Però si hi ha un entorn on es fan servir de forma massiva les màquines virtuals no és un entorn domèstic, on les màquines virtuals estan destinades a realitzar proves, simulacions o tenen un ús casual. Les màquines virtuals són utilitzades massivament en **entorns empresarials** i en **centres de processos de dades**, on es poden trobar desenes o fins i tot milers de màquines virtuals funcionant al mateix temps en diversos servidors físics.

Existeix un **programari específic** per realitzar proves de rendiment en entorns virtualitzats d’aquestes característiques, com és VMMark Virtualization Benchmark. Aquest programari està específicament pensat per centres de processos de dades. En aquest cas, a més del rendiment pur, es mesuren altres característiques importants en aquest tipus d’entorns com són l’escalabilitat i el consum d’energia, que no deixen de ser avantatges que s’obtenen amb la utilització de màquines virtuals.

### Documentació del procés d'instal·lació i creació de màquines virtuals

La documentació del sistema informàtic és la informació que ens diu **que fan** aquests sistemes informàtics, **com ho fan** i **per a qui ho fan**. La documentació està formada per dades que ens donen les característiques tècniques del sistema informàtic i la seva funció.

La virtualització permet la creació de sistemes informàtics simulats, coneguts com a _virtuals_. Aquests sistemes informàtics virtuals inclouen processadors, memòries, dispositius de xarxa i sistemes operatius, entre altres components virtuals, que es recolzen en els components reals.

La virtualització afegeix una nova capa de complexitat respecte a la documentació d’un sistema tradicional. Caldrà mantenir tant la documentació de cadascun dels sistemes hostes o convidats i sumar-li la informació de la màquina amfitrió on estan executant-se les màquines virtuals o els contenidors.

Com més precisa sigui la documentació que generem, més útil ens podrà ser **en cas de consulta**. Documentant el procés, ajudem al fet que qualsevol altra persona que no hagi intervingut directament en el procés de creació i configuració, pugui conèixer el treball fet, facilitem la formació i aprenentatge del personal i augmentem la productivitat i el rendiment.

Pel que fa al sistema amfitrió, caldrà mantenir constància de les diferents màquines virtuals i contenidors que emmagatzema, així com els recursos físics reals assignats a cadascun d’ells. És convenient recordar que la suma total de recursos físics assignats a les diferents màquines virtuals pot superar els recursos reals disponibles al sistema amfitrió. Aquest fet no té per què suposar un problema si les màquines virtuals no s’estan executant de forma simultània, però cal deixar constància a la documentació.

A la **documentació de virtualització** hem de deixar constància de les dades referents a la màquina virtual o contenidor i les referents a la màquina real.

Sobre la màquina real podem documentar:

* **Dades del maquinari.** Cal descriure, de forma precisa, les característiques de l’equip que hem configurat. Incloent el tipus de processador, la memòria RAM, discos durs i perifèrics, com targetes, impressores, etc.
* **Sistema operatiu instal·lat**. Hem de deixar constància del sistema operatiu amfitrió. Cal indicar el nom del sistema operatiu i la versió, així com les actualitzacions instal·lades.
* **Configuració de xarxa**. Hem de documentar l’adreça IP de l’equip si es fixa, la màscara de subxarxa, la porta d’enllaç, el servidor DNS que estem utilitzant i, si és el cas, el nom del domini o grup de treball on es troba integrat l’equip.

Sobre la màquina virtual o el contenidor podem tenir en compte:

* **Dades del maquinari.** Cal descriure, de forma precisa, les característiques de l’equip que hem configurat. Incloent el tipus de processador, la memòria RAM, discos durs i perifèrics, com targetes, impressores, etc.
* **Sistema operatiu instal·lat**. Hem de deixar constància del sistema operatiu convidat. Cal indicar el nom del sistema operatiu i la versió, així com les actualitzacions instal·lades.
* **Configuració de la màquina virtual o del contenidor**. Hem de documentar la configuració general referent a la màquina virtual o contenidor, carpetes compatides, xifratge del disc, _proxy_, etc.
* **Configuració de xarxa**. Hem de documentar la configuració de xarxa referent a la màquina virtual, mode de connexió, adreça MAC, redirecció de ports, entre altres elements.
* **Aplicacions virtualitzades**. Hem d’indicar les aplicacions instal·lades i les seves funcions.
* **Funció de la màquina virtual o contenidor**. Cal indicar la funció del sistema virtual, com duu a terme la funció que té encomanada i per a qui fa aquesta funció.

