---
title: 'Procedura dettagliata: Modello a oggetti e query semplici (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: c878e457-f715-46e4-a136-ff14d6c86018
ms.openlocfilehash: c6d00271f412829cb8e030c2b9a338f73327977b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54724174"
---
# <a name="walkthrough-simple-object-model-and-query-visual-basic"></a><span data-ttu-id="4bbff-102">Procedura dettagliata: Modello a oggetti e query semplici (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4bbff-102">Walkthrough: Simple Object Model and Query (Visual Basic)</span></span>
<span data-ttu-id="4bbff-103">Questa procedura dettagliata descrive uno scenario [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] end-to-end di base con complessità minime.</span><span class="sxs-lookup"><span data-stu-id="4bbff-103">This walkthrough provides a fundamental end-to-end [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] scenario with minimal complexities.</span></span> <span data-ttu-id="4bbff-104">Verranno create una classe di entità per la modellazione della tabella Customers nel database Northwind di esempio,</span><span class="sxs-lookup"><span data-stu-id="4bbff-104">You will create an entity class that models the Customers table in the sample Northwind database.</span></span> <span data-ttu-id="4bbff-105">quindi una semplice query per elencare i clienti residenti nell'area londinese.</span><span class="sxs-lookup"><span data-stu-id="4bbff-105">You will then create a simple query to list customers who are located in London.</span></span>  
  
 <span data-ttu-id="4bbff-106">Questa procedura dettagliata è basata sul codice in fase di progettazione per illustrare i concetti di [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bbff-106">This walkthrough is code-oriented by design to help show [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] concepts.</span></span> <span data-ttu-id="4bbff-107">Normalmente per creare il modello a oggetti si usa [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bbff-107">Normally speaking, you would use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] to create your object model.</span></span>  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="4bbff-108">Questa procedura dettagliata è stata scritta usando Impostazioni di sviluppo di Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="4bbff-108">This walkthrough was written by using Visual Basic Development Settings.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="4bbff-109">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="4bbff-109">Prerequisites</span></span>  
  
-   <span data-ttu-id="4bbff-110">Per i file usati nella procedura dettagliata viene usata una cartella dedicata ("c:\linqtest").</span><span class="sxs-lookup"><span data-stu-id="4bbff-110">This walkthrough uses a dedicated folder ("c:\linqtest") to hold files.</span></span> <span data-ttu-id="4bbff-111">Creare la cartella prima di avviare la procedura.</span><span class="sxs-lookup"><span data-stu-id="4bbff-111">Create this folder before you begin the walkthrough.</span></span>  
  
-   <span data-ttu-id="4bbff-112">Per questa procedura dettagliata è richiesto il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="4bbff-112">This walkthrough requires the Northwind sample database.</span></span> <span data-ttu-id="4bbff-113">Se questo database non è disponibile nel computer di sviluppo, è possibile scaricarlo dal sito di download Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4bbff-113">If you do not have this database on your development computer, you can download it from the Microsoft download site.</span></span> <span data-ttu-id="4bbff-114">Per istruzioni, vedere [download dei database di esempio](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="4bbff-114">For instructions, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span> <span data-ttu-id="4bbff-115">Dopo avere scaricato il database, copiare il file nella cartella c:\linqtest.</span><span class="sxs-lookup"><span data-stu-id="4bbff-115">After you have downloaded the database, copy the file to the c:\linqtest folder.</span></span>  
  
## <a name="overview"></a><span data-ttu-id="4bbff-116">Panoramica</span><span class="sxs-lookup"><span data-stu-id="4bbff-116">Overview</span></span>  
 <span data-ttu-id="4bbff-117">La procedura dettagliata è costituita da sei attività principali:</span><span class="sxs-lookup"><span data-stu-id="4bbff-117">This walkthrough consists of six main tasks:</span></span>  
  
-   <span data-ttu-id="4bbff-118">Creazione di un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] soluzione in Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4bbff-118">Creating a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] solution in Visual Studio.</span></span>  
  
-   <span data-ttu-id="4bbff-119">Mapping di una classe a una tabella del database.</span><span class="sxs-lookup"><span data-stu-id="4bbff-119">Mapping a class to a database table.</span></span>  
  
-   <span data-ttu-id="4bbff-120">Definizione di proprietà nella classe per rappresentare colonne del database.</span><span class="sxs-lookup"><span data-stu-id="4bbff-120">Designating properties on the class to represent database columns.</span></span>  
  
-   <span data-ttu-id="4bbff-121">Definizione della connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="4bbff-121">Specifying the connection to the Northwind database.</span></span>  
  
-   <span data-ttu-id="4bbff-122">Creazione di una semplice query da eseguire sul database.</span><span class="sxs-lookup"><span data-stu-id="4bbff-122">Creating a simple query to run against the database.</span></span>  
  
-   <span data-ttu-id="4bbff-123">Esecuzione della query e analisi dei risultati.</span><span class="sxs-lookup"><span data-stu-id="4bbff-123">Executing the query and observing the results.</span></span>  
  
## <a name="creating-a-linq-to-sql-solution"></a><span data-ttu-id="4bbff-124">Creazione di una soluzione LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4bbff-124">Creating a LINQ to SQL Solution</span></span>  
 <span data-ttu-id="4bbff-125">In questa prima attività, si crea una soluzione di Visual Studio che contiene i riferimenti necessari per compilare ed eseguire un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] progetto.</span><span class="sxs-lookup"><span data-stu-id="4bbff-125">In this first task, you create a Visual Studio solution that contains the necessary references to build and run a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] project.</span></span>  
  
#### <a name="to-create-a-linq-to-sql-solution"></a><span data-ttu-id="4bbff-126">Per creare una soluzione LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="4bbff-126">To create a LINQ to SQL solution</span></span>  
  
1.  <span data-ttu-id="4bbff-127">Scegliere **Nuovo progetto** dal menu **File**.</span><span class="sxs-lookup"><span data-stu-id="4bbff-127">On the **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="4bbff-128">Nel **tipi di progetto** riquadro della finestra di **nuovo progetto** nella finestra di dialogo fare clic su **Visual Basic**.</span><span class="sxs-lookup"><span data-stu-id="4bbff-128">In the **Project types** pane of the **New Project** dialog box, click **Visual Basic**.</span></span>  
  
3.  <span data-ttu-id="4bbff-129">Nel riquadro **Modelli** fare clic su **Applicazione console**.</span><span class="sxs-lookup"><span data-stu-id="4bbff-129">In the **Templates** pane, click **Console Application**.</span></span>  
  
4.  <span data-ttu-id="4bbff-130">Nel **Name** , digitare **LinqConsoleApp**.</span><span class="sxs-lookup"><span data-stu-id="4bbff-130">In the **Name** box, type **LinqConsoleApp**.</span></span>  
  
5.  <span data-ttu-id="4bbff-131">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4bbff-131">Click **OK**.</span></span>  
  
## <a name="adding-linq-references-and-directives"></a><span data-ttu-id="4bbff-132">Aggiunta di riferimenti e direttive LINQ</span><span class="sxs-lookup"><span data-stu-id="4bbff-132">Adding LINQ References and Directives</span></span>  
 <span data-ttu-id="4bbff-133">In questa procedura dettagliata vengono usati assembly che potrebbero non essere installati per impostazione predefinita nel progetto.</span><span class="sxs-lookup"><span data-stu-id="4bbff-133">This walkthrough uses assemblies that might not be installed by default in your project.</span></span> <span data-ttu-id="4bbff-134">Se `System.Data.Linq` non è elencato come riferimento nel progetto (fare clic su **Mostra tutti i file** nelle **Esplora soluzioni** ed espandere la **riferimenti** nodo), aggiungerlo come spiegato nella la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="4bbff-134">If `System.Data.Linq` is not listed as a reference in your project (click **Show All Files** in **Solution Explorer** and expand the **References** node), add it, as explained in the following steps.</span></span>  
  
#### <a name="to-add-systemdatalinq"></a><span data-ttu-id="4bbff-135">Per aggiungere System.Data.Linq</span><span class="sxs-lookup"><span data-stu-id="4bbff-135">To add System.Data.Linq</span></span>  
  
1.  <span data-ttu-id="4bbff-136">Nelle **Esplora soluzioni**, fare doppio clic su **riferimenti**, quindi fare clic su **Aggiungi riferimento**.</span><span class="sxs-lookup"><span data-stu-id="4bbff-136">In **Solution Explorer**, right-click **References**, and then click **Add Reference**.</span></span>  
  
2.  <span data-ttu-id="4bbff-137">Nel **Aggiungi riferimento** finestra di dialogo, fare clic su **.NET**, fare clic sull'assembly e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4bbff-137">In the **Add Reference** dialog box, click **.NET**, click the System.Data.Linq assembly, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4bbff-138">L'assembly verrà aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="4bbff-138">The assembly is added to the project.</span></span>  
  
3.  <span data-ttu-id="4bbff-139">Anche nel **Aggiungi riferimento** finestra di dialogo, fare clic su **.NET**, scorrere fino alla e fare clic su Forms e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="4bbff-139">Also in the **Add Reference** dialog box, click **.NET**, scroll to and click System.Windows.Forms, and then click **OK**.</span></span>  
  
     <span data-ttu-id="4bbff-140">Questo assembly, che supporta la finestra di messaggio nella procedura dettagliata, viene aggiunto al progetto.</span><span class="sxs-lookup"><span data-stu-id="4bbff-140">This assembly, which supports the message box in the walkthrough, is added to the project.</span></span>  
  
4.  <span data-ttu-id="4bbff-141">Aggiungere la seguente direttiva sopra a `Module1`:</span><span class="sxs-lookup"><span data-stu-id="4bbff-141">Add the following directives above `Module1`:</span></span>  
  
     [!code-vb[DLinqWalk1VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#1)]  
  
## <a name="mapping-a-class-to-a-database-table"></a><span data-ttu-id="4bbff-142">Mapping di una classe a una tabella del database</span><span class="sxs-lookup"><span data-stu-id="4bbff-142">Mapping a Class to a Database Table</span></span>  
 <span data-ttu-id="4bbff-143">In questo passaggio verrà creata una classe ed eseguito il mapping della classe a una tabella di database.</span><span class="sxs-lookup"><span data-stu-id="4bbff-143">In this step, you create a class and map it to a database table.</span></span> <span data-ttu-id="4bbff-144">Tale classe è detta un' *classe di entità*.</span><span class="sxs-lookup"><span data-stu-id="4bbff-144">Such a class is termed an *entity class*.</span></span> <span data-ttu-id="4bbff-145">Notare che il mapping viene eseguito semplicemente aggiungendo l'attributo <xref:System.Data.Linq.Mapping.TableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="4bbff-145">Note that the mapping is accomplished by just adding the <xref:System.Data.Linq.Mapping.TableAttribute> attribute.</span></span> <span data-ttu-id="4bbff-146">La proprietà <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> consente di specificare il nome della tabella nel database.</span><span class="sxs-lookup"><span data-stu-id="4bbff-146">The <xref:System.Data.Linq.Mapping.TableAttribute.Name%2A> property specifies the name of the table in the database.</span></span>  
  
#### <a name="to-create-an-entity-class-and-map-it-to-a-database-table"></a><span data-ttu-id="4bbff-147">Per creare una classe di entità ed eseguire il mapping della classe a una tabella di database</span><span class="sxs-lookup"><span data-stu-id="4bbff-147">To create an entity class and map it to a database table</span></span>  
  
-   <span data-ttu-id="4bbff-148">Digitare o incollare il codice seguente in Module1.vb immediatamente sopra `Sub Main`:</span><span class="sxs-lookup"><span data-stu-id="4bbff-148">Type or paste the following code into Module1.vb immediately above `Sub Main`:</span></span>  
  
     [!code-vb[DLinqWalk1VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#2)]  
  
## <a name="designating-properties-on-the-class-to-represent-database-columns"></a><span data-ttu-id="4bbff-149">Definizione di proprietà nella classe per rappresentare colonne del database</span><span class="sxs-lookup"><span data-stu-id="4bbff-149">Designating Properties on the Class to Represent Database Columns</span></span>  
 <span data-ttu-id="4bbff-150">In questo passaggio si completeranno diverse attività.</span><span class="sxs-lookup"><span data-stu-id="4bbff-150">In this step, you accomplish several tasks.</span></span>  
  
-   <span data-ttu-id="4bbff-151">Usare l'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute> per definire le proprietà `CustomerID` e `City` nella classe di entità in modo che rappresentino colonne nella tabella del database.</span><span class="sxs-lookup"><span data-stu-id="4bbff-151">You use the <xref:System.Data.Linq.Mapping.ColumnAttribute> attribute to designate `CustomerID` and `City` properties on the entity class as representing columns in the database table.</span></span>  
  
-   <span data-ttu-id="4bbff-152">Definire la proprietà `CustomerID` in modo che rappresenti una colonna di chiave primaria nel database.</span><span class="sxs-lookup"><span data-stu-id="4bbff-152">You designate the `CustomerID` property as representing a primary key column in the database.</span></span>  
  
-   <span data-ttu-id="4bbff-153">Definire i campi `_CustomerID` e `_City` per l'archiviazione privata.</span><span class="sxs-lookup"><span data-stu-id="4bbff-153">You designate `_CustomerID` and `_City` fields for private storage.</span></span> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4bbff-154">sarà quindi in grado di archiviare e recuperare direttamente i valori, anziché usare funzioni di accesso pubbliche che potrebbero includere la logica di business.</span><span class="sxs-lookup"><span data-stu-id="4bbff-154">can then store and retrieve values directly, instead of using public accessors that might include business logic.</span></span>  
  
#### <a name="to-represent-characteristics-of-two-database-columns"></a><span data-ttu-id="4bbff-155">Per rappresentare caratteristiche di due colonne del database</span><span class="sxs-lookup"><span data-stu-id="4bbff-155">To represent characteristics of two database columns</span></span>  
  
-   <span data-ttu-id="4bbff-156">Digitare o incollare il codice seguente in Module1.vb subito prima di `End Class`:</span><span class="sxs-lookup"><span data-stu-id="4bbff-156">Type or paste the following code into Module1.vb just before `End Class`:</span></span>  
  
     [!code-vb[DLinqWalk1VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#3)]  
  
## <a name="specifying-the-connection-to-the-northwind-database"></a><span data-ttu-id="4bbff-157">Definizione della connessione al database Northwind</span><span class="sxs-lookup"><span data-stu-id="4bbff-157">Specifying the Connection to the Northwind Database</span></span>  
 <span data-ttu-id="4bbff-158">In questo passaggio viene usato un oggetto <xref:System.Data.Linq.DataContext> per stabilire una connessione tra le strutture di dati basate sul codice e il database stesso.</span><span class="sxs-lookup"><span data-stu-id="4bbff-158">In this step you use a <xref:System.Data.Linq.DataContext> object to establish a connection between your code-based data structures and the database itself.</span></span> <span data-ttu-id="4bbff-159"><xref:System.Data.Linq.DataContext> è il canale principale tramite il quale vengono recuperati oggetti dal database e vengono inviate modifiche.</span><span class="sxs-lookup"><span data-stu-id="4bbff-159">The <xref:System.Data.Linq.DataContext> is the main channel through which you retrieve objects from the database and submit changes.</span></span>  
  
 <span data-ttu-id="4bbff-160">Viene anche dichiarato un oggetto `Table(Of Customer)` che fungerà da tabella tipizzata logica per le query sulla tabella Customers nel database.</span><span class="sxs-lookup"><span data-stu-id="4bbff-160">You also declare a `Table(Of Customer)` to act as the logical, typed table for your queries against the Customers table in the database.</span></span> <span data-ttu-id="4bbff-161">Tali query verranno quindi create ed eseguite nei passaggi successivi.</span><span class="sxs-lookup"><span data-stu-id="4bbff-161">You will create and execute these queries in later steps.</span></span>  
  
#### <a name="to-specify-the-database-connection"></a><span data-ttu-id="4bbff-162">Per specificare la connessione al database</span><span class="sxs-lookup"><span data-stu-id="4bbff-162">To specify the database connection</span></span>  
  
-   <span data-ttu-id="4bbff-163">Digitare o incollare il codice seguente nel metodo `Sub Main`:</span><span class="sxs-lookup"><span data-stu-id="4bbff-163">Type or paste the following code into the `Sub Main` method.</span></span>  
  
     <span data-ttu-id="4bbff-164">Si presuppone che il file `northwnd.mdf` si trovi nella cartella linqtest.</span><span class="sxs-lookup"><span data-stu-id="4bbff-164">Note that the `northwnd.mdf` file is assumed to be in the linqtest folder.</span></span> <span data-ttu-id="4bbff-165">Per altre informazioni, vedere la sezione precedente relativa ai prerequisiti.</span><span class="sxs-lookup"><span data-stu-id="4bbff-165">For more information, see the Prerequisites section earlier in this walkthrough.</span></span>  
  
     [!code-vb[DLinqWalk1VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1VB/vb/Module1.vb#4)]  
  
## <a name="creating-a-simple-query"></a><span data-ttu-id="4bbff-166">Creazione di una query semplice</span><span class="sxs-lookup"><span data-stu-id="4bbff-166">Creating a Simple Query</span></span>  
 <span data-ttu-id="4bbff-167">In questo passaggio viene creata una query per cercare i clienti nella tabella di database Customers residenti nell'area londinese.</span><span class="sxs-lookup"><span data-stu-id="4bbff-167">In this step, you create a query to find which customers in the database Customers table are located in London.</span></span> <span data-ttu-id="4bbff-168">Il codice della query in questo passaggio descrive semplicemente la query,</span><span class="sxs-lookup"><span data-stu-id="4bbff-168">The query code in this step just describes the query.</span></span> <span data-ttu-id="4bbff-169">ma non la esegue.</span><span class="sxs-lookup"><span data-stu-id="4bbff-169">It does not execute it.</span></span> <span data-ttu-id="4bbff-170">Questo approccio è noto come *un'esecuzione posticipata*.</span><span class="sxs-lookup"><span data-stu-id="4bbff-170">This approach is known as *deferred execution*.</span></span> <span data-ttu-id="4bbff-171">Per altre informazioni, vedere [Introduzione alle query LINQ (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4bbff-171">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 <span data-ttu-id="4bbff-172">Verrà anche prodotto un output del log per mostrare i comandi SQL generati da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4bbff-172">You will also produce a log output to show the SQL commands that [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] generates.</span></span> <span data-ttu-id="4bbff-173">Questa funzionalità di registrazione, che usa <xref:System.Data.Linq.DataContext.Log%2A>, è utile per eseguire il debug e per determinare che i comandi inviati al database rappresentano accuratamente la query.</span><span class="sxs-lookup"><span data-stu-id="4bbff-173">This logging feature (which uses <xref:System.Data.Linq.DataContext.Log%2A>) is helpful in debugging, and in determining that the commands being sent to the database accurately represent your query.</span></span>  
  
#### <a name="to-create-a-simple-query"></a><span data-ttu-id="4bbff-174">Per creare una query semplice</span><span class="sxs-lookup"><span data-stu-id="4bbff-174">To create a simple query</span></span>  
  
-   <span data-ttu-id="4bbff-175">Digitare o incollare il codice seguente nel metodo `Sub Main` dopo la dichiarazione `Table(Of Customer)`:</span><span class="sxs-lookup"><span data-stu-id="4bbff-175">Type or paste the following code into the `Sub Main` method after the `Table(Of Customer)` declaration:</span></span>  
  
     [!code-vb[DLinqWalk1AVB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#5)]  
  
## <a name="executing-the-query"></a><span data-ttu-id="4bbff-176">Esecuzione della query</span><span class="sxs-lookup"><span data-stu-id="4bbff-176">Executing the Query</span></span>  
 <span data-ttu-id="4bbff-177">In questo passaggio verrà effettivamente eseguita la query.</span><span class="sxs-lookup"><span data-stu-id="4bbff-177">In this step, you actually execute the query.</span></span> <span data-ttu-id="4bbff-178">Le espressioni di query create nei passaggi precedenti non vengono valutate finché i risultati non saranno necessari.</span><span class="sxs-lookup"><span data-stu-id="4bbff-178">The query expressions you created in the previous steps are not evaluated until the results are needed.</span></span> <span data-ttu-id="4bbff-179">Quando si inizia l'iterazione `For Each`, viene eseguito un comando SQL sul database e gli oggetti vengono materializzati.</span><span class="sxs-lookup"><span data-stu-id="4bbff-179">When you begin the `For Each` iteration, a SQL command is executed against the database and objects are materialized.</span></span>  
  
#### <a name="to-execute-the-query"></a><span data-ttu-id="4bbff-180">Per eseguire la query</span><span class="sxs-lookup"><span data-stu-id="4bbff-180">To execute the query</span></span>  
  
1.  <span data-ttu-id="4bbff-181">Digitare o incollare il codice seguente alla fine del metodo `Sub Main` dopo la descrizione della query:</span><span class="sxs-lookup"><span data-stu-id="4bbff-181">Type or paste the following code at the end of the `Sub Main` method (after the query description):</span></span>  
  
     [!code-vb[DLinqWalk1AVB#6](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk1AVB/vb/Module1.vb#6)]  
  
2.  <span data-ttu-id="4bbff-182">‎Premere F5 per eseguire il debug dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4bbff-182">Press F5 to debug the application.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="4bbff-183">Se l'applicazione genera un errore di run-time, vedere la sezione Risoluzione dei problemi dei [apprendimento tramite procedure dettagliate](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span><span class="sxs-lookup"><span data-stu-id="4bbff-183">If your application generates a run-time error, see the Troubleshooting section of [Learning by Walkthroughs](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md).</span></span>  
  
     <span data-ttu-id="4bbff-184">Nella finestra di messaggio viene visualizzato un elenco di sei clienti.</span><span class="sxs-lookup"><span data-stu-id="4bbff-184">The message box displays a list of six customers.</span></span> <span data-ttu-id="4bbff-185">Nella finestra della console verrà visualizzato il codice SQL generato.</span><span class="sxs-lookup"><span data-stu-id="4bbff-185">The Console window displays the generated SQL code.</span></span>  
  
3.  <span data-ttu-id="4bbff-186">Fare clic su **OK** per chiudere la finestra del messaggio.</span><span class="sxs-lookup"><span data-stu-id="4bbff-186">Click **OK** to dismiss the message box.</span></span>  
  
     <span data-ttu-id="4bbff-187">L'applicazione verrà chiusa.</span><span class="sxs-lookup"><span data-stu-id="4bbff-187">The application closes.</span></span>  
  
4.  <span data-ttu-id="4bbff-188">Nel menu **File** fare clic su **Salva tutto**.</span><span class="sxs-lookup"><span data-stu-id="4bbff-188">On the **File** menu, click **Save All**.</span></span>  
  
     <span data-ttu-id="4bbff-189">Questa applicazione sarà necessaria se si continua con la successiva procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="4bbff-189">You will need this application if you continue with the next walkthrough.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4bbff-190">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="4bbff-190">Next Steps</span></span>  
 <span data-ttu-id="4bbff-191">Il [procedura dettagliata: Esecuzione di query tra relazioni (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md) argomento continua in cui termina questa procedura dettagliata.</span><span class="sxs-lookup"><span data-stu-id="4bbff-191">The [Walkthrough: Querying Across Relationships (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-querying-across-relationships-visual-basic.md) topic continues where this walkthrough ends.</span></span> <span data-ttu-id="4bbff-192">La procedura dettagliata l'esecuzione di query tra relazioni illustra la modalità [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] eseguire query tra tabelle, simile a *join* in un database relazionale.</span><span class="sxs-lookup"><span data-stu-id="4bbff-192">The Querying Across Relationships walkthrough demonstrates how [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] can query across tables, similar to *joins* in a relational database.</span></span>  
  
 <span data-ttu-id="4bbff-193">Se si desidera eseguire la procedura dettagliata relativa all'esecuzione di query tra relazioni, è indispensabile salvare la soluzione per la procedura dettagliata appena completata.</span><span class="sxs-lookup"><span data-stu-id="4bbff-193">If you want to do the Querying Across Relationships walkthrough, make sure to save the solution for the walkthrough you have just completed, which is a prerequisite.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bbff-194">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4bbff-194">See also</span></span>
- [<span data-ttu-id="4bbff-195">Apprendimento tramite procedure dettagliate</span><span class="sxs-lookup"><span data-stu-id="4bbff-195">Learning by Walkthroughs</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
