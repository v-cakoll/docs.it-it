---
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: fd7f484733e7135d2d6c8094b6527d672a988088
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150298"
---
# <a name="function-entity-sql"></a>FUNCTION (Entity SQL)
Definisce una funzione nell'ambito di un comando di query Entity SQL.  
  
## <a name="syntax"></a>Sintassi  
  
```sql  
FUNCTION function-name  
( [ { parameter_name <type_definition>
        [ ,...n ]  
  ]  
) AS ( function_expression )
  
<type_definition>::=  
    { data_type | COLLECTION ( <type_definition> )
                | REF ( data_type )
                | ROW ( row_expression )
        }
```  
  
## <a name="arguments"></a>Argomenti  
 `function-name`  
 Nome della funzione.  
  
 `parameter-name`  
 Nome di un parametro nella funzione.  
  
 `function_expression`  
 Espressione Entity SQL valida che è la funzione. Il comando nella funzione può agire sui parametri `parameter_name` passati alla funzione.  
  
 `data_type`  
 Nome di un tipo supportato.  
  
 COLLECTION (`>` <type_definition )  
 Espressione che restituisce una raccolta di tipi supportati, righe o riferimenti.  
  
 REF **(**`data_type`**)**  
 Espressione che restituisce un riferimento a un tipo di entità.  
  
 RIGA **(**`row_expression`**)**  
 Espressione che restituisce record anonimi strutturalmente tipizzati da uno o più valori. Per altre informazioni, vedere [ROW](row-entity-sql.md).  
  
## <a name="remarks"></a>Osservazioni  
 Più funzioni con lo stesso nome possono essere dichiarate inline, purché le firme delle funzioni siano differenti. Per altre informazioni, vedere [Function Overload Resolution](function-overload-resolution-entity-sql.md).  
  
 È possibile chiamare una funzione inline in un comando Entity SQL solo dopo che è stata definita in quel comando. Tuttavia, una funzione inline può essere chiamata in un'altra funzione inline prima o dopo che la funzione chiamata è stata definita. Nell'esempio seguente la funzione A chiama la funzione B prima che la funzione B sia definita:  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 Per altre informazioni, vedere [Procedura: chiamare una funzione definita dall'utente](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd490951(v=vs.100)).  
  
 Le funzioni possono essere dichiarate anche nel modello stesso. Le funzioni dichiarate nel modello vengono eseguite nello stesso modo delle funzioni dichiarate inline nel comando. Per ulteriori informazioni, vedere [Funzioni definite dall'utente](user-defined-functions-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nel comando Entity SQL seguente viene definita una funzione `Products` che usa un valore Integer per filtrare i prodotti restituiti.  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION1](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function1)]  
  
## <a name="example"></a>Esempio  
 Nel comando Entity SQL seguente viene definita una funzione `StringReturnsCollection` che usa una raccolta di stringhe per filtrare i contatti restituiti.  
  
 [!code-sql[DP EntityServices Concepts#FUNCTION2](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#function2)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimento a Entity SQL](entity-sql-reference.md)
- [Linguaggio Entity SQL](entity-sql-language.md)
