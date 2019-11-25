---
title: Introduzione a LINQ
ms.date: 08/28/2018
helpviewer_keywords:
- queries [LINQ in Visual Basic], about LINQ in Visual Basic queries
- query execution [LINQ in Visual Basic]
- range variables [Visual Basic]
- LINQ [Visual Basic]
- LINQ [Visual Basic], about LINQ in Visual Basic
- query expressions [LINQ in Visual Basic]
- LINQ
- deferred execution
- iteration variables [Visual Basic]
ms.assetid: 3047d86e-0d49-40e2-928b-dc02e46c7984
ms.openlocfilehash: 610f2a1020cc15f855b3ddfc0917e14aae34fb82
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344930"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Introduzione a LINQ in Visual Basic
Language-Integrated Query (LINQ) adds query capabilities to Visual Basic and provides simple and powerful capabilities when you work with all kinds of data. Rather than sending a query to a database to be processed, or working with different query syntax for each type of data that you are searching, LINQ introduces queries as part of the Visual Basic language. Utilizza una sintassi unificata indipendentemente dal tipo di dati.  
  
 LINQ enables you to query data from a SQL Server database, XML, in-memory arrays and collections, ADO.NET datasets, or any other remote or local data source that supports LINQ. You can do all this with common Visual Basic language elements. Because your queries are written in the Visual Basic language, your query results are returned as strongly-typed objects. Questi oggetti supportano IntelliSense, che consente di scrivere il codice più velocemente e di individuare errori nelle query in fase di compilazione anziché in fase di esecuzione. Le query LINQ possono essere utilizzate come origine di query aggiuntive per perfezionare i risultati. Possono anche venire associate a controlli in modo che gli utenti possano facilmente visualizzare e modificare i risultati della query.  
  
 Nell'esempio di codice seguente viene illustrata una query LINQ che restituisce un elenco di clienti da una raccolta e li raggruppa in base alla località.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#1)]  
  
## <a name="running-the-examples"></a>Esecuzione degli esempi  
 To run the examples in the introduction and in the [Structure of a LINQ Query](#structure-of-a-linq-query) section, include the following code, which returns lists of customers and orders.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#31)]  
  
## <a name="linq-providers"></a>LINQ providers  
 A *LINQ provider* maps your Visual Basic LINQ queries to the data source being queried. Quando si scrive una query LINQ, il provider prende tale query e la traduce in comandi che l'origine dati sarà in grado di eseguire. Il provider converte anche i dati dall'origine negli oggetti che costituiscono il risultato della query. Infine, converte gli oggetti in dati quando si inviano aggiornamenti all'origine dati.  
  
 Visual Basic includes the following LINQ providers.  
  
|Provider|Descrizione|  
|---|---|  
|LINQ to Objects|Il provider LINQ to Objects consente di eseguire una query su raccolte e matrici in memoria. Se un oggetto supporta l'interfaccia <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, il provider LINQ to Objects consente di eseguire una query su di esso.<br /><br /> You can enable the LINQ to Objects provider by importing the <xref:System.Linq> namespace, which is imported by default for all Visual Basic projects.<br /><br /> For more information about the LINQ to Objects provider, see [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|Il provider LINQ to SQL consente di eseguire query e di modificare i dati su un database SQL server. Questo semplifica il mapping del modello a oggetti per un'applicazione alle tabelle e agli oggetti in un database.<br /><br /> Visual Basic makes it easier to work with LINQ to SQL by including the Object Relational Designer (O/R Designer). Questa finestra di progettazione viene utilizzata per creare un modello a oggetti in un'applicazione con mapping sugli oggetti in un database. The O/R Designer also provides functionality to map stored procedures and functions to the <xref:System.Data.Linq.DataContext> object, which manages communication with the database and stores state for optimistic concurrency checks.<br /><br /> For more information about the LINQ to SQL provider, see [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). For more information about the Object Relational Designer, see [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Il provider LINQ to XML consente di eseguire query e di modificare l'XML. È possibile modificare l'XML in memoria o caricare l'XML da file o salvare l'XML in un file.<br /><br /> Additionally, the LINQ to XML provider enables XML literals and XML axis properties that enable you to write XML directly in your Visual Basic code. For more information, see [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|The LINQ to DataSet provider enables you to query and update data in an ADO.NET dataset. È possibile aggiungere le caratteristiche avanzate di LINQ ad applicazioni che utilizzano set di dati per semplificare ed estendere le funzionalità per l'esecuzione di query, l'aggregazione e l'aggiornamento dei dati nel set di dati.<br /><br /> Per altre informazioni, vedere [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
## <a name="structure-of-a-linq-query"></a>Structure of a LINQ query  
 A LINQ query, often referred to as a *query expression*, consists of a combination of query clauses that identify the data sources and iteration variables for the query. Un'espressione di query può includere anche istruzioni per ordinare, filtrare, raggruppare e unire o eseguire calcoli da applicare ai dati di origine. La sintassi delle espressioni di query è simile alla sintassi SQL; pertanto, gran parte della sintassi risulterà familiare.  
  
 Un'espressione di query inizia con una clausola `From`. Questa clausola identifica i dati di origine per una query e le variabili utilizzate per fare riferimento a ogni singolo elemento dell'insieme di origine. These variables are named *range variables* or *iteration variables*. La clausola `From` è obbligatoria per una query, tranne per le query `Aggregate`, in cui la clausola `From` è facoltativa. Dopo che l'ambito e l'origine della query sono identificati nelle clausole `From` o `Aggregate`, è possibile includere qualsiasi combinazione di clausole di query per perfezionare la query. For details about query clauses, see Visual Basic LINQ Query Operators later in this topic. Ad esempio, nella query seguente viene identificata una raccolta di origine di dati sul cliente come variabile `customers` e una variabile di iterazione denominata `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#2)]  
  
 In questo esempio viene illustrata una query valida; tuttavia, la query diventa molto più efficace quando si aggiungono altre clausole di query per perfezionare il risultato. Ad esempio, è possibile aggiungere una clausola `Where` per filtrare il risultato per uno o più valori. Le espressioni di query consistono in una sola riga di codice; è possibile inserire clausole aggiuntive solo alla fine della query. You can break up a query across multiple lines of text to improve readability by using the underscore (\_) line-continuation character. Nell'esempio di codice seguente viene illustrato un esempio di query che include una clausola `Where`.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#3)]  
  
 Un'altra efficace clausola di query è `Select`, che consente di restituire dall'origine dati solo i campi selezionati. Le query LINQ restituiscono raccolte enumerabili di oggetti fortemente tipizzati. Una query può restituire una raccolta di tipi anonimi o tipi denominati. È possibile utilizzare la clausola `Select` per restituire solo un unico campo dall'origine dati. Quando si esegue questa operazione, il tipo dell'insieme restituito è il tipo di quell'unico campo. È possibile utilizzare anche la clausola `Select` per restituire più campi dall'origine dati. In questo caso, il tipo della raccolta restituita è un nuovo tipo anonimo. È anche possibile far corrispondere i campi restituiti dalla query ai campi di un tipo denominato specificato. Nell'esempio di codice seguente viene illustrata un'espressione di query che restituisce una raccolta di tipi anonimi che hanno membri popolati con dati dai campi selezionati dell'origine dati.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#4)]  
  
 Le query LINQ possono essere utilizzate anche per combinare più origini di dati e restituire un unico risultato. Questa operazione può essere eseguita con una o più clausole `From` oppure utilizzando le clausole di query `Join` o `Group Join`. Nell'esempio di codice seguente viene illustrata un'espressione di query che combina dati del cliente e dell'ordine e restituisce una raccolta di tipi anonimi che contengono dati del cliente e dell'ordine.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#5)]  
  
 È possibile utilizzare la clausola `Group Join` per creare un risultato della query gerarchico che contiene una raccolta di oggetti Customer. Ogni oggetto Customer ha una proprietà che contiene una raccolta di tutti gli ordini per quel cliente. Nell'esempio di codice seguente viene illustrata un'espressione di query che combina dati del cliente e dell'ordine in un risultato gerarchico e restituisce una raccolta di tipi anonimi. La query restituisce un tipo che include una proprietà `CustomerOrders` che contiene una raccolta di dati dell'ordine per tale cliente. Include anche una proprietà `OrderTotal` che contiene la somma dei totali per tutti gli ordini per quel cliente. (Questa query è equivalente a una query LEFT OUTER JOIN).  
  
 [!code-vb[VbVbalrIntroToLINQ#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#6)]  
  
 Esistono molti altri operatori di query LINQ che è possibile utilizzare per creare efficaci espressioni di query. Nella prossima sezione di questo argomento vengono discusse le varie clausole di query che è possibile includere in un'espressione di query. For details about Visual Basic query clauses, see [Queries](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Visual Basic LINQ query operators  

Le classi nello spazio dei nomi <xref:System.Linq> e negli altri spazi dei nomi che supportano query LINQ includono metodi che è possibile chiamare per creare e perfezionare query basate sulle esigenze dell'applicazione. Visual Basic includes keywords for the following common query clauses. For details about Visual Basic query clauses, see [Queries](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>Clausola From

Either a [`From` clause](../../../../visual-basic/language-reference/queries/from-clause.md) or an `Aggregate` clause is required to begin a query. Una clausola `From` specifica una raccolta di origine e una variabile di iterazione per una query. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#7)]

### <a name="select-clause"></a>clausola Select

Parametro facoltativo. A [`Select` clause](../../../../visual-basic/language-reference/queries/select-clause.md) declares a set of iteration variables for a query. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#8)]

Se non viene specificata nessuna clausola `Select`, le variabili di iterazione per la query consistono nelle variabili di iterazione specificate dalla clausola `From` o `Aggregate`.

### <a name="where-clause"></a>Clausola Where

Parametro facoltativo. A [`Where` clause](../../../../visual-basic/language-reference/queries/where-clause.md) specifies a filtering condition for a query. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#9)]

### <a name="order-by-clause"></a>Order By clause]

|Optional. An [`Order By` clause](../../../../visual-basic/language-reference/queries/order-by-clause.md) specifies the sort order for columns in a query. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#10)]

### <a name="join-clause"></a>clausola Join

Parametro facoltativo. A [`Join` clause](../../../../visual-basic/language-reference/queries/join-clause.md) combines two collections into a single collection. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#11)]

### <a name="group-by-clause"></a>clausola Group By

Parametro facoltativo. A [`Group By` clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) groups the elements of a query result. It can be used to apply aggregate functions to each group. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#12)]

### <a name="group-join-clause"></a>clausola Group Join

Parametro facoltativo. A [`Group Join` clause](../../../../visual-basic/language-reference/queries/group-join-clause.md) combines two collections into a single hierarchical collection. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#13)]

### <a name="aggregate-clause"></a>clausola di aggregazione

Either an [`Aggregate` clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) or a `From` clause is required to begin a query. Una clausola `Aggregate` applica una o più funzioni di aggregazione a una raccolta. For example, you can use the `Aggregate` clause to calculate a sum for all the elements returned by a query, as the following example does.

 [!code-vb[VbVbalrIntroToLINQ#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#14)]

È anche possibile utilizzare la clausola `Aggregate` per modificare una query. Ad esempio, è possibile utilizzare la clausola `Aggregate` per eseguire un calcolo su una raccolta di query correlata. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#15)]

### <a name="let-clause"></a>Let (clausola)

Parametro facoltativo. A [`Let` clause](../../../../visual-basic/language-reference/queries/let-clause.md) computes a value and assigns it to a new variable in the query. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#16)]

### <a name="distinct-clause"></a>clausola Distinct

Parametro facoltativo. A `Distinct` clause restricts the values of the current iteration variable to eliminate duplicate values in query results. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#17)]

### <a name="skip-clause"></a>Skip (clausola)

Parametro facoltativo. A [`Skip` clause](../../../../visual-basic/language-reference/queries/skip-clause.md) bypasses a specified number of elements in a collection and then returns the remaining elements. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#18)]

### <a name="skip-while-clause"></a>Skip While (clausola)

Parametro facoltativo. A [`Skip While` clause](../../../../visual-basic/language-reference/queries/skip-while-clause.md) bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#19)]

### <a name="take-clause"></a>Take (clausola)

Parametro facoltativo. A [`Take` clause](../../../../visual-basic/language-reference/queries/take-clause.md) returns a specified number of contiguous elements from the start of a collection. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#20)]

### <a name="take-while-clause"></a>Take While (clausola)

Parametro facoltativo. A [`Take While` clause](../../../../visual-basic/language-reference/queries/take-while-clause.md) includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements. Esempio:

 [!code-vb[VbVbalrIntroToLINQ#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#21)]
  
## <a name="use-additional-linq-query-features"></a>Use additional LINQ query features  
  
È possibile utilizzare le funzionalità aggiuntive delle query LINQ chiamando i membri dei tipi enumerabili e disponibili per query forniti da LINQ. È possibile utilizzare queste funzionalità aggiuntive chiamando un particolare operatore di query sul risultato di un'espressione di query. For example, the following example uses the <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> method to combine the results of two queries into one query result. Viene utilizzato il metodo <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> per restituire il risultato della query come elenco generico.
  
 [!code-vb[VbVbalrIntroToLINQ#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#22)]  
  
 For details about additional LINQ capabilities, see [Standard Query Operators Overview](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Connect to a database by using LINQ to SQL  
 In Visual Basic, you identify the SQL Server database objects, such as tables, views, and stored procedures, that you want to access by using a LINQ to SQL file. Un file LINQ to SQL ha un'estensione .dbml.  
  
 When you have a valid connection to a SQL Server database, you can add a **LINQ to SQL Classes** item template to your project. Verrà visualizzato Object Relational Designer (O/R Designer). The O/R Designer enables you to drag the items that you want to access in your code from the **Server Explorer**/**Database Explorer** onto the designer surface. Il file LINQ to SQL aggiunge un oggetto <xref:System.Data.Linq.DataContext> al progetto. Questo oggetto include proprietà e raccolte per tabelle e visualizzazioni alle quali si desidera accedere e metodi per le stored procedure che si desidera chiamare. Dopo avere salvato le modifiche nel file LINQ to SQL (.dbml), è possibile accedere a questi oggetti nel codice facendo riferimento all'oggetto <xref:System.Data.Linq.DataContext> che viene definito da O/R Designer. L'oggetto <xref:System.Data.Linq.DataContext> per il progetto viene denominato in base al nome del file LINQ to SQL. Ad esempio, un file LINQ to SQL denominato Northwind.dbml creerà un oggetto <xref:System.Data.Linq.DataContext> chiamato `NorthwindDataContext`.  
  
 For examples with step-by-step instructions, see [How to: Query a Database](how-to-query-a-database-by-using-linq.md) and [How to: Call a Stored Procedure](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Visual Basic features that support LINQ  
 Visual Basic includes other notable features that make the use of LINQ simple and reduce the amount of code that you must write to perform LINQ queries. tra cui:  
  
- **Anonymous types**, which enable you to create a new type based on a query result.  
  
- **Implicitly typed variables**, which enable you to defer specifying a type and let the compiler infer the type based on the query result.  
  
- **Extension methods**, which enable you to extend an existing type with your own methods without modifying the type itself.  
  
 For details, see [Visual Basic Features That Support LINQ](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Deferred and immediate query execution

 L'esecuzione della query è distinta dalla creazione della query. Dopo che una query viene creata, l'esecuzione viene attivata da un meccanismo separato. A query can be executed as soon as it is defined (*immediate execution*), or the definition can be stored and the query can be executed later (*deferred execution*).  
  
 Per impostazione predefinita, quando si crea una query, la query stessa non viene eseguita immediatamente. Al contrario, la definizione della query viene archiviata nella variabile utilizzata per fare riferimento al risultato della query. Quando si accede in un secondo momento alla variabile del risultato della query nel codice, ad esempio in un ciclo `For…Next`, la query viene eseguita. This process is referred to as *deferred execution*.  
  
 Queries can also be executed when they are defined, which is referred to as *immediate execution*. È possibile attivare l'esecuzione immediata applicando un metodo che richiede l'accesso ai singoli elementi del risultato della query. Questo potrebbe risultare dall'inclusione di una funzione di aggregazione, come `Count`, `Sum`, `Average`, `Min` o `Max`. For more information about aggregate functions, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md).  
  
 Anche l'utilizzo dei metodi `ToList` o `ToArray` forza l'esecuzione immediata. Ciò può essere utile quando si desidera eseguire immediatamente la query e memorizzare nella cache i risultati. For more information about these methods, see [Converting Data Types](../../concepts/linq/converting-data-types.md).  
  
 For more information about query execution, see [Writing Your First LINQ Query](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>XML in Visual Basic  
 The XML features in Visual Basic include XML literals and XML axis properties, which enable you easily to create, access, query, and modify XML in your code. I valori letterali XML consentono di scrivere l'XML direttamente nel codice. Il compilatore di Visual Basic tratta l'XML come oggetto dati di prima classe.  
  
 Nell'esempio di codice seguente viene mostrato come creare un elemento XML, accedere ai sottoelementi e agli attributi ed eseguire una query sul contenuto dell'elemento utilizzando LINQ.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 For more information, see [XML](../xml/index.md).  
  
## <a name="related-resources"></a>Risorse correlate  
  
|Argomento|Descrizione|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Describes the XML features in Visual Basic that can be queried and that enable you to include XML as first-class data objects in your Visual Basic code.|  
|[Query](../../../language-reference/queries/index.md)|Provides reference information about the query clauses that are available in Visual Basic.|  
|[LINQ (Language-Integrated Query)](../../concepts/linq/index.md)|Sono incluse informazioni generali, indicazioni di programmazione ed esempi per LINQ.|  
|[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)|Sono incluse informazioni generali, indicazioni di programmazione ed esempi per LINQ to SQL.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|Sono incluse informazioni generali, indicazioni di programmazione ed esempi per LINQ to Objects.|  
|[LINQ to ADO.NET (pagina portale)](../../concepts/linq/linq-to-adonet-portal-page.md)|Includes links to general information, programming guidance, and samples for LINQ to ADO.NET.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|Sono incluse informazioni generali, indicazioni di programmazione ed esempi per LINQ to XML.|  
  
## <a name="how-to-and-walkthrough-topics"></a>How to and walkthrough topics
 [Procedura: Eseguire query in un database](how-to-query-a-database-by-using-linq.md)  
  
 [Procedura: Chiamare una stored procedure](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Procedura: Modificare dati in un database](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Procedura: Combinare dati utilizzando join](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Procedura: Ordinare i risultati di query](how-to-sort-query-results-by-using-linq.md)  
  
 [Procedura: Filtrare i risultati di una query](how-to-filter-query-results-by-using-linq.md)  
  
 [Procedura: Conteggio, somma o media di dati](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Procedura: Trovare il valore minimo o massimo in un risultato di query](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Featured book chapters  
 [Chapter 17: LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) in [Programming Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query)](../../concepts/linq/index.md)
- [Cenni preliminari su LINQ to XML in Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md)
- [Panoramica di LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [Strumenti LINQ to SQL in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
