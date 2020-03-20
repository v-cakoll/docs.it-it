---
title: Query in LINQ to Entities
ms.date: 03/30/2017
ms.assetid: c015a609-29eb-4e95-abb1-2ca721c6e2ad
ms.openlocfilehash: 3144796dfb1a970152d8ae56424aa37592d5da09
ms.sourcegitcommit: 515469828d0f040e01bde01df6b8e4eb43630b06
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2020
ms.locfileid: "78848782"
---
# <a name="queries-in-linq-to-entities"></a>Query in LINQ to Entities
Una query è un'espressione che recupera dati da un'origine dati. Le query sono in genere espresse in un linguaggio di query specializzato, ad esempio SQL per i database relazionali e XQuery per XML. Gli sviluppatori hanno dovuto pertanto imparare un nuovo linguaggio di query per ogni tipo di origine dati o formato dati usato per le query. LINQ (Language-Integrated Query) offre un modello più semplice e coerente per l'uso di dati in diversi tipi di origini dati e formati di dati. In una query LINQ vengono sempre usati oggetti di programmazione.  
  
 Un'operazione di query LINQ comporta tre azioni: il recupero di una o più origini dati, la creazione della query e l'esecuzione della query.  
  
 È possibile usare LINQ per eseguire query su origini dati che implementano l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601> o <xref:System.Linq.IQueryable%601>. Le istanze <xref:System.Data.Objects.ObjectQuery%601> della classe generica, che implementa l'interfaccia generica, <xref:System.Linq.IQueryable%601> fungono da origine dati per le query LINQ to Entities. La classe generica <xref:System.Data.Objects.ObjectQuery%601> rappresenta una query che restituisce una raccolta di zero o più oggetti tipizzati. È anche possibile consentire al compilatore di dedurre `var` il tipo di un'entità utilizzando la parola chiave di C , ovvero Dim in Visual Basic.  
  
 Nella query è necessario specificare esattamente le informazioni che si desidera recuperare dall'origine dati. Una query può inoltre specificare in che modo ordinare, raggruppare e formattare le informazioni prima che vengano restituite. In LINQ una query viene archiviata in una variabile. Se la query restituisce una sequenza di valori, la variabile di query deve essere un tipo queryable. La variabile di query non esegue azioni né restituisce dati. Viene solo usata per archiviare le informazioni sulla query. Dopo aver creato una query è necessario eseguirla per recuperare eventuali dati.  
  
## <a name="query-syntax"></a>Sintassi di query  
 Le query LINQ to Entities possono essere composte in due sintassi diverse, ovvero la sintassi delle espressioni di query e la sintassi delle query basate su metodo. La sintassi delle espressioni di query è una novità di C# 3.0 e Visual Basic 9.0 e consiste in un set di clausole scritte in una sintassi dichiarativa simile a Transact-SQL o a XQuery. Tuttavia, Common Language Runtime (CLR) di .NET Framework non è in grado di leggere la sintassi dell'espressione di query stessa. Pertanto, in fase di compilazione, le espressioni di query vengono convertite in chiamate al metodo in modo da poter essere usate da CLR. Questi metodi sono noti come operatori di *query standard.* Gli sviluppatori possono scegliere di chiamare direttamente questi metodi usando la relativa sintassi, anziché usare la sintassi delle query. Per altre informazioni, vedere [Sintassi di query e sintassi di metodi in LINQ](../../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
### <a name="query-expression-syntax"></a>Sintassi delle espressioni di query  
 Le espressioni di query vengono scritte in una sintassi di query dichiarativa. Questa sintassi consente a uno sviluppatore di scrivere query in un linguaggio di alto livello formattato in modo simile a Transact-SQL. Tramite la sintassi delle espressioni di query è possibile eseguire anche complesse operazioni di filtro, ordinamento e raggruppamento sulle origini dati usando una quantità minima di codice. Per ulteriori informazioni, [operazioni di query di base (Visual Basic)](../../../../../visual-basic/programming-guide/concepts/linq/basic-query-operations.md). Per esempi che illustrano come usare la sintassi delle espressioni di query, vedere gli argomenti seguenti:  
  
- [Esempi di sintassi dell'espressione di query: proiezione](query-expression-syntax-examples-projection.md)  
  
- [Esempi di sintassi dell'espressione di query: filtro](query-expression-syntax-examples-filtering.md)  
  
- [Esempi di sintassi dell'espressione di query: ordinamento](query-expression-syntax-examples-ordering.md)  
  
- [Esempi di sintassi di espressione di query: operatori di aggregazione](query-expression-syntax-examples-aggregate-operators.md)  
  
- [Esempi di sintassi dell'espressione di query: partizionamento](query-expression-syntax-examples-partitioning.md)  
  
- [Esempi di sintassi di espressione di query: operatori di join](query-expression-syntax-examples-join-operators.md)  
  
- [Esempi di sintassi di espressione di query: operatori di elemento](query-expression-syntax-examples-element-operators.md)  
  
- [Esempi di sintassi dell'espressione di query: raggruppamento](query-expression-syntax-examples-grouping.md)  
  
- [Esempi di sintassi di espressione di query: esplorazione di relazioni](query-expression-syntax-examples-navigating-relationships.md)  
  
### <a name="method-based-query-syntax"></a>Sintassi delle query basate su metodo  
 Un altro modo per comporre query LINQ to Entities consiste nell'utilizzare query basate su metodo. La sintassi delle query basate su metodo è costituita da una sequenza di chiamate dirette ai metodi dell'operatore LINQ, in cui come parametri vengono passate espressioni lambda. Per ulteriori informazioni, vedere [Espressioni lambda](../../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md). Per esempi che illustrano come usare la sintassi delle query basate su metodo, consultare gli argomenti seguenti:  
  
- [Esempi di sintassi di query basate sul metodo: proiezione](method-based-query-syntax-examples-projection.md)  
  
- [Esempi di sintassi di query basate sul metodo: filtro](method-based-query-syntax-examples-filtering.md)  
  
- [Esempi di sintassi di query basate sul metodo: ordinamento](method-based-query-syntax-examples-ordering.md)  
  
- [Esempi di sintassi di query basate sul metodo: operatori di aggregazione](method-based-query-syntax-examples-aggregate-operators.md)  
  
- [Esempi di sintassi di query basate sul metodo: partizionamento](method-based-query-syntax-examples-partitioning.md)  
  
- [Esempi di sintassi di query basate sul metodo: conversione](method-based-query-syntax-examples-conversion.md)  
  
- [Esempi di sintassi di query basate sul metodo: operatori di join](method-based-query-syntax-examples-join-operators.md)  
  
- [Esempi di sintassi di query basate sul metodo: operatori di elemento](method-based-query-syntax-examples-element-operators.md)  
  
- [Esempi di sintassi di query basate sul metodo: raggruppamento](method-based-query-syntax-examples-grouping.md)  
  
- [Esempi di sintassi di query basate sul metodo: esplorazione di relazioni](method-based-query-syntax-examples-navigating-relationships.md)  
  
## <a name="see-also"></a>Vedere anche

- [LINQ to Entities](linq-to-entities.md)
- [Introduzione a LINQ in C #](../../../../../csharp/programming-guide/concepts/linq/index.md)
- [Introduzione a LINQ in Visual Basic](../../../../../visual-basic/programming-guide/concepts/linq/getting-started-with-linq.md)
- [Opzioni di unione di Entity Framework e query compilate](https://docs.microsoft.com/archive/blogs/dsimmons/ef-merge-options-and-compiled-queries)
