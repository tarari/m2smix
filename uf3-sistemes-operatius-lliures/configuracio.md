# Configuració

Després de finalitzar el procés d’instal·lació del sistema operatiu, una de les opcions més recomanades és configurar-lo. Configurar el sistema operatiu instal·lat ens permet treure el màxim profit possible del sistema informàtic quant a **rendiment** i **seguretat**.

Dins del procés de configuració d’un sistema operatiu hi intervenen diferents **etapes**, com la gestió de les sessions dels usuaris, la selecció de la interfície d’usuari utilitzada, la selecció d’aplicacions que volem instal·lar, la gestió de les actualitzacions, la configuració dels dispositius perifèrics i l’organització dels arxius i directoris del sistema.

### Arrencada i parada del sistema. Sessions.

Quan iniciem el sistema informàtic, tenen lloc una sèrie d’esdeveniments de forma automàtica per preparar el sistema per al seu ús. De la mateixa manera, tenen lloc altres accions similars per aturar el sistema de forma ordenada. És el que es coneix com a processos d’arrencada i parada del sistema.

En els sistemes operatius GNU/Linux, quan iniciem l’equip informàtic es carrega el **microprogramari** o _**firmware**_ necessari per a l’ús del sistema, ja sigui BIOS \(_Basic Input Output System_\) o UEFI \(_Unified Extensible Firmware Interface_\). Aquest microprogramari s’encarrega d’iniciar i comprovar el maquinari del sistema informàtic durant el procés d’arrencada del sistema operatiu. Després de carregar el microprogramari s’executa el gestor d’arrencada, s’inicia el nucli del sistema operatiu i s’executen els diferents guions d’inici i serveis necessaris per al sistema.

El microprogramari o _firmware_ fa d’intermediari entre part del programari i els elements electrònics del sistema informàtic.

A les distribucions GNU/Linux, el gestor d’arrencada més utilitzat s’anomena **GRUB2**, la versió que substitueix el GRUB \(_Grand Unified Bootloader_\). Aquest gestor d’arrencada desenvolupat pel projecte GNU ens permet triar quin sistema operatiu volem iniciar al sistema informàtic. El gestor d’arrencada ens proporciona un menú amb les diferents opcions d’arrencada. Quan seleccionem una de les opcions o s’activa l’opció per defecte, el gestor d’arrencada càrrega el nucli del sistema operatiu seleccionat en memòria i li cedeix el control. Podeu observar una imatge de GRUB2 a la [figura.1](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig1).FiguraGRUB2![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/grub.png)

El **nucli**, una vegada ubicat en memòria, duu a terme les accions necessàries per habilitar tot el maquinari del sistema i, finalment, executa el procés inicial \(anomenat _systemd_ a la distribució Ubuntu\). El procés inicial és el primer procés en execució després de la càrrega del nucli i s’encarrega de generar la resta de processos del sistema operatiu.

En el cas de sistemes operatius GNU/Linux amb entorn gràfic, per defecte, s’inicia l’entorn gràfic amb un programari anomenat _**display manager**_ o **gestor de pantalla** que permet l’entrada dels usuaris al sistema informàtic. A Ubuntu 20.04 el gestor de pantalles s’anomena _gdm3_ i és el gestor de pantalla que incorpora GNOME, l’entorn d’escriptori del sistema operatiu.

El **procés de parada** segueix l’ordre invers al procés d’arrencada. En primer lloc el sistema operatiu finalitza de forma ordenada tots els processos fins que finalment li envia al sistema informàtic l’ordre d’aturada que apaga la font d’alimentació.

#### Inici de sessions

Per poder utilitzar el sistema operatiu GNU/Linux, l’usuari ha d’iniciar una sessió. Normalment es configura el sistema perquè després d’arrancar l’equip calgui fer l’inici de sessió mitjançant la identificació amb un nom d’usuari i una contrasenya, tot i que també es pot configurar perquè l’inici de sessió sigui automàtic. Aquesta darrera opció, però, no és aconsellable per qüestions de seguretat.

Es pot iniciar sessió al sistema tant en mode gràfic, mitjançant el gestor de pantalla, com en mode ordre, utilitzant els terminals TTY.

Què són els terminals TTY?

Un TTY, abreviatura del terme anglès _teletype_ i més comunament anomenat terminal, és un dispositiu que permet interactuar amb el sistema enviant ordres i rebent la sortida que produeixen. Hi ha molts tipus de ttys, però actualment la majoria s’implementen en programari, com ara els terminals de la pantalla del sistema als quals podeu accedir amb les combinacions de tecles Ctrl + Alt + Fn.

A la majoria de distribucions GNU/Linux hi ha sis **terminals TTY** \(de tty1 a tty6\) per interactuar amb el sistema operatiu en mode ordre, que es poden utilitzar simultàniament. Per accedir a les pantalles d’aquests terminals utilitzem les combinacions de tecles Ctrl + Alt + F1 per a la tty1, Ctrl + Alt+ F2 per a la tty2, etc., durant el funcionament del sistema operatiu. A més d’aquests terminals normalment en podem trobar altres a partir de la setena pantalla \(Ctrl + Alt + F7, etc.\) que permeten l’accés en mode gràfic als usuaris.

En el cas de l’entorn d’escriptori **GNOME**, el gestor d’inici de sessió gràfic, anomenat gdm3, s’executa en el primer terminal i no després dels terminals en mode ordre. A GNOME cada sessió gràfica iniciada s’executa en el primer terminal disponible a partir del segon.

A la [figura.2](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig2) i [figura.3](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig3) podeu observar la pantalla d’inici de sessió en un terminal en mode ordre i l’inici de sessió en un terminal en mode gràfic, respectivament.FiguraInici de sessió en un terminal![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/tty.png)FiguraInici de sessió amb un gestor de pantalla![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/gdm3.png)

Per iniciar sessió, l’usuari ha d’escriure el seu nom d’usuari i la contrasenya, ja sigui en la pantalla d’inici de sessió del terminal en mode ordre, com en el terminal gràfic. Cada sessió es manté en un espai de treball separat, fins i tot si un mateix usuari ha iniciat dues sessions en una mateixa màquina.

#### Finalització de sessions

Quan un usuari acaba d’utilitzar l’equip informàtic, pot apagar-lo, suspendre’l o deixar-lo encès amb la sessió tancada.

Si hem acabat de treballar i volem que altres persones utilitzin l’equip informàtic, podem **tancar la sessió** o **canviar d’usuari** sense la necessitat d’apagar l’equip. Si canviem d’usuari, totes les nostres aplicacions seguiran funcionant i tot estarà com ho havíem deixat quan tornem a iniciar sessió. Si tanquem la sessió, els nostres documents quedaran guardats i les aplicacions tancades.

Per fer qualsevol d’aquestes dues accions des de l’entorn gràfic cal anar al menú de sistema a la part dreta de la barra superior i prémer sobre el triangle per seleccionar l’opció _Apaga/Surt_ per després seleccionar _Surt_ o _Canvia d’usuari_. Per tancar sessió al mode ordre podem utilitzar l’ordre `exit` i per canviar d’usuari l’ordre `login`.

L’opció _Canvia d’usuari_ del mode gràfic només apareix si tenim més d’un compte d’usuari al sistema.

Per estalviar energia, podem **suspendre l’equip informàtic** quan no l’estem utilitzant. Si treballem amb un ordinador portàtil, el sistema operatiu per defecte suspèn l’equip quan tanquem la pantalla. Suspendre l’equip manté totes les aplicacions i documents oberts però apaga la pantalla. En aquest estat les dades es guarden en memòria per estalviar consum. Sempre és recomanable guardar tota la feina abans de suspendre l’equip per si el subministrament elèctric fallés, ja que s’eliminarien les dades emmagatzemades en memòria.

Per suspendre l’equip a l’entorn gràfic, cal anar a _Atura temporalment_, tot i que també podem configurar el sistema perquè se suspengui automàticament després d’un temps sense utilitzar-lo. Si volem suspendre l’equip des del mode ordre es pot fer servir l’ordre `systemctl suspend`.

Per apagar o reiniciar l’equip des de l’entorn gràfic, cal anar al menú de sistema a la part dreta de la barra superior i prémer el triangle per seleccionar l’opció _Apaga/Surt &gt; Apaga_ per seleccionar _Apagar_ o _Reiniciar_. A l’entorn de text podem apagar el sistema amb l’ordre `poweroff` i reiniciar-lo amb l’ordre `reboot`.

### Interfície d'usuari del sistema operatiu

Per definició, una interfície és qualsevol medi interposat entre dos elements o sistemes. Als sistemes operatius, aquesta interfície serveix per posar en relació dos elements: el propi sistema operatiu i l’usuari del sistema informàtic. En funció de com s’efectua aquesta relació es poden classificar les interfícies en:

* **Interfície de línia d’ordres \(CLI\)** en el cas que la interacció es produeixi mitjançant línies de text. Aquest tipus d’interfície s’ha fet servir des dels primers sistemes informàtics i encara s’utilitza actualment, sobretot la utilitza l’administrador de sistemes.
* **Interfície gràfica d’usuari \(GUI\)** en cas que la informació es representi de forma gràfica mitjançant imatges com ara icones, finestres, quadres de diàleg i punters que situen l’element apuntador que realitzarà la interacció.
* **Interfície natural d’usuari \(NUI\)**: s’utilitzen en els dispositius més moderns i actuals on es permet una interacció directa amb el sistema ja sigui amb gestos tàctils o la pròpia veu.

Quan es fa referència a **interfície d’usuari** es fa referència al mitjà o tipus de comunicació amb un sistema informàtic. És a dir, la interfície d’usuari no és un programa informàtic, és un mitjà d’interacció.

#### Mode ordre i mode gràfic

La utilització d’un tipus d’interfície d’usuari o d’un altre dependrà tant de les preferències de l’usuari com del sistema que s’estigui fent servir.

Alguns sistemes operatius disposen únicament d’**interfície de línia d’ordres** \(CLI\), altres estan limitats a una **interfície natural d’usuari** \(NUI\) com és el cas dels telèfons intel·ligents, i altres sistemes disposen d’una **interfície gràfica d’usuari** \(GUI\). Evidentment, existeix la possibilitat que el sistema permeti triar entre una o altra interfície. En aquest darrer cas, la utilització d’una o altra interfície d’usuari dependrà de les preferències de l’usuari en cada moment.

Quan fem servir una interfície en línia d’ordres \(CLI\), habitualment diem que estem utilitzant el **mode ordre** del sistema, mentre que quan fem servir una interfície gràfica d’usuari \(GUI\) o una interfície natural d’usuari \(NUI\) diem que estem treballant en **mode gràfic**.

Als sistemes operatius GNU/Linux, per utilitzar qualsevol dels dos modes, disposem d’un programari anomenat _**shell**_. Als sistemes GNU/Linux podem interactuar amb una gran quantitat de shells diferents tant a nivell d’interfície de línia d’ordres com a nivell d’interfície gràfica. Podeu observar un esquema de l’estructura d’un sistema operatiu GNU/Linux a la [figura.4](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig4).FiguraEstructura d’un sistema operatiu GNU/Linux![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/smx_m02_u3_001.png)

Un _**shell**_ és una interfície que permet que l’usuari interactuï amb el sistema operatiu utilitzant ordres escrites, si ens trobem en el mode ordre, o utilitzant un escriptori, si ens trobem al mode gràfic. Al sistemes operatiu Ubuntu 20.04, el _shell_ predeterminat al mode gràfic és _GNOME Shell_ mentre que al mode ordre és _Bash_.

#### Intèrpret d'ordres

Un intèrpret d’ordres d’un sistema operatiu és un programa encarregat de llegir les ordres que tecleja l’usuari i convertir-les en instruccions que el sistema operatiu pot executar. Als sistemes GNU/Linux hi ha una gran multitud d’intèrprets d’ordres diferents. El més conegut i més utilitzat és el _**shell Bash**_, ja que és l’intèrpret que ve per defecte a la gran majoria de distribucions GNU/Linux, però també n’hi ha altres com el _Bourne shell_ \(sh\), el _Korn shell_ \(ksh\), el _C shell_ \(csh\), etc.

_Bash_ és un intèrpret d’ordres que pertany al projecte GNU. El seu nom és l’acrònim de _Bourne-Again Shell_ en referència a _Bourne shell_ \(sh\), un dels primers intèrprets d’ordres d’Unix.

Per poder utilitzar _Bash_, cal tenir iniciada una sessió al sistema amb una interfície de línia d’ordres, ja sigui utilitzant un dels terminals TTY o utilitzant un emulador de terminal des de l’entorn gràfic.

Un emulador de terminal o PTS \(pseudoterminal\) és una aplicació que permet virtualitzar un terminal dins de la pròpia interfície gràfica. A la [figura.5](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig5) podeu observar l’aplicació **Terminal** de GNOME a Ubuntu.

Trobareu més informació sobre els TTY del sistema en el punt “Inici de sessions”, d’aquest mateix contingut.FiguraTerminal d’Ubuntu 20.04![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/terminal.jpg)

Per dur a terme una acció \(executar una ordre\) a una interfície de línia d’ordres, s’ha d’escriure l’ordre concreta respectant una sintaxi determinada. La **sintaxi** és la unió d’una ordre amb les seves opcions, ja siguin necessàries o opcionals; aquestes opcions poden modificar i definir el comportament de l’ordre.

#### Execució d'ordres a 'Bash'

Les ordres que escrivim en l’indicador de la línia d’ordres del _shell Bash_ tenen el **format** següent:

```text
nom_ordre [-opcions] [arguments] <return>
```

On:

* _nom\_ordre_: és el nom de l’ordre que volem executar
* _opcions_: les ordres poden o no portar opcions. Normalment les opcions s’escriuen amb un guió davant.
* _arguments_: depenent de l’ordre, es poden posar arguments que moltes vegades representen una cadena de caràcters, el nom d’un fitxer o directori.

El _shell_ interpreta sempre l’**espai en blanc** com a separador d’ordres, opcions o arguments. Si no posem els espais correctament, obtindrem un missatge d’error.

És possible que una mateixa ordre accepti **diferents modes d’execució**: a soles, amb opcions i/o amb arguments. Per exemple:

* A soles: `ls`
* Amb una opció: `ls -l`
* Amb un argument: `ls /etc/shells`
* Amb una opció i un argument: `ls -l /etc/shells`

Quan escrivim una ordre al _shell_, hem d’anar amb compte i seguir la sintaxi correctament. Per **separar l’ordre** dels paràmetres utilitzem l’espai en blanc. Si no el posem, obtindrem un error. Podeu observar un exemple a la [figura.6](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig6) on s’executa l’ordre `ls`.FiguraExemple d’execució d’ordres![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/ls.jpg)

Amb les quatre primeres execucions obtenim un resultat d’ordre correcte però amb les dues últimes, on no s’han respectat els espais en blanc, obtenim errors. Al primer error, on no hem respectat l’espai entre les opcions `-la` i el nom del directori que volem llistar, obtenim un error que ens indica que l’opció no és valida. Al segon error, on no hem deixat l’espai entre l’ordre i les opcions, l’error ens indica que no s’ha trobat l’ordre.

Als sistemes GNU/Linux, l’ordre **`man`** s’utilitza per obtenir ajuda sobre les ordres que es volen executar així com les opcions que es poden fer servir. La sintaxi d’aquesta ordre és:

* `man nom_ordre`

Per exemple, si volem obtenir ajuda sobre l’ordre `ls` cal escriure la següent ordre:

* `man ls`

I si volem obtenir ajuda sobre la pròpia ordre `man` farem servir l’ordre:

* `man man`

Quan utilitzem el mode ordres i introduïm algunes ordres concretes, és possible que obtinguem un missatge del tipus “l’operació sol·licitada requereix privilegis de superusuari”. Això significa que només podem executar aquesta ordre amb un usuari amb certs privilegis. Per obtenir els privilegis del superusuari del sistema \(anomenat _**root**_\) cal que fem servir l’eina `sudo`. Per defecte, quan un usuari executa `sudo` s’ha d’autenticar amb la seva contrasenya.

La utilitat **`sudo`**, de l’anglès _superuser do_, permet als usuaris executar programes amb els privilegis de seguretat d’un altre usuari, normalment el superusuari, i així es converteix temporalment en superusuari.

A la [figura.7](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig7) podeu observar un exemple de l’ús de l’ordre `sudo`. Com a usuari sense privilegis no podem veure el contingut del directori /root utilitzant l’ordre `ls -l /root`. Si utilitzem la mateixa ordre precedida de `sudo` podem veure el contingut del directori, ja que obtenim els privilegis d’administrador per fer aquesta acció.FiguraExemple d’utilització de `sudo`![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/sudo.png)

A la [taula.1.2](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#Taula1) hi ha algunes de les ordres bàsiques que podem trobar als sistemes GNU/Linux i la seva funció.Taula: Algunes ordres bàsiques dels sistemes operatius GNU/Linux

| Ordre | Funció |
| :--- | :--- |
| `clear` | Esborra el contingut de la pantalla |
| `date` | Mostra la data de l’equip informàtic |
| `who` | Mostra informació sobre els usuaris connectats al sistema |
| `uname` | Mostra informació sobre el sistema |
| `history` | Permet consultar una llista amb totes les ordres utilitzades per l’usuari |
| `exit` | Permet sortir d’una sessió d’un terminal |
| `ls` | Sense opcions ni arguments, llista el contingut del directori |
| `uptime` | Mostra el temps de connexió de l’equip |

#### Interfície gràfica d'usuari

El concepte d’**escriptori informàtic** pren el nom del mateix moble, ja que es tracta d’intentar representar els conceptes necessaris per treballar amb el sistema informàtic, com poden ser documents o carpetes de manera anàloga a com es faria amb un escriptori físic. Aquest escriptori informàtic, com que és la primera imatge que veurà l’usuari a l’iniciar la sessió, es convertirà en l’entorn principal de treball i mètode d’interacció amb el sistema.

En un sistema operatiu amb entorn gràfic d’usuari, l’**escriptori** és la pantalla principal de treball i on se situen els principals elements d’interacció amb l’usuari.

L’escriptori per defecte d’Ubuntu 20.04 és GNOME Shell. GNOME és una interfície d’usuari dissenyada per minimitzar les distraccions i ajudar-nos amb la feina ja que la majoria dels elements es mantenen fora de la vista de l’usuari. El podeu observar a la [figura.8](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig8).FiguraEscriptori GNOME![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/escriptori.jpg)

Quan entrem per primera vegada, el que veiem és un escriptori pràcticament buit amb una barra superior que proporciona accés a les aplicacions, al calendari i a les propietats del sistema. A la part esquerra de la pantalla, en posició vertical trobem el tauler, que mostra les nostres aplicacions preferides i les que es troben en execució. Podem prémer qualsevol icona del tauler per obrir l’aplicació respectiva. Si les aplicacions s’estan executant, es mostraran **ressaltades**. Si volem observar totes les aplicacions cal que seleccionem el botó de reixeta de la part inferior. Per col·locar les nostres aplicacions preferides en aquest tauler només cal arrossegar-les dins del tauler.

A l’escriptori, una altra forma d’accedir a les aplicacions és portar el ratolí a la cantonada superior esquerra i prémer el botó _Activitats_. Quan ho fem podem veure les nostres aplicacions actives i podem buscar aplicacions, arxius o directoris utilitzant el quadre de cerca que apareix a la part superior.

Quan obrim qualsevol aplicació, al costat del botó _Activitats_ apareix el menú de l’aplicació seleccionada que proporciona un accés ràpid a les finestres, els detalls de l’aplicació i a l’opció de sortir-ne. Podeu observar el menú d’aplicació a la [figura.9](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig9).FiguraMenú de l’aplicació LibreOffice![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/menuaplicacions.jpg)

Si volem accedir al rellotge o calendari, podem prémer al rellotge del centre de la barra superior. I si volem accedir a les **propietats del sistema** cal fer clic a les opcions de configuració que trobem a la part dreta superior de la pantalla. Aquí podem modificar el volum, la brillantor, configurar la xarxa, canviar d’usuari, tancar la sessió i apagar l’equip.

**Àrees de treball**

GNOME ens ofereix una forma de treballar amb diferents aplicacions ubicades en altres entorns d’escriptori anomenats **àrees de treball**. Cada àrea de treball és un escriptori independent però que es troba relacionat amb la resta. Podem tenir fins a quatre àrees de treball que ens poden ser d’utilitat quan tenim diferents programes en execució i volem organitzar-los per poder centrar-nos en les tasques que volem fer sense distraccions.

Per accedir a les àrees de treball cal clicar al botó _Activitats_ i les veurem a la part dreta de la pantalla. Si volem utilitzar una de les àrees de treball, només cal clicar-hi i quedarà com àrea activa. Podem passar aplicacions d’una àrea a una altra però només podem treballar amb les aplicacions de l’àrea de treball activa. Podeu veure les àrees de treball a la [figura.10](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig10).FiguraÀrees de treball d’Ubuntu 20.04![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/areestreball.jpg)

#### Accessibilitat

Quan parlem d’accessibilitat ens referim a certes facilitats que proporcionen els sistemes operatius perquè el sistema pugui ser **utilitzat per tots els usuaris** independentment de les seves capacitats cognitives o físiques. La majoria d’aquestes facilitats estan relacionades amb les tipografies d’alt contrast o de gran mida, ampliacions de pantalla, lectors de pantalla, programes de reconeixement de veu i dispositius adaptats. El conjunt d’aquestes eines s’anomenen _eines d’accessibilitat_.

Les **eines d’accessibilitat** permeten facilitar l’ús del sistema i millorar l’experiència a les persones independentment de les seves capacitats cognitives o físiques.

Per poder configurar les **opcions d’accessibilitat** del sistema operatiu Ubuntu 20.04, cal accedir al menú de configuració d’accés universal. Podem accedir obrint el quadre de cerca a _Activitats_ i escrivint _Accés universal_ o podem accedir a partir de l’opció _Configuració_ que trobem a la part dreta de la barra superior de l’escriptori.

Les principals opcions que trobem al menú de configuració d’accés universal estan relacionades amb millores visuals, auditives i motores. Podeu observar aquest menú de configuració a la [figura.11](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig11). La primera opció del menú _Mostra sempre el menú d’accés universal_ ens permet ancorar un accés directe a aquest menú al quadre de cerca d’aplicacions si l’activem.FiguraMenú de configuració d’accessibilitat![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/accessibilitat.jpg)

Podem classificar les opcions del menú de configuració d’accés universal en tres grups: millores audiovisuals, auditives i sonores.

Millores visuals:

* **Lector de pantalla**. Podem activar el lector de pantalla i utilitzar-lo perquè el sistema llegeixi en veu alta el contingut de la pantalla. Per utilitzar aquesta opció cal activar l’opció _Lector de pantalla_ a la secció _Visió_.
* **Ajustar el contrast**. Podem ajustar el contrast de les finestres i botons perquè es vegin fàcilment. Aquesta opció no canvia la brillantor de tota la pantalla, només d’algunes parts de la interfície d’usuari. Per utilitzar aquesta opció cal activar l’opció _Contrast alt_ a la secció _Visió_.
* **Canviar la mida del text a la pantalla**. Si tenim dificultats per llegir el text a la pantalla, podem canviar la mida de la tipografia. Per fer-ho cal activar l’opció _Text gran_ a la secció _Visió_.
* **Parpelleig del cursor del teclat**. Si tenim dificultats per veure el cursor del teclat en un camp de text, podem fer que parpellegi perquè sigui més fàcil ubicar-lo. Per fer-ho cal ajustar la velocitat del cursor quan activem l’opció _Parpelleig del cursor_ a la secció _Escriptura_.
* **Fer més gran una àrea de la pantalla**. Podem utilitzar una lupa que podem anar movent per la pantalla per ampliar-ne parts. Per fer-ho cal activar l’opció _Ampliació_ a la secció _Visió_. A l’activar aquesta opció podem seleccionar diferents paràmetres com el valor d’ampliació de la lupa, si volem que segueixi el ratolí o donar-li alguns efectes de color, contrast o brillantor.

Millores auditives:

* **Alertes visuals**. Quan rebem un missatge del sistema operatiu, aquest emet un so d’alerta. Si tenim dificultats per escoltar aquests sons podem fer que el sistema il·lumini la finestra actual o pantalla cada vegada que produeix un so d’alerta. Per activar aquesta opció cal activar l’opció _Alertes visuals_ a la secció _Audició_. Quan activem aquesta opció podem decidir si volem que s’il·lumini la finestra o la pantalla sencera.

Millores motores:

El teclat numèric és un conjunt de botons numèrics del nostre teclat ubicat a la part dreta normalment col·locats en forma de matriu quadrada.

* **Retardar la velocitat d’espera del doble clic**. La doble pulsació succeeix quan polsem el botó del ratolí dues vegades suficient ràpid. Si triguem molt en polsar per segona vegada obtindrem dues pulsacions separades i no una doble pulsació. Si ens trobem amb aquesta dificultat podem incrementar el temps d’espera entre pulsacions a l’opció _Retard del doble clic_ a la secció _Apuntar i fer clic_.
* **Utilitzar el ratolí amb el teclat numèric**. Si tenim dificultats per utilitzar el ratolí o un altre dispositiu senyalitzador, podem controlar el punter utilitzant el teclat numèric del nostre teclat. Per activar aquesta opció cal activar l’opció _Tecles del ratolí_ a la secció _Apuntar i fer clic_. Cada número del teclat numèric es correspondrà a una direcció del ratolí, en què la tecla central \(núm.5\) farà la funció de pulsació del ratolí. Per utilitzar el teclat numèric per teclejar números caldrà prémer la tecla _Bloq. Num_.
* **Simulació de pulsacions del ratolí**. Si tenim dificultats per moure el ratolí i polsar els seus botons a la vegada podem activar l’opció _Assistència en fer clic_ a la secció _Apuntar i fer clic_. Aquesta opció ens permet polsar al col·locar el punter del ratolí sobre un objecte de la pantalla o bé prémer el botó secundari del ratolí mantenint premut el botó primari.
* **Activar el rebuig de tecles**. El sistema pot ignorar les pulsacions de tecles repetides ràpidament. Si, per exemple, tenim tremolors a les mans que poden fer que premem diverses vegades la mateixa tecla quan només ho volíem fer una vegada, podem activar aquesta opció activant _Tecles lentes_ a l’opció _Assistent d’escriptura_ a la secció _Escriptura_.
* **Activar la repetició de tecles**. Si mantenim una tecla premuda en el temps, es repeteix la seva lletra o símbol fins que deixem anar la tecla. Si tenim dificultats per retirar el dit suficientment ràpid podem modificar el temps que triguen els caràcters en repetir-se, amb l’opció _Repetició de tecles_ a la secció _Escriptura_.
* **Utilitzar un teclat en pantalla**. Si no podem utilitzar un teclat podem activar un teclat virtual en pantalla per introduir el text utilitzant el ratolí. Per activar aquest teclat cal activar l’opció _Teclat en pantalla_ a la secció _Escriptura_.

### Organització i gestió de la informació

L’organització i la gestió de la informació és un aspecte fonamental de la utilització d’un sistema operatiu. La informació amb la que treballem als sistemes informàtics està ordenada en estructures anomenades arxius i directoris.

Un **arxiu** és un conjunt d’informació estructurada de forma que es pot emmagatzemar en un dispositiu d’emmagatzematge. Un **directori** permet agrupar un conjunt d’arxius informàtics i altres subdirectoris en funció del seu contingut o propòsit.

Als sistemes GNU/Linux els arxius tenen molta importància, ja que pràcticament quasi tot es representa mitjançat arxius. Els directoris són un tipus d’arxiu, els dispositius de maquinari són representats amb arxius especials i algunes interfícies també.

Saber crear, eliminar, moure, canviar el nom i gestionar els arxius és una habilitat fonamental per a qualsevol usuari.

#### Arbre de directoris dels sistemes operatius GNU/Linux

Als sistemes operatius GNU/Linux l’organització dels directoris es fa de forma jeràrquica en forma d’**arbre invertit**. Està invertit perquè la carpeta arrel es troba a la part superior i a dins hi ha les carpetes i arxius de sistema, així com els arxius i directoris personals de cada usuari. A la [figura.12](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig12) podeu veure la jerarquia típica del sistema d’arxius Linux.FiguraJerarquia típica del sistema d’arxius de Linux![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/smx_m02_u3_003_n.png)

El **directori** _**arrel**_ es reconeix amb el **símbol /** i és la carpeta que conté els altres directoris i es troba a la part superior de la jerarquia. El caràcter **/** s’usa també com a separador de cada directori. Per exemple de la ruta _/home/usuari_ es pot dir que la carpeta _usuari_ està dins de _home_ i que _home_ està dins d’_arrel_.

L’estructura de directoris dels sistemes operatius GNU/Linux ve definit per l’estàndard de jerarquia del sistema d’arxius, en anglès _Filesystem Hierachy Standard_, també conegut per les seves sigles FHS. Aquest estàndard és una norma que defineix els directoris principals i el seu contingut basant-se en l’organització tradicional de directoris dels sistemes Unix.

Els directoris més importants que podem trobar als sistemes GNU/Linux són:

* /. Directori _arrel_. D’aquest directori en pengen tots els directoris del sistema informàtic.
* _/boot_. Conté els arxius relacionats amb l’arrencada inicial del sistema informàtic.
* _/bin_. Conté els arxius executables de les aplicacions del sistema operatiu. Aquestes aplicacions són accessibles per a tots els usuaris del sistema informàtic.
* _/sbin_. En aquest directori trobem els arxius executables de les aplicacions que normalment executa l’administrador del sistema.
* _/home_. Aquest és el directori on trobem els directoris personals de tots els usuaris del sistema.
* _/usr_. En aquest directori hi ha els programes generals dels usuaris.
* _/opt_. Aquest directori guarda els paquets de les aplicacions que no venen amb el sistema operatiu, com, per exemple, els jocs.
* _/dev_. En aquest directori trobem els arxius especials associats als dispositius físics \(maquinari\) del sistema informàtic.
* _/lib_. Conté les llibreries que permeten executar les aplicacions emmagatzemades a /bin i /sbin.
* _/etc_. En aquest directori trobem els arxius de configuració del sistema operatiu.
* _/media_. En aquest directori trobem els punts de muntatge de les unitats físiques que tenim muntades al sistema, com unitats de CD/DVD, memòries USB, etc.
* _/var_. Aquest directori conté arxius variables, com ara arxius de registre del sistema, d’impressió, de correu, etc.
* _/tmp_. En aquest directori es guarden els arxius temporals que necessiten algunes aplicacions.
* _/root_. Aquest és el directori personal de l’usuari root.
* _/mnt_. En aquesta partició és on es troben els sistemes d’arxius muntats temporalment.
* _/proc_. És un directori amb un sistema d’arxius virtual on Linux emmagatzema informació sobre l’estat del sistema.

A la [figura.13](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig13) podeu observar un exemple de l’estructura de directoris al sistema operatiu Ubuntu 20.04 obtingut amb l’ordre `tree`.FiguraEstructura de directoris d’Ubuntu 20.04![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/estructura.png)

#### Accés a la informació. Rutes relatives i absolutes

La ruta d’accés d’un arxiu seguida del seu nom identifica de forma unívoca aquest arxiu i permet diferenciar-lo de la resta d’arxius del sistema. No poden existir dos arxius amb el mateix nom i ruta relativa, de la mateixa forma que no poden existir dos arxius amb el mateix nom i ruta absoluta.

La localització exacta d’un arxiu o directori dins de l’estructura de directoris d’un sistema s’anomena **ruta d’accés**.

En el moment de fer referència a la ubicació d’un fitxer, aquesta referència es pot fer tant des de la localització actual de l’usuari, que s’anomena en aquest cas **ruta relativa**, com des de l’arrel del sistema i en aquest cas s’anomena **ruta absoluta**.

A la [figura.14](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig14) podeu observar la ruta fins a l’arxiu _document.odt_ en mode ordre i gràfic. Al mode ordre podeu observar tant la ruta relativa com l’absoluta. Es pot observar que el nom de l’arxiu és el mateix i tan sols varia la forma de referenciar-lo.FiguraRuta en mode ordre i en mode gràfic![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/ruta.jpg)

#### Característiques d'arxius i directoris

Els directoris als sistemes operatius són un conjunt d’arxius i altres directoris agrupats en funció del seu contingut o propòsit. Als sistemes GNU/Linux un directori és un tipus d’arxiu que emmagatzema informació sobre els arxius i directoris que conté. És important destacar que als sistemes operatius GNU/Linux els noms d’arxius i directoris són diferents si s’escriuen en majúscula o en minúscules i que es recomana **utilitzar les minúscules** sempre que sigui possible.

Les principals característiques dels arxius i directoris són:

* **Nom**. El nom identifica tant arxius com directoris, aquest nom serveix per identificar-ne el contingut. Si es tracta d’un arxiu també és habitual trobar una extensió separada del nom per un punt que indica quin tipus de dada conté l’arxiu.
* **Mida**. La mida dels arxius i directoris es mesura en bytes. Com més gran, més quantitat d’informació conté l’arxiu.
* **Ubicació**. És la referència des de l’_arrel_ o altre directori al directori que conté l’arxiu. Tots els arxius i directoris han d’estar emmagatzemats dins d’un altre directori.
* **Informació**. Cada arxiu i directori conté informació relacionada amb el sistema d’arxius, com poden ser els permisos d’accés per als usuaris, l’usuari i el grup propietari i la data de modificació del contingut.

**Permisos dels arxius i directoris**

Als sistemes GNU/Linux cada arxiu té uns permisos o propietats que venen determinats per un conjunt de deu caràcters. Al sistema operatiu Ubuntu 20.04, si utilitzem el terminal per visualitzar els arxius i directoris podem observar aquests deu caràcters amb l’ordre `ls -l`. Amb aquesta ordre generem una llista llarg que inclou la informació del propietari i els permisos. Podeu observar un exemple a la [figura.15](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig15).FiguraPermisos d’un directori i un arxiu en mode text![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/permisos.jpg)

Els **permisos** determinen el tipus d’operació que es pot realitzar sobre un directori o arxiu depenent de l’usuari que hagi iniciat sessió al sistema.

D’aquests deu caràcters, el primer començant per l’esquerra fa referència al **tipus d’arxiu** que tenim. Els nou caràcters restants, s’agrupen en grups de tres i fan referència als permisos del propietari, del grup i de la resta d’usuaris del sistema. El **propietari** d’un arxiu o directori és l’usuari que l’ha creat, el **grup** fa referència al grup d’usuaris que tenen permisos sobre l’arxiu o directori i, finalment, la **resta d’usuaris** fa referència als permisos que tenen la resta d’usuaris del sistema que no són ni el propietari ni pertanyen al grup assignat.

El primer caràcter del grup de permisos fa referència al tipus d’arxiu i podem trobar els següents:

* **- \(Arxiu estàndard\)**. Aquest caràcter indica que és un arxiu que pot ser de text, executable o un arxiu que contingui qualsevol altre tipus de dades.
* **d \(Directori\)**. Aquest caràcter indica que és un directori.
* **b \(Dispositiu de bloc\)**. El caràcter indica que és un arxiu que es correspon a un dispositiu de maquinari on es transfereix informació en bloc, per exemple discos durs, unitats òptiques, etc.
* **c \(Arxiu de caràcters\)**. En aquest cas indica que és un arxiu que es correspon a un dispositiu de maquinari on es transfereix informació en unitats d’un byte.
* **l \(Enllaç simbòlic\)**. En aquest cas indica que l’arxiu és un enllaç a un altre arxiu. Aquests arxius contenen el nom d’un altre arxiu o directori.
* **p \(Arxiu de canonada\)**. En aquest cas, són arxius que permeten comunicar entre ells a dos programes en execució.
* **s \(Arxiu de socket\)**. Aquests són arxius que permeten comunicar de forma bidireccional enllaços de xarxa.

De la resta de caràcters, cada grup de tres, fa referència als tipus de permisos sobre el propietari, el grup i altres usuaris. Els permisos no tenen el mateix significat per a fitxers i directoris.

Als directoris el significat dels permisos és el següent:

* **r \(Lectura\)**. Aquest permís permet llistar quins arxius i directoris conté el directori.
* **w \(Escriptura\)**. Aquest permís permet crear, eliminar i modificar arxius en el directori.
* **x \(Execució\)**. Aquest permís permet accedir al directori per examinar-ne el contingut. Si a més d’aquest permís disposem dels permisos d’escriptura i lectura, podrem realitzar totes les operacions possibles sobre el directori.

Als arxius el significat dels permisos és el següent:

* **r \(Lectura\)**. Aquest permís permet veure el contingut de l’arxiu.
* **w \(Escriptura\)**. Aquest permís permet modificar el contingut de l’arxiu.
* **x \(Execució\)**. Aquest permís permet executar l’arxiu si és un arxiu executable.

Amb la interfície gràfica, també podem veure i gestionar aquests permisos. Per fer-ho només cal que ens situem sobre l’arxiu o directori, seleccionem l’opció _Propietats_ amb el botó dret del ratolí i accedim a la pestanya _Permisos_. En aquesta pestanya, que podeu observar a la [figura.16](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig16), podeu assignar els permisos desitjats al propietari, grup i altres usuaris.FiguraPermisos d’un directori i un arxiu en mode gràfic![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/permisosgrafic.jpg)

Si volem fer canvis en aquests permisos hem d’utilitzar l’odre `chmod`. Aquesta ordre, de l’anglès _change mode_, permet canviar els permisos d’accés a un arxiu o directori. La seva sintaxi bàsica és:

Per informar que un paràmetre és opcional, es mostra entre claudàtors en el moment de presentar la sintaxi de l’ordre.

* `chmod [opcions] [mode] nom de l’arxiu`

En aquesta ordre les opcions principals que trobem són:

* **-f**. Aquesta opció no visualitza els missatges d’error generats per conflictes en l’assignació de permisos.
* **-v**. Llista els arxius i directoris on s’estan aplicant els permisos a mesura que els assigna.
* **-R**. Aplica l’ordre de forma recursiva a tots els arxius i subdirectoris del directori on s’aplica.

El conjunt \[mode\] especifica els permisos de l’arxiu. El mode es pot especificar utilitzant un número octal o de forma simbòlica utilitzant un conjunt de codis. El conjunt de codis que es poden utilitzar per la forma simbòlica són:

* **+**. Afegeix permisos.
* **-**. Elimina permisos.
* **=**. Afegeix permisos concrets sobreescrivint els anteriors.
* **u**. Els permisos s’apliquen al propietari.
* **g**. Els permisos s’apliquen al grup propietari de l’arxiu.
* **o**. Els permisos s’apliquen a la resta d’usuaris que no són propietaris ni formen part del grup.
* **a**. Els permisos s’apliquen a tothom.

Si volem especificar els permisos utilitzant la notació octal, hem de convertir cada grup de permisos \(propietari, grup i altres\) al sistema octal. A la [taula.1.2](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#Taula1) podeu observar la correspondència entre els permisos en notació simbòlica i la seva correspondència octal.Taula: Correspondència entre la representació octal i els permisos

| Número octal | Lectura \(r=22\) | Escriptura \(w=21\) | Execució \(x=20\) | Permisos |
| :--- | :--- | :--- | :--- | :--- |
| 0 | 0 | 0 | 0 | - - - \(Sense permisos\) |
| 1 | 0 | 0 | 1 | - - x \(Execució\) |
| 2 | 0 | 1 | 0 | - w - \(Escriptura\) |
| 3 | 0 | 1 | 1 | - w x \(Escriptura i execució\) |
| 4 | 1 | 0 | 0 | r - - \(Lectura\) |
| 5 | 1 | 0 | 1 | r - x \(Lectura i execució\) |
| 6 | 1 | 1 | 0 | r w - \(Lectura i escriptura\) |
| 7 | 1 | 1 | 1 | r w x \(Lectura, escriptura i execució\) |

Permisos especials a GNU/Linux: 'sticky bit'

L’_**sticky bit**_ és un permís d’accés que pot ser assignat a directoris als sistemes GNU/Linux. Quan assignem aquest permís a un directori, significa que només el propietari d’un arxiu del directori, o bé el propietari del directori o el superusuari \(root\) poden canviar el nom de l’arxiu, modificar-lo o eliminar-lo. Sense l’_sticky bit_, qualsevol usuari amb permisos d’escriptura i execució per al directori pot modificar o eliminar qualsevol arxiu de dins del directori, independentment del seu propietari.

  
Podem assignar aquest permís de diferents formes:

* En notació simbòlica utilitzem les següents ordres per activar o desactivar el permís respectivament:
  * chmod +t /nom\_del\_directori
  * chmod -t /nom\_del\_directori
* En notació octal, per activar-lo cal sumar 1000 a la representació octal dels permisos del directori. Per desactivar-lo cal restar-ne 1000. Les ordres que utilitzem per activar i desactivar l’_sticky bit_ en un directori amb permisos inicials 777 són:
  * chmod 1777 /nom\_del\_directori
  * chmod 0777 /nom\_del\_directori

Si després d’activar l’_sticky bit_ executem l’ordre `ls -l` podem observar que en lloc d’una “x” apareix un “t” als permisos d’execució corresponents a la resta d’usuaris. Si el directori inicialment no tenia els permisos d’execució atorgats, apareixerà un “t”, si els tenia apareixerà una “T”. És molt comú trobar l’_sticky bit_ activat als directoris temporals \(com /tmp o /var/tmp\) per evitar que els usuaris que no són propietaris eliminin arxius.

Gestió de permisos

A continuació podeu observar alguns exemples de gestió de permisos sobre un arxiu anomenat _document_ en notació simbòlica i octal:

* Amb les següents ordres podeu afegir tots els permisos de lectura, escriptura i execució a tots els usuaris:
  * Notació simbòlica: `chmod a+rwx document`
  * Notació octal: `chmod 777 document`
* Amb les següents ordres podeu afegir privilegis de lectura, escriptura i execució només al propietari de l’arxiu:
  * Notació simbòlica: `chmod u+rwx document`
  * Notació octal: `chmod 700 document`
* Amb les següents ordres podeu afegir permisos de lectura i escriptura per al propietari i permisos de lectura per a la resta d’usuaris.
  * Notació simbòlica: `chmod u+rw,g+r,o+r document`
  * Notació octal: `chmod 644 document`

#### Operacions generals sobre arxius i directoris utilitzant el mode ordre

Hi ha diferents operacions generals que podem efectuar sobre els arxius i directoris en un sistema GNU/Linux, algunes de les més bàsiques són crear, consultar, visualitzar o eliminar un arxiu o directori.

**Creació d’un directori**: per crear un directori utilitzem l’ordre `mkdir`, de l’anglès _make directories_. Aquesta ordre crea un directori si aquest no existeix. La sintaxi d’aquesta ordre és:

* `mkdir [opcions] nom_del_directori`

A la majoria dels casos, `mkdir` s’utilitza sense cap opció tot i que les més utilitzades són:

* **-m, –mode**. Aquesta opció permet especificar els permisos del directori en notació octal, com ho faríem amb l’ordre `chmod`
* **-p, –parents**. Aquesta opció permet crear el directori pare si és necessari, ja que normalment si volem crear un directori en un directori que no existeix, l’ordre ens donarà un error. Amb aquesta opció es crearà el directori superior.

**Canvi de directori**: l’ordre `cd`, de l’anglès _change directory_ s’utilitza per moure’s entre els directoris. La sintaxi d’aquesta ordre és:

* `cd [opcions] [nom_del_directori]`

L’ordre `cd` sense arguments ens situa al nostre directori d’inici, sigui on sigui que estem situats de l’arbre de directoris del sistema.

Algunes de les maneres habituals d’utilitzar aquesta ordre és acompanyada de:

* **.. \(dos punts\)**. Ens permet desplaçar-nos al directori superior \(el directori pare\) del directori actiu.
* **~ \(titlla\)**. Permet accedir al directori d’inici de l’usuari actiu.
* **- \(guió\)**. Permet anar al directori anterior.

El símbol titlla \(~\)

El símbol titlla \(~\) representa el directori d’inici, també anomenat directori _home_ \(per l’anglès _home directory_\), de l’usuari que ha iniciat sessió. Si som l’usuari pau i escrivim `cd /home/pau` anirem al directori home de l’usuari pau, si escrivim `cd ~` també, i si escrivim `cd` sense arguments també.

**Eliminació d’un directori**: l’eliminació de directoris o subdirectoris la realitzem amb l’ordre `rmdir`, abreviatura de _remove empty directories_. Aquesta ordre elimina els directoris sempre que estiguin buits. Si volem eliminar directoris que no estiguin buits haurem d’utilitzar l’ordre `rm` La sintaxi de l’ordre `rmdir` és:

* `rmdir [opcions] nom_del_directori`

Aquesta ordre admet diverses opcions; les més importants són:

* **-p, –parents**. Aquesta opció permet eliminar el directori i els seus directoris pare. Per exemple, executar `rmdir -p a/b/c` és equivalent a executar `rmdir a/b/c`, `rmdir a/b` i `rmdir a`.
* **-v, –verbose**. Aquesta opció va mostrant per pantalla els directoris que va eliminant.

**Consulta d’un directori**: l’ordre utilitzada per mostrar el contingut d’un directori és `ls`, de l’anglès _list directory contents_. D’aquesta manera podem veure una llista dels arxius i subdirectoris que en formen part. La sintaxi d’aquesta ordre és:

* `ls [opcions][arxius]`

Aquesta ordre disposa d’una gran quantitat d’opcions. Entre les més destacades trobem:

* **-a, –all**. Normalment l’ordre `ls` no mostra els arxius ocults. Per mostrar tots els arxius cal utilitzar aquesta opció. Els arxius ocults es representen amb un punt “.” al davant.
* **-l**. Aquesta opció serveix per mostrar informació dels arxius i directoris llistats, com els bits de permisos, el propietari, el grup, la mida i la data de creació de l’arxiu.
* **R, –recursive**. Aquesta opció mostra el contingut del directori indicat i el contingut dels subdirectoris que conté.

Als sistemes operatius GNU/Linux hi ha dos directoris considerats especials que podem consultar amb l’ordre `ls -la` per veure tota la seva informació, ja que es troben ocults. Aquests directoris són:

* **Directori actiu `.` \(un punt\)**. Fa referència al directori on està situat l’usuari.
* **Directori pare `..` \(dos punts\)**. Fa referència al directori superior en la jerarquia de directoris. En el cas del directori arrel, el directori pare fa referència a ell mateix.

**Eliminació d’arxius i directoris**: per eliminar un arxiu o directori s’utilitza l’ordre `rm`, de l’anglès _remove_. Aquesta ordre per defecte no elimina directoris, només arxius, caldrà que utilitzem les opcions -rf per eliminar els directoris no buits. La seva sintaxi és:

* `rm [opcions] arxiu o directori`

Les principals opcions que podem utilitzar amb aquesta ordre són:

* **-r, -R, –recursive**. Elimina un directori i el seu contingut de forma recursiva.
* **-f, –force**. Força l’eliminació del directori.
* **-d, –dir**. Elimina directoris buits.

Els sistemes GNU/Linux no proporcionen, per defecte, cap funcionalitat del tipus paperera per la seva ordre `rm`. Quan esborrem un arxiu amb `rm` no el podrem recuperar si no en teníem una còpia de seguretat.

**Creació d’un arxiu**: normalment, per crear un arxiu, utilitzem el programa adequat al tipus d’arxius que volem crear. Al terminal tenim la possibilitat d’executar editors de text pensats per treballar amb arxius de text pla que no generen cap tipus de caràcter de control especial. Els més coneguts són vim i nano:

* **vim**. És la versió millorada de vi, un editor de text per a Unix. És un editor de text molt complet que fins i tot disposa d’extensions que permeten millorar la interfície de treball, per exemple ressaltant la sintaxi d’una forma específica, cosa que pot ser útil per als programadors.
* **nano**. És un editor de text minimalista pensat per utilitzar al terminal. Quan editem un arxiu amb nano, s’obre la seva interfície, que mostra el contingut de l’arxiu. Té diferents opcions d’edició com cercar, tallar, copiar, enganxar i guardar els canvis, antre altres. Per utilitzar les seves opcions d’edició cal mantenir pressionada la tecla _Ctrl_.

Amb l’ordre `touch` també podem crear un arxiu en blanc ràpidament des de la línia d’ordres del terminal. Per exemple, podem utilitzar l’ordre `touch arxiu.txt` per crear un arxiu de text buit al directori actiu anomenat _arxiu.txt_.

**Visualització d’un arxiu**: en funció de quin és el contingut d’un arxiu, cal que fem servir el programari adequat per poder-lo visualitzar. La identificació del tipus de contingut es pot realitzar consultant l’extensió de l’arxiu. Sempre podem visualitzar un arxiu de text sense format des del terminal fent servir l’ordre `cat` abreviació de _concatenate files and print on the standard output_. La sintaxi d’aquesta ordre és:

* `cat [opcions] [nom_arxiu]`

Les opcions més utilitzades amb aquesta ordre són:

* **-n, –number**. Mostra el contingut de l’arxiu juntament amb els números de línia al començament.
* **-v, –show-nonprinting**. Mostra els caràcters no imprimibles, com per exemple, els caràcters de tabulació.

**Copiar arxius i directoris**: l’ordre cp, abreviatura de _copy_, copia un arxiu. La seva sintaxi bàsica és la següent:

* `cp [opcions] origen desti`

Al copiar, l’ordre manté el nom de l’arxiu original si no proporcionem un altre nom indicat al destí. Aquesta ordre compta amb un gran número d’opcions. Algunes de les més utilitzades són:

* **-l, –link**. Aquesta opció crea arxius d’enllaç en comptes de copiar l’arxiu.
* **-f, –force**. Aquesta ordre força la sobreescriptura dels arxius de destí existents sense demanar confirmació.
* **-i, –interactive**. Aquesta opció obliga l’ordre a confirmar la còpia d’arxius si s’han de sobreescriure.
* **-r, -R, –recursive**. Permet copiar tots els arxius d’un directori complet incloent els seus subdirectoris i arxius ocults.

**Moure o canviar el nom a un arxiu o directori**: per moure o canviar el nom a directoris i arxius s’utilitza l’ordre `mv`. La seva sintaxi és la següent:

* `mv [opcions] origen desti`

Les opcions més utilitzades d’aquesta ordre són:

* **-f, –force**. Aquesta ordre sobreescriu els arxius existents sense demanar confirmació.
* **-i, –interactive**. Aquesta opció obliga l’ordre a confirmar la còpia d’arxius si s’han de sobreescriure.
* **-n, –no-clobber**. Amb aquesta opció, l’ordre mai sobreescriurà un arxiu existent.
* **-u, –update**. Amb aquesta opció no sobreescriurà els arxius si són més nous.

L’ordre `mv` s’utilitza tant per moure arxius i directoris d’un lloc a un altre com per canviar-ne el nom.

**Visualitzar la ruta de treball actual**: per visualitzar la ruta del directori de treball actual on ens trobem utilitzem l’ordre `pwd`, abreviatura de _print name of working directory_. Aquesta ordre retorna la ruta absoluta del directori actual. La seva sintaxi és la següent:

* `pwd [opcions]`

#### Caràcters comodins

Un caràcter comodí és un caràcter que es pot utilitzar per representar un altre caràcter o cadena de caràcters, i l’utilitzem habitualment en el mode ordre.

Els **caràcters comodins** són caràcters que tenen un significat especial en un sistema informàtic. Normalment s’utilitzen per referir-se a diferents arxius que tenen en comú algunes lletres del seu nom.

Alguns dels caràcters comodins utilitzats als sistemes operatius GNU/Linux són els següents:

* **“?”**. Representa un únic caràcter vàlid al nom d’un arxiu i a la posició on està ubicat.
* **“\*”**. Representa zero o més caràcters vàlids al nom d’un arxiu.
* **\[valors\]**. Representa un conjunt de caràcters indicats a la llista de valors.
* **\[valor1 – valor n\]**. Representa un rang de caràcters entre el valor 1 i el valor n.
* **\[!valors\]**. Representa un conjunt de caràcters no indicats a la llista de valors.
* **\[!valor1 – valor n\]**. Representa un rang de caràcters no continguts entre el valor 1 i el valor n.

Exemples d'utilització de caràcters comodins

Suposeu que esteu treballant a un terminal en mode ordre i executeu l’ordre `ls a*`. El resultat serà una llista de tots els arxius del directori actual que tenen un nom que comença per la lletra _a_. Altres exemples d’utilització de caràcters comodins poden ser:

* **\*.pdf** Identifica tots els arxius que tenen una extensió .pdf
* **\[ajm\]???** Identifica tots els arxius que tenen un nom de 4 caràcters que comença per la lletra _a_, la lletra _j_ o la lletra _m_.
* **document\[1-9\].txt** Identifica tots els arxius que tenen un nom que comença per document seguit d’un número comprès entre 1 i 9 inclosos i tenen extensió .txt.
* **document\[!1-9\].**\* Identifica tots els arxius que tenen un nom que comença per document seguit d’un número que no es troba comprès entre 1 i 9 i tenen qualsevol extensió.
* **\[Dd\]ocument.??** Identifica tots els arxius amb el nom Document o document i només dos caràcters d’extensió.
* **guio??.sh** Identifica tots els arxius amb un nom que comença per guió seguit de dos caràcters qualsevol i extensió .sh.

#### Operacions generals sobre arxius i directoris utilitzant l'entorn gràfic

Quan iniciem sessió en el mode gràfic per treballar amb els arxius i directoris del sistema podem fer servir el gestor d’arxius. Hi ha diferents gestors d’arxius en funció de la distribució que estiguem fent servir.

El **gestor d’arxius** proporciona una interfície d’usuari que permet administrar arxius i directoris i fer-hi les operacions més comunes, com obrir, visualitzar, moure, eliminar, etc.

A Ubuntu 20.04 l’aplicació gestora d’arxius que ve instal·lada per defecte és _**Fitxers**_. Per accedir a aquesta aplicació d’Ubuntu 20.04 cal seleccionar la icona corresponent al tauler d’aplicacions o cercar-la utilitzant el botó _Activitats_ de la barra superior.

L’eina _Fitxers_ mostra una finestra dividida en tres taulers. El tauler esquerre, anomenat _**accés ràpid**_, inclou una llista d’accés amb referències a les diferents ubicacions utilitzades amb més freqüència o aquelles que l’usuari desitja tenir més accessibles. Aquestes ubicacions poden ser directoris tant locals com remots. Si desitgem tenir un directori accessible directament en aquesta àrea simplement l’hem d’arrossegar. En la [figura.17](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig17) s’observa l’aplicació _Fitxers_.FiguraAplicació Fitxers de Gnome executant-se a l’Ubuntu 20.04![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/fitxers.png)

Els arxius i directoris estan representats al tauler dret de la finestra. Aquesta representació es fa mitjançant icones que representen el tipus de contingut de l’arxiu o si és o no un directori. Si fem doble clic sobre la icona es visualitza el contingut de l’arxiu \(obrint l’aplicació amb capacitat per interpretar-ne el contingut sempre que estigui instal·lada al sistema\) o es visualitza el contingut del directori.

Finalment, la part superior de la finestra de l’aplicació _Fitxers_ inclou informació com la ubicació actual dins de l’arbre de directoris, botons de navegació i icones d’accés ràpid a funcions com cercar, el menú d’accions o la configuració de representació de la informació.

La **creació d’un directori** a l’entorn gràfic es fa situant-nos en el directori que contindrà el nou subdirectori i fent clic amb el botó dret del ratolí sobre algun espai buit. Una vegada apareix el menú contextual cal seleccionar _Carpeta nova_. En aquest moment ens demana el nom del directori, el posem i cliquem a _Crea_.

La **creació d’arxius** no es fa directament amb l’eina Fitxers, sinó que cal que fem servir el programa adequat per a la creació del tipus de fitxer desitjat i posteriorment haurem de fer servir l’opció de cada programa per tal d’emmagatzemar aquest fitxer a la ubicació desitjada.

L’**eliminació d’arxius i directoris** es pot fer a la mateixa aplicació Fitxers si utilitzem el menú contextual que apareix al fer clic amb el botó dret sobre la icona de l’element que es desitja eliminar i seleccionant l’opció _Mou a la paperera_. Si l’element \(o elements\) està simplement seleccionat \(apareixerà el seu nom ressaltat en un color\) es pot eliminar pressionant la tecla _Supr_ del teclat. L’eliminació d’un element el situarà a una ubicació especial del sistema anomenada _Paperera_.

La paperera permet recuperar aquells arxius i directoris eliminats per error o de forma accidental. Per recuperar-los simplement cal que seleccionem la icona de la paperera i naveguem pel seu contingut fins a seleccionar la informació que desitgem recuperar. Si volem eliminar definitivament el contingut de la paperera \(i per tant la possibilitat de recuperar la informació\) podem fer clic sobre l’opció _Buidar la paperera_ al menú contextual que apareix al fer-hi clic a sobre amb el botó dret.

A més d’esborrar arxius i directoris, també podem **copiar i moure**. Per moure un arxiu o directori cal fer dues accions: tallar i enganxar. Per poder-ho realitzar hi ha diverses possibilitats:

* Mitjançant el menú contextual i les opcions copiar, tallar i enganxar.
* Mitjançant les dreceres de teclat Ctrl+C \(copiar\), Ctrl+X \(tallar\) i Ctrl+V \(enganxar\).
* També es pot moure un arxiu o directori arrossegant-lo amb el cursor des de la seva ubicació actual a la nova ubicació.

Cal tenir en consideració que copiar crearà un nou element, per tant existiran dos elements al sistema: l’original i la còpia. Per la seva banda, al moure \(o tallar i enganxar\) un element, desapareixerà de la seva ubicació original i estarà únicament disponible en la nova ubicació.

Si només desitgem canviar el nom a un arxiu o directori ho podem fer amb l’opció del menú contextual _Canviar el nom_.

#### Compressió i descompressió d'arxius

La compressió resulta de gran utilitat, ja que permet que els arxius ocupin menys espai als dispositius d’emmagatzematge i es puguin transferir més ràpidament entre equips o per Internet.

La **compressió d’un arxiu** permet emmagatzemar la mateixa informació ocupant menys espai d’emmagatzematge.

Hi ha diverses utilitats als sistemes GNU/Linux per comprimir i descomprimir arxius, cadascuna de les quals fa servir el seu propi format d’arxiu comprimit. Aquest format s’identifica gràcies a l’extensió de l’arxiu.

Els formats de compressió més coneguts que podem utilitzar als sistemes operatius lliures acostumen a tenir les següents extensions:

A Linux, les extensions dels arxius no són obligatòries, però habitualment s’utilitzen per convenció.

* **.tar**. El programa GNU Tar s’utilitza per emmagatzemar arxius i directoris en un únic arxiu però no per comprimir-los.
* **.gz**. Són els arxius comprimits amb el programa Gzip, que és l’abreviatura de GNU Zip, un programa lliure que comprimeix arxius però no directoris. Degut a això s’acostuma a utilitzar juntament amb el programa GNU Tar. El resultat de la combinació de les dues eines és un arxiu .tar.gz \(o .tgz\) que pot contenir diversos arxius i directoris comprimits en un únic arxiu.
* **.bz2**. Són els arxius comprimits amb el programa bzip2 desenvolupat sota la llicència BSD.
* **.zip**. Són els arxius comprimits amb el format de compressió ZIP, un dels formats més coneguts, perquè és el que utilitzen per defecte la majoria dels sistemes operatius propietaris.
* **.rar**. Són els arxius comprimits amb el format de compressió RAR. RAR és un format de compressió propietari amb una gran potència de compressió.

Tot i que el sistema operatiu té eines pròpies per comprimir i descomprimir \(tar, gzip, bzip2 i zip\), podem obtenir altres aplicacions de tercers que ens permeten utilitzar altres algorismes de compressió \(com rar\). Algunes de les eines de descompressió de tercers més conegudes pels sistemes GNU/Linux són **RAR** i **ZIP**.

A Ubuntu 20.04 per comprimir un arxiu o directori utilitzant el **mode gràfic** ho fem a partir del gestor d’arxius _Fitxers_. Seleccionem l’arxiu o el grup d’arxius desitjat i al menú contextual que apareix al fer clic amb el botó dret, seleccionem l’opció _Comprimeix_. A continuació cal seleccionar el format o tipus de compressió i introduir un nom per a l’arxiu. D’aquesta manera es crearà un nou arxiu comprimit a la mateixa ubicació i amb l’extensió seleccionada.

Per descomprimir un arxiu des del mode gràfic, cal seleccionar-lo amb el botó dret, triar l’opció _Extreu a_ i seguir les instruccions per determinar el directori on es descomprimirà.

Si volem utilitzar el **mode d’ordres** per comprimir i descomprimir arxius podem fer servir el terminal.

Per arxivar i desarxivar **arxius .tar** utilitzem l’ordre `tar`, que té la següent sintaxi:

* `tar [opcions] nom_arxiu`

Aquesta ordre disposa d’una gran quantitat d’opcions. Les més utilitzades són:

* **c**. Crea un nou arxiu .tar.
* **f**. Indica el nom de l’arxiu.
* **x**. Extreu l’arxiu comprimit.
* **v**. Mostra la descripció del progrés de compressió/descompressió.
* **z**. Indica que volem fer servir l’eina de compressió gzip.
* **j**. Indica que volem fer servir l’eina de compressió bzip2.

Per comprimir els arxius podem utilitzar les **opcions cvf**, de tal manera que per comprimir tots els arxius d’un directori utilitzem l’ordre: `tar cvf arxiu.tar /directori/*`. Per descomprimir un arxiu amb extensió .tar podem utilitzar la següent ordre: `tar xvf arxiu.tar`.

Per comprimir i descomprimir **arxius .gz** utilitzem l’odre `gzip`, que té la següent sintaxi:

* `gzip [opcions] nom_arxiu`

Aquesta ordre disposa d’una gran quantitat d’opcions. Les més utilitzades són:

* **-q**. Desactiva totes les notificacions de `gzip`.
* **-d**. Descomprimeix l’arxiu indicat al directori actual.
* **-1..-9**. Defineix el grau de compressió, 1 és la compressió més dèbil però més ràpida i 9 és la millor compressió però la més lenta.
* **-r**. Comprimeix de forma recursiva tot el directori, incloent subdirectoris i arxius.

Per comprimir un arxiu desactivant totes les notificacions podem utilitzar l’ordre: `gzip -q arxiu.gz /directori/*`.  
Per descomprimir un arxiu amb extensió .gz al directori actual utilitzem: `gzip -d arxiu.gz`.

Ja que l’extensió .tar permet arxivar diferents arxius en un de sol i `gzip` permet comprimir els arxius, en alguns casos podem trobar arxius que combinen les dues tècniques i que tenen **extensió .tar.gz**. Per gestionar aquests arxius podem utilitzar l’aplicació tar.

Per comprimir tots els arxius d’un directori amb una extensió .tar.gz podem utilitzar l’ordre: `tar czvf arxiu.tar.gz /directori/*`.  
Per descomprimir un arxiu amb extensió .tar.gz podem utilitzar l’ordre: `tar xzvf arxiu.tar.gz`

Per comprimir i descomprimir **arxius .bz2** utilitzem l’odre `bzip2`, que té la següent sintaxi:

* `bzip2 [opcions] nom_arxiu`

Aquesta ordre disposa d’una gran quantitat d’opcions. Les més utilitzades són:

* **-d**. Força la descompressió.
* **-f**. Sobreescriu l’arxiu de sortida.
* **-q**. No mostra els missatges informatius no essencials.
* **-1..-9**. Defineix el grau de compressió, 1 és la compressió més dèbil però més ràpida i 9 és la millor compressió però la més lenta.

Per comprimir un arxiu amb la utilitat `bzip2` podem fer servir l’ordre: `bzip2 arxiu /directori/*`.  
Per descomprimir un arxiu amb extensió .gz podem utilitzar: `bzip2 -d arxiu.bz2`.

Per comprimir i descomprimir **arxius .zip** utilitzem l’ordre `zip`, que té la següent sintaxi:

* `zip [opcions] nom_arxiu`

Aquesta ordre disposa d’una gran quantitat d’opcions. Les més utilitzades són:

* **-r**. Comprimeix de forma recursiva tot el directori, inclosos subdirectoris i arxius.
* **-P**. Permet descomprimir arxius protegits amb contrasenya.
* **-q**. No mostra els missatges informatius no essencials.
* **-u**. Permet afegir nous arxius a un arxiu .zip existent.

Per comprimir un arxiu amb la utilitat `zip` podem utilitzar l’ordre: `zip arxiu /directori/*`.  
Per descomprimir un arxiu amb extensió .zip podem utilitzar: `unzip arxiu.zip`.

### Gestió del programari del sistema operatiu

Amb la instal·lació per defecte d’un sistema operatiu s’inclouen diverses aplicacions. Els equips de desenvolupament dels sistemes operatius trien un conjunt d’**aplicacions predeterminades** que pensen que poden fer el sistema operatiu útil per a la majoria de les tasques diàries dels usuaris. De totes formes, en qualsevol moment podem instal·lar altres aplicacions que ens permetin tenir un sistema informàtic més adaptat a les nostres necessitats.

Als sistemes operatius GNU/Linux, les aplicacions s’instal·len mitjançant **paquets**. Un paquet conté els arxius, llibreries i documentació necessària per a un programa en particular o per a un conjunt de programes relacionats entre si.

Molts paquets utilitzen **dependències**. Les dependències són les relacions que existeixen entre els paquets. Normalment aquestes dependències solen ser dels següents tipus:

* Un paquet A depèn d’un altre paquet B que s’ha d’instal·lar per poder executar el paquet A.
* Un paquet A recomana la instal·lació d’un paquet B perquè els usuaris voldran instal·lar el paquet A amb les funcionalitats que ofereix el paquet B, que fins i tot podem millorar la funcionalitat del paquet A.
* Un paquet A està en conflicte amb un paquet B, és a dir, el paquet A no funcionarà si s’instal·la el paquet B al sistema operatiu.
* Un paquet A substitueix un paquet quan els arxius instal·lats pel paquet B són sobreescrits pel paquet A.
* Un paquet A inclou un paquet B quan tots els arxius del paquet B estan incorporats al paquet A.

Els formats clàssics de paquets són **.deb** i **.rpm**. Els paquets .deb són els que utilitzen les distribucions basades en Debian \(com Ubuntu, Linux Mint, etc\) mentre que els paquets .rpm els utilitzen les distribucions derivades de Red Hat \(com Fedora o CentOS\) i altres distribucions com OpenSUSE.

Paquets Deb

El sistema de paquets d’Ubuntu 20.04 deriva del mateix sistema utilitzat per la distribució GNU/Linux Debian. Per això els paquets que podem instal·lar es coneixen com “paquets Deb” i tenen l’extensió .deb.

Per poder gestionar els paquets fem servir els **gestors de paquets** de la distribució que estem utilitzant. Els gestors de paquets permeten instal·lar i desinstal·lar paquets gestionant les dependències de forma automàtica. Gràcies a aquests gestors també podem cercar aplicacions o actualitzacions de les aplicacions.

Els gestors de paquets i els tipus de paquets que utilitza una distribució són un dels elements que defineixen i marquen la diferència entre unes distribucions i altres. També ens ajuda a classificar-les, juntament amb l’origen \(si és una distribució basada en una anterior\) i l’escriptori que utilitza, entre altres factors.

Els gestors de paquets més coneguts són **apt** que és el gestor de paquets estàndard de les distribucions derivades de Debian \(paquets .deb\) i **dnf**, que utilitzen les distribucions derivades de Red Hat \(paquets .rpm\). Altres distribucions utilitzen altres gestors com _Zypper_ a openSUSE o _Pacman_ a Arch Linux.

Els gestors de paquets dels sistemes operatius GNU/Linux ens proporcionen una gran varietat d’eines per interactuar-hi, ja siguin utilitats que podem utilitzar des d’un terminal en mode ordre, fins a diferents aplicacions utilitzables a la interfície gràfica. Per exemple, a les distribucions derivades de Debian trobem la utilitat _apt_ per interactuar amb el gestor de paquets apt en mode text i algunes aplicacions com _Synaptic_ per interactuar amb el gestor de paquets apt en mode gràfic.

#### Repositoris de programari

Als sistemes GNU/Linux, els paquets de programari els podem trobar als repositoris. Els repositoris mantenen una llista del programari, normalment actualitzada, que ens permet cercar i descarregar fàcilment els programes que volem.

A l’àmbit de Linux, un **repositori** és un servidor accessible a través d’Internet que emmagatzema i organitza programari perquè els usuaris el puguem descarregar i instal·lar en la nostra distribució GNU/Linux.

Els repositoris ens permeten descarregar aplicacions sense visitar pàgines web de programari. Els repositoris ofereixen un catàleg d’aplicacions centralitzat i supervisat per la comunitat d’usuaris. Gràcies als repositoris és molt fàcil **gestionar les actualitzacions** de les aplicacions que tenim instal·lades, ja que els gestors de paquets ens avisen quan hi ha una nova versió de l’aplicació al repositori.

De totes maneres, podria passar que no trobéssim l’aplicació desitjada als repositoris o que els usuaris més avançats vulguin obtenir el codi font des de la pàgina web del desenvolupador o empresa distribuïdora i compilar-lo directament al seu sistema informàtic. En aquest cas, sempre hi ha l’opció de cercar el programa utilitzant la web.

Hi ha diferents repositoris: els que emmagatzemen el programari predeterminat d’un sistema operatiu en concret, que per defecte ja el trobem afegit al sistema operatiu, o altres **repositoris de tercers**, que si els volem utilitzar caldrà afegir-los primer a la llista de repositoris disponibles al sistema operatiu. Normalment amb el repositori predeterminat del sistema operatiu ja podrem cobrir la major part de les nostres necessitats.

Al sistema operatiu Ubuntu 20.04, per configurar i actualitzar els repositoris que utilitza el sistema, podem utilitzar l’entorn gràfic o el terminal.

Per al **procediment**, des de l’entorn gràfic anem a l’aplicació _Programari i actualitzacions_. Per cercar aquesta aplicació ho podem fer utilitzant el quadre de cerca de la barra superior. A la finestra que apareix seleccionem la pestanya _Altre programari_. Si volem afegir una nova línia als repositoris polsem _Afegeix_ i escrivim la nova línia. Per finalitzar cal polsar el botó _Afegeix un origen_ i tancar la finestra perquè Ubuntu comprovi els orígens de programari. Podeu observar aquesta finestra a la [figura.18](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig18).FiguraIntroducció de nous repositoris al mode gràfic![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/altreprogramari.png)

La majoria dels repositoris proporcionen una clau de signatura per poder comprovar els paquets descarregats. A més de seguir els passos per afegir un repositori cal descarregar i instal·lar la clau de signatura.

La clau la podem descarregar de la pàgina web del propietari del repositori. Per instal·lar-la al sistema cal anar a _Programari i actualitzacions_, seleccionar la pestanya _Autenticació_ i afegir la clau amb el botó _Importa un fitxer de clau_. Podeu observar aquesta finestra a la [figura.19](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig19).FiguraIntroducció de clau de signatura al mode gràfic![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/clau.png)

Per consultar, afegir, actualitzar o eliminar repositoris al nostre sistema operatiu des d’un terminal en mode ordre, hem de localitzar l’arxiu que conté la llista de repositoris. Aquest arxiu es troba al directori /etc/apt i s’anomena **source.list**. Dins d’aquest arxiu podem observar línies amb els noms dels repositoris. Els repositoris que no comencen per \# són els que estem utilitzant i els que comencen per \# són els que tenim deshabilitats, ja que es consideren comentaris.

Si volem afegir un nou repositori podem editar l’arxiu /etc/apt/source.list, anar al final i afegir la línia corresponent que faci referència al nou repositori. Després caldrà guardar els canvis a l’arxiu.

També podem **afegir una nova línia** al repositori d’una manera més segura, sense editar directament l’arxiu, utilitzant l’ordre `add-apt-repository` de la següent manera:

* `sudo add-apt-repository nom_del_repositori`.

En qualsevol cas, després d’introduir el nou repositori, cal **actualitzar la llista de repositoris** amb els últims canvis realitzats. Per fer-ho utilitzem l’ordre:

* `sudo apt update`.

És possible que també s’hagi d’**instal·lar la clau de signatura** del repositori. Per fer-ho, el propietari del repositori proporciona una adreça web des d’on descarregar aquesta clau de signatura. Un cop l’hem descarregat, cal afegir-la amb la següent ordre:

* `sudo apt-key add arxiu_amb_la_clau`.

#### Botigues d'aplicacions

A més de poder instal·lar aplicacions mitjançant els repositoris o pàgines web que distribueixen programari, cada vegada són més populars les botigues d’aplicacions. Les més conegudes ofereixen paquets en format **Snap** o **Flatpak**.

Un dels inconvenients de la instal·lació de paquets de tipus .deb o .rpm als sistemes GNU/Linux són les **dependències**. És normal que un paquet tingui dependència de diferents paquets, i això complica la instal·lació al gestor de paquets. És per això que en els últims anys han anat sortint altres models i formats de distribució d’aplicacions, basats en un format d’aplicació autocontinguda \(que ja incorpori dins tots els components i les dependències que necessita per funcionar\), i que, a la vegada, siguin compatibles amb totes les distribucions, facilitant en gran mesura la tasca d’empaquetat.

Els paquets Snap i Flatpak permeten instal·lar aplicacions en qualsevol distribució sense preocupar-nos de les dependències, ja que permeten empaquetar una aplicació qualsevol en un paquet que conté l’aplicació juntament amb les seves biblioteques i dependències.

L’empresa creadora del format Snap és Canonical, mentre que els paquets Flatpak no estan vinculats a cap gran empresa però reben suport de l’empresa Red Hat. Els dos formats tenen les seves pròpies botigues d’aplicacions per cercar i descarregar els paquets. Aquestes aplicacions s’anomenen Snap Store i Flathub, respectivament.

Tot i que els dos formats es poden utilitzar en qualsevol distribució GNU/Linux, els paquets Snap els acostumem a trobar a les distribucions Ubuntu, i Flatpak ve de forma predeterminada a Fedora, Elementary i PureOS, entre altres.

Per instal·lar una aplicació mitjançat les botigues de paquets Snap o Flatpak podem utilitzar les aplicacions de botiga en mode gràfic o fer-ho des de les eines que incorporen per treballar en mode ordre.

Òbviament, el catàleg d’aplicacions d’aquestes botigues és molt més reduït que el dels repositoris oficials, però ja hi ha diverses aplicacions que estan disponibles de les dues maneres, com passa, per exemple, amb el navegador web Chromium o el reproductor de mitjans VLC. En aquests casos, a la botiga apareixen les dues variants perquè l’usuari esculli la que vol instal·lar.

#### Instal·lació de programari

A Ubuntu 20.04, si volem utilitzar la interfície gràfica d’usuari per poder **gestionar les aplicacions** proporcionades pel sistema operatiu i instal·lar-ne de noves, cal anar a l’aplicació Ubuntu Software. Podem accedir a l’aplicació des del tauler ubicat a la part esquerra de la pantalla o des del botó _Activitats_ fent la cerca corresponent. L’aplicació Ubuntu Software mostra els paquets en format Snap i Deb, tot i que prioritza els paquets Snap sobre els Deb.

Si volem **instal·lar un nou paquet**, cal seleccionar la lupa que trobem a la part superior esquerra de la finestra per cercar-lo pel seu nom. Si no coneixem el nom del programa i volem investigar una mica quins programes podem instal·lar, podem navegar per les categories de programes que trobem a la part inferior de la finestra. Un cop hem seleccionat l’aplicació , polsem _Instal·lar_ i el sistema ens demanarà que ens autentifiquem introduint la nostra contrasenya abans de començar la instal·lació. Podeu observar l’aplicació Ubuntu Software a la [figura.20](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig20).FiguraAplicació Ubuntu Software![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/ubuntusoftware.jpg)

A la interfície gràfica d’usuari també podem utilitzar el gestor de paquets **Synaptic**, una eina per la gestió del programari més avançada que Ubuntu Software i que pot realitzar una sèrie de tasques que aquest últim no pot fer. Synaptic no es troba instal·lat de forma predeterminada, però el podem instal·lar sense problema des del mateix Ubuntu Software. Cal tenir en compte que actualment, Synaptic no mostra els paquets en format Snap o Flatpak i només permet gestionar els paquets en format Deb.

A Ubuntu 20.04, si volem utilitzar el terminal per instal·lar programes disposem de les següents eines per defecte:

* **dpkg**. Aquesta eina és la base del sistema de gestió de paquets de GNU/Linux Debian. S’utilitza per instal·lar, eliminar i proporcionar informació sobre els paquets Deb. Aquesta és una eina de baix nivell que no permet descarregar paquets de repositoris ni resoldre conflictes de dependències complexos.
* **apt**. L’eina apt permet realitzar la instal·lació de paquets de programari, l’actualització de paquets de programari ja instal·lats, l’actualització dels repositoris i fins i tot l’actualització de tot el sistema Ubuntu.
* **snap**. L’eina permet instal·lar programari de forma fàcil independentment de la distribució que utilitzem. Aquests paquets contenen l’aplicació desitjada però també les biblioteques i els arxius necessaris per executar-se correctament.

Per instal·lar un paquet .deb utilitzant l’**eina dpkg**, cal utilitzar l’ordre següent:

* `sudo dpkg –install nom_del_paquet.deb`

Per instal·lar un paquet utilitzant l’**eina apt**, cal utilitzar l’ordre següent:

* `sudo apt install nom_del_paquet`

Per instal·lar un paquet utilitzant l’**eina snap**, cal utilitzar l’ordre següent:

* `sudo snap install nom_del_paquet`

#### Desinstal·lació de programari

Als sistemes operatius GNU/Linux podem utilitzar tant la interfície gràfica d’usuari com el terminal per desinstal·lar aplicacions.

Per **eliminar una aplicació** utilitzant Ubuntu Software, cal seleccionar l’opció _Instal·lat_ a la part central superior de la finestra, per després seleccionar l’aplicació que volem eliminar de la llista d’aplicacions instal·lades, i eliminar-la polsant _Suprimeix_. Perquè l’aplicació s’elimini cal que confirmem que volem desinstal·lar l’aplicació i que introduïm la nostra contrasenya per autentificar-nos. Podeu observar aquesta finestra a la [figura.21](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig21).FiguraVisualització d’aplicacions instal·lades a Ubuntu Software![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/ubuntusoftwared.jpg)

Algunes aplicacions depenen d’altres per funcionar correctament. Si volem eliminar una aplicació que és necessària per una altra, el sistema ens avisarà i ens demanarà que confirmem si volem eliminar les dues aplicacions.

A Ubuntu 20.04 si volem utilitzar el terminal per desinstal·lar programes disposem, per defecte, de les mateixes eines que per instal·lar els paquets, dpkg, apt i snap.

Per desinstal·lar un paquet .deb, utilitzant l’**eina dpkg**, cal utilitzar l’ordre següent:

* `sudo dpkg –remove nom_del_paquet.deb`

Aquesta eliminació no és completa, es mantindran tots els arxius de configuració i altres dades, de forma que hem eliminat el programa però és possible tornar a instal·lar-lo de nou amb la mateixa configuració. Per eliminar completament totes les dades associades a un paquet cal utilitzar l’ordre:

* `sudo dpkg –purge nom_del_paquet.deb`

No es recomana desinstal·lar paquets utilitzant dpkg a la majoria dels casos. És millor utilitzar un administrador de paquets que controli les dependències per assegurar-nos que el sistema es troba en un estat coherent. Amb l’eina dpkg és possible que eliminem un paquet però no els paquets que en depenen, que seguiran instal·lats i podrien no funcionar correctament.

Per desinstal·lar un paquet utilitzant l’**eina apt** caldrà utilitzar l’ordre següent:

* `sudo apt remove nom_del_paquet`

Igual que passa amb l’eina dpkg, aquesta opció només elimina el paquet però no els arxius associats al paquet. Si volem eliminar totes les dades vinculades al paquet cal utilitzar l’ordre:

* `sudo apt purge nom_del_paquet`

Per desinstal·lar un paquet utilitzant l’**eina snap** caldrà utilitzar l’ordre següent:

* `sudo snap remove nom_del_paquet`

#### Inventari

Podem mantenir un inventari del programari instal·lat al sistema informàtic, tenint un registre dels programes instal·lats, les dates d’instal·lació, número de llicències o el cost monetari. Aquesta llista permet verificar si algun programari ha estat instal·lat sense el consentiment de l’administrador del sistema o si existeixen aplicacions no utilitzades.

La llista de tot el programari instal·lat en un sistema informàtic s’anomena _**inventari del programari**_

La llista amb tots els programes instal·lats al sistema Ubuntu 20.04 es pot trobar a Ubuntu Software, a l’opció _Instal·lats_.

Si volem utilitzar el terminal a Ubuntu 20.04 per visualitzar els programes instal·lats podem utilitzar les eines dpkg o snap.

Per enumerar tots els paquets Deb instal·lats al sistema operatiu utilitzant l’**eina dpkg** ho farem amb l’ordre:

* `dpkg -l`

Per mostrar la llista de paquets instal·lats mitjançant l’**eina apt**, ho farem amb l’ordre:

* `apt list –installed`

Per enumerar tots els paquets **en format snap** instal·lats al sistema operatiu utilitzant l’eina snap ho farem amb l’ordre:

* `snap list`

#### Actualització del sistema operatiu

El programari o sistema operatiu publicat pels desenvolupadors no es pot considerar mai totalment finalitzat. Una vegada publicat, **sempre es pot millorar** incloent noves funcionalitats, corregint errors o problemes de seguretat. Aquestes millores i correccions s’implanten al sistema mitjançant actualitzacions.

Les **actualitzacions** són fragments addicionals de programari que publiquen els desenvolupadors dels sistemes operatius i serveixen per millorar aquests sistemes.

Als sistemes GNU/Linux tots els paquets d’arxius d’actualització és troben als **repositoris**.

A Ubuntu 20.04 per instal·lar les actualitzacions del sistema operatiu utilitzant la interfície gràfica d’usuari cal executar el _**Gestor d’actualitzacions**_. Podeu observar la finestra de configuració del gestor d’actualitzacions a la [figura.22](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig22).FiguraGestor d’actualitzacions![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/gestoractualitzacions.png)

En aquesta finestra podem seleccionar quins tipus d’actualitzacions volem comprovar, amb quina freqüència i què volem fer quan hi hagi noves actualitzacions. També podem seleccionar si volem que el sistema operatiu ens avisi quan hi hagi una nova versió d’Ubuntu per descarregar.

A la majoria de casos no cal reiniciar el sistema operatiu després de l’actualització, però és possible que el sistema ens demani fer-ho perquè els nous canvis s’apliquin.

Si volem utilitzar el mode d’ordres per actualitzar el sistema operatiu ho farem mitjançant el terminal amb l’ordre `apt upgrade`. L’ordre `apt upgrade` acostuma a utilitzar-se després de l’ordre `apt update`. L’ordre `apt update` actualitza la llista de paquets disponibles i les seves versions, però no instal·la ni actualitza cap paquet. Aquesta llista de paquets s’actualitza en funció dels repositoris que tenim definits al nostre sistema operatiu. L’ordre `apt upgrade` permet **instal·lar les noves versions** de programari un cop l’ordre anterior ha descarregat la llista actualitzada de programari disponible. Per tant, per actualitzar el sistema operatiu a l’últim nivell d’actualitzacions disponibles, executarem aquestes dues ordres:

* `sudo apt update`
* `sudo apt upgrade`

Si volem actualitzar tots els **paquets snap** instal·lats al sistema operatiu, utilitzem l’ordre:

* `sudo snap refresh`.

Si només volem **llistar les actualitzacions disponibles** dels paquets snap sense instal·lar-les utilitzem l’opció –list de la següent forma: `snap refresh –list`.

### Configuració dels dispositius perifèrics

Als sistemes operatius GNU/Linux, la detecció del maquinari la realitza el nucli del sistema operatiu quan arrenca el sistema oferint també la possibilitat de reconèixer altres dispositius que s’han connectat més tard i que no requereixen el reinici del sistema operatiu per funcionar.

El nucli de Linux té un **disseny modular**. Quan es realitza la instal·lació del sistema operatiu es fa un escaneig del maquinari present al sistema. Basant-se en aquest escaneig i en la informació que proporciona l’usuari, el programa d’instal·lació decideix quins mòduls necessitaran estar disponibles en el sistema en el moment de l’arrencada.

Mòdul del nucli

Un mòdul del nucli de Linux és un programari que pot carregar-se o descarregar-se del nucli quan l’usuari o algun dispositiu que es connecta o desconnecta del sistema ho sol·licita.

Quan s’afegeix nou maquinari després de la instal·lació, si el mòdul que el suporta no està disponible al sistema, caldrà configurar el nucli perquè pugui carregar el mòdul adequat en el moment en què sigui necessari.

Aquests mòduls poden haver estat desenvolupats pels propis desenvolupadors del nucli de Linux o per les companyies que han fabricat el dispositiu de maquinari. Aquests mòduls també es poden anomenar _**controladors**_.

Ens podem trobar que alguns controladors no venen instal·lats per defecte, sobretot els propietaris. Llavors caldrà instal·lar uns controladors addicionals. A Ubuntu 20.04, per fer-ho, anem a _Programari i actualitzacions_ i seleccionem la pestanya _Controladors addicionals_. Instal·lant aquests controladors addicionals millorarem el rendiment del maquinari i podrem accedir a les seves funcions addicionals. Podeu observar la finestra de controladors addicionals a la [figura.23](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/a2/continguts.html#fig23).FiguraControladors addicionals![](https://ioc.xtec.cat/materials/FP/Recursos/fp_smx_m02_/web/fp_smx_m02_htmlindex/WebContent/u3/media/controladorsaddicionals.png)

Si volem utilitzar el mode d’ordres podem comprovar quins controladors i maquinari detecta el nostre sistema operatiu amb les ordres següents:

* `lshw`. Aquesta ordre fa uns llista de tot el maquinari detectat pel nostre sistema informàtic.
* `fdisk -l`. Aquesta ordre llista tots els dispositius d’emmagatzematge que tenim al sistema informàtic.
* `lsusb`. Aquesta ordre permet llistar tots els dispositius USB connectats al sistema.
* `lspci`. Mostra informació sobre els busos i dispositius PCI al sistema.
* `dmesg`. Mostra tots els controladors de dispositius reconeguts pel nucli.

### Verificació i documentació del procés de configuració d'un sistema operatiu

L’últim pas, un cop hem configurat el sistema operatiu, serà verificar que funciona correctament i documentar el procés de configuració.

És molt important documentar tot el procés de configuració que s’ha fet del sistema operatiu per diferents **motius**. Els més destacables són:

* Aconseguirem que qualsevol persona que vulgui reproduir el procés de documentació ho pugui fer de la mateixa forma.
* Qualsevol persona podrà reprendre el treball de configuració més endavant perquè coneixerà el procés que s’ha seguit.
* S’evita que una única persona conegui tot el procés i que tota la configuració depengui d’aquesta única persona.
* Redactar el procés de configuració fa possible revisar el procés per buscar oportunitats de millora.

Un manual d’instal·lació i configuració pot estar format per diferents apartats, alguns dels quals fan referència al procés d’instal·lació, incidències aparegudes, dades del sistema, etc.

Per a més informació sobre la gestió de la documentació, podeu consultar el punt “Documentació del procés d’instal·lació i incidències”, dins de l’apartat “Instal·lació de sistemes operatius lliures” d’aquesta mateixa unitat.

Dins de l’apartat relacionat amb la configuració del sistema, cal afegir la **informació referent al programari instal·lat** al sistema, indicant el nom, la versió, la data d’instal·lació, la seva llicència i una petita descripció. També cal deixar constància dels perifèrics que utilitza el sistema, les seves característiques i configuració, i finalment es pot documentar com i quan es fan les actualitzacions de programari al sistema.

Una opció també interessant que es pot incloure a la documentació del procés de configuració del sistema és la creació d’arxius i directoris bàsics a l’entorn empresarial. És interessant documentar els principals directoris que s’han creat, quin és el seu contingut i quins permisos tenen assignats.

