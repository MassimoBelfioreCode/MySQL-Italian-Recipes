**MySQL Italian Recipes Database**

DBMS: MySQL. Il file Massimo_Belfiore_X81001087_relazioneprogetto.pdf contiene la documentazione **dettagliata** del progetto.

Questo progetto consiste nella **progettazione** e quindi **realizzazione** del **database** relazionale per una piattaforma di ricette di cucina italiana e gestione delle recensioni. Include la progettazione, la creazione delle tabelle, il popolamento dei dati, una serie di query SQL dimostrative e uno script php che mostra la ricetta del giorno.

**Tecnologie utilizzate**

    MySQL (DBMS)
    phpMyAdmin per la gestione del database
    MySQL Workbench per la progettazione e il diagramma ER
    Apache + PHP come ambiente server locale
    SQL (DDL + DML) per la definizione e manipolazione dei dati

Il Database realizzato è stato ottimizzato tramite l'aggiunta di indici. Il database permette di effettuare operazioni di DML e DLL, quindi supporta tutte le principali operazioni SQL:

    creazione e gestione tabelle (DDL)
    inserimento, modifica e cancellazione dati (DML)
    relazioni tra entità tramite chiavi primarie ed esterne
    ecc...

**Contenuto degli script**

«» Lo script db_ricette.sql contiene il codice per creare il database.

«» Lo script operazioni.sql contiene l’implementazione in SQL delle operazioni previste.

«» Lo script trigger.sql contiene dei trigger.

«» Lo script homepage_piattaforma_ricette.php contiene il codice per visualizzare sul Web Browser dell'utente la ricetta del giorno.

**Utilizzare il Database**

Istruzioni:

    Apri phpMyAdmin o MySQL Workbench.
    Crea un nuovo database, ad esempio:

    CREATE DATABASE piattaforma_ricette;

    Importa il file ricette.sql.
    Esegui le query dimostrative presenti in operazioni.sql.

Alternativamente è possibile utilizzare MySQL CLI prima installandolo sulla propria macchina e successivamente creando un utente. --> Istruzioni su come configurare un database MySQL utilizzando la shell mysql:

    Avviate mysql dalla riga di comando della shell:

    mysql -u root -p

    Inserisci Password: metti la password

    Create un nuovo utente per il database("nome database") e la relativa password("nome password")

    CREATE USER 'duser'@'localhost' IDENTIFIED BY 'nome password';

    Create un nuovo database per il progetto("db_piattaforma_ricette"):

    CREATE DATABASE db_piattaforma_ricette;

    Adesso potete concedere sostanzialmente al nuovo utente che avete creato i diritti di accesso al nuovo database con:

    GRANT ALL ON db_piattaforma_ricette.* TO 'duser'@'localhost';

**Esempio di query:**

#Ricerca di una ricetta in base agli ingredienti

SELECT R.id_ricetta, R.titolo, R.id_categoria, R.numero_recensioni, R.dosi_per, R.preparazione, R.senza_glutine, R.senza_lattosio, R.gourmet, R.media_apprezzamento

FROM ricetta R, contiene C, ingrediente I

WHERE R.id_ricetta = C.id_ricetta AND C.id_ingrediente = I.id_ingrediente AND I.nome = "Spaghetti" AND C.quantita < "350g"

**SCHEMA**

<img width="1064" height="562" alt="db_ricette(2)" src="https://github.com/user-attachments/assets/f45d7f13-b573-42e5-b93b-66139857f077" />

<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE svg
PUBLIC "-//W3C//DTD SVG 1.1//EN"
       "http://www.w3.org/Graphics/SVG/1.1/DTD/svg11.dtd">
<svg viewBox="55 56 1119 618" width="1064px" height="562px" xmlns="http://www.w3.org/2000/svg" version="1.1">
   <line x1="920" y1="501" x2="910" y2="501" style="stroke:#b0b;stroke-width:1;"/>
   <line x1="423" y1="101" x2="413" y2="101" style="stroke:#b0b;stroke-width:1;"/>
   <line x1="910" y1="501" x2="423" y2="101" style="stroke:#b0b;stroke-width:1;"/>
   <line x1="912.5" y1="501" x2="916.03553390593" y2="504.53553390593" style="stroke:#b0b;stroke-width:2;"/>
   <line x1="912.5" y1="501" x2="916.03553390593" y2="497.46446609407" style="stroke:#b0b;stroke-width:2;"/>
   <line x1="418" y1="101" x2="421.53553390593" y2="104.53553390593" style="stroke:#b0b;stroke-width:2;"/>
   <line x1="418" y1="101" x2="421.53553390593" y2="97.464466094067" style="stroke:#b0b;stroke-width:2;"/>
   <line x1="920" y1="521" x2="910" y2="521" style="stroke:#c00;stroke-width:1;"/>
   <line x1="516" y1="412" x2="506" y2="412" style="stroke:#c00;stroke-width:1;"/>
   <line x1="910" y1="521" x2="516" y2="412" style="stroke:#c00;stroke-width:1;"/>
   <line x1="912.5" y1="521" x2="916.03553390593" y2="524.53553390593" style="stroke:#c00;stroke-width:2;"/>
   <line x1="912.5" y1="521" x2="916.03553390593" y2="517.46446609407" style="stroke:#c00;stroke-width:2;"/>
   <line x1="511" y1="412" x2="514.53553390593" y2="415.53553390593" style="stroke:#c00;stroke-width:2;"/>
   <line x1="511" y1="412" x2="514.53553390593" y2="408.46446609407" style="stroke:#c00;stroke-width:2;"/>
   <line x1="284" y1="593" x2="294" y2="593" style="stroke:#cb0;stroke-width:1;"/>
   <line x1="358" y1="412" x2="368" y2="412" style="stroke:#cb0;stroke-width:1;"/>
   <line x1="294" y1="593" x2="358" y2="412" style="stroke:#cb0;stroke-width:1;"/>
   <line x1="291.5" y1="593" x2="287.96446609407" y2="596.53553390593" style="stroke:#cb0;stroke-width:2;"/>
   <line x1="291.5" y1="593" x2="287.96446609407" y2="589.46446609407" style="stroke:#cb0;stroke-width:2;"/>
   <line x1="363" y1="412" x2="359.46446609407" y2="415.53553390593" style="stroke:#cb0;stroke-width:2;"/>
   <line x1="363" y1="412" x2="359.46446609407" y2="408.46446609407" style="stroke:#cb0;stroke-width:2;"/>
   <line x1="566" y1="139" x2="556" y2="139" style="stroke:#c00;stroke-width:1;"/>
   <line x1="423" y1="101" x2="413" y2="101" style="stroke:#c00;stroke-width:1;"/>
   <line x1="556" y1="139" x2="423" y2="101" style="stroke:#c00;stroke-width:1;"/>
   <line x1="558.5" y1="139" x2="562.03553390593" y2="142.53553390593" style="stroke:#c00;stroke-width:2;"/>
   <line x1="558.5" y1="139" x2="562.03553390593" y2="135.46446609407" style="stroke:#c00;stroke-width:2;"/>
   <line x1="418" y1="101" x2="421.53553390593" y2="104.53553390593" style="stroke:#c00;stroke-width:2;"/>
   <line x1="418" y1="101" x2="421.53553390593" y2="97.464466094067" style="stroke:#c00;stroke-width:2;"/>
   <line x1="673" y1="119" x2="683" y2="119" style="stroke:#0bf;stroke-width:1;"/>
   <line x1="781" y1="111" x2="791" y2="111" style="stroke:#0bf;stroke-width:1;"/>
   <line x1="683" y1="119" x2="781" y2="111" style="stroke:#0bf;stroke-width:1;"/>
   <line x1="680.5" y1="119" x2="676.96446609407" y2="122.53553390593" style="stroke:#0bf;stroke-width:2;"/>
   <line x1="680.5" y1="119" x2="676.96446609407" y2="115.46446609407" style="stroke:#0bf;stroke-width:2;"/>
   <line x1="786" y1="111" x2="782.46446609407" y2="114.53553390593" style="stroke:#0bf;stroke-width:2;"/>
   <line x1="786" y1="111" x2="782.46446609407" y2="107.46446609407" style="stroke:#0bf;stroke-width:2;"/>
   <line x1="282" y1="253" x2="292" y2="253" style="stroke:#c00;stroke-width:1;"/>
   <line x1="296" y1="101" x2="306" y2="101" style="stroke:#c00;stroke-width:1;"/>
   <line x1="292" y1="253" x2="296" y2="101" style="stroke:#c00;stroke-width:1;"/>
   <line x1="289.5" y1="253" x2="285.96446609407" y2="256.53553390593" style="stroke:#c00;stroke-width:2;"/>
   <line x1="289.5" y1="253" x2="285.96446609407" y2="249.46446609407" style="stroke:#c00;stroke-width:2;"/>
   <line x1="301" y1="101" x2="297.46446609407" y2="104.53553390593" style="stroke:#c00;stroke-width:2;"/>
   <line x1="301" y1="101" x2="297.46446609407" y2="97.464466094067" style="stroke:#c00;stroke-width:2;"/>
   <line x1="282" y1="273" x2="292" y2="273" style="stroke:#cb0;stroke-width:1;"/>
   <line x1="358" y1="412" x2="368" y2="412" style="stroke:#cb0;stroke-width:1;"/>
   <line x1="292" y1="273" x2="358" y2="412" style="stroke:#cb0;stroke-width:1;"/>
   <line x1="289.5" y1="273" x2="285.96446609407" y2="276.53553390593" style="stroke:#cb0;stroke-width:2;"/>
   <line x1="289.5" y1="273" x2="285.96446609407" y2="269.46446609407" style="stroke:#cb0;stroke-width:2;"/>
   <line x1="363" y1="412" x2="359.46446609407" y2="415.53553390593" style="stroke:#cb0;stroke-width:2;"/>
   <line x1="363" y1="412" x2="359.46446609407" y2="408.46446609407" style="stroke:#cb0;stroke-width:2;"/>
   <line x1="268" y1="413" x2="278" y2="413" style="stroke:#bbb;stroke-width:1;"/>
   <line x1="781" y1="111" x2="791" y2="111" style="stroke:#bbb;stroke-width:1;"/>
   <line x1="278" y1="413" x2="781" y2="111" style="stroke:#bbb;stroke-width:1;"/>
   <line x1="275.5" y1="413" x2="271.96446609407" y2="416.53553390593" style="stroke:#bbb;stroke-width:2;"/>
   <line x1="275.5" y1="413" x2="271.96446609407" y2="409.46446609407" style="stroke:#bbb;stroke-width:2;"/>
   <line x1="786" y1="111" x2="782.46446609407" y2="114.53553390593" style="stroke:#bbb;stroke-width:2;"/>
   <line x1="786" y1="111" x2="782.46446609407" y2="107.46446609407" style="stroke:#bbb;stroke-width:2;"/>
   <line x1="268" y1="393" x2="278" y2="393" style="stroke:#c00;stroke-width:1;"/>
   <line x1="358" y1="412" x2="368" y2="412" style="stroke:#c00;stroke-width:1;"/>
   <line x1="278" y1="393" x2="358" y2="412" style="stroke:#c00;stroke-width:1;"/>
   <line x1="275.5" y1="393" x2="271.96446609407" y2="396.53553390593" style="stroke:#c00;stroke-width:2;"/>
   <line x1="275.5" y1="393" x2="271.96446609407" y2="389.46446609407" style="stroke:#c00;stroke-width:2;"/>
   <line x1="363" y1="412" x2="359.46446609407" y2="415.53553390593" style="stroke:#c00;stroke-width:2;"/>
   <line x1="363" y1="412" x2="359.46446609407" y2="408.46446609407" style="stroke:#c00;stroke-width:2;"/>
   <line x1="791" y1="191" x2="781" y2="191" style="stroke:#c00;stroke-width:1;"/>
   <line x1="740" y1="553" x2="730" y2="553" style="stroke:#c00;stroke-width:1;"/>
   <line x1="781" y1="191" x2="740" y2="553" style="stroke:#c00;stroke-width:1;"/>
   <line x1="783.5" y1="191" x2="787.03553390593" y2="194.53553390593" style="stroke:#c00;stroke-width:2;"/>
   <line x1="783.5" y1="191" x2="787.03553390593" y2="187.46446609407" style="stroke:#c00;stroke-width:2;"/>
   <line x1="735" y1="553" x2="738.53553390593" y2="556.53553390593" style="stroke:#c00;stroke-width:2;"/>
   <line x1="735" y1="553" x2="738.53553390593" y2="549.46446609407" style="stroke:#c00;stroke-width:2;"/>
   <line x1="791" y1="291" x2="781" y2="291" style="stroke:#bbb;stroke-width:1;"/>
   <line x1="516" y1="412" x2="506" y2="412" style="stroke:#bbb;stroke-width:1;"/>
   <line x1="781" y1="291" x2="516" y2="412" style="stroke:#bbb;stroke-width:1;"/>
   <line x1="783.5" y1="291" x2="787.03553390593" y2="294.53553390593" style="stroke:#bbb;stroke-width:2;"/>
   <line x1="783.5" y1="291" x2="787.03553390593" y2="287.46446609407" style="stroke:#bbb;stroke-width:2;"/>
   <line x1="511" y1="412" x2="514.53553390593" y2="415.53553390593" style="stroke:#bbb;stroke-width:2;"/>
   <line x1="511" y1="412" x2="514.53553390593" y2="408.46446609407" style="stroke:#bbb;stroke-width:2;"/>
   <line x1="506" y1="492" x2="516" y2="492" style="stroke:#c00;stroke-width:1;"/>
   <line x1="657" y1="402" x2="667" y2="402" style="stroke:#c00;stroke-width:1;"/>
   <line x1="516" y1="492" x2="657" y2="402" style="stroke:#c00;stroke-width:1;"/>
   <line x1="513.5" y1="492" x2="509.96446609407" y2="495.53553390593" style="stroke:#c00;stroke-width:2;"/>
   <line x1="513.5" y1="492" x2="509.96446609407" y2="488.46446609407" style="stroke:#c00;stroke-width:2;"/>
   <line x1="662" y1="402" x2="658.46446609407" y2="405.53553390593" style="stroke:#c00;stroke-width:2;"/>
   <line x1="662" y1="402" x2="658.46446609407" y2="398.46446609407" style="stroke:#c00;stroke-width:2;"/>
   <rect width="184" height="20" x="920" y="471" style="fill:#007;stroke:black;"/>
   <text width="184" height="20" x="925" y="485" style="fill:#fff;" font-family="Arial" font-size="16px"> allergia_alimentare_verso</text>
   <rect width="184" height="20" x="920" y="491" style="fill:#aea;stroke:black;"/>
   <text width="184" height="20" x="925" y="505" style="fill:black;" font-family="Arial" font-size="16px">id_ingrediente</text>
   <rect width="184" height="20" x="920" y="511" style="fill:none;stroke:black;"/>
   <text width="184" height="20" x="925" y="525" style="fill:black;" font-family="Arial" font-size="16px">nickname</text>
   <rect width="121" height="20" x="609" y="523" style="fill:#007;stroke:black;"/>
   <text width="121" height="20" x="614" y="537" style="fill:#fff;" font-family="Arial" font-size="16px"> categoriaricetta</text>
   <rect width="121" height="20" x="609" y="543" style="fill:#aea;stroke:black;"/>
   <text width="121" height="20" x="614" y="557" style="fill:black;" font-family="Arial" font-size="16px">id_categoria</text>
   <rect width="121" height="20" x="609" y="563" style="fill:none;stroke:black;"/>
   <text width="121" height="20" x="614" y="577" style="fill:black;" font-family="Arial" font-size="16px">nome</text>
   <rect width="133" height="20" x="151" y="543" style="fill:#007;stroke:black;"/>
   <text width="133" height="20" x="156" y="557" style="fill:#fff;" font-family="Arial" font-size="16px"> contattoinstagram</text>
   <rect width="133" height="20" x="151" y="563" style="fill:none;stroke:black;"/>
   <text width="133" height="20" x="156" y="577" style="fill:black;" font-family="Arial" font-size="16px">nome_contatto</text>
   <rect width="133" height="20" x="151" y="583" style="fill:none;stroke:black;"/>
   <text width="133" height="20" x="156" y="597" style="fill:black;" font-family="Arial" font-size="16px">nickname</text>
   <rect width="107" height="20" x="566" y="89" style="fill:#007;stroke:black;"/>
   <text width="107" height="20" x="571" y="103" style="fill:#fff;" font-family="Arial" font-size="16px"> contiene</text>
   <rect width="107" height="20" x="566" y="109" style="fill:#aea;stroke:black;"/>
   <text width="107" height="20" x="571" y="123" style="fill:black;" font-family="Arial" font-size="16px">id_ricetta</text>
   <rect width="107" height="20" x="566" y="129" style="fill:#aea;stroke:black;"/>
   <text width="107" height="20" x="571" y="143" style="fill:black;" font-family="Arial" font-size="16px">id_ingrediente</text>
   <rect width="107" height="20" x="566" y="149" style="fill:none;stroke:black;"/>
   <text width="107" height="20" x="571" y="163" style="fill:black;" font-family="Arial" font-size="16px">quantita</text>
   <rect width="107" height="20" x="306" y="71" style="fill:#007;stroke:black;"/>
   <text width="107" height="20" x="311" y="85" style="fill:#fff;" font-family="Arial" font-size="16px"> ingrediente</text>
   <rect width="107" height="20" x="306" y="91" style="fill:#aea;stroke:black;"/>
   <text width="107" height="20" x="311" y="105" style="fill:black;" font-family="Arial" font-size="16px">id_ingrediente</text>
   <rect width="107" height="20" x="306" y="111" style="fill:none;stroke:black;"/>
   <text width="107" height="20" x="311" y="125" style="fill:black;" font-family="Arial" font-size="16px">nome</text>
   <rect width="107" height="20" x="306" y="131" style="fill:none;stroke:black;"/>
   <text width="107" height="20" x="311" y="145" style="fill:black;" font-family="Arial" font-size="16px">con_glutine</text>
   <rect width="107" height="20" x="306" y="151" style="fill:none;stroke:black;"/>
   <text width="107" height="20" x="311" y="165" style="fill:black;" font-family="Arial" font-size="16px">con_lattosio</text>
   <rect width="212" height="20" x="70" y="223" style="fill:#007;stroke:black;"/>
   <text width="212" height="20" x="75" y="237" style="fill:#fff;" font-family="Arial" font-size="16px"> intolleranza_alimentare_verso</text>
   <rect width="212" height="20" x="70" y="243" style="fill:#aea;stroke:black;"/>
   <text width="212" height="20" x="75" y="257" style="fill:black;" font-family="Arial" font-size="16px">id_ingrediente</text>
   <rect width="212" height="20" x="70" y="263" style="fill:none;stroke:black;"/>
   <text width="212" height="20" x="75" y="277" style="fill:black;" font-family="Arial" font-size="16px">nickname</text>
   <rect width="156" height="20" x="112" y="363" style="fill:#007;stroke:black;"/>
   <text width="156" height="20" x="117" y="377" style="fill:#fff;" font-family="Arial" font-size="16px"> recensione</text>
   <rect width="156" height="20" x="112" y="383" style="fill:none;stroke:black;"/>
   <text width="156" height="20" x="117" y="397" style="fill:black;" font-family="Arial" font-size="16px">nickname</text>
   <rect width="156" height="20" x="112" y="403" style="fill:#aea;stroke:black;"/>
   <text width="156" height="20" x="117" y="417" style="fill:black;" font-family="Arial" font-size="16px">id_ricetta</text>
   <rect width="156" height="20" x="112" y="423" style="fill:none;stroke:black;"/>
   <text width="156" height="20" x="117" y="437" style="fill:black;" font-family="Arial" font-size="16px">descrizione</text>
   <rect width="156" height="20" x="112" y="443" style="fill:none;stroke:black;"/>
   <text width="156" height="20" x="117" y="457" style="fill:black;" font-family="Arial" font-size="16px">data</text>
   <rect width="156" height="20" x="112" y="463" style="fill:none;stroke:black;"/>
   <text width="156" height="20" x="117" y="477" style="fill:black;" font-family="Arial" font-size="16px">voto_apprezzamento</text>
   <rect width="169" height="20" x="791" y="81" style="fill:#007;stroke:black;"/>
   <text width="169" height="20" x="796" y="95" style="fill:#fff;" font-family="Arial" font-size="16px"> ricetta</text>
   <rect width="169" height="20" x="791" y="101" style="fill:#aea;stroke:black;"/>
   <text width="169" height="20" x="796" y="115" style="fill:black;" font-family="Arial" font-size="16px">id_ricetta</text>
   <rect width="169" height="20" x="791" y="121" style="fill:none;stroke:black;"/>
   <text width="169" height="20" x="796" y="135" style="fill:black;" font-family="Arial" font-size="16px">titolo</text>
   <rect width="169" height="20" x="791" y="141" style="fill:none;stroke:black;"/>
   <text width="169" height="20" x="796" y="155" style="fill:black;" font-family="Arial" font-size="16px">numero_recensioni</text>
   <rect width="169" height="20" x="791" y="161" style="fill:none;stroke:black;"/>
   <text width="169" height="20" x="796" y="175" style="fill:black;" font-family="Arial" font-size="16px">gourmet</text>
   <rect width="169" height="20" x="791" y="181" style="fill:none;stroke:black;"/>
   <text width="169" height="20" x="796" y="195" style="fill:black;" font-family="Arial" font-size="16px">id_categoria</text>
   <rect width="169" height="20" x="791" y="201" style="fill:none;stroke:black;"/>
   <text width="169" height="20" x="796" y="215" style="fill:black;" font-family="Arial" font-size="16px">media_apprezzamento</text>
   <rect width="169" height="20" x="791" y="221" style="fill:none;stroke:black;"/>
   <text width="169" height="20" x="796" y="235" style="fill:black;" font-family="Arial" font-size="16px">senza_glutine</text>
   <rect width="169" height="20" x="791" y="241" style="fill:none;stroke:black;"/>
   <text width="169" height="20" x="796" y="255" style="fill:black;" font-family="Arial" font-size="16px">senza_lattosio</text>
   <rect width="169" height="20" x="791" y="261" style="fill:none;stroke:black;"/>
   <text width="169" height="20" x="796" y="275" style="fill:black;" font-family="Arial" font-size="16px">data_pubblicazione</text>
   <rect width="169" height="20" x="791" y="281" style="fill:none;stroke:black;"/>
   <text width="169" height="20" x="796" y="295" style="fill:black;" font-family="Arial" font-size="16px">nickname</text>
   <rect width="169" height="20" x="791" y="301" style="fill:none;stroke:black;"/>
   <text width="169" height="20" x="796" y="315" style="fill:black;" font-family="Arial" font-size="16px">dosi_per</text>
   <rect width="169" height="20" x="791" y="321" style="fill:none;stroke:black;"/>
   <text width="169" height="20" x="796" y="335" style="fill:black;" font-family="Arial" font-size="16px">preparazione</text>
   <rect width="76" height="20" x="667" y="372" style="fill:#007;stroke:black;"/>
   <text width="76" height="20" x="672" y="386" style="fill:#fff;" font-family="Arial" font-size="16px"> utente</text>
   <rect width="76" height="20" x="667" y="392" style="fill:#aea;stroke:black;"/>
   <text width="76" height="20" x="672" y="406" style="fill:black;" font-family="Arial" font-size="16px">id_utente</text>
   <rect width="76" height="20" x="667" y="412" style="fill:none;stroke:black;"/>
   <text width="76" height="20" x="672" y="426" style="fill:black;" font-family="Arial" font-size="16px">nome</text>
   <rect width="76" height="20" x="667" y="432" style="fill:none;stroke:black;"/>
   <text width="76" height="20" x="672" y="446" style="fill:black;" font-family="Arial" font-size="16px">cognome</text>
   <rect width="138" height="20" x="368" y="382" style="fill:#007;stroke:black;"/>
   <text width="138" height="20" x="373" y="396" style="fill:#fff;" font-family="Arial" font-size="16px"> utenteregistrato</text>
   <rect width="138" height="20" x="368" y="402" style="fill:none;stroke:black;"/>
   <text width="138" height="20" x="373" y="416" style="fill:black;" font-family="Arial" font-size="16px">nickname</text>
   <rect width="138" height="20" x="368" y="422" style="fill:none;stroke:black;"/>
   <text width="138" height="20" x="373" y="436" style="fill:black;" font-family="Arial" font-size="16px">data_nascita</text>
   <rect width="138" height="20" x="368" y="442" style="fill:none;stroke:black;"/>
   <text width="138" height="20" x="373" y="456" style="fill:black;" font-family="Arial" font-size="16px">data_registrazione</text>
   <rect width="138" height="20" x="368" y="462" style="fill:none;stroke:black;"/>
   <text width="138" height="20" x="373" y="476" style="fill:black;" font-family="Arial" font-size="16px">newsletter</text>
   <rect width="138" height="20" x="368" y="482" style="fill:none;stroke:black;"/>
   <text width="138" height="20" x="373" y="496" style="fill:black;" font-family="Arial" font-size="16px">id_utente</text>
</svg>



<img width="1106" height="773" alt="fisico_modello_schema" src="https://github.com/user-attachments/assets/0e5dc62d-b255-43e9-9fa6-e5dec42e08e5" />
