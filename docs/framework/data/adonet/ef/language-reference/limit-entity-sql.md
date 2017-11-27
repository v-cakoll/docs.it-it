---
title: LIMIT (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c22ffede-0a52-44d1-99b9-4a91e651e1b9
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c890bf6950f94c04350902276193f5a43239f63f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="limit-entity-sql"></a>LIMIT (Entity SQL)
Il paging fisico può essere eseguito usando la sottoclausola LIMIT nella clausola ORDER BY. Non è possibile usare LIMIT separatamente dalla clausola ORDER BY.  
  
## <a name="syntax"></a>Sintassi  
  
```  
[ LIMIT n ]  
```  
  
## <a name="arguments"></a>Argomenti  
 `n`  
 Numero di elementi che verranno selezionati.  
  
 Se una sottoclausola dell'espressione LIMIT è presente in una clausola ORDER BY, la query verrà ordinata in base alla specifica di ordinamento e il numero risultante di righe sarà limitato dall'espressione LIMIT. LIMIT 5, ad esempio, limiterà il set di risultati a cinque istanze o righe. Dal punto di vista funzionale, LIMIT è equivalente a TOP, con l'eccezione che per la presenza di LIMIT è necessaria la clausola ORDER BY. È possibile usare SKIP e LIMIT in modo indipendente insieme alla clausola ORDER BY.  
  
> [!NOTE]
>  Una query Entity SQL viene considerata non valida se nella stessa espressione di query sono presenti il modificatore TOP e la sottoclausola SKIP. È necessario riscrivere la query modificando l'espressione TOP nell'espressione LIMIT.  
  
## <a name="example"></a>Esempio  
 Nella query Entity SQL seguente viene usato l'operatore ORDER BY con LIMIT per specificare l'ordinamento usato per gli oggetti restituiti in un'istruzione SELECT. La query è basata sul modello Sales di AdventureWorks. Per compilare ed eseguire questa query, effettuare le operazioni seguenti:  
  
1.  Seguire la procedura indicata in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).  
  
2.  Passare la query seguente come argomento al metodo `ExecuteStructuralTypeQuery`:  
  
 [!code-csharp[DP EntityServices Concepts 2#LIMIT](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#limit)]  
  
## <a name="see-also"></a>Vedere anche  
 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)  
 [Procedura: spostarsi tra Query i risultati](http://msdn.microsoft.com/en-us/ffc0f920-e7de-42e0-9b12-ef356421d030)  
 [Paging](../../../../../../docs/framework/data/adonet/ef/language-reference/paging-entity-sql.md)  
 [IN ALTO](../../../../../../docs/framework/data/adonet/ef/language-reference/top-entity-sql.md)
