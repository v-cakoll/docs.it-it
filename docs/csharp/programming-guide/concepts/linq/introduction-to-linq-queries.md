---
title: Introduzione alle query LINQ (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- deferred execution [LINQ]
- LINQ, queries
- LINQ, deferred execution
- queries [LINQ], about LINQ queries
ms.assetid: 37895c02-268c-41d5-be39-f7d936fa88a8
ms.openlocfilehash: 7fbdfa8656e3c4832226370dc6efe56964e14934
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "79168505"
---
# <a name="introduction-to-linq-queries-c"></a>Introduzione alle query LINQ (C#)
Una *query* è un'espressione che recupera dati da un'origine dati. Le query sono in genere espresse in un linguaggio di query specializzato. Nel tempo sono stati sviluppati diversi linguaggi per i vari tipi di origini dati, ad esempio SQL per database relazionali e XQuery per XML. Gli sviluppatori hanno dovuto pertanto imparare un nuovo linguaggio di query per ogni tipo di origine dati o formato dati supportato. LINQ semplifica questa situazione offrendo un modello coerente per l'utilizzo dei dati in vari tipi di origini dati e formati. In una query LINQ si lavora sempre con gli oggetti. Gli stessi modelli di codifica di base vengono utilizzati per eseguire query e trasformare i dati in documenti XML, database SQL, ADO.NET dataset, raccolte .NET e qualsiasi altro formato per il quale è disponibile un provider LINQ.  
  
## <a name="three-parts-of-a-query-operation"></a>Tre parti di un'operazione di query  
 Tutte le operazioni di query LINQLINQ sono costituite da tre azioni distinte:  
  
1. Ottenere l'origine dati.  
  
2. Creare la query.  
  
3. Esecuzione della query.  
  
 Nell'esempio seguente viene illustrato come le tre parti di un'operazione di query vengono espresse nel codice sorgente. Nell'esempio viene usata una matrice di valori interi come origine dati per motivi di praticità. Gli stessi concetti si applicano però anche ad altre origini dati. In questo argomento si fa riferimento sempre a tale esempio.  
  
 [!code-csharp[CsLINQGettingStarted#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#1)]  
  
 Nella figura seguente viene illustrata l'operazione di query completa. In LINQ, l'esecuzione della query è distinta dalla query stessa. In altre parole, non è stato recuperato alcun dato semplicemente creando una variabile di query.  
  
 ![Diagramma di un'operazione di query LINQ completa.](./media/introduction-to-linq-queries/linq-query-complete-operation.png)  
  
## <a name="the-data-source"></a>Origine dati  
 Poiché nell'esempio precedente è stata usata una matrice come origine dati, viene supportata implicitamente l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601>. Questo fatto significa che può essere eseguita una query con LINQ. Viene eseguita una query in un'istruzione `foreach` e `foreach` richiede <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>. I tipi che supportano <xref:System.Collections.Generic.IEnumerable%601> o un'interfaccia derivata, ad esempio l'interfaccia generica <xref:System.Linq.IQueryable%601> sono denominati *tipi queryable*.  
  
 Un tipo su cui è possibile eseguire query non richiede alcuna modifica o trattamento speciale da utilizzare come origine dati LINQ. Se i dati di origine non sono già in memoria come tipo queryable, il provider LINQ deve rappresentarlo come tale. Ad esempio, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] carica un documento XML in un tipo <xref:System.Xml.Linq.XElement> queryable:  
  
 [!code-csharp[CsLINQGettingStarted#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#2)]  
  
 Con [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] è necessario creare prima un mapping relazionale a oggetti in fase di progettazione, manualmente o usando gli [Strumenti LINQ to SQL in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2). È possibile scrivere le query sugli oggetti e in fase di esecuzione [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] gestisce la comunicazione con il database. Nell'esempio seguente `Customers` rappresenta una tabella specifica nel database e il tipo del risultato della query, <xref:System.Linq.IQueryable%601>, deriva da <xref:System.Collections.Generic.IEnumerable%601>.  
  
```csharp  
Northwnd db = new Northwnd(@"c:\northwnd.mdf");  
  
// Query for customers in London.  
IQueryable<Customer> custQuery =  
    from cust in db.Customers  
    where cust.City == "London"  
    select cust;  
```  
  
 Per altre informazioni su come creare tipi specifici di origini dati, vedere la documentazione relativa ai vari provider LINQ. Tuttavia, la regola di base è molto semplice: un'origine dati LINQ è qualsiasi oggetto che supporta l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601> o un'interfaccia che eredita da essa.  
  
> [!NOTE]
> Tipi come <xref:System.Collections.ArrayList> che supportano <xref:System.Collections.IEnumerable> l'interfaccia non generica possono essere utilizzati anche come origine dati LINQ. Per ulteriori informazioni, vedere [Come eseguire una query su un ArrayList con LINQ (C)](./how-to-query-an-arraylist-with-linq.md).  
  
## <a name="query"></a>La query  
 La query specifica le informazioni da recuperare dall'origine o dalle origini dati. Una query può anche specificare il modo in cui ordinare, raggruppare e definire le informazioni prima che vengano restituite. Una query viene archiviata in una variabile di query e inizializzata con un'espressione di query. Per semplificare la scrittura delle query, in C# è stata introdotta una nuova sintassi della query.  
  
 La query nell'esempio precedente restituisce tutti i numeri pari dalla matrice di valori interi. L'espressione di query contiene tre clausole: `from`, `where` e `select`. Se si ha familiarità con SQL, si sarà notato che l'ordine delle clausole è invertito rispetto all'ordine in SQL. La `from` clausola specifica l'origine dati, la `where` `select` clausola applica il filtro e la clausola specifica il tipo degli elementi restituiti. Queste e le altre clausole di query vengono descritte in dettaglio nella sezione [Language Integrated Query (LINQ).](../../../linq/index.md) Per ora, il punto importante è che in LINQ, la variabile di query stessa non esegue alcuna azione e non restituisce dati. Archivia solo le informazioni richieste per generare i risultati quando successivamente viene eseguita la query. Per altre informazioni sul modo in cui le query vengono costruite automaticamente, vedere [Cenni preliminari sugli operatori di query standard (C#)](./standard-query-operators-overview.md).  
  
> [!NOTE]
> Le query possono anche essere espresse usando la sintassi del metodo. Per altre informazioni, vedere [Sintassi di query e sintassi di metodi in LINQ](./query-syntax-and-method-syntax-in-linq.md).  
  
## <a name="query-execution"></a>Esecuzione di query  
  
### <a name="deferred-execution"></a>Esecuzione posticipata  
 Come indicato in precedenza, la variabile di query archivia solo i comandi della query. L'esecuzione effettiva della query è rinviata finché non si esegue l'iterazione della variabile di query in un'istruzione `foreach`. Questo concetto è detto *esecuzione posticipata* e viene illustrato nell'esempio seguente:  
  
 [!code-csharp[csLinqGettingStarted#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#4)]  
  
 Dall'istruzione `foreach` vengono anche recuperati i risultati della query. Ad esempio, nella query precedente la variabile di iterazione `num` contiene ogni valore (uno alla volta) della sequenza restituita.  
  
 Poiché la variabile di query stessa non contiene mai i risultati della query, è possibile eseguirla un numero illimitato di volte. Ad esempio, è possibile avere un database che viene aggiornato continuamente mediante un'applicazione separata. Nell'applicazione è possibile creare una query che recupera i dati più recenti ed eseguirla ripetutamente a determinati intervalli per recuperare ogni volta risultati diversi.  
  
### <a name="forcing-immediate-execution"></a>Esecuzione immediata  
 Le query che eseguono funzioni di aggregazione su un intervallo di elementi di origine devono prima eseguire l'iterazione in tali elementi. Esempi di tali query sono `Count`, `Max`, `Average` e `First`. Queste query vengono eseguite senza un'istruzione `foreach` esplicita poiché la query stessa deve usare `foreach` per poter restituire un risultato. Si noti anche che questi tipi di query restituiscono un solo valore, non una raccolta `IEnumerable`. Nella query seguente viene restituito un conteggio dei numeri pari nella matrice di origine:  
  
 [!code-csharp[csLinqGettingStarted#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#5)]  
  
 Per forzare l'esecuzione immediata di una query e memorizzarne nella cache i risultati, è possibile chiamare i metodi <xref:System.Linq.Enumerable.ToList%2A> o <xref:System.Linq.Enumerable.ToArray%2A>.  
  
 [!code-csharp[csLinqGettingStarted#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#6)]  
  
 È anche possibile forzare l'esecuzione inserendo il ciclo `foreach` immediatamente dopo l'espressione di query. Tuttavia, chiamando `ToList` o `ToArray` vengono memorizzati nella cache anche tutti i dati di un singolo oggetto della raccolta.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in C #](index.md)
- [Procedura dettagliata: scrittura di query in C#](./walkthrough-writing-queries-linq.md)
- [Language Integrated Query (LINQ)](../../../linq/index.md)
- [foreach, in](../../../language-reference/keywords/foreach-in.md)
- [Parole chiave di query (LINQ)Query Keywords (LINQ)](../../../language-reference/keywords/query-keywords.md)
