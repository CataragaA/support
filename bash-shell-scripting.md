# Introducere in Bash Shell Scripting
**Sarcina 1**: `Navigare` - Voi recapitula cum să navighez prin structura directorului și să vizualizez conținutul unui director.
* `ls -al` - listare toate fisiere si dorectoare. In prima coloana, cele care incep cu liniuta sunt fisiere, cele cu ,,d" sunt directoare. 

**Sarcina 2**: `Manipularea fișierelor `- Voi recapitula cum să vizualizez conținutul unui fișier, să creez fișiere noi, să șterg și să redenumesc fișierele și să deschid un fișier într-un editor de text.
* `cat file1.txt > newfile2.txt` - va prealua textul din file 1 si il va copia intr-un nou fisier 2.
* `cat file1.txt >> proiect.txt` -va prelua textul din file 1 si il va adauga la sfarsitul fisierului proiect, pastrand informatia deja prezenta.
* `more` sau `less`- vizualizare fisiere foarte mari.
* `nano proiect.txt` - modifici textul, apoi CTRL+S si CTRL+X pentru iesire.
  
**Sarcina 3**: `Găsiți informații` - Voi recapitula despre fișiere, istoricul comenzilor și căile de fișiere.
* mkdir + mv newDir backups + rm
* `rm -ir backups` - stergi directorul cu fisiere din el fiind intrebat inainte, se va raspunde cu ,,y".
* find +grep 
* `find / -name "*backup*" 2>/dev/null | grep $USER`
* `history | grep cat` - cautare in istoric de cate ori am folositt functia cat.

**Sarcina 4**: `Aliases` - Voi învăța cum să implementez un alias pe o linie de comandă și cum să creez unul în fișierul meu .bash_aliases. 
Uneori tastarea comenzilor poate deveni o sarcină destul de repetitivă, sau dacă trebuie să tastați comenzi lungi de mai multe ori este recomandat să aveți un alias pentru acele comenzi. Pentru crearea unui alias pentru o comandă putem specifica pur și simplu numele aliasului și apoi atribuirea acestuia respectivei comenzi. Aceste comenzi nu se vor salva după restartare (reboot), așa că va trebui să adaugați un alias permanent într-un fișier în funcție de distribuție, dacă dorim să persiste după restartare.
* `$ alias porecla='ls -la'` - astfel în loc să tastam ls -la, putem tasta _porecla_ și aceasta va executa comanda.
* `unalias porecla` - putem șterge aliasurile cu ajutorul comenzii unalias
* `nano .bash_aliases` - creare fisier cu introducerea scurtaturilor- am creat scurtatura `alias cdbackups='cd ~/Desktop/newdir/backups/'`. Apoi **source .bash_aliases** pentru inregistrare.
  
**Sarcina 5**: `Scrierea unui script` - Voi utiliza comenzile pe care le-am învățat pentru a dezvolta un script care va face backup fișierelor din directorul meu de utilizator.

**Sarcina 6**: `Automatizarea cu Cron` - După finalizarea scriptului de rezervă, astfel încât să trimită prin e-mail fișierele de rezervă, voi afla despre cron și crontab și cum să le utilizez pentru a automatiza scriptul de rezervă.

* _**Cron**_ permite utilizatorilor Linux să execute comenzi sau scripturi la anumite momente bine stabilite.Este folosită, de regulă, de administratorii de sistem pentru backup. Vom folosi comanda crontab pentru a edita lista sarcinilor impuse a fi executate. Pentru a deschide crontab-ul personal (fișierul de configurare cron), se va executa comanda: `crontab -e nume fisier` .
* În fiecare linie din acest fișier putem defini ce comandă sau script să se execute, la ce interval de timp (din 5 în 5 minute, de 2 ori pe lună, etc.). Structura unei linii este următoarea: `minute oră zi-din-lună lună zi-din-săptămână cale/către/comandă`\
Unde:
    * minute: 0 - 59
    * ora: 0 - 23
    * ziua-din-lună: 0 - 31
    * luna: 1 - 12 (12 == decembrie), sau jan, feb, mar,...
    * ziua-din-săptămână: 0 - 6 (0 == duminică), sau sun, mon, tue, wed, thu, fri, sat
    * cale/către/comandă: calea către scriptul sau comanda care trebuie să se execute
* Un operator permite specificarea a mai multor valori într-un singur câmp. Pentru cron există 4 operatori:

    * `asteriscul (*)`: specifică toate valorile posibile pentru un câmp; de exemplu, un * în câmpul oră înseamnă că linia respectivă va fi executată în fiecare oră, un * în câmpul zi a lunii semnifică execuția în fiecare zi;
    * `virgula (,)`: acest operator specifică o listă de valori; de exemplu, dacă avem în câmpul zi a lunii 1,5,9,17,23,28, linia respectivă se va executa doar în zilele specificate din fiecare lună;
    * `liniuța (-)`: acest operator specifică un interval de valori; de exemplu, putem scrie 1-5 în loc de 1,2,3,4,5
    * `separatorul slash (/)`: specifică pasul valorilor respective; de exemplu, cum am avut mai sus 0-23/2, semnifică faptul că linia se va executa din 2 în două ore; tot la fiecare două ore mai poate fi specificat prin */2; la fiecare 20 de minute putem specifica dacă trecem în câmpul minute */20
    * Pentru a șterge toate sarcinile cron folosim comanda: `crontab -r`
##  Folosirea șirurilor speciale
În loc să folosim primele 5 câmpuri (minute, oră, zi-din-lună, lună, zi-din-săptămână), putem să definim sarcini cron folosind unul din următoarele 8 șiruri speciale:
* `@reboot`	rulează o singură dată, la pornirea serverului
* `@yearly`	rulează o dată pe an; echivalent cu "0 0 1 1 *"
* `@annually`	la fel cu @yearly
* `@monthly`	rulează o dată pe lună; echivalent cu "0 0 1 * *"
* `@weekly`	rulează o dată pe săptămână; echivalent cu "0 0 * * 0"
* `@daily`	rulează o dată pe zi; echivalent cu "0 0 * * *"
* `@midnight`	la fel ca @daily
* `@hourly`	rulează la fiecare oră; echivalent cu "0 * * * * "
  
  
## Câteva exemple de sarcini cron:
  
1. Linia de mai jos execută scriptul backup.sh în fiecare zi a săptămânii la ora 2 dimineața:
`0 2 * * * /root/backup.sh`
2. Linia următoare execută o anumită comandă în fiecare zi a săptămânii la 5 minute după miezul nopții: 
   `5 0 * * *cale/către/comandă`
3. Linia următoare se execută în prima zi a fiecărei luni la ora 14:15:
   `15 14 1 * * cale/către/comandă`
4. Linia de mai jos se execută la ora 22:00 în fiecare zi de luni până vineri `0 22 * * 1-5 cale/către/comandă`
5. Linia următoare se execută în fiecare zi din două în două ore, începând cu ora 0:23, continuând cu 02:23, 04:23, etc.
`23 0-23/2 * * * cale/către/comandă`