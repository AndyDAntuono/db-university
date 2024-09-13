NB: dal momento che l'esercizio del 13-08-24 sono in realtà due esercizi, ho preferito creare due file di testo per esercizio, invece di scrivere tutte le soluzioni possibile nel file README.md della repo. In questo modo anche i file saranno più ordinati.

 /*CONSEGNA EX - Query con JOIN BY (13-09-24)*/

 1. Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
 2. Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di
    Neuroscienze
 3. Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
 4. Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui
    sono iscritti e il relativo dipartimento, in ordine alfabetico per cognome e
     nome
 5. Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
 6. Selezionare tutti i docenti che insegnano nel Dipartimento di
    Matematica (54)
 7. BONUS: Selezionare per ogni studente il numero di tentativi sostenuti
    per ogni esame, stampando anche il voto massimo. Successivamente,
    filtrare i tentativi con voto minimo 18.

  /*SOLUZIONE EX - Query con JOIN BY (13-09-24)*/

  Query 1 

  SELECT students.name, students.surname, students.registration_number 
  FROM students JOIN degrees ON students.degree_id = degrees.id 
  WHERE degrees.name = 'Corso di Laurea in Economia';

  Query 2 

  SELECT degrees.name AS nome_corso, departments.name AS nome_dipartimento 
  FROM degrees JOIN departments ON degrees.department_id = departments.id 
  WHERE departments.name = 'Dipartimento di Neuroscienze' 
  AND degrees.level = 'magistrale';