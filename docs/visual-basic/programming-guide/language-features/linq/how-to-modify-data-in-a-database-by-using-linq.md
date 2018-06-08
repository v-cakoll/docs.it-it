---
title: 'Procedura: modificare dati in un database utilizzando LINQ (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- inserting rows [LINQ to SQL]
- deleting rows [LINQ to SQL]
- updating rows [LINQ to SQL]
- inserting data [Visual Basic]
- deleting data
- data [Visual Basic], updating
- updating data [LINQ]
- queries [LINQ in Visual Basic], data changes in database
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: cf52635f-0c1b-46c3-aff1-bdf181cf19b1
ms.openlocfilehash: 617bb62f9009c507658b5d1262657cb4dfa860e9
ms.sourcegitcommit: d955cb4c681d68cf301d410925d83f25172ece86
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2018
ms.locfileid: "34827111"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="81f35-102">Procedura: modificare dati in un database utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="81f35-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="81f35-103">Language-Integrated Query (LINQ) in query rendono più semplice accedere alle informazioni di database e modificare i valori presenti nel database.</span><span class="sxs-lookup"><span data-stu-id="81f35-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>  
  
 <span data-ttu-id="81f35-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che recupera e aggiorna le informazioni in un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="81f35-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>  
  
 <span data-ttu-id="81f35-105">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="81f35-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="81f35-106">Se non è il database nel computer di sviluppo, è possibile scaricare da Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="81f35-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="81f35-107">Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="81f35-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="81f35-108">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="81f35-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="81f35-109">In Visual Studio, aprire **Esplora Server**/**Esplora Database** facendo il **vista** menu e quindi selezionare **Esplora Server** / **Esplora database**.</span><span class="sxs-lookup"><span data-stu-id="81f35-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>  
  
2.  <span data-ttu-id="81f35-110">Fare doppio clic su **connessioni dati** in **Esplora Server**/**Esplora Database**, fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="81f35-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="81f35-111">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="81f35-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="81f35-112">Per aggiungere un progetto con una LINQ file SQL</span><span class="sxs-lookup"><span data-stu-id="81f35-112">To add a Project with a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="81f35-113">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="81f35-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="81f35-114">Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="81f35-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="81f35-115">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="81f35-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="81f35-116">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="81f35-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="81f35-117">Denominare il file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="81f35-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="81f35-118">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="81f35-118">Click **Add**.</span></span> <span data-ttu-id="81f35-119">Viene aperto il Object Relational Designer (O/R Designer) per il `northwind.dbml` file.</span><span class="sxs-lookup"><span data-stu-id="81f35-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="81f35-120">Per aggiungere tabelle per eseguire query e modificare nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="81f35-120">To add tables to query and modify to the designer</span></span>  
  
1.  <span data-ttu-id="81f35-121">In **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="81f35-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="81f35-122">Espandere il **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="81f35-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="81f35-123">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic su di `northwind.dbml` file aggiunto in precedenza.</span><span class="sxs-lookup"><span data-stu-id="81f35-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="81f35-124">Fare clic sulla tabella di clienti e trascinarlo nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="81f35-124">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="81f35-125">La finestra di progettazione crea un nuovo oggetto Customer per il progetto.</span><span class="sxs-lookup"><span data-stu-id="81f35-125">The designer creates a new Customer object for your project.</span></span>  
  
3.  <span data-ttu-id="81f35-126">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="81f35-126">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="81f35-127">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="81f35-127">Save your project.</span></span>  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="81f35-128">Per aggiungere il codice per modificare il database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="81f35-128">To add code to modify the database and display the results</span></span>  
  
1.  <span data-ttu-id="81f35-129">Dal **della casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo Windows Form predefinito per il progetto, Form1.</span><span class="sxs-lookup"><span data-stu-id="81f35-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="81f35-130">Quando si aggiungono tabelle alla finestra di Progettazione relazionale, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetto al progetto.</span><span class="sxs-lookup"><span data-stu-id="81f35-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="81f35-131">Questo oggetto contiene codice che è possibile utilizzare per accedere alla tabella Customers.</span><span class="sxs-lookup"><span data-stu-id="81f35-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="81f35-132">Contiene anche il codice che definisce un oggetto Customer locale e una raccolta di clienti per la tabella.</span><span class="sxs-lookup"><span data-stu-id="81f35-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="81f35-133">Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml.</span><span class="sxs-lookup"><span data-stu-id="81f35-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="81f35-134">Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="81f35-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="81f35-135">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> dell'oggetto nel codice e query e modificare la raccolta di clienti specificata da O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="81f35-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="81f35-136">Le modifiche apportate alla raccolta di clienti non vengono riflesse nel database fino a quando non vengono inviate tramite la chiamata di <xref:System.Data.Linq.DataContext.SubmitChanges%2A> metodo il <xref:System.Data.Linq.DataContext> oggetto.</span><span class="sxs-lookup"><span data-stu-id="81f35-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>  
  
     <span data-ttu-id="81f35-137">Fare doppio clic su Windows Form, Form1 per aggiungere il codice per il <xref:System.Windows.Forms.Form.Load> evento per eseguire query nella tabella Customers è che viene esposto come una proprietà del <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="81f35-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="81f35-138">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="81f35-138">Add the following code:</span></span>  
  
    ```vb  
    Private db As northwindDataContext  
  
    Private Sub Form1_Load(ByVal sender As System.Object,   
                           ByVal e As System.EventArgs  
                          ) Handles MyBase.Load  
      db = New northwindDataContext()  
  
      RefreshData()  
    End Sub  
  
    Private Sub RefreshData()  
      Dim customers = From cust In db.Customers   
                      Where cust.City(0) = "W"   
                      Select cust  
  
      DataGridView1.DataSource = customers  
    End Sub  
    ```  
  
3.  <span data-ttu-id="81f35-139">Dal **della casella degli strumenti**, trascinare i tre <xref:System.Windows.Forms.Button> controlli nel form.</span><span class="sxs-lookup"><span data-stu-id="81f35-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="81f35-140">Selezionare il primo `Button` controllo.</span><span class="sxs-lookup"><span data-stu-id="81f35-140">Select the first `Button` control.</span></span> <span data-ttu-id="81f35-141">Nel **proprietà** finestra, impostare il `Name` del `Button` il controllo a `AddButton` e `Text` a `Add`.</span><span class="sxs-lookup"><span data-stu-id="81f35-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="81f35-142">Selezionare il secondo pulsante e impostare il `Name` proprietà `UpdateButton` e `Text` proprietà `Update`.</span><span class="sxs-lookup"><span data-stu-id="81f35-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="81f35-143">Selezionare il terzo pulsante e impostare il `Name` proprietà `DeleteButton` e `Text` proprietà `Delete`.</span><span class="sxs-lookup"><span data-stu-id="81f35-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>  
  
4.  <span data-ttu-id="81f35-144">Fare doppio clic su di **Aggiungi** pulsante per aggiungere codice al relativo `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="81f35-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="81f35-145">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="81f35-145">Add the following code:</span></span>  
  
    ```vb  
    Private Sub AddButton_Click(ByVal sender As System.Object,   
                                ByVal e As System.EventArgs  
                               ) Handles AddButton.Click  
      Dim cust As New Customer With {   
        .City = "Wellington",   
        .CompanyName = "Blue Yonder Airlines",   
        .ContactName = "Jill Frank",   
        .Country = "New Zealand",   
        .CustomerID = "JILLF"}  
  
      db.Customers.InsertOnSubmit(cust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
5.  <span data-ttu-id="81f35-146">Fare doppio clic su di **aggiornamento** pulsante per aggiungere codice al relativo `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="81f35-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="81f35-147">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="81f35-147">Add the following code:</span></span>  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  <span data-ttu-id="81f35-148">Fare doppio clic su di **eliminare** pulsante per aggiungere codice al relativo `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="81f35-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="81f35-149">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="81f35-149">Add the following code:</span></span>  
  
    ```vb  
    Private Sub DeleteButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles DeleteButton.Click  
      Dim deleteCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      db.Customers.DeleteOnSubmit(deleteCust)  
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
7.  <span data-ttu-id="81f35-150">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="81f35-150">Press F5 to run your project.</span></span> <span data-ttu-id="81f35-151">Fare clic su **Aggiungi** per aggiungere un nuovo record.</span><span class="sxs-lookup"><span data-stu-id="81f35-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="81f35-152">Fare clic su **aggiornamento** per modificare il nuovo record.</span><span class="sxs-lookup"><span data-stu-id="81f35-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="81f35-153">Fare clic su **eliminare** per eliminare il nuovo record.</span><span class="sxs-lookup"><span data-stu-id="81f35-153">Click **Delete** to delete the new record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81f35-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="81f35-154">See Also</span></span>  
 [<span data-ttu-id="81f35-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="81f35-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 [<span data-ttu-id="81f35-156">Query</span><span class="sxs-lookup"><span data-stu-id="81f35-156">Queries</span></span>](../../../../visual-basic/language-reference/queries/queries.md)  
 [<span data-ttu-id="81f35-157">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="81f35-157">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)  
 [<span data-ttu-id="81f35-158">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="81f35-158">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)  
 [<span data-ttu-id="81f35-159">Procedura: assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="81f35-159">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)
