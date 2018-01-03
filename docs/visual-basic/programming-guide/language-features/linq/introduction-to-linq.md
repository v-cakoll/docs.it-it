---
title: Introduzione a LINQ in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0bb55aecc1faafd812da212565a7a858c714e933
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/21/2017
---
# <a name="introduction-to-linq-in-visual-basic"></a>Introduzione a LINQ in Visual Basic
Language-Integrated Query (LINQ) aggiunge funzionalità di query a [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] e fornisce semplici e potenti funzionalità da utilizzare con qualsiasi tipo di dati. Anziché inviare una query a un database da elaborare, o utilizzare sintassi di query differenti per ogni tipo di dati da ricercare, LINQ introduce le query come parti del linguaggio [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Utilizza una sintassi unificata indipendentemente dal tipo di dati.  
  
 LINQ consente di eseguire query sui dati da un database di SQL Server, XML, le matrici in memoria e le raccolte, [!INCLUDE[vstecado](~/includes/vstecado-md.md)] set di dati, o qualsiasi altra locali o remoti origine dati che supporta LINQ. È possibile fare tutto per questo con i comuni elementi del linguaggio [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Poiché le query sono scritte nel linguaggio [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], i risultati della query vengono restituiti come oggetti fortemente tipizzati. Questi oggetti supportano IntelliSense, che consente di scrivere il codice più velocemente e di individuare errori nelle query in fase di compilazione anziché in fase di esecuzione. Le query LINQ possono essere utilizzate come origine di query aggiuntive per perfezionare i risultati. Possono anche venire associate a controlli in modo che gli utenti possano facilmente visualizzare e modificare i risultati della query.  
  
 Nell'esempio di codice seguente viene illustrata una query LINQ che restituisce un elenco di clienti da una raccolta e li raggruppa in base alla località.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_1.vb)]  
  
 In questo argomento vengono fornite informazioni sulle aree seguenti:  
  
-   [Esecuzione degli esempi](#RunningtheExamples)  
  
-   [Provider LINQ](#LINQProviders)  
  
-   [Struttura di una Query LINQ](#StructureOfALINQQuery)  
  
-   [Operatori di Query LINQ di Visual Basic](#VisualBasicLINQQueryOperators)  
  
-   [Connessione a un Database utilizzando LINQ to SQL](#ConnectingToADatabase)  
  
-   [Funzionalità di Visual Basic che supportano LINQ](#VisualBasicFeaturesThatSupportLINQ)  
  
-   [Esecuzione di Query posticipata e immediata](#QueryExecution)  
  
-   [XML in Visual Basic](#XMLInVisualBasic)  
  
-   [Risorse correlate](#RelatedResources)  
  
-   [Come e procedure dettagliate](#HowToAndWalkthroughTopics)  
  
##  <a name="RunningtheExamples"></a>Esecuzione degli esempi  
 Per eseguire gli esempi nell'introduzione e nella sezione "Struttura di una query LINQ", includere il seguente codice, che restituisce elenchi di clienti e ordini.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_2.vb)]  
  
##  <a name="LINQProviders"></a>Provider LINQ  
 Oggetto *provider LINQ* esegue il mapping del [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] query LINQ per l'origine dati sottoposte a query. Quando si scrive una query LINQ, il provider prende tale query e la traduce in comandi che l'origine dati sarà in grado di eseguire. Il provider converte anche i dati dall'origine negli oggetti che costituiscono il risultato della query. Infine, converte gli oggetti in dati quando si inviano aggiornamenti all'origine dati.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] include i seguenti provider LINQ.  
  
|Provider|Descrizione|  
|---|---|  
|LINQ to Objects|Il provider LINQ to Objects consente di eseguire una query su raccolte e matrici in memoria. Se un oggetto supporta l'interfaccia <xref:System.Collections.IEnumerable> o <xref:System.Collections.Generic.IEnumerable%601>, il provider LINQ to Objects consente di eseguire una query su di esso.<br /><br /> È possibile attivare il provider LINQ to Objects importando lo spazio dei nomi <xref:System.Linq>, che viene importato per impostazione predefinita per tutti i progetti [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].<br /><br /> Per ulteriori informazioni il provider LINQ to Objects, vedere [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9).|  
|LINQ to SQL|Il provider LINQ to SQL consente di eseguire query e di modificare i dati su un database SQL server. Questo semplifica il mapping del modello a oggetti per un'applicazione alle tabelle e agli oggetti in un database.<br /><br /> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] semplifica l'utilizzo di LINQ to SQL includendo Object Relational Designer (O/R Designer). Questa finestra di progettazione viene utilizzata per creare un modello a oggetti in un'applicazione con mapping sugli oggetti in un database. O/R Designer fornisce funzionalità per eseguire il mapping di stored procedure e funzioni ai anche il <xref:System.Data.Linq.DataContext> oggetto, che gestisce la comunicazione con il database e archivia lo stato per i controlli di concorrenza ottimistica.<br /><br /> Per ulteriori informazioni il provider LINQ to SQL, vedere [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). Per ulteriori informazioni su Progettazione relazionale oggetti, vedere [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Il provider LINQ to XML consente di eseguire query e di modificare l'XML. È possibile modificare l'XML in memoria o caricare l'XML da file o salvare l'XML in un file.<br /><br /> Inoltre, il provider LINQ to XML abilita i valori letterali XML e le proprietà asse XML che consentono di scrivere direttamente l'XML nel codice [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]. Per ulteriori informazioni, vedere [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|Il provider LINQ to DataSet consente di eseguire query e aggiornare dati in un [!INCLUDE[vstecado](~/includes/vstecado-md.md)] set di dati. È possibile aggiungere le caratteristiche avanzate di LINQ ad applicazioni che utilizzano set di dati per semplificare ed estendere le funzionalità per l'esecuzione di query, l'aggregazione e l'aggiornamento dei dati nel set di dati.<br /><br /> Per altre informazioni, vedere [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
##  <a name="StructureOfALINQQuery"></a>Struttura di una Query LINQ  
 Una query LINQ, noto anche come un *espressione di query*, costituito da una combinazione di clausole di query che identificano le origini dati e le variabili di iterazione per la query. Un'espressione di query può includere anche istruzioni per ordinare, filtrare, raggruppare e unire o eseguire calcoli da applicare ai dati di origine. La sintassi delle espressioni di query è simile alla sintassi SQL; pertanto, gran parte della sintassi risulterà familiare.  
  
 Un'espressione di query inizia con una clausola `From`. Questa clausola identifica i dati di origine per una query e le variabili utilizzate per fare riferimento a ogni singolo elemento dell'insieme di origine. Queste variabili sono denominate *le variabili di intervallo* o *le variabili di iterazione*. La clausola `From` è obbligatoria per una query, tranne per le query `Aggregate`, in cui la clausola `From` è facoltativa. Dopo che l'ambito e l'origine della query sono identificati nelle clausole `From` o `Aggregate`, è possibile includere qualsiasi combinazione di clausole di query per perfezionare la query. Per dettagli sulle clausole di query, vedere Operatori di query LINQ di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] più avanti in questo argomento. Ad esempio, nella query seguente viene identificata una raccolta di origine di dati sul cliente come variabile `customers` e una variabile di iterazione denominata `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_3.vb)]  
  
 In questo esempio viene illustrata una query valida; tuttavia, la query diventa molto più efficace quando si aggiungono altre clausole di query per perfezionare il risultato. Ad esempio, è possibile aggiungere una clausola `Where` per filtrare il risultato per uno o più valori. Le espressioni di query consistono in una sola riga di codice; è possibile inserire clausole aggiuntive solo alla fine della query. È possibile suddividere una query su più righe del testo per migliorarne la leggibilità utilizzando il carattere di continuazione della riga: il segno di sottolineatura (_). Nell'esempio di codice seguente viene illustrato un esempio di query che include una clausola `Where`.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_4.vb)]  
  
 Un'altra efficace clausola di query è `Select`, che consente di restituire dall'origine dati solo i campi selezionati. Le query LINQ restituiscono raccolte enumerabili di oggetti fortemente tipizzati. Una query può restituire una raccolta di tipi anonimi o tipi denominati. È possibile utilizzare la clausola `Select` per restituire solo un unico campo dall'origine dati. Quando si esegue questa operazione, il tipo dell'insieme restituito è il tipo di quell'unico campo. È possibile utilizzare anche la clausola `Select` per restituire più campi dall'origine dati. In questo caso, il tipo della raccolta restituita è un nuovo tipo anonimo. È anche possibile far corrispondere i campi restituiti dalla query ai campi di un tipo denominato specificato. Nell'esempio di codice seguente viene illustrata un'espressione di query che restituisce una raccolta di tipi anonimi che hanno membri popolati con dati dai campi selezionati dell'origine dati.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_5.vb)]  
  
 Le query LINQ possono essere utilizzate anche per combinare più origini di dati e restituire un unico risultato. Questa operazione può essere eseguita con una o più clausole `From` oppure utilizzando le clausole di query `Join` o `Group Join`. Nell'esempio di codice seguente viene illustrata un'espressione di query che combina dati del cliente e dell'ordine e restituisce una raccolta di tipi anonimi che contengono dati del cliente e dell'ordine.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_6.vb)]  
  
 È possibile utilizzare la clausola `Group Join` per creare un risultato della query gerarchico che contiene una raccolta di oggetti Customer. Ogni oggetto Customer ha una proprietà che contiene una raccolta di tutti gli ordini per quel cliente. Nell'esempio di codice seguente viene illustrata un'espressione di query che combina dati del cliente e dell'ordine in un risultato gerarchico e restituisce una raccolta di tipi anonimi. La query restituisce un tipo che include una proprietà `CustomerOrders` che contiene una raccolta di dati dell'ordine per tale cliente. Include anche una proprietà `OrderTotal` che contiene la somma dei totali per tutti gli ordini per quel cliente. (Questa query è equivalente a una query LEFT OUTER JOIN).  
  
 [!code-vb[VbVbalrIntroToLINQ#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_7.vb)]  
  
 Esistono molti altri operatori di query LINQ che è possibile utilizzare per creare efficaci espressioni di query. Nella prossima sezione di questo argomento vengono discusse le varie clausole di query che è possibile includere in un'espressione di query. Per informazioni dettagliate su [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] clausole di query, vedere [query](../../../../visual-basic/language-reference/queries/queries.md).  
  
##  <a name="VisualBasicLINQQueryOperators"></a>Operatori di Query LINQ di Visual Basic  
 Le classi nello spazio dei nomi <xref:System.Linq> e negli altri spazi dei nomi che supportano query LINQ includono metodi che è possibile chiamare per creare e perfezionare query basate sulle esigenze dell'applicazione. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] include parole chiave per le clausole di query più comuni, come illustrato nella tabella seguente.  
  
|Termine|Definizione|  
|---|---|  
|[Clausola From](../../../../visual-basic/language-reference/queries/from-clause.md)|Per iniziare una query è obbligatoria una clausola `From` o una clausola `Aggregate`. Una clausola `From` specifica una raccolta di origine e una variabile di iterazione per una query. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#7](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_8.vb)]|  
|[Clausola Select](../../../../visual-basic/language-reference/queries/select-clause.md)|Facoltativo. Dichiara un insieme di variabili di iterazione per una query. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#8](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_9.vb)]<br /><br /> Se non viene specificata nessuna clausola `Select`, le variabili di iterazione per la query consistono nelle variabili di iterazione specificate dalla clausola `From` o `Aggregate`.|  
|[Clausola Where](../../../../visual-basic/language-reference/queries/where-clause.md)|Facoltativo. Specifica una condizione di filtro per una query. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#9](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_10.vb)]|  
|[Clausola Order By](../../../../visual-basic/language-reference/queries/order-by-clause.md)|Facoltativo. Specifica l'ordinamento per le colonne in una query. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#10](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_11.vb)]|  
|[Clausola Join](../../../../visual-basic/language-reference/queries/join-clause.md)|Facoltativo. Combina due raccolte in un'unica raccolta. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_12.vb)]|  
|[Clausola Group By](../../../../visual-basic/language-reference/queries/group-by-clause.md)|Facoltativo. Raggruppa gli elementi di un risultato della query. Può essere utilizzata per applicare funzioni di aggregazione a ogni gruppo. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_13.vb)]|  
|[Clausola Group Join](../../../../visual-basic/language-reference/queries/group-join-clause.md)|Facoltativo. Combina due raccolte in un'unica raccolta gerarchica. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#13](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_14.vb)]|  
|[Clausola Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md)|Per iniziare una query è obbligatoria una clausola `From` o una clausola `Aggregate`. Una clausola `Aggregate` applica una o più funzioni di aggregazione a una raccolta. Ad esempio, è possibile utilizzare la clausola `Aggregate` per calcolare una somma di tutti gli elementi restituiti da una query.<br /><br /> [!code-vb[VbVbalrIntroToLINQ#14](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_15.vb)]<br /><br /> È anche possibile utilizzare la clausola `Aggregate` per modificare una query. Ad esempio, è possibile utilizzare la clausola `Aggregate` per eseguire un calcolo su una raccolta di query correlata.<br /><br /> [!code-vb[VbVbalrIntroToLINQ#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_16.vb)]|  
|[Clausola Let](../../../../visual-basic/language-reference/queries/let-clause.md)|Facoltativo. Calcola un valore e lo assegna a una nuova variabile nella query. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_17.vb)]|  
|[Clausola Distinct](../../../../visual-basic/language-reference/queries/distinct-clause.md)|Facoltativo. Limita i valori della variabile di iterazione corrente per eliminare i valori duplicati nei risultati della query. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#17](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_18.vb)]|  
|[Clausola Skip](../../../../visual-basic/language-reference/queries/skip-clause.md)|Facoltativo. Ignora un numero specificato di elementi in una raccolta e quindi restituisce gli elementi rimanenti. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#18](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_19.vb)]|  
|[Clausola Skip While](../../../../visual-basic/language-reference/queries/skip-while-clause.md)|Facoltativo. Ignora gli elementi in una raccolta finché una condizione specificata è `true` e quindi restituisce gli elementi rimanenti. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#19](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_20.vb)]|  
|[Clausola Take](../../../../visual-basic/language-reference/queries/take-clause.md)|Facoltativo. Restituisce un numero specificato di elementi contigui dall'inizio di una raccolta. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#20](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_21.vb)]|  
|[Clausola Take While](../../../../visual-basic/language-reference/queries/take-while-clause.md)|Facoltativo. Include gli elementi in una raccolta finché una condizione specificata è `true` e quindi ignora gli elementi rimanenti. Ad esempio:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#21](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_22.vb)]|  
  
 Per informazioni dettagliate su [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] clausole di query, vedere [query](../../../../visual-basic/language-reference/queries/queries.md).  
  
 È possibile utilizzare le funzionalità aggiuntive delle query LINQ chiamando i membri dei tipi enumerabili e disponibili per query forniti da LINQ. È possibile utilizzare queste funzionalità aggiuntive chiamando un particolare operatore di query sul risultato di un'espressione di query. Nell'esempio di codice seguente viene utilizzato il metodo <xref:System.Linq.Enumerable.Union%2A> per combinare i risultati di due query in un unico risultato. Viene utilizzato il metodo <xref:System.Linq.Enumerable.ToList%2A> per restituire il risultato della query come elenco generico.  
  
 [!code-vb[VbVbalrIntroToLINQ#22](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_23.vb)]  
  
 Per informazioni dettagliate sulle funzionalità LINQ aggiuntive, vedere [Cenni preliminari sugli operatori di Query Standard](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
##  <a name="ConnectingToADatabase"></a>Connessione a un Database utilizzando LINQ to SQL  
 In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] si identificano gli oggetti del database SQL Server, ad esempio tabelle, visualizzazioni e stored procedure, a cui si desidera accedere utilizzando un file LINQ to SQL. Un file LINQ to SQL ha un'estensione .dbml.  
  
 Quando si dispone di una connessione valida a un database di SQL Server, è possibile aggiungere un **classi LINQ to SQL** modello di elemento al progetto. Verrà visualizzato Object Relational Designer (O/R Designer). O/R Designer consente di trascinare gli elementi che si desidera accedere nel codice dal **Esplora Server**/**Esplora Database** nell'area di progettazione. Il file LINQ to SQL aggiunge un oggetto <xref:System.Data.Linq.DataContext> al progetto. Questo oggetto include proprietà e raccolte per tabelle e visualizzazioni alle quali si desidera accedere e metodi per le stored procedure che si desidera chiamare. Dopo avere salvato le modifiche nel file LINQ to SQL (.dbml), è possibile accedere a questi oggetti nel codice facendo riferimento all'oggetto <xref:System.Data.Linq.DataContext> che viene definito da O/R Designer. L'oggetto <xref:System.Data.Linq.DataContext> per il progetto viene denominato in base al nome del file LINQ to SQL. Ad esempio, un file LINQ to SQL denominato Northwind.dbml creerà un oggetto <xref:System.Data.Linq.DataContext> chiamato `NorthwindDataContext`.  
  
 Per esempi con istruzioni dettagliate, vedere [come: Query a un Database](../../../../visual-basic/programming-guide/language-features/linq/how-to-query-a-database-by-using-linq.md) e [procedura: chiamare una Stored Procedure](../../../../visual-basic/programming-guide/language-features/linq/how-to-call-a-stored-procedure-by-using-linq.md).  
  
##  <a name="VisualBasicFeaturesThatSupportLINQ"></a>Funzionalità di Visual Basic che supportano LINQ  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] include altre importanti funzionalità che rendono l'utilizzo di LINQ semplice e riducono la quantità di codice da scrivere per eseguire query LINQ, tra cui:  
  
-   **Tipi anonimi**, che consentono di creare un nuovo tipo basato su un risultato della query.  
  
-   **Variabili tipizzate in modo implicito**, che consente di rinviare la specifica di un tipo e permettere al compilatore di dedurre il tipo in base al risultato della query.  
  
-   **Metodi di estensione**, che consentono di estendere un tipo esistente con metodi senza modificare il tipo stesso.  
  
 Per informazioni dettagliate, vedere [funzionalità che il supporto LINQ di Visual Basic](../../../../visual-basic/programming-guide/concepts/linq/features-that-support-linq.md).  
  
##  <a name="QueryExecution"></a>Esecuzione di Query posticipata e immediata  
 L'esecuzione della query è distinta dalla creazione della query. Dopo che una query viene creata, l'esecuzione viene attivata da un meccanismo separato. Una query può essere eseguita non appena viene definito (*l'esecuzione immediata*), o può essere archiviata la definizione e la query può essere eseguita in un secondo momento (*esecuzione posticipata*).  
  
 Per impostazione predefinita, quando si crea una query, la query stessa non viene eseguita immediatamente. Al contrario, la definizione della query viene archiviata nella variabile utilizzata per fare riferimento al risultato della query. Quando si accede in un secondo momento alla variabile del risultato della query nel codice, ad esempio in un ciclo `For…Next`, la query viene eseguita. Questo processo è detto *esecuzione posticipata*.  
  
 Le query possono inoltre essere eseguite quando vengono definite, che è considerato *l'esecuzione immediata*. È possibile attivare l'esecuzione immediata applicando un metodo che richiede l'accesso ai singoli elementi del risultato della query. Questo potrebbe risultare dall'inclusione di una funzione di aggregazione, come `Count`, `Sum`, `Average`, `Min` o `Max`. Per ulteriori informazioni sulle funzioni di aggregazione, vedere [clausola Aggregate](../../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Anche l'utilizzo dei metodi `ToList` o `ToArray` forza l'esecuzione immediata. Ciò può essere utile quando si desidera eseguire immediatamente la query e memorizzare nella cache i risultati. Per ulteriori informazioni su questi metodi, vedere [la conversione di tipi di dati](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
 Per ulteriori informazioni sull'esecuzione di query, vedere [scrittura nella prima Query LINQ](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
##  <a name="XMLInVisualBasic"></a>XML in Visual Basic  
 Le funzionalità XML di [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] includono i valori letterali XML e le proprietà asse XML che semplificano la creazione, l'accesso, l'esecuzione di query e la modifica di XML nel codice. I valori letterali XML consentono di scrivere l'XML direttamente nel codice. Il compilatore di Visual Basic tratta l'XML come oggetto dati di prima classe.  
  
 Nell'esempio di codice seguente viene mostrato come creare un elemento XML, accedere ai sottoelementi e agli attributi ed eseguire una query sul contenuto dell'elemento utilizzando LINQ.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/introduction-to-linq_24.vb)]  
  
 Per ulteriori informazioni, vedere [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).  
  
##  <a name="RelatedResources"></a>Risorse correlate  
  
|Argomento|Descrizione|  
|---|---|  
|[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)|Vengono descritte le funzionalità XML in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] sulle quali è possibile eseguire una query e che consentono di includere l'XML come oggetto dati di prima classe nel codice [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].|  
|[Query](../../../../visual-basic/language-reference/queries/queries.md)|Vengono fornite informazioni di riferimento sulle clausole query disponibili in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].|  
|[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)|Sono incluse informazioni generali, materiale sussidiario sulla programmazione ed esempi per LINQ.|  
|[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)|Sono incluse informazioni generali, materiale sussidiario sulla programmazione ed esempi per LINQ to SQL.|  
|[LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)|Sono incluse informazioni generali, materiale sussidiario sulla programmazione ed esempi per LINQ to Objects.|  
|[LINQ to ADO.NET (pagina portale)](http://msdn.microsoft.com/library/dd7d3c6a-ff98-47e9-a1a7-2d4cfc42d150)|Sono inclusi collegamenti a informazioni generali, indicazioni di programmazione ed esempi per LINQ to [!INCLUDE[vstecado](~/includes/vstecado-md.md)].|  
|[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)|Sono incluse informazioni generali, indicazioni di programmazione ed esempi per LINQ to XML.|  
  
##  <a name="HowToAndWalkthroughTopics"></a>Come e procedure dettagliate  
 [Procedura: Eseguire query in un database](how-to-query-a-database-by-using-linq.md)  
  
 [Procedura: Chiamare una stored procedure](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Procedura: Modificare dati in un database](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Procedura: Combinare dati utilizzando join](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Procedura: Ordinare i risultati di query](how-to-sort-query-results-by-using-linq.md)  
  
 [Procedura: Filtrare i risultati di una query](how-to-filter-query-results-by-using-linq.md)  
  
 [Procedura: Conteggio, somma o media di dati](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Procedura: Trovare il valore minimo o massimo in un risultato di query](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Procedura: assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)  
  
## <a name="featured-book-chapters"></a>Capitoli del libro rappresentati  
 [Capitolo 17: LINQ](http://go.microsoft.com/fwlink/?LinkId=195277) in [Programming Visual Basic 2008](http://go.microsoft.com/fwlink/?LinkId=195383)  
  
## <a name="see-also"></a>Vedere anche  
 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [Cenni preliminari su LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 [Panoramica di LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset-overview.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [Strumenti LINQ to SQL in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)  
 [Metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
