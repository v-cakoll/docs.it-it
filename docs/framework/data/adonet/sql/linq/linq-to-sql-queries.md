---
title: Query [LINQ to SQL]
ms.date: 03/30/2017
ms.assetid: f4897aaa-7f44-4c20-a471-b948c2971aae
ms.openlocfilehash: 478138d26d6cdf656b2487c637a5eb13784126e9
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634380"
---
# <a name="linq-to-sql-queries"></a>Query [LINQ to SQL]
È possibile definire [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] query utilizzando la stessa sintassi di LINQ. La sola differenza riguarda il mapping degli oggetti a cui viene fatto riferimento nelle query, che viene eseguito agli elementi in un database. Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
 In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] le query create vengono convertite in query SQL equivalenti e inviate al server per l'elaborazione. In particolare l'applicazione utilizza l'API [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] per richiedere l'esecuzione di query. Il provider [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] trasforma quindi la query in testo SQL e delega l'esecuzione al provider ADO, che restituisce i risultati della query come `DataReader`. Il provider di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] converte i risultati ADO in una raccolta <xref:System.Linq.IQueryable> di oggetti utente.  
  
> [!NOTE]
> La maggior parte dei metodi e degli operatori su .NET Framework tipi incorporati include le conversioni dirette a SQL. Quelle che LINQ non è in grado di tradurre generano eccezioni in fase di esecuzione. Per ulteriori informazioni, vedere [mapping dei tipi SQL-CLR](sql-clr-type-mapping.md).  
  
 Nella tabella seguente vengono illustrate le analogie e le differenze tra LINQ e [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] gli elementi di query.  
  
|Elemento|Query LINQ|Query [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]|  
|----------|----------------|----------------------------------------------------------------------|  
|Tipo restituito della variabile locale che contiene la query (per le query che restituiscono sequenze)|`IEnumerable` generico|`IQueryable` generico|  
|Specifica dell'origine dati|Usa la clausola `From` (Visual Basic) o `from`C#()|Idem|  
|Filtro|Usa la clausola `Where`/`where`|Idem|  
|Raggruppamento|Usa la clausola `Group…By`/`groupby`|Idem|  
|Selezione (proiezione)|Usa la clausola `Select`/`select`|Idem|  
|Esecuzione posticipata e immediata|Vedere [Introduzione alle query LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)|Idem|  
|Implementazione di join|Usa la clausola `Join`/`join`|Può usare la clausola `Join`/`join`, ma usa più efficacemente l'attributo <xref:System.Data.Linq.Mapping.AssociationAttribute>. Per ulteriori informazioni, vedere [esecuzione di query tra relazioni](querying-across-relationships.md).|  
|Esecuzione in modalità remota e locale||Per ulteriori informazioni, vedere [Remote vs. ](remote-vs-local-execution.md)di esecuzione locale.|  
|Esecuzione di query mediante trasmissione o memorizzate nella cache|Non applicabile in un scenario con memoria locale||  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle query LINQ (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)
- [Operazioni di query LINQ di base](../../../../../csharp/programming-guide/concepts/linq/basic-linq-query-operations.md)
- [Relazioni tra i tipi nelle operazioni di query LINQ](../../../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
- [Concetti relativi alle query](query-concepts.md)
