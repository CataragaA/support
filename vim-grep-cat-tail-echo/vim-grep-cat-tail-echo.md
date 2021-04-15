Cuprins comenzi
- [1. VIM](#1-vim)
- [2. Grep](#2-grep)
- [3. Cat](#3-cat)
- [4. Echo](#4-echo)
- [5. Tail](#5-tail)


# 1. VIM
* Vim este un editor text pe care il putem folosi din linia de comanda Terminal. Asta ne ofera rapiditate si flexibilitate cand vine vorba de administrarea unui sistem, modificare fisierelor de configurare etc, fiind prezent in sistemul de operare Linux. Ne putem conecta de la distanta prin SSH si va trebui sa accesam direct din consola pentru editarea unui fisier, de aceea VIM este cea mai buna si rapida solutie.
* In primul rand pentru a putea folosi VIM, trebuie sa instalam programul: `apt-get install vim`
* In al doilea rand trebuie sa ne alegem un fisier pe care dorim sa-l accesam si sa intram in el pur si simplu: `vim file1` sau sa cream noi unul cu touch file1.
  - ## __*Operatii in Vim*__
* **Vizualizarea** (continutului) fisierului fara a-l modifica (“miscandu-ne” folosind “sagetile”)
* **Modificarea** acestuia (apasand tasta `i` si introducand textul dorit): tasta "i" ne va duce in modul “INSERT“ care ne permite sa facem modificari in fisier.
* **Iesire** din fisier trebuie sa urmam procedura:
    * Apasam ESC
    * Scriem `:q` (daca vrem exit din fisier)
    * Sau `:wq` (daca vrem save & exit)(write&quit)
    * Sau `:q!` (daca vrem exit fara salvarea modificarilor, am introdus un text si apoi m-am razgandit)
* `CTRL+E` - Scroll sus 
* `CTRL+Y` - Scroll jos
* `/` - cautare in textul fisierului cuvinte identifice(key sensitive) iar daca sunt mai multe rezultate, mutare cu tasta `n`
* `:set ignorecase` - anulare key sensitive, astfel incat textul sa poate fi cautat cu majuscule si minuscule.
  
# 2. Grep
Cu ajutorul grep **Get Regular Expression Patterns**, se poate căuta într-un fișier text linie cu linie după un anumit șir de caractere (care poate fi specificat și prin intermediul unei expresii regulate) și afișa liniile care conțin acel șablon (pattern) indicat.
* `man grep` - instructiuni in terminal pentru utilizare
* Cea mai simplă formă a comenzii grep este:
`grep support file-ana.txt` - Comanda îmi va afișa toate liniile din fișierul file-ana.txt care conțin șirul de caractere support.
* Uneori este deosebit de util să știm câte linii îndeplinesc un anumit criteriu (contorizarea numărului de potriviri). Pentru aceasta vom folosi comanda -`grep -c support file-ana.txt`
* Pentru a afișa numărul liniilor unde întâlnim o anumită potrivire (va mai ușor la editarea ulterioară a fișierului în cazul rezolvării unei anumite erori) vom folosi opțiunea -n :
`grep -n support file-ana.txt`
* Dacă ne aflăm într-un director și vrem să căutăm un anumit șablon în toate fișierele text din directorul curent și din subdirectoare vom folosi opțiunea -r sau -R:
`grep -r "șablon"` (În loc de grep -r se poate folosi și __rgrep__.
* Linux este un sistem de operare case sensitive, adică face diferența dintre litere mari și litere mici. Pentru a-i spune comenzii grep să ignore literele mari și cele mici, vom folosi opțiunea -i (ignore case): `grep -i Support file-ana.txt`
* Vom folosi comanda grep cu opțiunea -l pentru a afișa toate fișierele care conțin un anumit cuvânt: 
`grep -l 'support' *.md` -va afișa toate numele de fișiere cu extensia .md și care conțin cuvântul support.


# 3. Cat
* `cat` -prescurtarea de la concatenate. Nu este foarte bună pentru vizualizarea fișierelor mari, comanda fiind destinată doar pentru conținut de câteva zeci de linii. Există 4 utilizări comune ale cat comanda:
    * 3.1. Poate _afișa_ un fișier, 
    * 3.2. poate _concatena_ (combina) mai multe fișiere `$ cat document1 document2` . Dacă folosim comanda în același mod, dar îi oferim două sau mai multe fișiere, atunci scoate concatenarea pentru fișiere:  \
`echo "This is how we do it" > test1`\
`echo "*This is how we do it*" > test2`\
`cat test1 test2`
    * 3.3. poate reda text 
    * 3.4. poate fi folosit pentru a crea un fișier nou. `echo "Ana are mere" > newfile-ana.txt` - creare fisier nou newfile-ana cu continut -Ana are mere. Apoi folosim cat comanda pentru a afișa conținutul.
* `cat test1> test2` - vom redirecționa conținutul fișierului test1 către un nou fișier numit test2
* `cat test1 >> test2` -acest lucru permite să se atașeze fișierul existent prin simbolul >> (dublu mai mare decât), acest lucru va determina adăugarea conținutului fișierului la sfârșitul fișierului destinație. 
* `cat file1.txt | grep "ana" > test4.txt` - din file1.txt se va extrage randul care contine cuvantul "ana" si il va copia intr-un nou fisier denumit test4.

# 4. Echo
Echo este utilizat în mod frecvent în scripturile shell pentru a afișa un mesaj sau pentru a produce rezultatele altor comenzi.
* Folosim comanda cat pentru a vizualiza conținutul fișierului: `cat file1.txt`
* _Redicretionare catre un fisier_ =>
`echo -e 'Afara ploua si este urat' >> file.txt` . 
Dacă file.txt nu există, comanda îl va crea. Când utilizam **>**,  fișierul va fi suprascris, în timp ce **>>**- va adăuga noul text pe langa ce se afla in fișier.


# 5. Tail
Comanda tail afișează ultima parte (10 linii implicit) a unuia sau mai multor fișiere sau date conectate. Poate fi folosit și pentru a monitoriza modificările fișierului în timp real, de obicei combinate cu alte instrumente precum grep.
* `tail filename.txt` -va afișa ultimele 10 linii.
* `tail -n filename.txt` - utilizam opțiunea -n (- --lines ) pentru a specifica numărul de linii care urmează să fie afișate. Pentru a afișa ultimele 50 de linii, utilizam: `tail -n 50 filename.txt`.
* `tail -f filename.txt` -pentru a monitoriza un fișier pentru modificări.Această opțiune este utilă în special pentru monitorizarea fișierelor jurnal. Pentru a întrerupe comanda cozii în timp ce urmărește un fișier, apăsam **Ctrl+C** .
* `tail -F filename.txt` - Pentru a continua monitorizarea fișierului atunci când este recreat. Această opțiune este utilă în situațiile în care comanda de coadă urmărește un fișier jurnal care se rotește. Când se folosește cu opțiunea -F, comanda tail va redeschide fișierul imediat ce a devenit din nou disponibil.
* `tail filename1.txt filename2.txt` - Dacă sunt furnizate mai multe fișiere ca intrare la comanda coadă, acestea vor afișa ultimele zece linii din fiecare fișier.
* `tail -f /var/log/apache2/access.log | grep 192.168.42.12` - pentru a monitoriza fișierul jurnal de acces apache și pentru a afișa doar liniile care conțin adresa IP 192.168.42.12. Acest lucru este posibil, deoarece comanda de coadă poate fi utilizată în combinație cu alte comenzi prin redirecționarea ieșirii standard de la / la alte utilități folosind conducte.