# Oracle Pluggable Database Assignment II

## Student Information

| Field | Information |
|-------|------------|
| Name | AWASSI Greg Jeffrey |
| Student ID | 28315 |
| Program | Computer Science |
| Database Version | Oracle 21c |

---

# Overview

This assignment demonstrates the creation, management, and deletion of Pluggable Databases (PDB) using Oracle Database 21c. It also includes Oracle Enterprise Manager (OEM) configuration and monitoring.

---

# Task 1: Create a New Pluggable Database

## PDB Information

| Item | Value |
|------|-------|
| PDB Name | je_pdb_28315 |
| Admin User | pdbadmin |
| Application User | jeffrey_plsqlauca_28315 |
| Password | 1234 |
| Status | READ WRITE |

## Commands Used

```sql
sqlplus / as sysdba

SHOW CON_NAME;

CREATE PLUGGABLE DATABASE je_pdb_28315
ADMIN USER pdbadmin IDENTIFIED BY 1234
FILE_NAME_CONVERT = ('pdbseed','je_pdb_28315');

ALTER PLUGGABLE DATABASE je_pdb_2024101 OPEN;

SELECT name, open_mode FROM v$pdbs;

ALTER SESSION SET CONTAINER = je_pdb_28315;

SHOW CON_NAME;

CREATE USER jeffrey_plsqlauca_28315 IDENTIFIED BY 1234;

GRANT CONNECT, RESOURCE TO jeffrey_plsqlauca_28315;

SELECT username FROM dba_users;
```

---

# Task 2: Create and Delete a Temporary PDB

## Temporary PDB Information

| Item | Value |
|------|-------|
| Temporary PDB Name | je_to_delete_pdb_2024101 |
| Status After Creation | Successfully Created |
| Status After Deletion | Completely Removed |

## Commands Used

```sql
CREATE PLUGGABLE DATABASE je_to_delete_pdb_28315
ADMIN USER pdbadmin IDENTIFIED BY 1234
FILE_NAME_CONVERT = ('pdbseed','je_to_delete_pdb_28315');

SELECT name FROM v$pdbs;

ALTER PLUGGABLE DATABASE je_to_delete_pdb_28315 CLOSE IMMEDIATE;

DROP PLUGGABLE DATABASE je_to_delete_pdb_28315 INCLUDING DATAFILES;

SELECT name FROM v$pdbs;
```

---

# Task 3: Oracle Enterprise Manager (OEM)

Oracle Enterprise Manager was configured and accessed successfully.

## Verification

| Component | Status |
|-----------|--------|
| Oracle Instance | Running |
| PDB Created | Visible |
| Application User | Visible |
| Dashboard Access | Successful |

OEM Dashboard screenshot is available in the `/screenshots` folder.

---

# Screenshots

All required screenshots are stored inside:

```
/screenshots
```

Required screenshots:

- PDB Creation
- PDB Open State
- User Created
- Temporary PDB Creation
- Temporary PDB Deletion
- OEM Dashboard

---

# Challenges Faced

| Challenge | Solution |
|------------|----------|
| PDB not opening | Used ALTER PLUGGABLE DATABASE OPEN |
| Container error | Switched container using ALTER SESSION SET CONTAINER |
| Privilege issue | Granted CONNECT and RESOURCE roles |

---

# Oracle Environment Used

| Component | Details |
|-----------|----------|
| Database | Oracle 21c |
| Tool | SQL*Plus |
| OEM | Enterprise Manager |
| OS | Windows |

---

# Integrity Statement

I confirm that this assignment was completed independently and reflects my own work. All commands were executed and tested in my Oracle environment.

---


**Author:** AWASSI Greg Jeffrey  
**Student ID:** 28315



## Integrity Statement
I confirm that this work was completed independently as part of the practical assessment.
