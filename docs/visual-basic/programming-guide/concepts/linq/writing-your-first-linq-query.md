---
title: Scrittura della prima query LINQ (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- queries [LINQ in Visual Basic], writing
- LINQ queries [Visual Basic]
- LINQ [Visual Basic], writing queries
ms.assetid: 4affb732-3e9b-4479-aa31-1f9bd8183cbe
ms.openlocfilehash: 5c83d888f65ce5c216327e94c5d4d1267fb93c29
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69952004"
---
# <a name="writing-your-first-linq-query-visual-basic"></a>Scrittura della prima query LINQ (Visual Basic)
Una *query* è un'espressione che recupera dati da un'origine dati. Le query sono espresse in un linguaggio di query dedicato. Nel corso del tempo sono stati sviluppati linguaggi diversi per diversi tipi di origini dati, ad esempio SQL per i database relazionali e XQuery per XML. Questo consente allo sviluppatore di applicazioni di apprendere un nuovo linguaggio di query per ogni tipo di origine dati o formato dati supportato.  
  
 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]semplifica la situazione offrendo un modello coerente per l'utilizzo dei dati in diversi tipi di origini dati e formati. In una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] vengono sempre usati gli oggetti. Si utilizzano gli stessi modelli di codifica di base per eseguire query e trasformare i dati in documenti XML, database SQL, set di dati ADO.NET ed entità, raccolte di .NET Framework e qualsiasi altra origine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] o formato per cui è disponibile un provider. In questo documento vengono descritte le tre fasi della creazione e dell'utilizzo [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] di query di base.  
  
## <a name="three-stages-of-a-query-operation"></a>Tre fasi di un'operazione di query  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]le operazioni di query sono costituite da tre azioni:  
  
1. Ottenere l'origine dati o le origini.  
  
2. Creare la query.  
  
3. Eseguire la query.  
  
 In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]l'esecuzione di una query è diversa dalla creazione della query. Non è possibile recuperare i dati semplicemente creando una query. Questo punto viene illustrato più dettagliatamente di seguito in questo argomento.  
  
 Nell'esempio seguente vengono illustrate le tre parti di un'operazione di query. Nell'esempio viene utilizzata una matrice di numeri interi come un'origine dati comoda a scopo dimostrativo. Tuttavia, gli stessi concetti si applicano anche ad altre origini dati.  
  
> [!NOTE]
> Nella [pagina compilazione, Progettazione progetti (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic), assicurarsi che l' **opzione deduce** sia impostata **su on**.  
  
 [!code-vb[VbLINQFirstQuery#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#1)]  
  
 Output:  
  
 `0 2 4 6`  
  
## <a name="the-data-source"></a>Origine dati  
 Poiché l'origine dati nell'esempio precedente è una matrice, supporta implicitamente l'interfaccia generica <xref:System.Collections.Generic.IEnumerable%601> . In questo modo è possibile utilizzare una matrice come origine dati per una [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query. I tipi che supportano <xref:System.Collections.Generic.IEnumerable%601> o un'interfaccia derivata, ad esempio l'interfaccia generica <xref:System.Linq.IQueryable%601> sono denominati *tipi queryable*.  
  
 Come tipo sottoposta a query in modo implicito, la matrice non richiede alcuna modifica o trattamento [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] speciale per fungere da origine dati. Lo stesso vale per qualsiasi tipo di raccolta che supporta <xref:System.Collections.Generic.IEnumerable%601>, incluse le classi <xref:System.Collections.Generic.List%601>generiche, <xref:System.Collections.Generic.Dictionary%602>e altre classi nella libreria di classi .NET Framework.  
  
 Se i dati di origine non sono già <xref:System.Collections.Generic.IEnumerable%601>implementati [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] , è necessario un provider per implementare la funzionalità degli *operatori di query standard* per tale origine dati. Ad esempio, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] gestisce il lavoro di caricamento di un documento XML in un <xref:System.Xml.Linq.XElement> tipo Queryable, come illustrato nell'esempio seguente. Per ulteriori informazioni sugli operatori di query standard, vedere [Cenni preliminari sugli operatori di query standard (Visual Basic)](standard-query-operators-overview.md).  
  
 [!code-vb[VbLINQFirstQuery#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#2)]  
  
 Con [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)]è prima di tutto necessario creare un mapping relazionale a oggetti in fase di progettazione, manualmente o usando gli [strumenti LINQ to SQL in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2) in Visual Studio. È possibile scrivere le query sugli oggetti e in fase di esecuzione [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] gestisce la comunicazione con il database. Nell'esempio seguente, `customers` rappresenta una tabella specifica nel database e <xref:System.Data.Linq.Table%601> supporta Generic <xref:System.Linq.IQueryable%601>.  
  
```vb  
' Create a data source from a SQL table.  
Dim db As New DataContext("C:\Northwind\Northwnd.mdf")  
Dim customers As Table(Of Customer) = db.GetTable(Of Customer)  
```  
  
 Per altre informazioni sulla creazione di tipi specifici di origini dati, vedere la documentazione dei diversi provider [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]. Per un elenco di questi provider, vedere [LINQ (Language-Integrated Query)](../../../../visual-basic/programming-guide/concepts/linq/index.md). La regola di base è semplice: [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] un'origine dati è qualsiasi oggetto che supporta l' <xref:System.Collections.Generic.IEnumerable%601> interfaccia generica o un'interfaccia che eredita da essa.  
  
> [!NOTE]
> I tipi, <xref:System.Collections.ArrayList> ad esempio che supportano l'interfaccia <xref:System.Collections.IEnumerable> non generica, possono essere [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] utilizzati anche come origini dati. Per un esempio che usa un <xref:System.Collections.ArrayList>, vedere [procedura: Eseguire una query su un ArrayList con LINQ (](how-to-query-an-arraylist-with-linq.md)Visual Basic).  
  
## <a name="the-query"></a>Query  
 Nella query specificare le informazioni che si desidera recuperare dall'origine o dalle origini dati. È anche possibile specificare il modo in cui le informazioni devono essere ordinate, raggruppate o strutturate prima di essere restituite. Per abilitare la creazione della query, Visual Basic ha incorporato una nuova sintassi di query nel linguaggio.  
  
 Quando viene eseguita, la query nell'esempio seguente restituisce tutti i numeri pari da una matrice di interi, `numbers`.  
  
 [!code-vb[VbLINQFirstQuery#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#1)]  
  
 L'espressione di query contiene tre clausole `From`: `Where`, e `Select`. La funzione e lo scopo specifici di ogni clausola di espressione di query sono illustrati in [operazioni di query di base (Visual Basic)](basic-query-operations.md). Per ulteriori informazioni, vedere [query](../../../../visual-basic/language-reference/queries/index.md). Si noti che [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]in una definizione di query spesso è archiviata in una variabile ed eseguita in un secondo momento. La variabile `evensQuery` di query, ad esempio nell'esempio precedente, deve essere un tipo Queryable. Il tipo di `evensQuery` è `IEnumerable(Of Integer)`, assegnato dal compilatore usando l'inferenza del tipo locale.  
  
 È importante ricordare che la variabile di query non esegue alcuna azione e non restituisce alcun dato. Archivia solo la definizione della query. Nell'esempio precedente si tratta del `For Each` ciclo che esegue la query.  
  
## <a name="query-execution"></a>Esecuzione di query  
 L'esecuzione della query è separata dalla creazione della query. La creazione della query definisce la query, ma l'esecuzione viene attivata da un meccanismo diverso. Una query può essere eseguita non appena viene definita (*esecuzione immediata*) oppure la definizione può essere archiviata e la query può essere eseguita in un secondo momento (*esecuzione posticipata*).  
  
### <a name="deferred-execution"></a>Esecuzione posticipata  
 Una query [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] tipica è simile a quella dell'esempio precedente, in cui `evensQuery` è definito. Consente di creare la query, ma non di eseguirla immediatamente. Al contrario, la definizione della query viene archiviata nella `evensQuery`variabile di query. Si esegue la query in un secondo momento, in `For Each` genere usando un ciclo, che restituisce una sequenza di valori o applicando un operatore di query standard `Count` , `Max`ad esempio o. Questo processo viene definito *esecuzione posticipata*.  
  
 [!code-vb[VbLINQFirstQuery#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#7)]  
  
 Per una sequenza di valori, è possibile accedere ai dati recuperati usando la variabile di iterazione `For Each` nel`number` ciclo (nell'esempio precedente). Poiché la variabile di query `evensQuery`,, include la definizione della query anziché i risultati della query, è possibile eseguire una query con la frequenza desiderata utilizzando la variabile di query più di una volta. È ad esempio possibile che nell'applicazione sia presente un database che viene aggiornato continuamente da un'applicazione separata. Dopo aver creato una query che recupera i dati dal database, è possibile utilizzare un `For Each` ciclo per eseguire ripetutamente la query, recuperando i dati più recenti ogni volta.  
  
 Nell'esempio seguente viene illustrato il funzionamento dell'esecuzione posticipata. Dopo `evensQuery2` che è stato definito ed eseguito `For Each` con un ciclo, come negli esempi precedenti, alcuni elementi nell'origine `numbers` dati vengono modificati. Quindi, un `For Each` secondo ciclo `evensQuery2` viene eseguito nuovamente. I risultati sono diversi la seconda volta, perché il `For Each` ciclo esegue nuovamente la query, usando i nuovi valori in. `numbers`  
  
 [!code-vb[VbLINQFirstQuery#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#3)]  
  
 Output:  
  
 `Evens in original array:`  
  
 `0  2  4  6`  
  
 `Evens in changed array:`  
  
 `0  10  2  22  8`  
  
### <a name="immediate-execution"></a>Esecuzione immediata  
 Nell'esecuzione posticipata delle query, la definizione della query viene archiviata in una variabile di query per un'esecuzione successiva. Nell'esecuzione immediata la query viene eseguita al momento della relativa definizione. L'esecuzione viene attivata quando si applica un metodo che richiede l'accesso ai singoli elementi del risultato della query. L'esecuzione immediata viene spesso forzata utilizzando uno degli operatori di query standard che restituiscono valori singoli. Gli esempi `Count`sono `Max` ,`Average`, e `First`. Questi operatori di query standard eseguono la query non appena vengono applicati per calcolare e restituire un risultato singleton. Per ulteriori informazioni sugli operatori di query standard che restituiscono valori singoli, vedere operazioni di [aggregazione](aggregation-operations.md), [operazioni sugli elementi](element-operations.md)e [operazioni del quantificatore](quantifier-operations.md).  
  
 La query seguente restituisce un conteggio dei numeri pari in una matrice di numeri interi. La definizione della query non viene salvata `numEvens` ed è un `Integer`semplice.  
  
 [!code-vb[VbLINQFirstQuery#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#4)]  
  
 È possibile ottenere lo stesso risultato usando il `Aggregate` metodo.  
  
 [!code-vb[VbLINQFirstQuery#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#5)]  
  
 È anche possibile forzare l'esecuzione di una query chiamando `ToList` il `ToArray` metodo o su una query (immediate) o su una variabile di query (rinviata), come illustrato nel codice seguente.  
  
 [!code-vb[VbLINQFirstQuery#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbLINQFirstQuery/VB/Class1.vb#6)]  
  
 Negli esempi precedenti, `evensQuery3` è una variabile di query, ma `evensList` è un elenco ed `evensArray` è una matrice.  
  
 L' `ToList` utilizzo `ToArray` di o per forzare l'esecuzione immediata è particolarmente utile negli scenari in cui si desidera eseguire immediatamente la query e memorizzare nella cache i risultati in un singolo oggetto raccolta. Per ulteriori informazioni su questi metodi, vedere [conversione di tipi di dati](converting-data-types.md).  
  
 È anche possibile causare l'esecuzione di una query usando un `IEnumerable` metodo come il <xref:Microsoft.VisualBasic.Collection.System%23Collections%23IEnumerable%23GetEnumerator%2A> metodo.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione a LINQ in Visual Basic](getting-started-with-linq.md)
- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Panoramica degli operatori query standard (Visual Basic)](standard-query-operators-overview.md)
- [Introduzione a LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [Query](../../../../visual-basic/language-reference/queries/index.md)
