<!-- 

Group by:

- Contare quanti iscritti ci sono stati ogni anno
##  mysql> select year(enrolment_date) as enrolment_year,
    -> count(*) as enrolment_total
    -> from students
    -> group by year(enrolment_date)
    -> order by enrolment_year asc;  

- Contare gli insegnanti che hanno l'ufficio nello stesso edificio
##  mysql> select office_address,     
    -> count(*) as total_teachers
    -> from teachers
    -> group by office_address;

- Calcolare la media dei voti di ogni appello d'esame
## mysql> select exam_id, avg(vote) as average
    -> from exam_student
    -> group by exam_id;

- Contare quanti corsi di laurea ci sono per ogni dipartimento
##  mysql> select department_id, count(*) as total_degree_department
    -> from degrees
    -> group by department_id;

Joins:

- Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
##  mysql> select students.*
    -> from students     
    -> join degrees on degree_id = degrees.id
    -> where degrees.name = 'Corso di Laurea in Economia';

- Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
##  mysql> select degrees.level, degrees.name as degree_name, departments.name as department_name
    -> from degrees
    -> join departments on departments.id = 7
    -> where degrees.level = 'magistrale';

- Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
mysql> select id as id_teacher, name as Nome, surname as Cognome
    -> from teachers
    -> join course_teacher on teacher_id = teachers.id
    -> where teachers.name = 'Fulvio';
    // Da controllare!!!!

- Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono
  iscritti e il relativo dipartimento, in ordine alfabetico per cognome e nome

- Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

- Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

BONUS: 

- Selezionare per ogni studente il numero di tentativi sostenuti per ogni esame, stampando anche il
  voto massimo. Successivamente, filtrare i tentativi con voto minimo 18.

 -->