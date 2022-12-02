<!-- Modellizzare la struttura di una tabella per memorizzare tutti i dati riguardanti una università:
- sono presenti diversi Dipartimenti (es.: Lettere e Filosofia, Matematica, Ingegneria ecc.);
- ogni Dipartimento offre più Corsi di Laurea (es.: Civiltà e Letterature Classiche, Informatica, Ingegneria Elettronica ecc..)
- ogni Corso di Laurea prevede diversi Corsi (es.: Letteratura Latina, Sistemi Operativi 1, Analisi Matematica 2 ecc.);
- ogni Corso può essere tenuto da diversi Insegnanti;
- ogni Corso prevede più appelli d'Esame;
- ogni Studente è iscritto ad un solo Corso di Laurea;
- ogni Studente può iscriversi a più appelli di Esame;
- per ogni appello d'Esame a cui lo Studente ha partecipato, è necessario memorizzare il voto ottenuto, anche se non sufficiente.
Pensiamo a quali entità (tabelle) creare per il nostro database e cerchiamo poi di stabilirne le relazioni. Infine, andiamo a definire le colonne e i tipi di dato di ogni tabella. -->


Table name: Università 

--------------------------------------

Table name: Dipartimenti - Economia

- id | PK | AI UI NN
- nome_dipartimento | 

Table name: Corsi di laurea - Marketing

- id | PK | AI UI NN
- nome_corso |

Table name: Corsi - Marketing Avanzato

- id | PK | AI UI NN
- n_studenti | 
- n_appelli_esame |
- id_insegnati

Table name: Insegnanti

- id | PK | AI UI NN
- materia | 
- nome |
- cognome |
- matricola |


Table name: Esami

- id | PK | AI UI NN
- id_corso |
- sessione |
- numero_appelli
- data_appello
- numero_studenti_iscritti
- voti_conseguiti



Tabella Ponte
Table name: Appelli d'Esame

- id_esame
- id_studente



Table name: Voti

- id | PK | AI UI NN
- numero_voto |
- id_studente


Table name: Studenti

- id | PK | AI UI NN
- nome |
- cognome |
- matricola |
- codice_fiscale |
- data_nascita |
- luogo_nascita |



- Relazioni: 

