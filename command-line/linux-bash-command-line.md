
# **Command Line**
## Comenzi de bază în Linux 
### 1. _Moduri de exprimare a căii: aflarea directorului curent, schimbarea acestuia şi listarea conţinutului_:
* `pwd`-**print working directory**-identifica locul unde te afli (director curent)
* `cd` - **change directory** -schimbă directorul curent
  * `cd /` - radacina (root folder)
  * `cd ~/` - schimba director incepand cu _home/ana*_
* `ls` - afisare continut
  *  `ls -a` - listează toate fişierele şi directoarele inclusiv pe cele ascunse
  *  `ls c*` - va afişa fişiere care au numele cu c 
  * `ls /` - listează conţinutul directorului părinte
* `/` - **Root directory** -cel mai de sus director
* `.` - **Current directory** - directorul în care sunt acum
* `..` - **Parent directory** -doar un director mai sus

### 2. _Comenzi pentru manipularea fişierelor şi directoarelor_:
* `mkdir` - **make directory** - crează un director cu numele indicat
  * `mkdir "folder new"` -creare folder compus, denumirea va fi in ghilimele
* `rmdir` - **remove directory**-şterge directorul doar cel gol
  * `rmdir -r` - şterge directorul cu continut
  * `rmdir -rf` - Ştergere director cu conţinut foarte mare
* `touch` - crează un fişier text cu numele indicat
* `cp` - **copy** - copiază fişierul sau directorul indicat într-un nou loc:
    * exemplu => (cp -r ../../curs-Cmd-Line/ .)
    * `cp A B` – copiere fişier A şi se crează fişierul B (pe care il putem denumi)
* `mv` - **move** - mută un fişier sau director în altă locaţie dar în acelaşi timp poate să şi redenumească.
  * `mv A B` – mutare A în B în cazul în care B este director 
  * `mv A B` – redenumire A în B dacă B este fişier  
* `rm` -**remove** - şterge un fişier sau director. 
* `nano` - editare fişier
* `cat[nume fişier]`- cat arată conţinutul fişierului în mod text pe ecran
* `less[numele fişierului]` - Arată conţinutul fişierului pagina cu pagina
* `grep` [şir de caractere de căutat] [numele fişierului]\
    * grep c* /etc/fstab 


### 3. _Comenzi pentru ajutor_:
* `hostname` - Afiseaza sau schimba hostname-ul sistemului
* `whoami` - cine sunt?
* `whatis` - Listează informaţii despre rolul unei comenzi
* `info` - Afisează o pagină informativă despre comanda primită ca parametru;
* `man` - listează manualul pentru comanda primită ca parametru
* `less` - Program de pipe

## Blocknote
**_ATENŢIE!_**  
Fişierele şterse din consolă nu se duc într-un folder numit Trash ca în cazul interfeţelor grafice. Odată şterse fişierele nu mai pot fi recuperate.
