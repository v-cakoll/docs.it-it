---
title: TOP (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a4a0954-82e2-4eae-bcaf-7c4552f3532d
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 10967ac87fa8f8504dc9a6a29be99401e620085e
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/17/2018
---
# <a name="top-entity-sql"></a>TOP (Entity SQL)
La clausola SELECT può includere una sottoclausola TOP facoltativa dopo il modificatore ALL/DISTINCT facoltativo. La sottoclausola TOP specifica che verrà restituito solo il primo rowset del risultato della query.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ TOP (n) ]  
```  
  
## <a name="arguments"></a>Argomenti  
 `n`  
 Espressione numerica che specifica il numero di righe da restituire. `n` potrebbero essere un singolo valore letterale numerico o un singolo parametro.  
  
## <a name="remarks"></a>Note  
 L'espressione TOP deve essere un singolo valore letterale numerico o un singolo parametro. Se viene usato un valore letterale costante, il tipo del valore letterale deve essere implicitamente promuovibile a Edm.Int64 (byte, int16, int32 o int64 oppure qualsiasi tipo di provider mappato a un tipo promuovibile a Edm.Int64) e il suo valore deve essere maggiore o uguale a zero. In caso contrario, viene generata un'eccezione. Se come espressione viene usato un parametro, anche il tipo di parametro deve essere implicitamente promuovibile a Edm.Int64, ma non verrà eseguita alcuna convalida effettiva del valore del parametro durante la compilazione in quanto per i valori dei parametri viene usata l'associazione tardiva.  
  
 Di seguito è illustrato un esempio di espressione TOP costante.  
  
 `select distinct top(10) c.a1, c.a2 from T as a`  
  
 Di seguito è illustrato un esempio di espressione TOP con parametri.  
  
 `select distinct top(@topParam) c.a1, c.a2 from T as a`  
  
 L'espressione TOP non è deterministica, a meno che la query non venga ordinata. Se è necessario un risultato deterministico, usare le sottoclausole [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md) e [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md) nella clausola [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md) . TOP e SKIP/LIMIT si escludono a vicenda.  
  
## <a name="example"></a>Esempio  
 Nella query [!INCLUDE[esql](../../../../../../includes/esql-md.md)] seguente viene usato TOP per specificare la riga superiore da restituire dal risultato della query. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery` :  
  
 [!code-csharp[DP EntityServices Concepts 2#TOP](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#top)]  
  
## <a name="see-also"></a>Vedere anche  
 [SELECT](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md)  
 [SKIP](../../../../../../docs/framework/data/adonet/ef/language-reference/skip-entity-sql.md)  
 [LIMIT](../../../../../../docs/framework/data/adonet/ef/language-reference/limit-entity-sql.md)  
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [Riferimento a Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
