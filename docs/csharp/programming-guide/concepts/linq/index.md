---
title: Language-Integrated Query (LINQ) (C#)
ms.date: 02/02/2017
ms.assetid: 19dd1782-905b-4a9d-a3e9-618453037fa2
ms.openlocfilehash: 07a9d68c042d524ee9faba8122b406a81e816378
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "73418233"
---
# <a name="language-integrated-query-linq"></a>LINQ (Language-Integrated Query)

LINQ (Language-Integrated Query) è il nome di un set di tecnologie basate sull'integrazione delle funzionalità di query direttamente nel linguaggio C#. In genere, le query sui dati vengono espresse come stringhe semplici senza il controllo dei tipi in fase di compilazione o il supporto IntelliSense. È anche necessario imparare un linguaggio di query diverso per ogni tipo di origine dati: database SQL, documenti XML, svariati servizi Web e così via. Con LINQ, una query è un costrutto del linguaggio di prima classe, come le classi, i metodi e gli eventi. È possibile scrivere query su insiemi di oggetti fortemente tipizzati usando le parole chiave del linguaggio e gli operatori comuni. La famiglia di tecnologie LINQ offre coerenza per l'esecuzione di query per oggetti (LINQ to Objects), database relazionali (LINQ to SQL) e XML (LINQ to XML).

Per uno sviluppatore che scrive query, la parte integrata nel linguaggio più visibile di LINQ è l'espressione di query. Le espressioni di query vengono scritte con una *sintassi di query* dichiarativa. Tramite la sintassi di query è possibile eseguire operazioni di filtro, ordinamento e raggruppamento sulle origini dati usando una quantità minima di codice. Vengono usati gli stessi modelli di espressioni di query di base per eseguire una query e trasformare i dati in database SQL, set di dati ADO .NET, documenti e flussi XML e raccolte .NET.

È possibile scrivere query LINQ in C# per database SQL Server, documenti XML, set di dati ADO.NET e qualsiasi raccolta di oggetti che supporta <xref:System.Collections.IEnumerable> o l'interfaccia <xref:System.Collections.Generic.IEnumerable%601> generica. Il supporto per LINQ viene anche offerto da terze parti per numerosi servizi Web e altre implementazioni di database.

L'esempio seguente mostra l'operazione di query completa. L'operazione completa include la creazione di un'origine dati, la definizione dell'espressione di query e l'esecuzione della query in un'istruzione `foreach`.

[!code-csharp[csProgGuideLINQ#11](~/samples/snippets/csharp/concepts/linq/index_1.cs)]

Nella figura seguente presa da Visual Studio viene illustrata una query LINQ completata parzialmente su un database di SQL Server in C# e Visual Basic con controllo completo del tipo e supporto IntelliSense:

![Diagramma che illustra una query LINQ con Intellisense.](./media/introduction-to-linq/linq-query-intellisense.png)

## <a name="query-expression-overview"></a>Panoramica sulle espressioni di query

- Le espressioni di query possono essere usate per eseguire una query e trasformare dati da qualsiasi origine dati abilitata per LINQ. Una sola query, ad esempio, è in grado di recuperare dati da un database SQL e di produrre un flusso XML come output.
- Le espressioni di query sono facili da gestire perché usano molti costrutti di linguaggio C# di uso comune.
- Le variabili presenti in un'espressione di query sono tutte fortemente tipizzate, anche se in molti casi non è necessario specificare il tipo in modo esplicito perché il compilatore è in grado di dedurlo. Per altre informazioni, vedere [Relazioni tra i tipi nelle operazioni di query LINQ](type-relationships-in-linq-query-operations.md).
- Una query non viene eseguita finché non si esegue l'iterazione della variabile di query, ad esempio in un'istruzione `foreach`. Per altre informazioni, vedere [Introduzione alle query LINQ](introduction-to-linq-queries.md).
- In fase di compilazione, le espressioni di query vengono convertite in chiamate al metodo dell'operatore query standard secondo le regole definite nella specifica C#. Le query che possono essere espresse usando la sintassi di query possono essere espresse anche usando la sintassi dei metodi. Nella maggior parte dei casi, tuttavia, la sintassi di query è più leggibile e concisa. Per altre informazioni, vedere [Specifiche del linguaggio C#](~/_csharplang/spec/expressions.md#query-expressions) e [Panoramica degli operatori di query standard](standard-query-operators-overview.md).
- Come regola di scrittura delle query LINQ, è consigliabile usare la sintassi di query quando possibile e la sintassi dei metodi quando necessario. Tra le due diverse forme non esiste differenza semantica o a livello di prestazioni. Le espressioni di query sono spesso più leggibili delle espressioni equivalenti scritte nella sintassi dei metodi.
- Per alcune operazioni di query, ad esempio <xref:System.Linq.Enumerable.Count%2A> o <xref:System.Linq.Enumerable.Max%2A>, non è presente una clausola dell'espressione di query equivalente. Tali espressioni devono quindi essere espresse come chiamata di metodo. La sintassi dei metodi può essere combinata con la sintassi di query in diversi modi. Per ulteriori informazioni, vedere [Sintassi delle query e sintassi dei metodi in LINQ](query-syntax-and-method-syntax-in-linq.md).
- Le espressioni di query possono essere compilate in alberi delle espressioni o in delegati, a seconda del tipo al quale viene applicata la query. Le query <xref:System.Collections.Generic.IEnumerable%601> vengono compilate in delegati. Le query <xref:System.Linq.IQueryable> e <xref:System.Linq.IQueryable%601> vengono compilate in alberi delle espressioni. Per altre informazioni, vedere [Alberi delle espressioni](../../../expression-trees.md).

## <a name="next-steps"></a>Passaggi successivi

Per altre informazioni dettagliate su LINQ, iniziare ad acquisire dimestichezza con alcuni concetti di base nella sezione introduttiva [Nozioni fondamentali sulle espressioni di query](../../../linq/query-expression-basics.md) e quindi leggere la documentazione per la tecnologia LINQ a cui si è interessati:

- Documenti XML: [LINQ to XML](linq-to-xml-overview.md)  
- ADO.NET Entity Framework: [LINQ to Entities](../../../../framework/data/adonet/ef/language-reference/linq-to-entities.md)
- Raccolte, file e stringhe .NET: [LINQ to Objects](linq-to-objects.md)

Per approfondire LINQ in generale, vedere [LINQ in C#](../../../linq/linq-in-csharp.md).

Per iniziare a utilizzare LINQ in C#, vedere l'esercitazione [Uso di LINQ](../../../tutorials/working-with-linq.md).
