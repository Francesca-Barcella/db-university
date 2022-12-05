## Query Todo:
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
WHERE Year(2022)-(`date_of_birth`)>30;
```
risultato ? - 5000

## 4 - Selezionare tutti i corsi del primo semestre del primo anno di un qualsiasi corso di laurea (286)
```sql

```
risultato 286 - 

## 5 - Selezionare tutti gli appelli d'esame che avvengono nel pomeriggio (dopo le 14) del 20/06/2020 (21)
```sql

```
risultato 21 - 

## 6 - Selezionare tutti i corsi di laurea magistrale (38)
```sql

```
risultato 38 - 

## 7 - Da quanti dipartimenti è composta l'università? (12)
```sql

```
risultato 12 - 

## 8 - Quanti sono gli insegnanti che non hanno un numero di telefono? (50)
```sql

```
risultato 50 - 

