---
title: Tipi strutturati nullable (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3f294088e92951e964c3daa2a105b767bca1d288
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="nullable-structured-types-entity-sql"></a>Tipi strutturati nullable (Entity SQL)
Un'istanza `null` di un tipo strutturato è un'istanza che non esiste ed è diversa da un'istanza esistente nella quale tutte le proprietà hanno valori `null`.  
  
 In questo argomento vengono descritti i tipi strutturati che ammettono valori Null e viene indicato quali tipi ammettono valori Null e quali modelli di codice producono istanze `null` dei tipi strutturati che ammettono valori Null.  
  
## <a name="kinds-of-nullable-structured-types"></a>Tipi strutturati che ammettono valori Null  
 Esistono tre tipi di strutture che ammettono valori Null:  
  
-   Tipi di riga.  
  
-   Tipi complessi.  
  
-   Tipi di entità.  
  
## <a name="code-patterns-that-produce-null-instances-of-structured-types"></a>Modelli di codice che producono istanze null di tipi strutturati  
 Negli scenari seguenti vengono prodotte istanze `null`:  
  
-   Modellazione di `null` come tipo strutturato:  
  
    ```  
    TREAT (NULL AS StructuredType)  
    ```  
  
-   Upcast di un tipo di base a un tipo derivato:  
  
    ```  
    TREAT (BaseType AS DerivedType)  
    ```  
  
-   Outer join in una condizione false:  
  
    ```  
    Collection1 LEFT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     --oppure  
  
    ```  
    Collection1 RIGHT OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
     --oppure  
  
    ```  
    Collection1 FULL OUTER JOIN Collection2  
    ON FalseCondition  
    ```  
  
-   Dereferenziamento di riferimento `null`:  
  
    ```  
    DEREF(NullRef)  
    ```  
  
-   Recupero di ANYELEMENT da una raccolta vuota:  
  
    ```  
    ANYELEMENT(EmptyCollection)  
    ```  
  
-   Verifica delle istanze `null` dei tipi strutturati:  
  
    ```csharp  
    ...  
    for (int i = 0; i < reader.FieldCount; i++)  
    {  
        if (reader.IsDBNull(i))  
        {  
            Console.WriteLine("[NULL]");  
        }  
        else  
        {  
            Console.WriteLine(reader.GetValue(i).ToString());  
        }  
    }  
    ```  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica di Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
