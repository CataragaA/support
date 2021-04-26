# Teorie Linux
Cuprins :
  - [Capitol 1 - Introducere Linux](#capitol-1---introducere-linux)
  - [Capitol 2 - Sistem de fisiere](#capitol-2---sistem-de-fisiere)
  - [Capitol 3 - Scurtaturi manipulare foldere/fisiere](#capitol-3---scurtaturi-manipulare-folderefisiere)
  - [Capitol 4 - Utilizatori și grupuri](#capitol-4--utilizatori-și-grupuri)
  - [Capitol 5 - Permisiuni fisiere](#capitol-5---permisiuni-fisiere)
  - [Capitol 6 - Procese](#capitol-6---procese)
## Capitol 1 - Introducere Linux 
LINUX este denumit cel mai utilizat sistem de operare și este cel mai bine cunoscut pentru eficiența și performanța sa rapidă. LINUX a fost introdus pentru prima dată de Linux Torvalds și se bazează pe Linux Kernal. Poate rula pe diferite platforme hardware fabricate de HP, Intel, IBM etc.
![poza](linux-introducere.png)

* Diferența între LINUX și UNIX?
    * **LINUX** este un software open source și un sistem de operare gratuit utilizat pentru hardware și software pentru computer, dezvoltarea jocurilor, PC-uri etc.\
    **UNIX** este un sistem de operare care este practic utilizat în Intel, HP, servere de internet etc.
  * **LINUX** are prețuri, precum și versiuni distribuite și descărcate gratuit.	Diferite versiuni / arome de UNIX au structuri de preț diferite.
  * Utilizatorii **LINUX** ar putea fi oricine, inclusiv utilizatorii casnici, dezvoltatorii etc.	**UNIX** a fost dezvoltat practic pentru mainframe, servere și stații de lucru, cu excepția OSX, care este conceput astfel încât să poată fi folosit de oricine.
  * **LINUX** Sistemul de suport pentru fișiere include Ext2, Ext3, Ext4, Jfs, Xfs, Btrfs, FAT etc.	**UNIX** - sistemul de suport pentru fișiere include jfs, gpfs, hfs etc.
  * BASH (Bourne Again Shell) este shell-ul implicit **Linux**, adică interfața în modul text care acceptă mai mulți interpreți de comandă.	Pentru **UNIX** - Bourne shell servește ca interfață în modul text, care este acum compatibilă cu multe altele, inclusiv BASH.
  * **LINUX** oferă două interfețe grafice, KDE și Gnome.	Pentru **UNIX** fost creat un mediu desktop comun care servește ca GUI pentru UNIX.
  * Exemple **LINUX** : Red Hat, Fedora, Ubuntu, Debian etc.	Exemple **UNIX** : Solaris, All Linux
  *  **LINUX** oferă o securitate mai mare și are aproximativ 60-100 de viruși enumerați până în prezent.	**UNIX** de asemenea, este foarte securizat și are aproximativ 85-120 de viruși enumerați până în prezent.

### _Explicați LILO?_
Răspuns: `LILO (Linux Loader)` este încărcătorul de boot pentru sistemul de operare Linux care îl încarcă în memoria principală, astfel încât să poată începe operațiunile sale. Bootloader aici este un mic program care gestionează un boot dual. LILO domiciliat în MBR ( Master Boot Record ). 

### _Ce este spațiul Swap?_
Răspuns: Spațiul **swap** este cantitatea de memorie fizică care este alocată pentru a fi utilizată de Linux pentru a păstra temporar unele programe care rulează simultan. Această condiție apare de obicei atunci când memoria RAM nu are suficientă memorie pentru a suporta toate programele care rulează simultan. Această gestionare a memoriei implică schimbarea memoriei către și de la stocarea fizică.

### _Explicați desktop-ul virtual?_
Răspuns: Când există mai multe ferestre disponibile pe desktopul curent și apare problema minimizării și maximizării ferestrelor sau a restaurării tuturor programelor actuale, „Virtual Desktop” servește ca alternativă. Vă permite să deschideți unul sau mai multe programe pe o ardezie curată.

### _Explicați termenul GUI?_
Răspuns: GUI reprezintă `interfața grafică pentru utilizator.` GUI este considerat cel mai atractiv și mai ușor de utilizat, deoarece constă în utilizarea de imagini și pictograme. Aceste imagini și pictograme sunt făcute clic și sunt manipulate de către utilizatori în scopul comunicării cu sistemul.

### _Explicați termenul CLI?_
Răspuns: CLI înseamnă `Command Line Interface`. Este o modalitate prin care oamenii interacționează cu computerele și este, de asemenea, cunoscută sub numele de interfață cu linia de comandă. Se bazează pe procesul de tranzacție de solicitare și răspuns textual în care utilizatorul tastează comenzi declarative pentru a instrui computerul să efectueze operațiuni.

### _Tipuri de permisiuni de fișiere sub LINUX?_
Răspuns: Fiecărui fișier și director din Linux li se atribuie trei tipuri de proprietari și anume „Utilizator”, „Grup” și „Altele”. Cele trei tipuri de permisiuni definite pentru toți cei trei proprietari sunt:
* `Citit`: Această permisiune vă permite să deschideți și să citiți fișierul, precum și să enumerați conținutul directorului.
* `Scrie`: Această permisiune vă permite să modificați conținutul fișierului, precum și să adăugați, să eliminați și să redenumiți fișierele stocate în directoare.
* `Executa`: Utilizatorii pot accesa și rula fișierul din director. Nu puteți rula un fișier decât dacă este setată permisiunea de executare.

### _Explicați Linux Shell?_
Răspuns: Pentru executarea oricăror comenzi, utilizatorul folosește un program cunoscut sub numele de `shell`. Linux shell este practic o interfață de utilizator utilizată pentru executarea comenzilor și comunicarea cu sistemul de operare Linux. Shell nu folosește nucleul pentru a executa anumite programe, a crea fișiere etc.
Există mai multe shell-uri disponibile cu Linux, care includ următoarele:
* BASH (Bourne Again SHell)
* CSH (Shell C)
* KSH (Korn Shell)
* TCSH

### _Ce este un script Shell?_
Răspuns: este un fișier de program sau se spune un fișier text plat în care anumite comenzi Linux sunt executate una după alta. Deși viteza de execuție este lentă, scriptul Shell este ușor de depanat și poate simplifica și procesele de automatizare de zi cu zi.

### _De ce Linux este considerat mai sigur decât alte sisteme de operare?_
Răspuns: Linux este un sistem de operare open-source și în zilele noastre crește rapid în lumea / piața tehnologică. Deși întregul cod scris în Linux poate fi citit de oricine, atunci este considerat mai sigur din următoarele motive:
* Linux oferă utilizatorilor săi privilegii implicite limitate, care sunt practic restrânse la nivelurile inferioare. în cazul oricărui atac de virus, acesta va ajunge doar la fișierele și folderele locale în care sunt salvate daunele la nivelul întregului sistem.
* Are un sistem puternic de audit care include jurnalele detaliate.
* Caracteristicile îmbunătățite ale tabelelor IP sunt utilizate pentru a implementa un nivel mai mare de securitate pentru mașina Linux.
* Linux are permisiuni de program mai stricte înainte de a instala ceva pe computer.

## Capitol 2 - Sistem de fisiere
![teorie](teorie%20linux.jpg)
* / – Directorul rădăcină a întregii ierarhii a sistemului de fișiere. Totul se află în interiorul acestui director.
* /bin – Programe (fișiere binare) esențiale gata să fie rulate; include comenzile de bază ale sistemului cum ar fi ls sau cp.
* /boot – Conține fișierele necesare încărcării kernelului.
* /dev – Fișiere de dispozitiv.
* /etc – Directorul configurației de bază a sistemului. Ar trebui să conțină numai fișiere de configurare și nici un fișier binar.
* /home – Director personal pentru utilizatori. Aici sunt stocate documentele, fișierele și setările personale.
* /lib – Conține biblioteci de fișiere care sunt folosite (apelate) de fișierele binare.
* /media – Folosit ca punct de montare (atașare) pentru dispozitivele media cum ar fi memoriile USB, etc.
* /mnt – Sisteme de fișiere montate temporar.
* /opt – Pachete opționale ale aplicațiilor software.
* /proc – Informații despre procesele care rulează în acel moment.
* /root – Directorul utilizatorului root.
* /run – Informații despre sistemul care rulează în acel moment, de la ultima restartare.
* /sbin – Conține fișiere binare esențiale funcționării sistemului, de regulă pot fi rulate doar de utilizatorul root.
* /srv – Date specifice care sunt servite (oferite) de către sistem.
* /tmp – Director de stocare pentru fișierele temporare.
* /usr – Acest director este oarecum denumit în mod nefericit. De cele mai multe ori nu conține fișiere ale utilizatorilor ca cele pe care le regăsim în directorul home. Acesta este menit pentru programele și utilitarele instalate de către utilizator, însă asta nu vă împiedică să adaugați directoare personale înăuntrul acestuia. Aici mai regăsim și subdirectoare ca /usr/bin, /usr/local, etc.
* /var – Directorul cu variabile este folosit pentru jurnalizarea (fișierele jurnal ale) sistemului, a utilizatorilor, cache, etc. În principiu cam tot ce este predispus să se schimbe continuu.

## Capitol 3 - Scurtaturi manipulare foldere/fisiere
* `.` (directorul curent). Este directorul în care vă aflați în mod curent.
* `..` (directorul părinte). Accesează directorul de deasupra directorului curent.
* `~` (directorul home). Acest simbol special ~ vă duce direct în directorul utilizatorului dvs. din interiorul foldwului home, ca de exemplu /home/radu.
* `–` (directorul anterior). Vă va duce la directorul anterior accesat de dvs.
* `!!` - scurtatura comanda history - va executa ultima comandă introdusă de dvs.
* `CTRL+r`- alta scurtatura history - vor începe să vă fie afișate pe ecran sugestii de potrivire și puteți naviga prin acestea, in functie de cuvintele cheie introduse.
* `clear` sau `CTRL+l` -curatare terminal
* `*` Wildcard-ul suprem, este folosit pentru reprezentarea tuturor caracterelor singulare sau a oricărui șir de caractere.
* `?` folosit pentru repezentarea unui caracter
* `[ ]` folosit pentru a reprezenta orice caracter enumerat în parantezele drepte
* `>(stout)`  reprezintă un operator de redirecționare care ne permite să modificăm unde se duce output-ul standard. Ne permite să trimitem output-ul comenzii echo Salut Lume către un fișier în loc să fie trimis implicit către ecran. 
* `<(stdin)` -

## Capitol 4 -Utilizatori și grupuri
![poza](utilizatori_si_grupuri.jpg)

În orice sistem de operare tradițional, există utilizatori și grupuri. Acestea există doar pentru nivelul de acces și permisiuni.Fiecare utilizator are propriul lui director personal în folderul home, în care își stochează diverse fișiere. Sistemul folosește ID utilizator sau **(UID)** pentru a gestiona utilizatorii si ID-ul de grup **(GID)**.
### _Rolul Root_
În Linux, putem avea utilizatori și alții decât oamenii obișnuiți care utilizează sistemul. Uneori acești utilizatori sunt denumiți demoni de sistem, care rulează continuu procese pentru a menține integritatea sistemului de operare. Unul dintre cei mai importanți utilizatori este _root_ sau superutilizatorul. Utilizatorul **root** este cel mai puternic din acel sistem, iar acesta poate accesa orice fișier și mai ales poate porni și opri orice proces. Pentru acest motiv poate fi periculos să operam tot timpul pentru că s-ar putea să ștergem din greșeală anumite fișiere critice pentru sistem.
### _Comanda sudo_
Din fericire, dacă este nevoie de acces root și utilizatorul are acces la root sau privilegii administrative, pot rula comenzi ca și root, dintr-un utilizator normal, cu ajutorul comenzii sudo. Comanda `sudo` **(superuser do)** este folosita pentru a rula o comandă cu acces root. De ex : _sudo cat /etc/shadow_, va necesita parola pentru a avea acces la fisier.
### _Comanda su_
Mai putem rula comenzi ca root cu ajutorul comenzii `su`. Această comandă practic va “substitui utilizatorii” și va deschide un shell pentru root, dacă nici un utilizator nu este specificat. Putem folosi această comandă pentru a substitui orice utilizator, atât timp cât le știm parola.

### _Comanda visudo_
Acum că știm ce comenzi să rulam ca și super utilizator, întrebarea este cum știm cine are acces să facă acest lucru? Sistemul nu va lăsa pe oricine să ruleze comenzi ca root. Și totuși cum de știe care utilizator are dreptul? Exista un fișier denumit `/etc/sudoers`, iar acest fișier gestionează utilizatorii care au dreptul să ruleze comanda sudo. Putem edita acest fișier cu ajutorul comenzii `visudo`.

### _Fișierul /etc/passwd_ 
In mod normal într-o pagină de setări a utilizatorilor, ne așteptam să vedem numai utilizatori umani. Insă, vom remarca că fișierul /etc/passwd conține și alți utilizatori pentru a rula diferite procese cu permisiuni diferite. De exemplu, utilizatorul daemon este folosit pentru procese daemon.
`Fișierul /etc/passwd` - Pentru a afla ce ID îi corespunde unui utilizator, ne uităm în fișierul cat /etc/passwd. Fiecare linie afișează informație despre un singur utilizator, și de regulă, vom vedea utilizatorul root în prima line a acestui fișier : `root:x:0:0:root:/root:/bin/bash`  , unde sunt mai multe câmpuri separate prin simbolul : care ne oferă informații adiționale despre utilizatori. Acum, le explicăm pe rând:
  * 1.Utilizator
  * 2.Parola utilizatorului – parola nu este stocată în acest fișier, ci este stocată de regulă în fișierul /etc/shadow. Vom vorbi mai multe despre asta în următoarea lecție despre /etc/shadow, dar pentru moment, să țtiți că acesta conține parole de utilizator criptate. Aici, în acest câmp, veți vedea multe simboluri diferite. Dacă veți vedea un “x” asta înseamnă că parola este stocată în fișierul /etc/shadow, în timp ce un “*” se va traduce în faptul că utilizatorul nu are acces la logare (conectare), iar dacă acel câmp este gol, asta înseamnă că utilizatorul nu are o parolă.
  * 3.ID-ul utilizatorului – după cum vedeți UID-ul lui root este 0
  * 4.ID-ul grupului
  * 5.Câmpul GECOS – Acesta este de regulă folosit pentru a lăsa comentarii despre utilizator sau despre cont, cum ar fi numele lor real sau numărul de telefon. Aceste date sunt separate prin virgulă.
  * 6.Directorul home al utilizatorului
  * 7.Shell-ul utilizatorului – veți vedea probabil o mulțime de utilizatori cu shell-ul implicit setat pentru bash.

 `Fișierul /etc/shadow`  este folosit pentru a stoca informații despre autentificarea utilizatorilor. Necesită permisiuni de citire de nivel super utilizatore (root).
_sudo cat /etc/shadow_  :
root:MyEPTEa$6Nonsense:15000:0:99999:7:::

`Fișierul /etc/group`  - permite grupruri diferite cu permisiuni diferite.
_cat /etc/group_    :   root : * : 0 : pete\
Foarte similar cu structura câmpurilor din /etc/password, cele din /etc/group sunt după cum urmează:
    * 1.Nume grup
    * 2.Parola grup – Nu există o nevoie de a seta o parolă pentru un grup, ci doar folosirea comenzii sudo pentru elevarea privilegiilor mai degrabă este standardul. Un simbol “*” va fi pus acolo ca și valoare implicită.
    * 3.ID Grup (GID)
    * 4.Lista de utilizatori – puteți specifica manual utilizatorii pe care îi doriți să facă parte dintr-un anumit grup.
  
### _Gestionare utilizatori_
* `sudo useradd radu` - adaugarea utilizator nou prin crearea unui director home și altele, crează o intrare în fișierul /etc/passwd pentru utilizatorul radu, setează grupurile implicite și adaugă încă o intrare în fișierul /etc/shadow
* `sudo userdel radu` - anuleaza modificările făcute în fișiere de către comanda useradd. 
* `passwd radu` -permite să schimbam parola personala sau a unui alt utilizator (asta dacă avem privilegii root).

## Capitol 5 - Permisiuni fisiere
* `ls -l Desktop` rezulta `drwxr-xr-x 2 radu utilizatori 4096 Dec 1 11:45` . Permisiunile fișierelor sunt împărțite în patru părți sau grupuri. Prima parte este tipul de fișiere ,,d'' fiind director. Următoarele trei grupuri (părți) ale parametrilor fișierului reprezintă de fapt permisiunile în sine. Permisiunile sunt afișate în grupuri de 3 biți fiecare. Primii 3 biți reprezintă permisiunile **utilizatorului**, apoi permisiunile **grupului** și în final permisiunile pentru **alții**.
d | rwx | r-x | r-x 
    * r: citire
    * w: scriere
    * x: execuție (în principiu un program executabil)
    * -: gol (fără acea permisiune)

* Schimbarea permisiunilor poate fi făcută foarte ușor cu ajutorul comenzii `chmod 755 fisierul_meu`. Reprezentările numerice sunt prezentate mai jos:
4: permisiunile de citire
2: permisiunile de scriere
1: permisiunile de execuție\
7 = 4 + 2 + 1, deci 7 reprezintă permisiunile utilizatorului și conține drepturi de citire, scriere și execuție.\
5 = 4 + 1, grupul are permisiuni de citire și execuție.\
5 = 4 +1, și ceilalți utilizatori au drepturi de citire și execuție.

* Modificarea apartenenței la un grup `sudo chgrp utilizatori fisierul_meu`

## Capitol 6 - Procese
