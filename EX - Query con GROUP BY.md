NB: dal momento che l'esercizio del 13-08-24 sono in realtà due esercizi, ho preferito creare due file di testo per esercizio, invece di scrivere tutte le soluzioni possibile nel file README.md della repo. In questo modo anche i file saranno pi
 ordinati.

 /*CONSEGNA EX - Query con GROUP BY (13-09-24)*/

 1. Contare quanti iscritti ci sono stati ogni anno
 2. Contare gli insegnanti che hanno l'ufficio nello stesso edificio
 3. Calcolare la media dei voti di ogni appello d'esame
 4. Contare quanti corsi di laurea ci sono per ogni dipartimento

  /*SOLUZIONE EX - Query con GROUP BY (13-09-24)*/

  Query 1

  SELECT COUNT(*) AS number_students_for_year, YEAR(enrolment_date) AS enrolment_year 
  FROM students 
  GROUP BY YEAR(enrolment_date);

  Query 2 

  SELECT COUNT(*) AS teachers_quantity, office_address 
  FROM teachers 
  GROUP BY office_address;

  Query 3 (per sbaglio ho scritto "Query 1" anziche "Query 3" nel push precedente)

  SELECT AVG(vote) AS voto_medio, exam_id 
  FROM exam_student 
  GROUP BY exam_id;

  Query 4

  SELECT COUNT(*) AS degrees_number, department_id 
  FROM degrees 
  GROUP BY department_id;