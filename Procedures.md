# SAS Procedures (PROC)
Library of built-in programs known as SAS procdures. SAS procedures use data values from SAS data sets to produce preprogrammed reports.
A protion of a SAS program that beigns with a PROC statement and ends with a RUN statement (or is ended by another PROC or DATA statement)
 is called a **PROC step**.
 
 PROC steps comprise of the following:
 - a PROC statement, the name of the procedure that is to beused, and name of the SAS data set (if omitting the "DATA =" option, it uses
 the most recently used data set).
 - additional statements related to what is to be calculated: CLASS, VAR, TABLE, and TITLE
 - RUN statement indicating the preceding group of statements is ready to run. 
 
***
## Procedure Syntax
PROC *procedure* <DATA = SAS-data-set>;
***
**PROC PRINT DATA = *element*;**  displays the variables in a table or by itself.
Input:
```SAS
PROC PRINT DATA = weight_data;
  title 'Health Club Data';
run;
```
Output:  
Health Club Data

| Obs | IdNumber | Name | Team | StartWeight | EndWeight | Loss |
| ---: | ---: | :---| :--- | ---: | ---: | ---: |
| 1 | 1023 | David Shaw | red | 189 | 165 | 24 |
| 2 | 1049 | Amelia Serrano | yellow|145|124|21|
|3|1219|Alan Nance|red|210|192|18|
***

**PROC TABULATE DATA = *element*;**  displays specified information in a table format.
```SAS
PROC TABULATE DATA = weight_data;
  class Team;
  var StartWeight EndWeight Loss;
  table Team, mean*(StartWeight EndWeight Loss);
  title 'Mean Starting Weight, Ending Weight,';
  title2 'and Weight Loss''
run;
```
Output: 
Mean Starting Weight, Ending Weight,  
and Weight Loss

|Team|Mean|||
|---|---|---|---|
||StartingWeight|EndWeight|Loss|
|red|175.33|158.33|17.00|
|yellow|169.50|150.50|19.00|
***

