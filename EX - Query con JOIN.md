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

  Query 3

  SELECT courses.name AS corsi_di_Fuvio_Amato
  FROM courses
  JOIN course_teacher ON courses.id = course_teacher.course_id
  JOIN teachers ON teachers.id = course_teacher.teacher_id
  WHERE teachers.id = 44

  Query 4

  SELECT students.surname, students.name, departments.name AS name_department, degrees.name AS name_degree
  FROM students
  JOIN degrees ON students.degree_id = degrees.id
  JOIN departments ON degrees.department_id = departments.id
  ORDER BY students.surname, students.name

  Query 5 

  SELECT degrees.name AS name_degree, courses.name AS name_course, teachers.name AS name_teacher, teachers.surname AS surname_teacher
  FROM degrees
  JOIN courses ON courses.degree_id = degrees.id
  JOIN course_teacher ON course_teacher.course_id = courses.id
  JOIN teachers ON course_teacher.teacher_id = teachers.id
  ORDER BY name_degree, name_course