# Oracle Pluggable Database Assignment II

## Student Information
Name: Greg Jeffrey AWASSI 
Student ID: 28315

## Oracle Environment
Oracle Database 21c
SQL*Plus
Oracle Enterprise Manager (OEM)

## Task 1: Create a PDB
Created PDB: je_pdb_28315
Created user: jeffrey_plsqlauca_28315
The PDB was opened successfully in READ WRITE mode.

sqlplus / as sysdba
SHOW CON_NAME;
CREATE PLUGGABLE DATABASE je_pdb_2024101
ADMIN USER pdbadmin IDENTIFIED BY 1234
FILE_NAME_CONVERT = ('pdbseed','je_pdb_2024101');
ALTER PLUGGABLE DATABASE je_pdb_2024101 OPEN;
SELECT name, open_mode FROM v$pdbs;
ALTER SESSION SET CONTAINER = je_pdb_2024101;
SHOW CON_NAME;
CREATE USER jeffrey_plsqlauca_2024101 IDENTIFIED BY 1234;
GRANT CONNECT, RESOURCE TO jeffrey_plsqlauca_2024101;
SELECT username FROM dba_users;


## Task 2: Create and Delete a Temporary PDB
Temporary PDB: je_to_delete_pdb_28315
The PDB was successfully created, verified, and deleted completely.

CREATE PLUGGABLE DATABASE je_to_delete_pdb_2024101
ADMIN USER pdbadmin IDENTIFIED BY 1234
FILE_NAME_CONVERT = ('pdbseed','je_to_delete_pdb_2024101');


## Task 3: Oracle Enterprise Manager
OEM was configured and accessed successfully.
Dashboard confirmed:
- Oracle environment running
- Created PDB visible
- User visible

## Challenges Faced
Example:
Encountered ORA-65096 error (invalid common user name).
Solved by creating user inside PDB instead of CDB.

## Integrity Statement
I confirm that this work was completed independently as part of the practical assessment.
