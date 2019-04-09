---
title: Tipi strutturati nullable (Entity SQL)
ms.date: 03/30/2017
ms.assetid: ae006fa9-997e-45bb-8a04-a7f62026171e
ms.openlocfilehash: 632b092e1d0d99a2a40cc3cd4b323e234de6232b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59127855"
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

- [Cenni preliminari su Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
