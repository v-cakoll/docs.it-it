---
title: Scrittura della prima query LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
ms.openlocfilehash: f426aac5358837563081d2bf9783f6d4fe04d853
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33654889"
---
# <a name="writing-your-first-linq-query-visual-basic"></a>Scrittura della prima query LINQ (Visual Basic)
Una *query* è un'espressione che recupera dati da un'origine dati. Le query sono espresse in un linguaggio di query dedicato. Nel corso del tempo, sono stati sviluppati diversi linguaggi per diversi tipi di origini dati, ad esempio SQL per i database relazionali e XQuery per XML. Ciò rende necessario per lo sviluppatore dell'applicazione per informazioni su un nuovo linguaggio di query per ogni tipo di origine dati o formato dati supportato.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] semplifica la situazione offrendo un modello coerente per l'utilizzo di dati in diversi tipi di origini dati e formati. In una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] vengono sempre usati gli oggetti. Utilizzare gli stessi modelli di codifica di base per eseguire query e trasformare i dati nei documenti XML, database SQL, set di dati ADO.NET ed entità, le raccolte di .NET Framework e qualsiasi altro origine o formato per il quale un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider è disponibile. Questo documento vengono descritte le tre fasi della creazione e utilizzo di basic [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query.  
  
## <a name="three-stages-of-a-query-operation"></a>Tre fasi di un'operazione di Query  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] operazioni di query sono costituiti da tre azioni:  
  
1.  Ottenere l'origine dati o origini.  
  
2.  Creare la query.  
  
3.  Eseguire la query.  
  
 In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], l'esecuzione di una query è distinta dalla creazione della query. Non si recuperano i dati solo tramite la creazione di una query. Questo punto viene illustrato più dettagliatamente di seguito in questo argomento.  
  
 L'esempio seguente illustra le tre parti di un'operazione di query. L'esempio Usa una matrice di interi come origine dati utile a scopo dimostrativo. Tuttavia, gli stessi concetti si applicano anche ad altre origini dati.  
  
> [!NOTE]
>  Nel [pagina Compila, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), assicurarsi che **Option infer** è impostato su **su**.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 Output:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>Origine dati  
 Poiché l'origine dati nell'esempio precedente è una matrice, supporta in modo implicito il tipo generico <xref:System.Collections.Generic.IEnumerable%601> interfaccia. È il fatto che consente di utilizzare una matrice come un'origine dati per un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query. I tipi che supportano <xref:System.Collections.Generic.IEnumerable%601> o un'interfaccia derivata, ad esempio l'interfaccia generica <xref:System.Linq.IQueryable%601> sono denominati *tipi queryable*.  
  
 Come tipo queryable in modo implicito, la matrice non richiede alcuna modifica o un trattamento speciale come un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] origine dati. Lo stesso vale per qualsiasi tipo di insieme che supporta <xref:System.Collections.Generic.IEnumerable%601>, incluse le interfacce generiche <xref:System.Collections.Generic.List%601>, <xref:System.Collections.Generic.Dictionary%602>e altre classi nella libreria di classi .NET Framework.  
  
 Se i dati di origine non implementano già <xref:System.Collections.Generic.IEnumerable%601>, [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] provider è necessario per implementare la funzionalità del *operatori di query standard* per l'origine dati. Ad esempio, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] gestisce le operazioni di caricamento di un documento XML in un tipo queryable <xref:System.Xml.Linq.XElement> tipo, come illustrato nell'esempio seguente. Per ulteriori informazioni sugli operatori di query standard, vedere [Standard Query Cenni preliminari sugli operatori (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_2.vb)]  
  
 Con [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)], creare innanzitutto un mapping relazionale a oggetti in fase di progettazione, manualmente o tramite il [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) in Visual Studio. È possibile scrivere le query sugli oggetti e in fase di esecuzione [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] gestisce la comunicazione con il database. Nell'esempio seguente, `customers` rappresenta una tabella specifica nel database, e <xref:System.Data.Linq.Table%601> supporta l'interfaccia generica <xref:System.Linq.IQueryable%601>.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 Per altre informazioni sulla creazione di tipi specifici di origini dati, vedere la documentazione dei diversi provider [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. (Per un elenco di questi provider, vedere [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).) La regola di base è semplice: un [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] origine dati è qualsiasi oggetto che supporta il tipo generico <xref:System.Collections.Generic.IEnumerable%601> interfaccia o un'interfaccia che eredita da esso.  
  
> [!NOTE]
>  Tipi, ad esempio <xref:System.Collections.ArrayList> che supportano il tipo non generico <xref:System.Collections.IEnumerable> interfaccia può essere utilizzata anche come [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] origini dati. Per un esempio che utilizza un <xref:System.Collections.ArrayList>, vedere [procedura: eseguire Query di ArrayList con LINQ (Visual Basic)](how-to-query-an-arraylist-with-linq.md).  
  
## <a name="the-query"></a>La Query  
 Nella query, specificare le informazioni che si desidera recuperare dall'origine dati o origini. È inoltre possibile specificare come tali informazioni devono essere ordinate, raggruppate o strutturate prima che venga restituito. Per abilitare la creazione di query, Visual Basic è stato incorporato nuova sintassi della query nel linguaggio.  
  
 Quando viene eseguita, la query nell'esempio seguente restituisce tutti i numeri pari da una matrice di interi, `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#1](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_1.vb)]  
  
 L'espressione di query contiene tre clausole: `From`, `Where`, e `Select`. Viene illustrata la funzione specifica e lo scopo di ogni clausola dell'espressione di query in [operazioni di Query di base (Visual Basic)](basic-query-operations.md). Per ulteriori informazioni, vedere [query](../../../../visual-basic/language-reference/queries/queries.md). Si noti che in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)], una definizione di query viene spesso archiviata in una variabile ed eseguita in un secondo momento. La query variabile, ad esempio `evensQuery` nell'esempio precedente, deve essere un tipo queryable. Il tipo di `evensQuery` è `IEnumerable(Of Integer)`, assegnato dal compilatore mediante l'inferenza del tipo locale.  
  
 È importante ricordare che la variabile di query viene eseguita alcuna azione e non restituisce alcun dato. Archivia solo la definizione della query. Nell'esempio precedente, è il `For Each` ciclo che esegue la query.  
  
## <a name="query-execution"></a>Esecuzione di query  
 Esecuzione di query è distinta dalla creazione della query. Creazione di query definisce la query, ma l'esecuzione viene attivata da un meccanismo diverso. Una query può essere eseguita non appena viene definito (*l'esecuzione immediata*), o può essere archiviata la definizione e la query può essere eseguita in un secondo momento (*esecuzione posticipata*).  
  
### <a name="deferred-execution"></a>Esecuzione posticipata  
 Una tipica [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query simile a quello nell'esempio precedente, in cui `evensQuery` è definito. Crea la query, ma non eseguita immediatamente. Al contrario, la definizione di query viene archiviata nella variabile di query `evensQuery`. La query viene eseguita in un secondo momento, in genere utilizzando un `For Each` ciclo, che restituisce una sequenza di valori o applicando un operatore di query standard, ad esempio `Count` o `Max`. Questo processo è detto *esecuzione posticipata*.  
  
 [!code-vb[VbLINQFirstQuery#7](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_3.vb)]  
  
 Per una sequenza di valori, accedere ai dati recuperati usando la variabile di iterazione nel `For Each` ciclo (`number` nell'esempio precedente). Poiché la variabile di query, `evensQuery`, contiene la definizione della query invece i risultati della query, è possibile eseguire una query ogni volta che si desidera utilizzare la variabile di query più di una volta. Ad esempio, potrebbe essere un database dell'applicazione che viene continuamente aggiornato da un'applicazione separata. Dopo aver creato una query che recupera dati dal database, è possibile utilizzare un `For Each` loop per eseguire ripetutamente la query, recuperando i dati più recenti ogni volta.  
  
 L'esempio seguente illustra l'esecuzione posticipata come funziona. Dopo aver `evensQuery2` definito ed eseguito con un `For Each` ciclo, come negli esempi precedenti, alcuni elementi nell'origine dati `numbers` vengono modificati. Quindi un secondo `For Each` ciclo viene eseguito `evensQuery2` nuovamente. I risultati sono diversi la seconda volta, in quanto il `For Each` ciclo esegue nuovamente la query utilizzando i nuovi valori in `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#3](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_4.vb)]  
  
 Output:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Esecuzione immediata  
 In esecuzione posticipata delle query, la definizione di query viene archiviata in una variabile di query per un'esecuzione successiva. In esecuzione immediata, la query viene eseguita al momento della relativa definizione. Esecuzione viene attivata quando si applica un metodo che richiede l'accesso ai singoli elementi del risultato della query. Spesso l'esecuzione immediata è forzata utilizzando uno degli operatori di query standard che restituiscono valori singoli. Esempi sono `Count`, `Max`, `Average`, e `First`. Questi operatori query standard eseguire la query non appena vengono applicati per calcolare e restituire un risultato singleton. Per ulteriori informazioni sugli operatori di query standard che restituiscono valori singoli, vedere [operazioni di aggregazione](aggregation-operations.md), [operazioni elemento](element-operations.md), e [operazioni quantificatore](quantifier-operations.md).  
  
 La query seguente restituisce il conteggio dei numeri pari in una matrice di interi. Non viene salvata la definizione della query, e `numEvens` è un semplice `Integer`.  
  
 [!code-vb[VbLINQFirstQuery#4](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_5.vb)]  
  
 È possibile ottenere lo stesso risultato utilizzando il `Aggregate` metodo.  
  
 [!code-vb[VbLINQFirstQuery#5](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_6.vb)]  
  
 È inoltre possibile forzare l'esecuzione di una query chiamando la `ToList` o `ToArray` metodo su una query (esecuzione immediata) o una variabile di query (esecuzione posticipata), come illustrato nel codice seguente.  
  
 [!code-vb[VbLINQFirstQuery#6](../../../../visual-basic/programming-guide/concepts/linq/codesnippet/VisualBasic/writing-your-first-linq-query_7.vb)]  
  
 Negli esempi precedenti, `evensQuery3` è una query, variabile, ma `evensList` è riportato un elenco e `evensArray` è una matrice.  
  
 Utilizzando `ToList` o `ToArray` per forzare immediatamente l'esecuzione è particolarmente utile negli scenari in cui si desidera eseguire immediatamente la query e memorizzare nella cache i risultati in un singolo oggetto collection. Per ulteriori informazioni su questi metodi, vedere [la conversione di tipi di dati](converting-data-types.md).  
  
 È anche possibile causare una query da eseguire utilizzando un `IEnumerable` metodo, ad esempio il <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> metodo.  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione a LINQ in Visual Basic](getting-started-with-linq.md)  
 [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Panoramica degli operatori query standard (Visual Basic)](standard-query-operators-overview.md)  
 [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [Query](../../../../visual-basic/language-reference/queries/queries.md)
