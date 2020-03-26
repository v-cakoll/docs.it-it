---
title: Confronti Null
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ef88af8c-8dfe-4556-8b56-81df960a900b
ms.openlocfilehash: 697c933daeb3c68fb4ea89a957b639a79a9407f8
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249656"
---
# <a name="null-comparisons"></a>Confronti Null
Un valore `null` nell'origine dati indica che il valore è sconosciuto. Nelle query LINQ to Entities è possibile verificare la presenza di valori Null in modo che determinati calcoli o confronti vengano eseguiti solo su righe con dati validi o non null. Tuttavia, la semantica dei valori Null di CLR può differire da quella dell'origine dati. La maggior parte dei database usa una versione della logica con tre valori per la gestione dei confronti di valori Null. Ovvero, un confronto con un valore `true` null `false`non restituisce `unknown`o , restituisce . Spesso, ma non sempre, si tratta di un'implementazione di valori Null ANSI.  
  
 Per impostazione predefinita, in SQL Server il confronto tra valori Null con il metodo Equals restituisce un valore Null. Nell'esempio seguente, le `ShipDate` righe in cui è null vengono escluse dal set di risultati e l'istruzione Transact-SQLTransact-SQL restituisce 0 righe.  
  
```sql  
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
 Un *selettore di chiave* è una funzione utilizzata negli operatori di query standard per estrarre una chiave da un elemento. Nella funzione del selettore di chiave un'espressione può essere confrontata con una costante. La semantica dei valori Null di CLR viene usata in caso di confronto tra un'espressione e una costante Null o tra due costanti Null. La semantica dei valori Null dell'archivio viene usata se vengono confrontate due colonne con valori Null nell'origine dati. I selettori di chiave sono disponibili in molti operatori di query standard per il raggruppamento e l'ordinamento, come <xref:System.Linq.Queryable.GroupBy%2A> e vengono usati per selezionare le chiavi in base alle quali ordinare o raggruppare i risultati delle query.  
  
## <a name="null-property-on-a-null-object"></a>Proprietà Null in un oggetto Null  
 In Entity Framework, le proprietà di un oggetto null sono null. Quando si tenta di fare riferimento a una proprietà di un oggetto Null in CLR, viene ricevuto un oggetto <xref:System.NullReferenceException>. Quando una query LINQ include una proprietà di un oggetto Null, è possibile che si verifichi un comportamento incoerente.  
  
 Nella query seguente, ad esempio, viene eseguito il cast a `NewProduct` nel livello dell'albero dei comandi. Ciò potrebbe rendere la proprietà `Introduced` uguale a Null. Se nel database sono stati definiti confronti di valori Null in modo che il risultato del confronto di <xref:System.DateTime> sia True, la riga verrà inclusa.  
  
 [!code-csharp[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#castresultsisnull)]
 [!code-vb[DP L2E Conceptual Examples#CastResultsIsNull](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#castresultsisnull)]  
  
## <a name="passing-null-collections-to-aggregate-functions"></a>Passaggio di raccolte null a funzioni di aggregazione  
 In LINQ to Entities, quando si `IQueryable` passa una raccolta che supporta una funzione di aggregazione, le operazioni di aggregazione vengono eseguite nel database. Vi potrebbero essere delle differenze tra i risultati di una query eseguita in memoria e una query eseguita a livello di database. Se non vengono trovate corrispondenze, la query in memoria restituisce zero. A livello di database, la stessa query restituisce `null`. Se `null` un valore viene passato a una funzione di aggregazione LINQ, verrà generata un'eccezione. Per accettare `null` valori possibili, eseguire il cast dei tipi e delle proprietà dei tipi che ricevono i risultati della query ai tipi di valore nullable.  
  
## <a name="see-also"></a>Vedere anche

- [Espressioni in query di LINQ to Entities](expressions-in-linq-to-entities-queries.md)
