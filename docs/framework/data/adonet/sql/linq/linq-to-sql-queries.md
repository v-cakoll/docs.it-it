---
title: Query [LINQ to SQL]
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: 534da029664af0babc3dff6226ff095b7222c34d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915838"
---
# <a name="linq-to-sql-queries"></a>Query [LINQ to SQL]
Le query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] vengono definite usando la stessa sintassi usata in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]. La sola differenza riguarda il mapping degli oggetti a cui viene fatto riferimento nelle query, che viene eseguito agli elementi in un database. Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query create vengono convertite in query SQL equivalenti e inviate al server per l'elaborazione. In particolare l'applicazione utilizza l'API [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per richiedere l'esecuzione di query. Il provider [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] trasforma quindi la query in testo SQL e delega l'esecuzione al provider ADO, che restituisce i risultati della query come `DataReader`. Il [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] provider converte i risultati ADO in una <xref:System.Linq.IQueryable> raccolta di oggetti utente.  
  
> [!NOTE]
> La maggior parte dei metodi e degli operatori su .NET Framework tipi incorporati include le conversioni dirette a SQL. Quelli che non possono essere convertiti da [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] generano eccezioni in fase di esecuzione. Per ulteriori informazioni, vedere [mapping dei tipi SQL-CLR](../../../../../../docs/framework/data/adonet/sql/linq/sql-clr-type-mapping.md).  
  
 Nella tabella seguente sono illustrate le similitudini e le differenze tra [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] e gli elementi delle query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].  
  
|Elemento|Query LINQ|Query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]|  
|----------|----------------|----------------------------------------------------------------------|  
|Tipo restituito della variabile locale che contiene la query (per le query che restituiscono sequenze)|`IEnumerable` generico|`IQueryable` generico|  
|Specifica dell'origine dati|Usa la `From` clausola (Visual Basic) `from` oC#()|Idem|  
|Filtro|Usa la `Where`clausola / `where`|Idem|  
|Raggruppamento|Usa la `Group…By`clausola / `groupby`|Idem|  
|Selezione (proiezione)|Usa la `Select`clausola / `select`|Idem|  
|Esecuzione posticipata e immediata|Vedere [Introduzione alle query LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|Idem|  
|Implementazione di join|Usa la `Join`clausola / `join`|Può usare la `Join` / <xref:System.Data.Linq.Mapping.AssociationAttribute> clausola, ma usa più efficacemente l'attributo. `join` Per ulteriori informazioni, vedere [esecuzione di query tra relazioni](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md).|  
|Esecuzione in modalità remota e locale||Per ulteriori informazioni, vedere [Remote vs. Esecuzione](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md)locale.|  
|Esecuzione di query mediante trasmissione o memorizzate nella cache|Non applicabile in un scenario con memoria locale||  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle query LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Operazioni di query LINQ di base](../../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Relazioni tra i tipi nelle operazioni di query LINQ](../../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Concetti relativi alle query](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
