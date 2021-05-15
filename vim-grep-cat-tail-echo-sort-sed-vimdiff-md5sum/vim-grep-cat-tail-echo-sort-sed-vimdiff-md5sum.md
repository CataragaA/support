Cuprins comenzi
- [1. VIM](#1-vim)
- [2. GREP](#2-grep)
- [3. CAT](#3-cat)
- [4. ECHO](#4-echo)
- [5. TAIL](#5-tail)
- [6. SORT](#6-sort)
- [7. SED GNU](#7-sed-gnu)
- [8. DIFF](#8-diff)
  - [VIMDIFF](#vimdiff)
  - [MD5SUM](#md5sum)
    - [LINK-URI :](#link-uri-)
  

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
  
# 2. GREP
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
* `grep -v "string" file.txt` - inverseaza cautarea patternului. Poate afisa linii care nu se potrivesc cu patternul cautat 
* `grep -o "string" file.txt` -afiseaza doar patternurile gasite. Neinsotit de alta optiunea, grep afiseaza intreaga linie in care a fost gasit stringul cautat. Folosind optiunea –o va afisa doar stringul cautat.
* `grep -o -b "string" file.txt` - afiseaza pozitia stringului gasit in cadrul liniei. 
* `grep "^start" file.txt` sau `grep "end$" file.txt`-Gaseste liniile care incep sau se inchei cu stringul cautat.


# 3. CAT
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

# 4. ECHO
Echo este utilizat în mod frecvent în scripturile shell pentru a afișa un mesaj sau pentru a produce rezultatele altor comenzi.
* Folosim comanda cat pentru a vizualiza conținutul fișierului: `cat file1.txt`
* _Redicretionare catre un fisier_ =>
`echo -e 'Afara ploua si este urat' >> file.txt` . 
Dacă file.txt nu există, comanda îl va crea. Când utilizam **>**,  fișierul va fi suprascris, în timp ce **>>**- va adăuga noul text pe langa ce se afla in fișier.


# 5. TAIL
Comanda tail afișează ultima parte (10 linii implicit) a unuia sau mai multor fișiere sau date conectate. Poate fi folosit și pentru a monitoriza modificările fișierului în timp real, de obicei combinate cu alte instrumente precum grep.
* `tail filename.txt` -va afișa ultimele 10 linii.
* `tail -n filename.txt` - utilizam opțiunea -n (- --lines ) pentru a specifica numărul de linii care urmează să fie afișate. Pentru a afișa ultimele 50 de linii, utilizam: `tail -n 50 filename.txt`.
* `tail -f filename.txt` -pentru a monitoriza un fișier pentru modificări.Această opțiune este utilă în special pentru monitorizarea fișierelor jurnal. Pentru a întrerupe comanda cozii în timp ce urmărește un fișier, apăsam **Ctrl+C** .
* `tail -F filename.txt` - Pentru a continua monitorizarea fișierului atunci când este recreat. Această opțiune este utilă în situațiile în care comanda de coadă urmărește un fișier jurnal care se rotește. Când se folosește cu opțiunea -F, comanda tail va redeschide fișierul imediat ce a devenit din nou disponibil.
* `tail filename1.txt filename2.txt` - Dacă sunt furnizate mai multe fișiere ca intrare la comanda coadă, acestea vor afișa ultimele zece linii din fiecare fișier.
* `tail -f /var/log/apache2/access.log | grep 192.168.42.12` - pentru a monitoriza fișierul jurnal de acces apache și pentru a afișa doar liniile care conțin adresa IP 192.168.42.12. Acest lucru este posibil, deoarece comanda de coadă poate fi utilizată în combinație cu alte comenzi prin redirecționarea ieșirii standard de la / la alte utilități folosind conducte.
# 6. SORT
Comanda sort este utilizata pentru sortarea liniilor alfabetic, pentru aranjarea rândurilor.. Un exemplu de utilizare este:
* `sort fisier1.txt` sau `sort < fisier.txt`- aranjare in ordine afabetica randurile. Daca pui semnul mai mare ,,>", va sterge continutul fisierului si te va lasa scrii altul.
* `sort -r fisier.txt` - aranjare randuri in ordine inversa.
* `sort -n fisier1.txt` - in functie de valoarea numerica.
* Nu este întotdeauna esențial să rulam comanda sort într-un fișier. Putem să o conductăm direct pe terminal cu comanda efectivă.`ls -l /home/ana | sort -nk5`
* `sort -u fisier.txt` - elimina duplicatele
* `sort fisier.txt proiect.txt` - sorteaza continut 2 fisiere
* `sort -nk9 fisier.txt`-sorteaza coloana 9 cu cifre 
* `sort -k5 fisier.txt` - sorteaza 5 alfabetic 

# 7. SED GNU
Sed poate accepta un fișier ca intrare, îl va citi și va modifica linie cu linie conform ordinului dat. Rezultatul va fi afișat de ieșirea standard, adică de ecran în acest caz. Acest lucru vă permite să manipulați fluxurile de date pentru a găsi, tăia, insera sau înlocui linii de text folosind expresii regulate.
Forma generală de căutare și înlocuire a textului folosind sed are următoarea formă:   **`sed 's/regexp/replacement/g' inputFileName > outputFileName sed`** .

Parametri de baza:
* p - Imprimare - imprimă linii cu text de potrivire
* d - Șterge - șterge liniile cu textul corespunzător
* s - înlocuiește textul de potrivire pe fiecare linie
* n - suprimă imprimarea automată a textului care nu se potrivește
* E / r - permite expresii regulate extinse
* i - editează fișierul pe loc, în loc să tipărească pe ecran
* g - Steagul global de înlocuire.

Functiile de baza:

7.1. **Substitutie**  
sintaxa de baza `s/regexp/replacement/flags`
    - sed 's/y/Y/g' test.txt > test2.txt - inlocuire litera minuscula y cu majuscula Y cu creare rezultat in alt fisier.
    - sed 's/and/\&/g;s/^I/You/g' test.txt - inlocuire cuvinte ,,and" in & si ,,I" in You.
    - Opțiunea mai ușoară și mult mai ușor de citit este să folosești un alt caracter delimitator. Majoritatea oamenilor folosesc bara verticală ( | ) sau colon (:), dar puteți utiliza orice alt caracter: sed -i 's|/bin/bash|/usr/bin/zsh|g' file.txt
__PS: Când este furnizat steagul de înlocuire, toate evenimentele vor fi înlocuite.__


7.2. **Afișarea** (sau ștergerea) unei porțiuni alese dintr-un fișier:
* `sed -n 3,5p test.txt` -afiseaza randurile de la 3 la 5
* `sed 6,7d test.txt` - afisare tot in afara de randul 6 si 7
* `sed G test.txt` - adăugare o linie goală după fiecare linie de text
* `sed 4d test.txt` - stergere rand 4
* Pentru a face o copie de rezervă atunci când editați un fișier cu sed : `sed -i.bak 's/y/Y/g' test.txt`

7.3. **Filtrare**:
Sed este, de asemenea, frecvent utilizat pentru a filtra liniile dintr-un fișier sau un flux. De exemplu, dacă dorim doar să vedem liniile care conțin "John", utilizam: 
`sed -n'/John/p' test.txt > test2.txt`

# 8. DIFF 
- **diff**  înseamnă diferență. Această comandă este utilizată pentru a afișa diferențele din fișiere prin compararea fișierelor linie cu linie, si care ne spune care linii dintr-un fișier trebuie modificate pentru a face cele două fișiere identice.

- Important de reținut este că diff folosește anumite simboluri speciale și instrucțiuni care sunt necesare pentru a face două fișiere identice. Acesta ne spune instrucțiunile despre cum să schimbam primul fișier pentru a face ca acesta să se potrivească cu al doilea fișier.

Simbolurile speciale sunt:
`a: adăugați
c: schimbare
d: ștergeți`
Sintaxă: dif [opțiuni] File1 File2

- Liniile precedate de `a` <sunt linii din primul fișier.
- Liniile precedate de> sunt linii din al doilea fișier.
- Linia următoare conține 2,3c3 ceea ce înseamnă că de la linia 2 la linia 3 din primul fișier trebuie modificat pentru a se potrivi cu numărul 3 din al doilea fișier. Apoi ne spune acele linii cu simbolurile de mai sus.
-Cele trei liniuțe („-“) separă doar liniile fișierului 1 și fișierului 2.
- ieșirea 3d2 înseamnă ștergerea liniei a treia a primului fișier, astfel încât ambele fișiere să se sincronizeze la linia 2.

## VIMDIFF
> Modul diferit al lui Vim ne permite să comparăm cu ușurință conținutul a două (sau mai multe) fisiere. Putem apela `vimdiff` din linia de comandă dându-i două sau mai multe nume de fișiere. vimdiff lansează Vim, creează o fereastră pentru fiecare fișier specificat și evidențiază diferențele dintre acestea. 


## MD5SUM
> Md5sum este conceput pentru a verifica integritatea datelor folosind MD5 (Message Digest Algorithm 5). MD5 este un hash criptografic pe 128 de biți și, dacă este utilizat corect, poate fi utilizat pentru a verifica autenticitatea și integritatea fișierului.

Opțiuni :
- -b: citit în modul binar
- -c: citim MD5 din fișiere și le verificam
- -- tag: cream o sumă de control în stil BSD
- -t: citit în modul text (implicit)

Exemplu 1:
1. md5sum a.txt > checkmd5.md5
2. md5sum -c checkmd5.md5
3. Schimbam o litera din fisierul a.txt
4. md5sum -c checkmd5.md5 - output-ul va fi a.txt: FAILED
md5sum: WARNING: 1 computed checksum did NOT match.

### LINK-URI : 
* https://ro.joecomp.com/how-use-sed-find
* https://ro.eyewated.com/un-ghid-rapid-pentru-utilizarea-comenzilor-sed-in-linux/