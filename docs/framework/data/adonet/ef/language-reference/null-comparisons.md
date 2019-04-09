---
title: Confronti Null
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
ms.openlocfilehash: a9e519fb8b2ca021d66adb23659d83efc571afae
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222666"
---
# <a name="null-comparisons"></a>Confronti Null
Un valore `null` nell'origine dati indica che il valore è sconosciuto. Nella query [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] è possibile verificare la presenza di valori Null in modo che alcuni calcoli o confronti vengano eseguiti solo sulle righe che includono dati validi, ovvero non NULL. Tuttavia, la semantica dei valori Null di CLR può differire da quella dell'origine dati. La maggior parte dei database usa una versione della logica con tre valori per la gestione dei confronti di valori Null. Vale a dire, un confronto con un valore null non restituiscono `true` oppure `false`, viene restituito `unknown`. Spesso, ma non sempre, si tratta di un'implementazione di valori Null ANSI.  
  
 Per impostazione predefinita, in SQL Server il confronto tra valori Null con il metodo Equals restituisce un valore Null. Nell'esempio seguente, le righe in cui `ShipDate` è null sono escluse dal set di risultati e l'istruzione [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] restituisce 0 righe.  
  
```  
-- Find order details and orders with no ship date.  
SELECT h.SalesOrderID  
FROM Sales.SalesOrderHeader h  
JOIN Sales.SalesOrderDetail o ON o.SalesOrderID = h.SalesOrderID  
WHERE h.ShipDate IS Null  
```  
  
 Tale semantica è molto diversa da quella dei valori Null di CLR, in cui dal confronto tra valori Null con il metodo Equals viene restituito True.  
  
 La query LINQ seguente è espressa in CLR, ma viene eseguita nell'origine dati. Poiché non esiste alcuna garanzia che venga rispettata la semantica CLR nell'origine dati, il comportamento previsto è indeterminato.  
  
 [!code-csharp[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#joinonnull)]
 [!code-vb[DP L2E Conceptual Examples#JoinOnNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#joinonnull)]  
  
## <a name="key-selectors"></a>Selettori di chiave  
 Oggetto *selettore di chiave* è una funzione usata negli operatori query standard per estrarre una chiave da un elemento. Nella funzione del selettore di chiave un'espressione può essere confrontata con una costante. La semantica dei valori Null di CLR viene usata in caso di confronto tra un'espressione e una costante Null o tra due costanti Null. La semantica dei valori Null dell'archivio viene usata se vengono confrontate due colonne con valori Null nell'origine dati. I selettori di chiave sono disponibili in molti operatori di query standard per il raggruppamento e l'ordinamento, come <xref:System.Linq.Queryable.GroupBy%2A> e vengono usati per selezionare le chiavi in base alle quali ordinare o raggruppare i risultati delle query.  
  
## <a name="null-property-on-a-null-object"></a>Proprietà Null in un oggetto Null  
 In [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] le proprietà di un oggetto Null sono Null. Quando si tenta di fare riferimento a una proprietà di un oggetto Null in CLR, viene ricevuto un oggetto <xref:System.NullReferenceException>. Quando una query LINQ include una proprietà di un oggetto Null, è possibile che si verifichi un comportamento incoerente.  
  
 Nella query seguente, ad esempio, viene eseguito il cast a `NewProduct` nel livello dell'albero dei comandi. Ciò potrebbe rendere la proprietà `Introduced` uguale a Null. Se nel database sono stati definiti confronti di valori Null in modo che il risultato del confronto di <xref:System.DateTime> sia True, la riga verrà inclusa.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a>Passaggio di raccolte null a funzioni di aggregazione  
 Nelle [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)], quando si passa una raccolta che supporta `IQueryable` a una funzione di aggregazione, le operazioni di aggregazione vengono eseguite a livello di database. Potrebbero essere presenti differenze nei risultati di una query che è stata eseguita in memoria e una query che è stata eseguita a livello di database. Con una query in memoria, se non sono presenti corrispondenze, la query restituisce zero. A livello di database, la stessa query restituisce `null`. Se un `null` valore viene passato a una funzione di aggregazione LINQ, verrà generata un'eccezione. Per accettare i possibili `null` valori, eseguire il cast ai tipi e le proprietà dei tipi che ricevono i risultati di query per i tipi nullable.  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni in query di LINQ to Entities](../../../../../../docs/framework/data/adonet/ef/language-reference/expressions-in-linq-to-entities-queries.md)
