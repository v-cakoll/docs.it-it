---
title: Query [LINQ to SQL]
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: 49106502dc58eef36ea0c910c627c9cf397f419e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902876"
---
# <a name="linq-to-sql-queries"></a>Query [LINQ to SQL]
Le query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono definite usando la stessa sintassi usata in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. La sola differenza riguarda il mapping degli oggetti a cui viene fatto riferimento nelle query, che viene eseguito agli elementi in un database. Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query create vengono convertite in query SQL equivalenti e inviate al server per l'elaborazione. In particolare l'applicazione utilizza l'API [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per richiedere l'esecuzione di query. Il provider [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] trasforma quindi la query in testo SQL e delega l'esecuzione al provider ADO, che restituisce i risultati della query come `DataReader`. Il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provider converte i risultati di ADO per un <xref:System.Linq.IQueryable> raccolta di oggetti utente.  
  
> [!NOTE]
>  Per la maggior parte dei metodi e degli operatori nei tipi [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] incorporati sono disponibili conversioni dirette in SQL. Quelli che non possono essere convertiti da [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] generano eccezioni in fase di esecuzione. Per altre informazioni, vedere [Mapping dei tipi SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 Nella tabella seguente sono illustrate le similitudini e le differenze tra [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] e gli elementi delle query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Elemento|Query LINQ|Query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]|  
|----------|----------------|----------------------------------------------------------------------|  
|Tipo restituito della variabile locale che contiene la query (per le query che restituiscono sequenze)|`IEnumerable` generico|`IQueryable` generico|  
|Specifica dell'origine dati|Usa il `From` (Visual Basic) o `from` (C#) clausola|Idem|  
|Filtro|Usa il `Where` / `where` clausola|Idem|  
|Raggruppamento|Usa il `Group…By` / `groupby` clausola|Idem|  
|Selezione (proiezione)|Usa il `Select` / `select` clausola|Idem|  
|Esecuzione posticipata e immediata|Visualizzare [Introduzione alle query LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|Idem|  
|Implementazione di join|Usa il `Join` / `join` clausola|Può usare la `Join` / `join` clausola, ma in modo più efficace viene utilizzato il <xref:System.Data.Linq.Mapping.AssociationAttribute> attributo. Per altre informazioni, vedere [eseguire query tra relazioni](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).|  
|Esecuzione in modalità remota e locale||Per altre informazioni, vedere [esecuzione remota. Esecuzione locale](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md).|  
|Esecuzione di query mediante trasmissione o memorizzate nella cache|Non applicabile in un scenario con memoria locale||  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle query LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Operazioni di query LINQ di base](~/docs/csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Relazioni tra i tipi nelle operazioni di query LINQ](~/docs/csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
