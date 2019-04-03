---
title: 'Procedura: Modificare i dati in un Database utilizzando LINQ (Visual Basic)'
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
ms.openlocfilehash: c92a94cd6223aad8e4ea3da86a8dd37bd71aad2c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58820997"
---
# <a name="how-to-modify-data-in-a-database-by-using-linq-visual-basic"></a><span data-ttu-id="1f0b1-102">Procedura: Modificare i dati in un Database utilizzando LINQ (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1f0b1-102">How to: Modify Data in a Database by Using LINQ (Visual Basic)</span></span>
<span data-ttu-id="1f0b1-103">Language Integrated Query (LINQ) query rendono più semplice accedere alle informazioni sul database e modificare i valori nel database.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-103">Language-Integrated Query (LINQ) queries make it easy to access database information and modify values in the database.</span></span>  
  
 <span data-ttu-id="1f0b1-104">Nell'esempio seguente viene illustrato come creare una nuova applicazione che recupera e aggiorna le informazioni in un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-104">The following example shows how to create a new application that retrieves and updates information in a SQL Server database.</span></span>  
  
 <span data-ttu-id="1f0b1-105">Gli esempi in questo argomento usano il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-105">The examples in this topic use the Northwind sample database.</span></span> <span data-ttu-id="1f0b1-106">Se non è questo database nel computer di sviluppo, è possibile scaricarlo da Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="1f0b1-107">Per istruzioni, vedere [download dei database di esempio](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="1f0b1-107">For instructions, see [Downloading Sample Databases](../../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
### <a name="to-create-a-connection-to-a-database"></a><span data-ttu-id="1f0b1-108">Per creare una connessione a un database</span><span class="sxs-lookup"><span data-stu-id="1f0b1-108">To create a connection to a database</span></span>  
  
1.  <span data-ttu-id="1f0b1-109">In Visual Studio, aprire **Esplora Server**/**Esplora Database** facendo la **visualizzazione** dal menu e quindi selezionare **Esplora Server** / **Esplora database**.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-109">In Visual Studio, open **Server Explorer**/**Database Explorer** by clicking the **View** menu, and then select **Server Explorer**/**Database Explorer**.</span></span>  
  
2.  <span data-ttu-id="1f0b1-110">Fare doppio clic su **connessioni dati** nelle **Esplora Server**/**Esplora Database**, fare clic su **Aggiungi connessione**.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-110">Right-click **Data Connections** in **Server Explorer**/**Database Explorer**, and click **Add Connection**.</span></span>  
  
3.  <span data-ttu-id="1f0b1-111">Specificare una connessione valida al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-111">Specify a valid connection to the Northwind sample database.</span></span>  
  
### <a name="to-add-a-project-with-a-linq-to-sql-file"></a><span data-ttu-id="1f0b1-112">Per aggiungere un progetto con un LINQ per file SQL</span><span class="sxs-lookup"><span data-stu-id="1f0b1-112">To add a Project with a LINQ to SQL file</span></span>  
  
1.  <span data-ttu-id="1f0b1-113">In Visual Studio scegliere **Nuovo** dal menu **File** e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-113">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span> <span data-ttu-id="1f0b1-114">Selezionare Visual Basic **Windows Forms Application** come tipo di progetto.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-114">Select Visual Basic **Windows Forms Application** as the project type.</span></span>  
  
2.  <span data-ttu-id="1f0b1-115">Nel menu **Progetto** fare clic su **Aggiungi nuovo elemento**.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-115">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="1f0b1-116">Selezionare il **classi LINQ to SQL** modello di elemento.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-116">Select the **LINQ to SQL Classes** item template.</span></span>  
  
3.  <span data-ttu-id="1f0b1-117">Denominare il file `northwind.dbml`.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-117">Name the file `northwind.dbml`.</span></span> <span data-ttu-id="1f0b1-118">Fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-118">Click **Add**.</span></span> <span data-ttu-id="1f0b1-119">Viene aperto il Object Relational Designer (O/R Designer) per il `northwind.dbml` file.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-119">The Object Relational Designer (O/R Designer) is opened for the `northwind.dbml` file.</span></span>  
  
### <a name="to-add-tables-to-query-and-modify-to-the-designer"></a><span data-ttu-id="1f0b1-120">Per aggiungere le tabelle per eseguire query e modificare nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="1f0b1-120">To add tables to query and modify to the designer</span></span>  
  
1.  <span data-ttu-id="1f0b1-121">Nelle **Esplora Server**/**Esplora Database**, espandere la connessione al database Northwind.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-121">In **Server Explorer**/**Database Explorer**, expand the connection to the Northwind database.</span></span> <span data-ttu-id="1f0b1-122">Espandere la **tabelle** cartella.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-122">Expand the **Tables** folder.</span></span>  
  
     <span data-ttu-id="1f0b1-123">Se è stato chiuso O/R Designer, è possibile riaprirlo facendo doppio clic il `northwind.dbml` file aggiunti in precedenza.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-123">If you have closed the O/R Designer, you can reopen it by double-clicking the `northwind.dbml` file that you added earlier.</span></span>  
  
2.  <span data-ttu-id="1f0b1-124">Fare clic nella tabella Customers e trascinarla nel riquadro sinistro della finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-124">Click the Customers table and drag it to the left pane of the designer.</span></span>  
  
     <span data-ttu-id="1f0b1-125">La finestra di progettazione crea un nuovo oggetto Customer per il progetto.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-125">The designer creates a new Customer object for your project.</span></span>  
  
3.  <span data-ttu-id="1f0b1-126">Salvare le modifiche e chiudere la finestra di progettazione.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-126">Save your changes and close the designer.</span></span>  
  
4.  <span data-ttu-id="1f0b1-127">Salvare il progetto.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-127">Save your project.</span></span>  
  
### <a name="to-add-code-to-modify-the-database-and-display-the-results"></a><span data-ttu-id="1f0b1-128">Per aggiungere il codice per modificare il database e visualizzare i risultati</span><span class="sxs-lookup"><span data-stu-id="1f0b1-128">To add code to modify the database and display the results</span></span>  
  
1.  <span data-ttu-id="1f0b1-129">Dal **casella degli strumenti**, trascinare un <xref:System.Windows.Forms.DataGridView> controllo nel Form di Windows predefinito per il progetto, Form1.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-129">From the **Toolbox**, drag a <xref:System.Windows.Forms.DataGridView> control onto the default Windows Form for your project, Form1.</span></span>  
  
2.  <span data-ttu-id="1f0b1-130">Quando si aggiungono tabelle alla finestra di Progettazione relazionale oggetti, la finestra di progettazione aggiunge un <xref:System.Data.Linq.DataContext> oggetti al progetto.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-130">When you added tables to the O/R Designer, the designer added a <xref:System.Data.Linq.DataContext> object to your project.</span></span> <span data-ttu-id="1f0b1-131">Questo oggetto contiene codice che è possibile usare per accedere alla tabella Customers.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-131">This object contains code that you can use to access the Customers table.</span></span> <span data-ttu-id="1f0b1-132">Include anche codice che definisce un oggetto locale del cliente e una raccolta di clienti per la tabella.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-132">It also contains code that defines  a local Customer object and a Customers collection for the table.</span></span> <span data-ttu-id="1f0b1-133">Il <xref:System.Data.Linq.DataContext> oggetto per il progetto viene denominato in base al nome del file. dbml.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-133">The <xref:System.Data.Linq.DataContext> object for your project is named based on the name of your .dbml file.</span></span> <span data-ttu-id="1f0b1-134">Per questo progetto, il <xref:System.Data.Linq.DataContext> oggetto è denominato `northwindDataContext`.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-134">For this project, the <xref:System.Data.Linq.DataContext> object is named `northwindDataContext`.</span></span>  
  
     <span data-ttu-id="1f0b1-135">È possibile creare un'istanza di <xref:System.Data.Linq.DataContext> dell'oggetto nel codice e query e modificare la raccolta di clienti specificata da O/R Designer.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-135">You can create an instance of the <xref:System.Data.Linq.DataContext> object in your code and query and modify the Customers collection specified by the O/R Designer.</span></span> <span data-ttu-id="1f0b1-136">Le modifiche apportate alla raccolta di clienti non vengono riflesse nel database fino a quando non vengono inviate chiamando il <xref:System.Data.Linq.DataContext.SubmitChanges%2A> metodo di <xref:System.Data.Linq.DataContext> oggetto.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-136">Changes that you make to the Customers collection are not reflected in the database until you submit them by calling the <xref:System.Data.Linq.DataContext.SubmitChanges%2A> method of the <xref:System.Data.Linq.DataContext> object.</span></span>  
  
     <span data-ttu-id="1f0b1-137">Fare doppio clic sul Windows Form, Form1, per aggiungere codice per il <xref:System.Windows.Forms.Form.Load> eventi di query nella tabella Customers è che viene esposto come proprietà del <xref:System.Data.Linq.DataContext>.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-137">Double-click the Windows Form, Form1, to add code to the <xref:System.Windows.Forms.Form.Load> event to query the Customers table that is exposed as a property of your <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="1f0b1-138">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1f0b1-138">Add the following code:</span></span>  
  
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
  
3.  <span data-ttu-id="1f0b1-139">Dal **casella degli strumenti**, trascinare tre <xref:System.Windows.Forms.Button> controlli nel form.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-139">From the **Toolbox**, drag three <xref:System.Windows.Forms.Button> controls onto the form.</span></span> <span data-ttu-id="1f0b1-140">Selezionare il primo `Button` controllo.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-140">Select the first `Button` control.</span></span> <span data-ttu-id="1f0b1-141">Nel **proprietà** impostare nella finestra di `Name` del `Button` il controllo a `AddButton` e la `Text` per `Add`.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-141">In the **Properties** window, set the `Name` of the `Button` control to `AddButton` and the `Text` to `Add`.</span></span> <span data-ttu-id="1f0b1-142">Selezionare il secondo pulsante e impostare il `Name` proprietà `UpdateButton` e il `Text` proprietà `Update`.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-142">Select the second button and set the `Name` property to `UpdateButton` and the `Text` property to `Update`.</span></span> <span data-ttu-id="1f0b1-143">Selezionare il terzo pulsante e impostare il `Name` proprietà `DeleteButton` e il `Text` proprietà `Delete`.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-143">Select the third button and set the `Name` property to `DeleteButton` and the `Text` property to `Delete`.</span></span>  
  
4.  <span data-ttu-id="1f0b1-144">Fare doppio clic il **Add** pulsante per aggiungere codice al relativo `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-144">Double-click the **Add** button to add code to its `Click` event.</span></span> <span data-ttu-id="1f0b1-145">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1f0b1-145">Add the following code:</span></span>  
  
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
  
5.  <span data-ttu-id="1f0b1-146">Fare doppio clic il **Update** pulsante per aggiungere codice al relativo `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-146">Double-click the **Update** button to add code to its `Click` event.</span></span> <span data-ttu-id="1f0b1-147">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1f0b1-147">Add the following code:</span></span>  
  
    ```vb  
    Private Sub UpdateButton_Click(ByVal sender As System.Object, _  
                                   ByVal e As System.EventArgs  
                                  ) Handles UpdateButton.Click  
      Dim updateCust = (From cust In db.Customers   
                        Where cust.CustomerID = "JILLF").ToList()(0)  
  
      updateCust.ContactName = "Jill Shrader"
      updateCust.Country = "Wales"
      updateCust.CompanyName = "Red Yonder Airlines"
      updateCust.City = "Cardiff"
  
      Try  
        db.SubmitChanges()  
      Catch  
        ' Handle exception.  
      End Try  
  
      RefreshData()  
    End Sub  
    ```  
  
6.  <span data-ttu-id="1f0b1-148">Fare doppio clic il **eliminare** pulsante per aggiungere codice al relativo `Click` evento.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-148">Double-click the **Delete** button to add code to its `Click` event.</span></span> <span data-ttu-id="1f0b1-149">Aggiungere il codice seguente:</span><span class="sxs-lookup"><span data-stu-id="1f0b1-149">Add the following code:</span></span>  
  
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
  
7.  <span data-ttu-id="1f0b1-150">Premere F5 per eseguire il progetto.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-150">Press F5 to run your project.</span></span> <span data-ttu-id="1f0b1-151">Fare clic su **Add** per aggiungere un nuovo record.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-151">Click **Add** to add a new record.</span></span> <span data-ttu-id="1f0b1-152">Fare clic su **Update** per modificare il nuovo record.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-152">Click **Update** to modify the new record.</span></span> <span data-ttu-id="1f0b1-153">Fare clic su **eliminare** per eliminare il nuovo record.</span><span class="sxs-lookup"><span data-stu-id="1f0b1-153">Click **Delete** to delete the new record.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f0b1-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1f0b1-154">See also</span></span>

- [<span data-ttu-id="1f0b1-155">LINQ</span><span class="sxs-lookup"><span data-stu-id="1f0b1-155">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="1f0b1-156">Query</span><span class="sxs-lookup"><span data-stu-id="1f0b1-156">Queries</span></span>](../../../../visual-basic/language-reference/queries/index.md)
- [<span data-ttu-id="1f0b1-157">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="1f0b1-157">LINQ to SQL</span></span>](../../../../framework/data/adonet/sql/linq/index.md)
- [<span data-ttu-id="1f0b1-158">Metodi DataContext (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="1f0b1-158">DataContext Methods (O/R Designer)</span></span>](/visualstudio/data-tools/datacontext-methods-o-r-designer)
- [<span data-ttu-id="1f0b1-159">Procedura: Assegnare stored procedure per eseguire aggiornamenti, inserimenti ed eliminazioni (O/R Designer)</span><span class="sxs-lookup"><span data-stu-id="1f0b1-159">How to: Assign stored procedures to perform updates, inserts, and deletes (O/R Designer)</span></span>](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)
