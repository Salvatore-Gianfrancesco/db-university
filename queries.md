Query Todo:
 - Selezionare tutti gli studenti nati nel 1990 (160)
 ```sql
SELECT *
FROM `students`
WHERE YEAR(`date_of_birth`) = 1990;
 ```

 - Selezionare tutti i corsi che valgono più di 10 crediti (479)
 ```sql
SELECT *
FROM `courses`
WHERE `cfu` > 10;
 ```

 - Selezionare tutti gli studenti che hanno più di 30 anni
 ```sql
SELECT *
FROM `students`
WHERE YEAR(CURRENT_DATE()) - YEAR(`date_of_birth`) > 30;
 ```

 - Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
 ```sql
SELECT *
FROM `courses`
WHERE `year` = 1
AND period = 'I semestre';
 ```

 - Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)
 ```sql
SELECT *
FROM `exams`
WHERE `hour` BETWEEN '14:00:00' AND '23:59:59'
AND `date` = '2020-06-20';
 ```

 - Selezionare tutti i corsi di laurea magistrale (38)
 ```sql
SELECT *
FROM `degrees`
WHERE `level` = 'magistrale';
 ```

 - Da quanti dipartimenti è composta l'università? (12)
 ```sql
SELECT COUNT(`id`) AS `total_departments`
FROM `departments`;
 ```

 - Quanti sono gli insegnanti che non hanno un numero di telefono? (50)
 ```sql
SELECT *
FROM `teachers`
WHERE `phone` is NULL;
 ```

Group by:
 - Contare quanti iscritti ci sono stati ogni anno
 ```sql
SELECT YEAR(`students`.`enrolment_date`) AS `year`, COUNT(*) AS `students_number`
FROM `students`
GROUP BY YEAR(`enrolment_date`);
 ```
 
 - Contare gli insegnanti che hanno l'ufficio nello stesso edificio
 ```sql
SELECT `teachers`.`office_address`, COUNT(*) AS `teachers_number`
FROM `teachers`
GROUP BY `office_address`;
 ```
 
 - Calcolare la media dei voti di ogni appello d'esame
 ```sql
SELECT `exam_student`.`exam_id`, `courses`.`name`, AVG(`exam_student`.`vote`) AS `average_vote`
FROM `exam_student`
JOIN `exams` ON `exams`.`id` = `exam_student`.`exam_id`
JOIN `courses` ON `courses`.`id` = `exams`.`course_id`
GROUP BY `exam_student`.`exam_id`;
 ```
 
 - Contare quanti corsi di laurea ci sono per ogni dipartimento
 ```sql
SELECT `departments`.`name`, COUNT(`degrees`.`id`) AS `degrees_number`
FROM `degrees`
JOIN `departments` ON `departments`.`id` = `degrees`.`department_id`
GROUP BY `departments`.`name`;
 ```
