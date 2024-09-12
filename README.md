/*CONSERGNA 11-09-24*/

nome repo: db-university
Modellizzare la struttura di un database per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi Insegnanti;
- ogni Corso prevede più appelli d'Esame;
- ogni Studente è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.
Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella.
Utilizzare https://www.drawio.com/ per la creazione dello schema.
Esportare quindi il diagramma in jpg e caricarlo nella repo.
Buon lavoro

/*CONSEGNA 12-09-24*/

Dopo aver creato un nuovo database nel vostro phpMyAdmin e aver importato lo schema allegato, eseguite le query del file allegato.
Cosa consegnare? Nella stessa repo dell'esercizio di ieri, dopo aver testato le vostre query con phpMyAdmin, riportatele in un file txt o nel file README.md e caricatelo nella vostra repo.
Numero push: 1 per ogni query.
Le query 9,10,11 sono da considerarsi bonus

/*SOLUZIONE ESERCIZIO 12-09-24*/


Query 1

SELECT * 
FROM students 
WHERE YEAR(date_of_birth) = 1990;

Query 2

SELECT *
FROM courses
WHERE cfu > 10;

Query 3
SELECT * 
FROM students 
WHERE YEAR(CURDATE()) - YEAR(date_of_birth) > 30;


QuERY 4
SELECT *
FROM courses
WHERE period LIKE 'I semestre'
AND year = 1;

Query 5

SELECT *
FROM exams
WHERE date LIKE '2020-06-20'
AND hour > '14:00:00';