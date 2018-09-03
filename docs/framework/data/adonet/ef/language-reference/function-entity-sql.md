---
title: FUNCTION (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 0bb88992-37ed-4991-ace5-55be612a2c4d
ms.openlocfilehash: 1c02583400f9092dcb5008239bfd1fd73c63c326
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43485547"
---
# <a name="function-entity-sql"></a>FUNCTION (Entity SQL)
Definisce una funzione nell'ambito di un comando di query Entity SQL.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
 COLLECTION ( <type_definition`>` )  
 Espressione che restituisce una raccolta di tipi supportati, righe o riferimenti.  
  
 REF **(**`data_type`**)**  
 Espressione che restituisce un riferimento a un tipo di entità.  
  
 ROW **(**`row_expression`**)**  
 Espressione che restituisce record anonimi strutturalmente tipizzati da uno o più valori. Per altre informazioni, vedere [ROW](../../../../../../docs/framework/data/adonet/ef/language-reference/row-entity-sql.md).  
  
## <a name="remarks"></a>Note  
 Più funzioni con lo stesso nome possono essere dichiarate inline, purché le firme delle funzioni siano differenti. Per altre informazioni, vedere [Function Overload Resolution](../../../../../../docs/framework/data/adonet/ef/language-reference/function-overload-resolution-entity-sql.md).  
  
 È possibile chiamare una funzione inline in un comando Entity SQL solo dopo che è stata definita in quel comando. Tuttavia, una funzione inline può essere chiamata in un'altra funzione inline prima o dopo che la funzione chiamata è stata definita. Nell'esempio seguente la funzione A chiama la funzione B prima che la funzione B sia definita:  
  
 `Function A() as ('A calls B. ' + B())`  
  
 `Function B() as ('B was called.')`  
  
 `A()`  
  
 Per altre informazioni, vedere [procedura: chiamare una funzione definita dall'utente](https://msdn.microsoft.com/library/ad131b86-8b4e-4747-8605-d4fc64fb9d02).  
  
 Le funzioni possono essere dichiarate anche nel modello stesso. Le funzioni dichiarate nel modello vengono eseguite nello stesso modo delle funzioni dichiarate inline nel comando. Per altre informazioni, vedere [funzioni definite dall'utente](../../../../../../docs/framework/data/adonet/ef/language-reference/user-defined-functions-entity-sql.md).  
  
## <a name="example"></a>Esempio  
 Nel comando Entity SQL seguente viene definita una funzione `Products` che usa un valore Integer per filtrare i prodotti restituiti.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function1)]  
  
## <a name="example"></a>Esempio  
 Nel comando Entity SQL seguente viene definita una funzione `StringReturnsCollection` che usa una raccolta di stringhe per filtrare i contatti restituiti.  
  
 [!code-csharp[DP EntityServices Concepts 2#FUNCTION2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#function2)]  
  
## <a name="see-also"></a>Vedere anche  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [Linguaggio Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
