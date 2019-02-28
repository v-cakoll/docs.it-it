---
title: Introduzione a LINQ in Visual Basic
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
ms.openlocfilehash: 6987263854b0d0372bc08bb7e4d6efb498e265f1
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2019
ms.locfileid: "56973626"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Introduzione a LINQ in Visual Basic
Language-Integrated Query (LINQ) aggiunge funzionalità di query a Visual Basic e fornisce semplici e potenti funzionalità quando si lavora con tutti i tipi di dati. Anziché inviare una query a un database da elaborare, o utilizzare sintassi di query differenti per ogni tipo di dati che si stanno cercando, LINQ introduce le query come parte del linguaggio Visual Basic. Utilizza una sintassi unificata indipendentemente dal tipo di dati.  
  
 LINQ consente di eseguire query sui dati da un database di SQL Server, XML, le matrici in memoria e le raccolte, i dataset ADO.NET o qualsiasi altra origine dati locale o remoto che supporta LINQ. È possibile eseguire tutte queste con elementi comuni del linguaggio Visual Basic. Poiché le query sono scritte in linguaggio Visual Basic, i risultati della query vengono restituiti come oggetti fortemente tipizzati. Questi oggetti supportano IntelliSense, che consente di scrivere il codice più velocemente e di individuare errori nelle query in fase di compilazione anziché in fase di esecuzione. Le query LINQ possono essere utilizzate come origine di query aggiuntive per perfezionare i risultati. Possono anche venire associate a controlli in modo che gli utenti possano facilmente visualizzare e modificare i risultati della query.  
  
 Nell'esempio di codice seguente viene illustrata una query LINQ che restituisce un elenco di clienti da una raccolta e li raggruppa in base alla località.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#1)]  
  
## <a name="running-the-examples"></a>Esecuzione degli esempi  
 Per eseguire gli esempi nell'introduzione e nella [struttura di una Query LINQ](#structure-of-a-linq-query) sezione, includere il codice seguente, che restituisce elenchi di clienti e ordini.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#31)]  
  
## <a name="linq-providers"></a>Provider LINQ  
 Oggetto *provider LINQ* viene eseguito il mapping delle query LINQ di Visual Basic all'origine dati sottoposto a query. Quando si scrive una query LINQ, il provider prende tale query e la traduce in comandi che l'origine dati sarà in grado di eseguire. Il provider converte anche i dati dall'origine negli oggetti che costituiscono il risultato della query. Infine, converte gli oggetti in dati quando si inviano aggiornamenti all'origine dati.  
  
 Visual Basic include i seguenti provider LINQ.  
  
|Provider|Descrizione|  
|---|---|  
|LINQ to Objects|Il provider LINQ to Objects consente di eseguire una query su raccolte e matrici in memoria. Se un oggetto supporta l'interfaccia <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, il provider LINQ to Objects consente di eseguire una query su di esso.<br /><br /> È possibile abilitare il provider LINQ to Objects importando il <xref:System.Linq> dello spazio dei nomi, che viene importato per impostazione predefinita per tutti i progetti di Visual Basic.<br /><br /> Per altre informazioni sul provider LINQ to Objects, vedere [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|Il provider LINQ to SQL consente di eseguire query e di modificare i dati su un database SQL server. Questo semplifica il mapping del modello a oggetti per un'applicazione alle tabelle e agli oggetti in un database.<br /><br /> Visual Basic semplifica l'utilizzo di LINQ to SQL includendo il Object Relational Designer (O/R Designer). Questa finestra di progettazione viene utilizzata per creare un modello a oggetti in un'applicazione con mapping sugli oggetti in un database. O/R Designer anche fornisce funzionalità per eseguire il mapping di stored procedure e funzioni per i <xref:System.Data.Linq.DataContext> oggetto, che gestisce la comunicazione con il database e archivia lo stato per le verifiche della concorrenza ottimistica.<br /><br /> Per altre informazioni sul provider LINQ to SQL, vedere [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). Per altre informazioni su Progettazione relazionale oggetti, vedere [strumenti LINQ to SQL in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Il provider LINQ to XML consente di eseguire query e di modificare l'XML. È possibile modificare l'XML in memoria o caricare l'XML da file o salvare l'XML in un file.<br /><br /> Inoltre, il provider LINQ to XML consente i valori letterali XML e proprietà axis XML che consentono di scrivere codice XML direttamente nel codice Visual Basic. Per altre informazioni, vedere [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|Il provider LINQ to DataSet consente di eseguire query e aggiornamento dati in un [!INCLUDE[vstecado](~/includes/vstecado-md.md)] set di dati. È possibile aggiungere le caratteristiche avanzate di LINQ ad applicazioni che utilizzano set di dati per semplificare ed estendere le funzionalità per l'esecuzione di query, l'aggregazione e l'aggiornamento dei dati nel set di dati.<br /><br /> Per altre informazioni, vedere [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
## <a name="structure-of-a-linq-query"></a>Struttura di una query LINQ  
 Una query LINQ, noto anche come un *espressione di query*, costituito da una combinazione di clausole di query che identificano le origini dati e variabili di iterazione per la query. Un'espressione di query può includere anche istruzioni per ordinare, filtrare, raggruppare e unire o eseguire calcoli da applicare ai dati di origine. La sintassi delle espressioni di query è simile alla sintassi SQL; pertanto, gran parte della sintassi risulterà familiare.  
  
 Un'espressione di query inizia con una clausola `From`. Questa clausola identifica i dati di origine per una query e le variabili utilizzate per fare riferimento a ogni singolo elemento dell'insieme di origine. Queste variabili sono denominate *variabili di intervallo* oppure *variabili di iterazione*. La clausola `From` è obbligatoria per una query, tranne per le query `Aggregate`, in cui la clausola `From` è facoltativa. Dopo che l'ambito e l'origine della query sono identificati nelle clausole `From` o `Aggregate`, è possibile includere qualsiasi combinazione di clausole di query per perfezionare la query. Per informazioni dettagliate sulle clausole di query, vedere operatori di Query LINQ di Visual Basic più avanti in questo argomento. Ad esempio, nella query seguente viene identificata una raccolta di origine di dati sul cliente come variabile `customers` e una variabile di iterazione denominata `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#2)]  
  
 In questo esempio viene illustrata una query valida; tuttavia, la query diventa molto più efficace quando si aggiungono altre clausole di query per perfezionare il risultato. Ad esempio, è possibile aggiungere una clausola `Where` per filtrare il risultato per uno o più valori. Le espressioni di query consistono in una sola riga di codice; è possibile inserire clausole aggiuntive solo alla fine della query. È possibile suddividere una query su più righe di testo per migliorarne la leggibilità utilizzando il carattere di sottolineatura (\_) carattere di continuazione di riga. Nell'esempio di codice seguente viene illustrato un esempio di query che include una clausola `Where`.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#3)]  
  
 Un'altra efficace clausola di query è `Select`, che consente di restituire dall'origine dati solo i campi selezionati. Le query LINQ restituiscono raccolte enumerabili di oggetti fortemente tipizzati. Una query può restituire una raccolta di tipi anonimi o tipi denominati. È possibile utilizzare la clausola `Select` per restituire solo un unico campo dall'origine dati. Quando si esegue questa operazione, il tipo dell'insieme restituito è il tipo di quell'unico campo. È possibile utilizzare anche la clausola `Select` per restituire più campi dall'origine dati. In questo caso, il tipo della raccolta restituita è un nuovo tipo anonimo. È anche possibile far corrispondere i campi restituiti dalla query ai campi di un tipo denominato specificato. Nell'esempio di codice seguente viene illustrata un'espressione di query che restituisce una raccolta di tipi anonimi che hanno membri popolati con dati dai campi selezionati dell'origine dati.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#4)]  
  
 Le query LINQ possono essere utilizzate anche per combinare più origini di dati e restituire un unico risultato. Questa operazione può essere eseguita con una o più clausole `From` oppure utilizzando le clausole di query `Join` o `Group Join`. Nell'esempio di codice seguente viene illustrata un'espressione di query che combina dati del cliente e dell'ordine e restituisce una raccolta di tipi anonimi che contengono dati del cliente e dell'ordine.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#5)]  
  
 È possibile utilizzare la clausola `Group Join` per creare un risultato della query gerarchico che contiene una raccolta di oggetti Customer. Ogni oggetto Customer ha una proprietà che contiene una raccolta di tutti gli ordini per quel cliente. Nell'esempio di codice seguente viene illustrata un'espressione di query che combina dati del cliente e dell'ordine in un risultato gerarchico e restituisce una raccolta di tipi anonimi. La query restituisce un tipo che include una proprietà `CustomerOrders` che contiene una raccolta di dati dell'ordine per tale cliente. Include anche una proprietà `OrderTotal` che contiene la somma dei totali per tutti gli ordini per quel cliente. (Questa query è equivalente a una query LEFT OUTER JOIN).  
  
 [!code-vb[VbVbalrIntroToLINQ#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#6)]  
  
 Esistono molti altri operatori di query LINQ che è possibile utilizzare per creare efficaci espressioni di query. Nella prossima sezione di questo argomento vengono discusse le varie clausole di query che è possibile includere in un'espressione di query. Per informazioni dettagliate sulle clausole di query di Visual Basic, vedere [query](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Operatori di query LINQ per Visual Basic  

Le classi nello spazio dei nomi <xref:System.Linq> e negli altri spazi dei nomi che supportano query LINQ includono metodi che è possibile chiamare per creare e perfezionare query basate sulle esigenze dell'applicazione. Visual Basic include parole chiave per le clausole di query comuni seguenti. Per informazioni dettagliate sulle clausole di query di Visual Basic, vedere [query](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>Clausola From

Entrambi una [ `From` clausola](../../../../visual-basic/language-reference/queries/from-clause.md) o un `Aggregate` è necessario specificare la clausola per iniziare una query. Una clausola `From` specifica una raccolta di origine e una variabile di iterazione per una query. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#7)]

### <a name="select-clause"></a>clausola Select

Facoltativo. Oggetto [ `Select` clausola](../../../../visual-basic/language-reference/queries/select-clause.md) dichiara un set di variabili di iterazione per una query. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#8)]

Se non viene specificata nessuna clausola `Select`, le variabili di iterazione per la query consistono nelle variabili di iterazione specificate dalla clausola `From` o `Aggregate`.

### <a name="where-clause"></a>Clausola Where

Facoltativo. Oggetto [ `Where` clausola](../../../../visual-basic/language-reference/queries/where-clause.md) specifica una condizione di filtro per una query. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#9)]

### <a name="order-by-clause"></a>Clausola Order By]

| Facoltativo. Un' [ `Order By` clausola](../../../../visual-basic/language-reference/queries/order-by-clause.md) specifica l'ordinamento per le colonne in una query. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#10)]

### <a name="join-clause"></a>clausola Join

Facoltativo. Oggetto [ `Join` clausola](../../../../visual-basic/language-reference/queries/join-clause.md) combina due raccolte in un'unica raccolta. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#11)]

### <a name="group-by-clause"></a>clausola Group By

Facoltativo. Oggetto [ `Group By` clausola](../../../../visual-basic/language-reference/queries/group-by-clause.md) Raggruppa gli elementi del risultato della query. Può essere utilizzato per applicare le funzioni di aggregazione a ogni gruppo. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#12)]

### <a name="group-join-clause"></a>clausola Group Join

Facoltativo. Oggetto [ `Group Join` clausola](../../../../visual-basic/language-reference/queries/group-join-clause.md) combina due raccolte in un'unica raccolta gerarchica. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#13)]

### <a name="aggregate-clause"></a>clausola di aggregazione

Entrambi un [ `Aggregate` clausola](../../../../visual-basic/language-reference/queries/aggregate-clause.md) o un `From` è necessario specificare la clausola per iniziare una query. Una clausola `Aggregate` applica una o più funzioni di aggregazione a una raccolta. Ad esempio, è possibile usare il `Aggregate` clausola per calcolare una somma di tutti gli elementi restituiti da una query, come avviene nell'esempio seguente.

 [!code-vb[VbVbalrIntroToLINQ#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#14)]

È anche possibile utilizzare la clausola `Aggregate` per modificare una query. Ad esempio, è possibile utilizzare la clausola `Aggregate` per eseguire un calcolo su una raccolta di query correlata. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#15)]

### <a name="let-clause"></a>Let (clausola)

Facoltativo. Oggetto [ `Let` clausola](../../../../visual-basic/language-reference/queries/let-clause.md) calcola un valore e lo assegna a una nuova variabile nella query. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#16)]

### <a name="distinct-clause"></a>clausola Distinct

Facoltativo. Oggetto `Distinct` clausola limita i valori della variabile di iterazione corrente per eliminare i valori duplicati nei risultati della query. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#17)]

### <a name="skip-clause"></a>Skip (clausola)

Facoltativo. Oggetto [ `Skip` clausola](../../../../visual-basic/language-reference/queries/skip-clause.md) ignora un numero specificato di elementi in una raccolta e quindi restituisce gli elementi rimanenti. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#18)]

### <a name="skip-while-clause"></a>Skip While (clausola)

Facoltativo. Oggetto [ `Skip While` clausola](../../../../visual-basic/language-reference/queries/skip-while-clause.md) ignora gli elementi in una raccolta, purché una condizione specificata sia `true` e quindi restituisce gli elementi rimanenti. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#19)]

### <a name="take-clause"></a>Take (clausola)

Facoltativo. Oggetto [ `Take` clausola](../../../../visual-basic/language-reference/queries/take-clause.md) restituisce un numero specificato di elementi contigui dall'inizio di una raccolta. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#20)]

### <a name="take-while-clause"></a>Take While (clausola)

Facoltativo. Oggetto [ `Take While` clausola](../../../../visual-basic/language-reference/queries/take-while-clause.md) include gli elementi in una raccolta, purché una condizione specificata sia `true` e ignora gli elementi rimanenti. Ad esempio:

 [!code-vb[VbVbalrIntroToLINQ#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#21)]
  
## <a name="use-additional-linq-query-features"></a>Usare le funzionalità di query LINQ aggiuntive  
  
È possibile utilizzare le funzionalità aggiuntive delle query LINQ chiamando i membri dei tipi enumerabili e disponibili per query forniti da LINQ. È possibile utilizzare queste funzionalità aggiuntive chiamando un particolare operatore di query sul risultato di un'espressione di query. Ad esempio, l'esempio seguente usa il <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> metodo per combinare i risultati di due query in un unico risultato. Viene utilizzato il metodo <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType> per restituire il risultato della query come elenco generico.
  
 [!code-vb[VbVbalrIntroToLINQ#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#22)]  
  
 Per informazioni dettagliate sulle funzionalità LINQ aggiuntive, vedere [panoramica degli operatori Query Standard](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Connettersi a un database tramite LINQ to SQL  
 In Visual Basic è identificare gli oggetti di database di SQL Server, ad esempio tabelle, viste e stored procedure, che si desidera accedere usando un LINQ per file SQL. Un file LINQ to SQL ha un'estensione .dbml.  
  
 Quando si dispone di una connessione valida a un database di SQL Server, è possibile aggiungere un **classi LINQ to SQL** modello di elemento al progetto. Verrà visualizzato Object Relational Designer (O/R Designer). O/R Designer consente di trascinare gli elementi che si vuole accedere nel codice dal **Esplora Server**/**Esplora Database** nell'area di progettazione. Il file LINQ to SQL aggiunge un oggetto <xref:System.Data.Linq.DataContext> al progetto. Questo oggetto include proprietà e raccolte per tabelle e visualizzazioni alle quali si desidera accedere e metodi per le stored procedure che si desidera chiamare. Dopo avere salvato le modifiche nel file LINQ to SQL (.dbml), è possibile accedere a questi oggetti nel codice facendo riferimento all'oggetto <xref:System.Data.Linq.DataContext> che viene definito da O/R Designer. L'oggetto <xref:System.Data.Linq.DataContext> per il progetto viene denominato in base al nome del file LINQ to SQL. Ad esempio, un file LINQ to SQL denominato Northwind.dbml creerà un oggetto <xref:System.Data.Linq.DataContext> chiamato `NorthwindDataContext`.  
  
 Per esempi con istruzioni dettagliate, vedere [come: Query su un Database](how-to-query-a-database-by-using-linq.md) e [come: Chiamare una Stored Procedure](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Funzionalità di Visual Basic che supportano LINQ  
 Visual Basic include altre importanti funzionalità che semplificano l'uso di LINQ e ridurre la quantità di codice da scrivere per eseguire query LINQ. tra cui:  
  
-   **I tipi anonimi**, che consentono di creare un nuovo tipo basato su un risultato della query.  
  
-   **Variabili tipizzate in modo implicito**, che consentono di rinviare la specifica di un tipo e permettere al compilatore di dedurre il tipo in base al risultato della query.  
  
-   **I metodi di estensione**, che consentono di estendere un tipo esistente con i propri metodi senza modificare il tipo stesso.  
  
 Per informazioni dettagliate, vedere [le funzionalità che il supporto LINQ per Visual Basic](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Esecuzione di query posticipata e immediata

 L'esecuzione della query è distinta dalla creazione della query. Dopo che una query viene creata, l'esecuzione viene attivata da un meccanismo separato. Una query può essere eseguita non appena viene definito (*l'esecuzione immediata*), o può essere archiviata la definizione e la query può essere eseguita in un secondo momento (*esecuzione posticipata*).  
  
 Per impostazione predefinita, quando si crea una query, la query stessa non viene eseguita immediatamente. Al contrario, la definizione della query viene archiviata nella variabile utilizzata per fare riferimento al risultato della query. Quando si accede in un secondo momento alla variabile del risultato della query nel codice, ad esempio in un ciclo `For…Next`, la query viene eseguita. Questo processo è detto *un'esecuzione posticipata*.  
  
 Le query possono essere eseguite anche quando sono definiti, che viene considerata *l'esecuzione immediata*. È possibile attivare l'esecuzione immediata applicando un metodo che richiede l'accesso ai singoli elementi del risultato della query. Questo potrebbe risultare dall'inclusione di una funzione di aggregazione, come `Count`, `Sum`, `Average`, `Min` o `Max`. Per altre informazioni sulle funzioni di aggregazione, vedere [clausola Aggregate](../../../language-reference/queries/aggregate-clause.md).  
  
 Anche l'utilizzo dei metodi `ToList` o `ToArray` forza l'esecuzione immediata. Ciò può essere utile quando si desidera eseguire immediatamente la query e memorizzare nella cache i risultati. Per altre informazioni su questi metodi, vedere [conversione di tipi di dati](../../concepts/linq/converting-data-types.md).  
  
 Per altre informazioni sull'esecuzione di query, vedere [Writing Your prima Query LINQ](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>XML in Visual Basic  
 Le funzionalità XML in Visual Basic includono valori letterali XML e proprietà axis XML, che consentono facilmente creare, accedere, eseguire una query e modificare codice XML nel codice. I valori letterali XML consentono di scrivere l'XML direttamente nel codice. Il compilatore di Visual Basic tratta l'XML come oggetto dati di prima classe.  
  
 Nell'esempio di codice seguente viene mostrato come creare un elemento XML, accedere ai sottoelementi e agli attributi ed eseguire una query sul contenuto dell'elemento utilizzando LINQ.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Per altre informazioni, vedere [XML](../xml/index.md).  
  
## <a name="related-resources"></a>Risorse correlate  
  
|Argomento|Descrizione|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Descrive le funzionalità XML in Visual Basic che è possibile eseguire query e che consentono di includere dati XML come oggetti di dati di prima classe nel codice Visual Basic.|  
|[Query](../../../language-reference/queries/index.md)|Fornisce informazioni di riferimento sulle clausole di query disponibili in Visual Basic.|  
|[LINQ (Language-Integrated Query)](../../concepts/linq/index.md)|Sono incluse informazioni generali, indicazioni di programmazione ed esempi per LINQ.|  
|[LINQ to SQL](~/docs/framework/data/adonet/sql/linq/index.md)|Sono incluse informazioni generali, indicazioni di programmazione ed esempi per LINQ to SQL.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|Sono incluse informazioni generali, indicazioni di programmazione ed esempi per LINQ to Objects.|  
|[LINQ to ADO.NET (pagina portale)](../../concepts/linq/linq-to-adonet-portal-page.md)|Include collegamenti a informazioni generali, materiale sussidiario sulla programmazione ed esempi per LINQ to ADO.NET.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|Sono incluse informazioni generali, indicazioni di programmazione ed esempi per LINQ to XML.|  
  
## <a name="how-to-and-walkthrough-topics"></a>Come e procedure dettagliate
 [Procedura: Query su un Database](how-to-query-a-database-by-using-linq.md)  
  
 [Procedura: Chiamare una Stored Procedure](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Procedura: Modificare i dati in un Database](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Procedura: Combinare dati utilizzando join](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Procedura: Risultati della Query di ordinamento](how-to-sort-query-results-by-using-linq.md)  
  
 [Procedura: Filtrare i risultati della Query](how-to-filter-query-results-by-using-linq.md)  
  
 [Procedura: Conteggio, somma o Media di dati](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Procedura: Trovare il valore minimo o massimo in un risultato di Query](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Capitoli del libro rappresentati  
 [Capitolo 17: LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) in [programmazione Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>Vedere anche

- [LINQ (Language-Integrated Query)](../../concepts/linq/index.md)
- [Cenni preliminari su LINQ to XML in Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md)
- [Panoramica di LINQ to DataSet](~/docs/framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](~/docs/framework/data/adonet/sql/linq/index.md)
- [Strumenti LINQ to SQL in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
