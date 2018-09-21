---
title: Scrittura della prima query LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
ms.openlocfilehash: 4c04c00c5392d8ba363346b06c806ec79041c439
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2018
ms.locfileid: "46508687"
---
# <a name="writing-your-first-linq-query-visual-basic"></a>Scrittura della prima query LINQ (Visual Basic)
Una *query* è un'espressione che recupera dati da un'origine dati. Le query sono espresse in un linguaggio di query dedicato. Nel corso del tempo, sono stati sviluppati diversi linguaggi per diversi tipi di origini dati, ad esempio, SQL per i database relazionali e XQuery per XML. Ciò rende necessario per lo sviluppatore dell'applicazione per informazioni su un nuovo linguaggio di query per ogni tipo di origine dati o formato dati supportato.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] semplifica la situazione, offrendo un modello coerente per l'utilizzo di dati in diversi tipi di origini dati e formati. In una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] vengono sempre usati gli oggetti. Si usano gli stessi modelli di codifica basilari per eseguire una query e trasformare i dati nei documenti XML, database SQL, i dataset ADO.NET e le entità, raccolte di .NET Framework e qualsiasi altro origine o formato per il quale un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider è disponibile. Questo documento vengono descritte le tre fasi della creazione e uso di basic [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] le query.  
  
## <a name="three-stages-of-a-query-operation"></a>Tre fasi di un'operazione di Query  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] operazioni di query sono costituiti da tre azioni:  
  
1.  Ottenere l'origine dati o origini.  
  
2.  Creare la query.  
  
3.  Eseguire la query.  
  
 In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], l'esecuzione di una query è distinta dalla creazione della query. Tutti i dati non vengono recuperati solo creando una query. Questo punto viene illustrato più dettagliatamente di seguito in questo argomento.  
  
 L'esempio seguente illustra le tre parti di un'operazione di query. L'esempio Usa una matrice di numeri interi come origine dei dati utile a scopo dimostrativo. Tuttavia, gli stessi concetti si applicano anche ad altre origini dati.  
  
> [!NOTE]
>  Nel [pagina compilazione, creazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), assicurarsi che **Option infer** è impostata su **su**.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Output:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>Origine dati  
 Poiché l'origine dati nell'esempio precedente è una matrice, viene supportata implicitamente il tipo generico <xref:System.Collections.Generic.IEnumerable%601> interfaccia. È il fatto che consente di usare una matrice come origine dati per un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query. I tipi che supportano <xref:System.Collections.Generic.IEnumerable%601> o un'interfaccia derivata, ad esempio l'interfaccia generica <xref:System.Linq.IQueryable%601> sono denominati *tipi queryable*.  
  
 Come un tipo queryable in modo implicito, la matrice non richiede alcuna modifica o trattamento speciale da usare come un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] zdroj dat. Lo stesso vale per qualsiasi tipo di raccolta che supporta <xref:System.Collections.Generic.IEnumerable%601>, incluse le interfacce generiche <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>e altre classi nella libreria di classi .NET Framework.  
  
 Se i dati di origine non implementano già <xref:System.Collections.Generic.IEnumerable%601>, una [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] è necessario per implementare la funzionalità del provider il *operatori query standard* per l'origine dati. Ad esempio, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] gestisce il caricamento di un documento XML in un queryable <xref:System.Xml.Linq.XElement> digitare, come illustrato nell'esempio seguente. Per altre informazioni sugli operatori di query standard, vedere [panoramica degli operatori di Query Standard (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 Con [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], prima di tutto creare prima un mapping relazionale a oggetti in fase di progettazione, manualmente o tramite il [strumenti LINQ to SQL in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) in Visual Studio. È possibile scrivere le query sugli oggetti e in fase di esecuzione [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] gestisce la comunicazione con il database. Nell'esempio riportato di seguito `customers` rappresenta una tabella specifica nel database, e <xref:System.Data.Linq.Table%601> supporta l'interfaccia generica <xref:System.Linq.IQueryable%601>.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 Per altre informazioni sulla creazione di tipi specifici di origini dati, vedere la documentazione dei diversi provider [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. (Per un elenco di questi provider, vedere [LINQ (Language-Integrated Query)](../../../../visual-basic/programming-guide/concepts/linq/index.md).) La regola di base è semplice: una [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] origine dati è qualsiasi oggetto che supporta il tipo generico <xref:System.Collections.Generic.IEnumerable%601> interfaccia o un'interfaccia che eredita da esso.  
  
> [!NOTE]
>  I tipi, ad esempio <xref:System.Collections.ArrayList> che supportano non generica <xref:System.Collections.IEnumerable> interfaccia può essere utilizzata anche come [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] origini dati. Per un esempio che usa un' <xref:System.Collections.ArrayList>, vedere [procedura: eseguire una Query su un ArrayList con LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a>La Query  
 Nella query, si specificano quali informazioni si desidera recuperare dall'origine dati o origini. È inoltre possibile specificare come tali informazioni devono essere ordinate, raggruppate o strutturate prima che venga restituito. Per abilitare la creazione di query, Visual Basic è stato incorporato nuova sintassi della query nel linguaggio.  
  
 Quando viene eseguita, la query nell'esempio seguente restituisce tutti i numeri pari dalla matrice di interi, `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 L'espressione di query contiene tre clausole: `From`, `Where`, e `Select`. La funzione specifica e lo scopo di ogni clausola dell'espressione di query è descritto in [operazioni di Query (Visual Basic) base](basic-query-operations.md). Per altre informazioni, vedere [query](../../../../visual-basic/language-reference/queries/index.md). Si noti che in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], definizione di una query viene spesso archiviata in una variabile ed eseguita in un secondo momento. La query, variabili, ad esempio `evensQuery` nell'esempio precedente, deve essere un tipo queryable. Il tipo della `evensQuery` è `IEnumerable(Of Integer)`, assegnato dal compilatore mediante l'inferenza del tipo locale.  
  
 È importante ricordare che la variabile di query viene eseguita alcuna azione e non restituisce alcun dato. Archivia solo la definizione della query. Nell'esempio precedente, è il `For Each` ciclo che esegue la query.  
  
## <a name="query-execution"></a>Esecuzione di query  
 L'esecuzione di query è distinta dalla creazione di query. Creazione di query definisce la query, ma l'esecuzione viene attivata da un meccanismo diverso. Una query può essere eseguita non appena viene definito (*l'esecuzione immediata*), o può essere archiviata la definizione e la query può essere eseguita in un secondo momento (*esecuzione posticipata*).  
  
### <a name="deferred-execution"></a>Esecuzione posticipata  
 Una tipica [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query è simile a quello nell'esempio precedente, in cui `evensQuery` è definito. Crea la query, ma non la esegue immediatamente. Al contrario, la definizione di query viene archiviata nella variabile di query `evensQuery`. La query viene eseguita in un secondo momento, in genere tramite un `For Each` ciclo, che restituisce una sequenza di valori, o applicando un operatore query standard, ad esempio `Count` o `Max`. Questo processo è detto *un'esecuzione posticipata*.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 Per una sequenza di valori, accedere ai dati recuperati usando la variabile di iterazione nel `For Each` ciclo (`number` nell'esempio precedente). Poiché la variabile di query, `evensQuery`, contiene la definizione della query anziché i risultati della query, è possibile eseguire una query ogni volta che desidera usando la variabile di query più di una volta. Ad esempio, potrebbe essere un database dell'applicazione che viene aggiornato continuamente mediante un'applicazione separata. Dopo aver creato una query che recupera i dati dal database, è possibile usare un `For Each` ciclo per eseguire la query più volte, recuperando i dati più recenti ogni volta.  
  
 L'esempio seguente illustra l'esecuzione posticipata come funziona. Dopo aver `evensQuery2` viene definita ed eseguito con un `For Each` ciclo, come negli esempi precedenti, alcuni elementi nell'origine dati `numbers` vengono modificati. Quindi una seconda `For Each` esecuzioni del ciclo `evensQuery2` nuovamente. I risultati sono diversi la seconda volta, poiché il `For Each` ciclo esegue nuovamente la query utilizzando i nuovi valori in `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 Output:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Esecuzione immediata  
 In esecuzione posticipata di query, la definizione di query viene archiviata in una variabile di query per un'esecuzione successiva. L'esecuzione immediata, la query viene eseguita al momento della relativa definizione. L'esecuzione viene attivata quando si applica un metodo che richiede l'accesso ai singoli elementi del risultato della query. Spesso l'esecuzione immediata è forzato usando uno degli operatori query standard che restituiscono valori singoli. Sono esempi `Count`, `Max`, `Average`, e `First`. Questi operatori query standard eseguire la query, non appena vengono applicati per calcolare e restituire un risultato singleton. Per altre informazioni sugli operatori di query standard che restituiscono valori singoli, vedere [operazioni di aggregazione](aggregation-operations.md), [operazioni sugli elementi](element-operations.md), e [operazioni del quantificatore](quantifier-operations.md).  
  
 La query seguente restituisce un conteggio dei numeri pari nella matrice di interi. Non viene salvata la definizione della query, e `numEvens` è un semplice `Integer`.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 È possibile ottenere lo stesso risultato utilizzando il `Aggregate` (metodo).  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 È anche possibile forzare l'esecuzione di una query chiamando il `ToList` o `ToArray` metodo in una query (immediato) o una variabile di query (rinviato), come illustrato nel codice seguente.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 Negli esempi precedenti `evensQuery3` è una query, variabile, ma `evensList` è riportato un elenco e `evensArray` è una matrice.  
  
 Usando `ToList` o `ToArray` per forzare immediatamente l'esecuzione è particolarmente utile negli scenari in cui si desidera eseguire immediatamente la query e memorizzare nella cache i risultati in un singolo oggetto collection. Per altre informazioni su questi metodi, vedere [conversione di tipi di dati](converting-data-types.md).  
  
 È anche possibile causare una query da eseguire utilizzando un `IEnumerable` metodo, ad esempio il <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> (metodo).  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](getting-started-with-linq.md)  
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
- [Panoramica degli operatori query standard (Visual Basic)](standard-query-operators-overview.md)  
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
- [Query](../../../../visual-basic/language-reference/queries/index.md)
