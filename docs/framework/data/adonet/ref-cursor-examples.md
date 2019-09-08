---
title: Esempi di REF CURSOR
ms.date: 03/30/2017
ms.assetid: c257da03-c6c9-4cf8-b591-b7740a962c40
ms.openlocfilehash: 24830452e6d1ab11605ffa88a925fbc55c80b9bf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794701"
---
# <a name="ref-cursor-examples"></a>Esempi di REF CURSOR
Gli esempi di REF CURSOR sono illustrati nei tre esempi seguenti di Microsoft Visual Basic relativi all'utilizzo di REF CURSOR.  
  
|Esempio|Descrizione|  
|------------|-----------------|  
|[Parametri REF CURSOR in un oggetto OracleDataReader](ref-cursor-parameters-in-an-oracledatareader.md)|Nell'esempio seguente viene eseguita una stored procedure PL/SQL che restituisce un parametro REF CURSOR e legge il valore come un tipo <xref:System.Data.OracleClient.OracleDataReader>.|  
|[Recupero di dati da più oggetti REF CURSOR tramite OracleDataReader](retrieving-data-from-multiple-ref-cursors.md)|In questo esempio viene eseguito un stored procedure PL/SQL che restituisce due parametri REF CURSOR e legge i valori utilizzando **OracleDataReader**.|  
|[Compilazione di un oggetto DataSet tramite uno o più oggetti REF CURSOR](filling-a-dataset-using-one-or-more-ref-cursors.md)|Nell'esempio seguente viene eseguita una stored procedure PL/SQL che restituisce due parametri REF CURSOR e consente la compilazione di un tipo <xref:System.Data.DataSet> con le righe restituite.|  
  
 Per usare questi esempi può essere necessario creare tabelle Oracle ed è necessario creare un package e un corpo package PL/SQL.  
  
## <a name="creating-the-oracle-tables"></a>Creazione di tabelle Oracle  
 In questi esempi vengono usate tabelle definite nello schema Oracle Scott/Tiger. Tale schema è incluso nella maggior parte delle installazioni di Oracle. Se questo schema non esiste, è possibile usare il file di comandi SQL che si trova nel percorso {OracleHome}\rdbms\admin\scott.sql per creare le tabelle e gli indici usati in questi esempi.  
  
## <a name="creating-the-oracle-package-and-package-body"></a>Creazione del package e del corpo package Oracle  
 Questi esempi richiedono che sul server siano presenti i seguenti package e corpo package PL/SQL. Creare il seguente package Oracle sul server Oracle.  
  
```sql
CREATE OR REPLACE PACKAGE CURSPKG AS   
    TYPE T_CURSOR IS REF CURSOR;   
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,   
                               IO_CURSOR IN OUT T_CURSOR);   
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
                                DEPTCURSOR OUT T_CURSOR);  
END CURSPKG;  
/   
```  
  
 Creare il seguente corpo del package Oracle sul server Oracle.  
  
```sql
CREATE OR REPLACE PACKAGE BODY CURSPKG AS  
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,  
                               IO_CURSOR IN OUT T_CURSOR)  
    IS   
        V_CURSOR T_CURSOR;   
    BEGIN   
        IF N_EMPNO <> 0   
        THEN  
             OPEN V_CURSOR FOR   
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME   
                  FROM EMP, DEPT   
                  WHERE EMP.DEPTNO = DEPT.DEPTNO   
                  AND EMP.EMPNO = N_EMPNO;  
  
        ELSE   
             OPEN V_CURSOR FOR   
             SELECT EMP.EMPNO, EMP.ENAME, DEPT.DEPTNO, DEPT.DNAME   
                  FROM EMP, DEPT   
                  WHERE EMP.DEPTNO = DEPT.DEPTNO;  
  
        END IF;  
        IO_CURSOR := V_CURSOR;   
    END OPEN_ONE_CURSOR;   
  
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,  
                                DEPTCURSOR OUT T_CURSOR)  
    IS   
        V_CURSOR1 T_CURSOR;   
        V_CURSOR2 T_CURSOR;   
    BEGIN   
        OPEN V_CURSOR1 FOR SELECT * FROM EMP;  
        OPEN V_CURSOR2 FOR SELECT * FROM DEPT;  
        EMPCURSOR  := V_CURSOR1;   
        DEPTCURSOR := V_CURSOR2;   
    END OPEN_TWO_CURSORS;   
END CURSPKG;  
/  
```  
  
## <a name="see-also"></a>Vedere anche

- [Oggetti REF CURSOR Oracle](oracle-ref-cursors.md)
- [Panoramica di ADO.NET](ado-net-overview.md)
