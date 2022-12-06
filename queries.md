# GIORNO 1° - Query Todo:
1 - Selezionare tutti gli studenti nati nel 1990 (160)
2 - Selezionare tutti i corsi che valgono più di 10 crediti (479)
3 - Selezionare tutti gli studenti che hanno più di 30 anni
4 - Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
5 - Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)
6 - Selezionare tutti i corsi di laurea magistrale (38)
7 - Da quanti dipartimenti è composta l'università? (12)
8 - Quanti sono gli insegnanti che non hanno un numero di telefono? (50)

## 1 - Selezionare tutti gli studenti nati nel 1990 (160)
```sql
SELECT *
FROM `students`
WHERE year(`date_of_birth`)=1990;
```
risultato 160 - ok

## 2 - Selezionare tutti i corsi che valgono più di 10 crediti (479)
```sql
SELECT *
FROM `courses`
WHERE `cfu` > 10;
```
risultato 479 - ok

## 3 - Selezionare tutti gli studenti che hanno più di 30 anni
```sql
SELECT*
FROM `students`
/* WHERE Year(2022)-(`date_of_birth`)>30; */
WHERE TIMESTAMPDIFF(Year, date_of_birth, curdate()) >30;
```
risultato ? - 5000

## 4 - Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
```sql
SELECT *
FROM `courses`
WHERE `year` = 1 AND `period` = 'I semestre';
```
risultato 286 - ok

## 5 - Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)
```sql
SELECT *
FROM `exams`
WHERE `date` = '2020-06-20' AND `hour` >= '14:00:00';
```
risultato 21 - ok

## 6 - Selezionare tutti i corsi di laurea magistrale (38)
```sql
SELECT *
FROM `degrees`
WHERE `level` LIKE 'magistrale';
```
risultato 38 - ok

## 7 - Da quanti dipartimenti è composta l'università? (12)
```sql
SELECT *
FROM `departments`;
```
risultato 12 - ok

## 8 - Quanti sono gli insegnanti che non hanno un numero di telefono? (50)
```sql
SELECT * FROM
`teachers` WHERE
`phone` IS NULL;
```
risultato 50 - ok

# GIORNO 2° - NUOVE QUERY:
## Group by:
1 - Contare quanti iscritti ci sono stati ogni anno
2 - Contare gli insegnanti che hanno l'ufficio nello stesso edificio
3 - Calcolare la media dei voti di ogni appello d'esame
4 - Contare quanti corsi di laurea ci sono per ogni dipartimento

## GROUP
## 1 - Contare quanti iscritti ci sono stati ogni anno
```sql
/* SELECT COUNT(id) as total_subscribers, year(enrolment_date) FROM students GROUP BY enrolment_date; */

SELECT COUNT(id) as total_subscribers, year(`students`.`enrolment_date`) as enrolment_year
FROM `students` 
GROUP BY year(`enrolment_date`);

```
## 2 - Contare gli insegnanti che hanno l'ufficio nello stesso edificio
```sql
SELECT COUNT(id) as total_teachers, `office_address` as same_address
FROM `teachers`
GROUP BY `office_address`;
```
## 3 - Calcolare la media dei voti di ogni appello d'esame
<!-- AVG()	Return the average value of the argument -->
```sql
SELECT AVG(`vote`) as media, `exam_id` as number_degree
FROM `exam_student`
GROUP BY `exam_student`.`exam_id`;

```

## 4 - Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico 1 per cognome e nome
```sql

```
## Join:
1 - Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia
2 - Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze
3 - Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)
4 - Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico 1 per cognome e nome
5 - Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti
6 - Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

## 1 - Selezionare tutti gli studenti iscritti al Corso di Laurea in Economia

## 2 - Selezionare tutti i Corsi di Laurea Magistrale del Dipartimento di Neuroscienze

## 3 - Selezionare tutti i corsi in cui insegna Fulvio Amato (id=44)

## 4 - Selezionare tutti gli studenti con i dati relativi al corso di laurea a cui sono iscritti e il relativo dipartimento, in ordine alfabetico 1 per cognome e nome

## 5 - Selezionare tutti i corsi di laurea con i relativi corsi e insegnanti

## 6 - Selezionare tutti i docenti che insegnano nel Dipartimento di Matematica (54)

## BONUS: Selezionare per ogni studente quanti tentativi d’esame ha sostenuto per superare ciascuno dei suoi esami

