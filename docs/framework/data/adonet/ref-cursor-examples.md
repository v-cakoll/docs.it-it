---
title: Esempi di REF CURSOR
ms.date: 03/30/2017
ms.assetid: c257da03-c6c9-4cf8-b591-b7740a962c40
ms.openlocfilehash: 803c921b76369aa9268c7fd34d1f15dd51bb17f3
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/01/2018
ms.locfileid: "43406059"
---
# <a name="ref-cursor-examples"></a><span data-ttu-id="3f858-102">Esempi di REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="3f858-102">REF CURSOR Examples</span></span>
<span data-ttu-id="3f858-103">Gli esempi di REF CURSOR sono illustrati nei tre esempi seguenti di Microsoft Visual Basic relativi all'utilizzo di REF CURSOR.</span><span class="sxs-lookup"><span data-stu-id="3f858-103">The REF CURSOR examples are comprised of the following three Microsoft Visual Basic examples that demonstrate using REF CURSORs.</span></span>  
  
|<span data-ttu-id="3f858-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="3f858-104">Sample</span></span>|<span data-ttu-id="3f858-105">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f858-105">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3f858-106">Parametri REF CURSOR in un oggetto OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="3f858-106">REF CURSOR Parameters in an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/ref-cursor-parameters-in-an-oracledatareader.md)|<span data-ttu-id="3f858-107">Nell'esempio seguente viene eseguita una stored procedure PL/SQL che restituisce un parametro REF CURSOR e legge il valore come un tipo <xref:System.Data.OracleClient.OracleDataReader>.</span><span class="sxs-lookup"><span data-stu-id="3f858-107">This example executes a PL/SQL stored procedure that returns a REF CURSOR parameter, and reads the value as an <xref:System.Data.OracleClient.OracleDataReader>.</span></span>|  
|[<span data-ttu-id="3f858-108">Recupero di dati da più oggetti REF CURSOR tramite OracleDataReader</span><span class="sxs-lookup"><span data-stu-id="3f858-108">Retrieving Data from Multiple REF CURSORs Using an OracleDataReader</span></span>](../../../../docs/framework/data/adonet/retrieving-data-from-multiple-ref-cursors.md)|<span data-ttu-id="3f858-109">Questo esempio viene eseguita una procedura stored PL/SQL che restituisce due parametri REF CURSOR e legge i valori utilizzando un **OracleDataReader**.</span><span class="sxs-lookup"><span data-stu-id="3f858-109">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and reads the values using an **OracleDataReader**.</span></span>|  
|[<span data-ttu-id="3f858-110">Compilazione di un oggetto DataSet tramite uno o più oggetti REF CURSOR</span><span class="sxs-lookup"><span data-stu-id="3f858-110">Filling a DataSet Using One or More REF CURSORs</span></span>](../../../../docs/framework/data/adonet/filling-a-dataset-using-one-or-more-ref-cursors.md)|<span data-ttu-id="3f858-111">Nell'esempio seguente viene eseguita una stored procedure PL/SQL che restituisce due parametri REF CURSOR e consente la compilazione di un tipo <xref:System.Data.DataSet> con le righe restituite.</span><span class="sxs-lookup"><span data-stu-id="3f858-111">This example executes a PL/SQL stored procedure that returns two REF CURSOR parameters, and fills a <xref:System.Data.DataSet> with the rows that are returned.</span></span>|  
  
 <span data-ttu-id="3f858-112">Per usare questi esempi può essere necessario creare tabelle Oracle ed è necessario creare un package e un corpo package PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="3f858-112">To use these examples, you may need to create the Oracle tables, and you must create a PL/SQL package and package body.</span></span>  
  
## <a name="creating-the-oracle-tables"></a><span data-ttu-id="3f858-113">Creazione di tabelle Oracle</span><span class="sxs-lookup"><span data-stu-id="3f858-113">Creating the Oracle Tables</span></span>  
 <span data-ttu-id="3f858-114">In questi esempi vengono usate tabelle definite nello schema Oracle Scott/Tiger.</span><span class="sxs-lookup"><span data-stu-id="3f858-114">These examples use tables that are defined in the Oracle Scott/Tiger schema.</span></span> <span data-ttu-id="3f858-115">Tale schema è incluso nella maggior parte delle installazioni di Oracle.</span><span class="sxs-lookup"><span data-stu-id="3f858-115">The Oracle Scott/Tiger schema is included with most Oracle installations.</span></span> <span data-ttu-id="3f858-116">Se questo schema non esiste, è possibile usare il file di comandi SQL che si trova nel percorso {OracleHome}\rdbms\admin\scott.sql per creare le tabelle e gli indici usati in questi esempi.</span><span class="sxs-lookup"><span data-stu-id="3f858-116">If this schema does not exist, you can use the SQL commands file in {OracleHome}\rdbms\admin\scott.sql to create the tables and indexes used by these examples.</span></span>  
  
## <a name="creating-the-oracle-package-and-package-body"></a><span data-ttu-id="3f858-117">Creazione del package e del corpo package Oracle</span><span class="sxs-lookup"><span data-stu-id="3f858-117">Creating the Oracle Package and Package Body</span></span>  
 <span data-ttu-id="3f858-118">Questi esempi richiedono che sul server siano presenti i seguenti package e corpo package PL/SQL.</span><span class="sxs-lookup"><span data-stu-id="3f858-118">These examples require the following PL/SQL package and package body on your server.</span></span> <span data-ttu-id="3f858-119">Creare il seguente package Oracle sul server Oracle.</span><span class="sxs-lookup"><span data-stu-id="3f858-119">Create the following Oracle package on the Oracle server.</span></span>  
  
```  
CREATE OR REPLACE PACKAGE CURSPKG AS   
    TYPE T_CURSOR IS REF CURSOR;   
    PROCEDURE OPEN_ONE_CURSOR (N_EMPNO IN NUMBER,   
                               IO_CURSOR IN OUT T_CURSOR);   
    PROCEDURE OPEN_TWO_CURSORS (EMPCURSOR OUT T_CURSOR,   
                                DEPTCURSOR OUT T_CURSOR);  
END CURSPKG;  
/   
```  
  
 <span data-ttu-id="3f858-120">Creare il seguente corpo del package Oracle sul server Oracle.</span><span class="sxs-lookup"><span data-stu-id="3f858-120">Create the following Oracle package body on the Oracle server.</span></span>  
  
```  
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
  
## <a name="see-also"></a><span data-ttu-id="3f858-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f858-121">See Also</span></span>  
 [<span data-ttu-id="3f858-122">Oggetti REF CURSOR Oracle</span><span class="sxs-lookup"><span data-stu-id="3f858-122">Oracle REF CURSORs</span></span>](../../../../docs/framework/data/adonet/oracle-ref-cursors.md)  
 [<span data-ttu-id="3f858-123">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="3f858-123">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
