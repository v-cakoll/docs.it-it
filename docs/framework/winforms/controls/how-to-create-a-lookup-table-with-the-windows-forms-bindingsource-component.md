---
title: Creare una tabella di ricerca con il componente BindingSource
ms.date: 03/30/2017
helpviewer_keywords:
- lookup tables
- tables [Windows Forms], creating lookup tables
- BindingSource component [Windows Forms], creating a lookup table
- BindingSource component [Windows Forms], examples
ms.assetid: 622fce80-879d-44be-abbf-8350ec22ca2b
ms.openlocfilehash: ccf2bfa6cf3f56a38b55f8c87004c42a46172891
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736804"
---
# <a name="how-to-create-a-lookup-table-with-the-windows-forms-bindingsource-component"></a><span data-ttu-id="c092f-102">Procedura: creare una tabella di ricerca con il componente BindingSource di Windows Form</span><span class="sxs-lookup"><span data-stu-id="c092f-102">How to: Create a Lookup Table with the Windows Forms BindingSource Component</span></span>
<span data-ttu-id="c092f-103">Una tabella di ricerca è una tabella di dati che include una colonna che mostra i dati presenti nei record di una tabella correlata.</span><span class="sxs-lookup"><span data-stu-id="c092f-103">A lookup table is a table of data that has a column that displays data from records in a related table.</span></span> <span data-ttu-id="c092f-104">Nelle procedure seguenti sarà usato un controllo <xref:System.Windows.Forms.ComboBox> per visualizzare il campo che include la relazione di chiave esterna dalla tabella padre alla tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="c092f-104">In the following procedures, a <xref:System.Windows.Forms.ComboBox> control is used to display the field with the foreign-key relationship from the parent to the child table.</span></span>  
  
 <span data-ttu-id="c092f-105">Per semplificare la visualizzazione delle due tabelle e della relazione corrispondente, di seguito è disponibile un esempio di una tabella padre e una tabella figlio:</span><span class="sxs-lookup"><span data-stu-id="c092f-105">To help visualize these two tables and this relationship, here is an example of a parent and child table:</span></span>  
  
 <span data-ttu-id="c092f-106">CustomersTable (tabella padre)</span><span class="sxs-lookup"><span data-stu-id="c092f-106">CustomersTable (parent table)</span></span>  
  
|<span data-ttu-id="c092f-107">CustomerID</span><span class="sxs-lookup"><span data-stu-id="c092f-107">CustomerID</span></span>|<span data-ttu-id="c092f-108">CustomerName</span><span class="sxs-lookup"><span data-stu-id="c092f-108">CustomerName</span></span>|  
|----------------|------------------|  
|<span data-ttu-id="c092f-109">712</span><span class="sxs-lookup"><span data-stu-id="c092f-109">712</span></span>|<span data-ttu-id="c092f-110">Davide Milano</span><span class="sxs-lookup"><span data-stu-id="c092f-110">Paul Koch</span></span>|  
|<span data-ttu-id="c092f-111">713</span><span class="sxs-lookup"><span data-stu-id="c092f-111">713</span></span>|<span data-ttu-id="c092f-112">Fiamma Greco</span><span class="sxs-lookup"><span data-stu-id="c092f-112">Tamara Johnston</span></span>|  
  
 <span data-ttu-id="c092f-113">OrdersTable (tabella figlio)</span><span class="sxs-lookup"><span data-stu-id="c092f-113">OrdersTable (child table)</span></span>  
  
|<span data-ttu-id="c092f-114">OrderID</span><span class="sxs-lookup"><span data-stu-id="c092f-114">OrderID</span></span>|<span data-ttu-id="c092f-115">OrderDate</span><span class="sxs-lookup"><span data-stu-id="c092f-115">OrderDate</span></span>|<span data-ttu-id="c092f-116">CustomerID</span><span class="sxs-lookup"><span data-stu-id="c092f-116">CustomerID</span></span>|  
|-------------|---------------|----------------|  
|<span data-ttu-id="c092f-117">903</span><span class="sxs-lookup"><span data-stu-id="c092f-117">903</span></span>|<span data-ttu-id="c092f-118">Lunedì, 12.02.04</span><span class="sxs-lookup"><span data-stu-id="c092f-118">February 12, 2004</span></span>|<span data-ttu-id="c092f-119">712</span><span class="sxs-lookup"><span data-stu-id="c092f-119">712</span></span>|  
|<span data-ttu-id="c092f-120">904</span><span class="sxs-lookup"><span data-stu-id="c092f-120">904</span></span>|<span data-ttu-id="c092f-121">Lunedì, 13.02.04</span><span class="sxs-lookup"><span data-stu-id="c092f-121">February 13, 2004</span></span>|<span data-ttu-id="c092f-122">713</span><span class="sxs-lookup"><span data-stu-id="c092f-122">713</span></span>|  
  
 <span data-ttu-id="c092f-123">In questo scenario, in una tabella, CustomersTable, sono archiviate le informazioni effettive da visualizzare e salvare.</span><span class="sxs-lookup"><span data-stu-id="c092f-123">In this scenario, one table, CustomersTable, stores the actual information you want to display and save.</span></span> <span data-ttu-id="c092f-124">Per risparmiare spazio, tuttavia, la tabella esclude dati che possono rendere più chiare le informazioni.</span><span class="sxs-lookup"><span data-stu-id="c092f-124">But to save space, the table leaves out data that adds clarity.</span></span> <span data-ttu-id="c092f-125">L'altra tabella, OrdersTable, include solo informazioni correlate all'aspetto e relative alle corrispondenze tra numero di ID, data di ordine e ID ordine.</span><span class="sxs-lookup"><span data-stu-id="c092f-125">The other table, OrdersTable, contains only appearance-related information about which customer ID number is equivalent to which order date and order ID.</span></span> <span data-ttu-id="c092f-126">Non include informazioni sui nomi dei clienti.</span><span class="sxs-lookup"><span data-stu-id="c092f-126">There is no mention of the customers' names.</span></span>  
  
 <span data-ttu-id="c092f-127">Nel controllo [ComboBox](combobox-control-windows-forms.md) sono impostate quattro proprietà importanti per creare la tabella di ricerca.</span><span class="sxs-lookup"><span data-stu-id="c092f-127">Four important properties are set on the [ComboBox Control](combobox-control-windows-forms.md) control to create the lookup table.</span></span>  
  
- <span data-ttu-id="c092f-128">La proprietà <xref:System.Windows.Forms.ComboBox.DataSource%2A> include il nome della tabella.</span><span class="sxs-lookup"><span data-stu-id="c092f-128">The <xref:System.Windows.Forms.ComboBox.DataSource%2A> property contains the name of the table.</span></span>  
  
- <span data-ttu-id="c092f-129">La proprietà <xref:System.Windows.Forms.ListControl.DisplayMember%2A> include la colonna di dati della tabella da visualizzare per il testo del controllo (nome del cliente).</span><span class="sxs-lookup"><span data-stu-id="c092f-129">The <xref:System.Windows.Forms.ListControl.DisplayMember%2A> property contains the data column of that table that you want to display for the control text (the customer's name).</span></span>  
  
- <span data-ttu-id="c092f-130">La proprietà <xref:System.Windows.Forms.ListControl.ValueMember%2A> include la colonna di dati della tabella con le informazioni archiviate (numero di ID nella tabella padre).</span><span class="sxs-lookup"><span data-stu-id="c092f-130">The <xref:System.Windows.Forms.ListControl.ValueMember%2A> property contains the data column of that table with the stored information (the ID number in the parent table).</span></span>  
  
- <span data-ttu-id="c092f-131">La proprietà <xref:System.Windows.Forms.ListControl.SelectedValue%2A> fornisce il valore di ricerca per la tabella figlio, in base a <xref:System.Windows.Forms.ListControl.ValueMember%2A>.</span><span class="sxs-lookup"><span data-stu-id="c092f-131">The <xref:System.Windows.Forms.ListControl.SelectedValue%2A> property provides the lookup value for the child table, based on the <xref:System.Windows.Forms.ListControl.ValueMember%2A>.</span></span>  
  
 <span data-ttu-id="c092f-132">Le procedure seguenti mostrano come definire il layout del form come tabella di ricerca e associare i dati ai controlli disponibili nel form.</span><span class="sxs-lookup"><span data-stu-id="c092f-132">The procedures below show you how to lay out your form as a lookup table and bind data to the controls on it.</span></span> <span data-ttu-id="c092f-133">Per completare correttamente le procedure, è necessario avere un'origine dati con tabelle padre e figlio con una relazione di chiave esterna, come indicato in precedenza.</span><span class="sxs-lookup"><span data-stu-id="c092f-133">To successfully complete the procedures, you must have a data source with parent and child tables that have a foreign-key relationship, as mentioned previously.</span></span>  
  
### <a name="to-create-the-user-interface"></a><span data-ttu-id="c092f-134">Per creare l'interfaccia utente</span><span class="sxs-lookup"><span data-stu-id="c092f-134">To create the user interface</span></span>  
  
1. <span data-ttu-id="c092f-135">Dalla **casella degli strumenti**trascinare un controllo <xref:System.Windows.Forms.ComboBox> nel form.</span><span class="sxs-lookup"><span data-stu-id="c092f-135">From the **ToolBox**, drag a <xref:System.Windows.Forms.ComboBox> control onto the form.</span></span>  
  
     <span data-ttu-id="c092f-136">Il controllo mostrerà una colonna della tabella padre.</span><span class="sxs-lookup"><span data-stu-id="c092f-136">This control will display the column from parent table.</span></span>  
  
2. <span data-ttu-id="c092f-137">Trascinare altri controlli per visualizzare i dettagli disponibili nella tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="c092f-137">Drag other controls to display details from the child table.</span></span> <span data-ttu-id="c092f-138">La scelta dei controlli dovrebbe dipendere dal formato dei dati nella tabella.</span><span class="sxs-lookup"><span data-stu-id="c092f-138">The format of the data in the table should determine which controls you choose.</span></span> <span data-ttu-id="c092f-139">Per altre informazioni, vedere [Controlli di Windows Form per funzione](windows-forms-controls-by-function.md).</span><span class="sxs-lookup"><span data-stu-id="c092f-139">For more information, see [Windows Forms Controls by Function](windows-forms-controls-by-function.md).</span></span>  
  
3. <span data-ttu-id="c092f-140">Trascinare un controllo <xref:System.Windows.Forms.BindingNavigator> nel form, per permettere di esplorare i dati nella tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="c092f-140">Drag a <xref:System.Windows.Forms.BindingNavigator> control onto the form; this will allow you to navigate the data in the child table.</span></span>  
  
### <a name="to-connect-to-the-data-and-bind-it-to-controls"></a><span data-ttu-id="c092f-141">Per connettersi ai dati e associarli ai controlli</span><span class="sxs-lookup"><span data-stu-id="c092f-141">To connect to the data and bind it to controls</span></span>  
  
1. <span data-ttu-id="c092f-142">Selezionare <xref:System.Windows.Forms.ComboBox> e fare clic sul glifo Smart Task per visualizzare la finestra di dialogo Smart Task.</span><span class="sxs-lookup"><span data-stu-id="c092f-142">Select the <xref:System.Windows.Forms.ComboBox> and click the Smart Task glyph to display the Smart Task dialog box.</span></span>  
  
2. <span data-ttu-id="c092f-143">Selezionare **Usa elementi associati a dati**.</span><span class="sxs-lookup"><span data-stu-id="c092f-143">Select **Use data bound items**.</span></span>  
  
3. <span data-ttu-id="c092f-144">Fare clic sulla freccia accanto alla casella di riepilogo a discesa **Origine dati**.</span><span class="sxs-lookup"><span data-stu-id="c092f-144">Click the arrow next to the **Data Source** drop-down box.</span></span> <span data-ttu-id="c092f-145">Se un'origine dati è stata configurata in precedenza per il progetto o il form, sarà visualizzata. In caso contrario, completare i passaggi seguenti. In questo esempio sono usate le tabelle Customers e Orders del database di esempio Northwind e tali tabelle sono indicate tra parentesi.</span><span class="sxs-lookup"><span data-stu-id="c092f-145">If a data source has previously been configured for the project or form, it will appear; otherwise, complete the following steps (This example uses the Customers and Orders tables of the Northwind sample database and refers to them in parentheses).</span></span>  
  
    1. <span data-ttu-id="c092f-146">Fare clic su **Aggiungi origine dati progetto** per connettersi ai dati e creare un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="c092f-146">Click **Add Project Data Source** to connect to data and create a data source.</span></span>  
  
    2. <span data-ttu-id="c092f-147">Nella pagina iniziale della **Configurazione guidata origine dati** fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c092f-147">On the **Data Source Configuration Wizard** welcome page, click **Next**.</span></span>  
  
    3. <span data-ttu-id="c092f-148">Selezionare **Database** nella pagina **Seleziona un tipo di origine dati**.</span><span class="sxs-lookup"><span data-stu-id="c092f-148">Select **Database** on the **Choose a Data Source Type** page.</span></span>  
  
    4. <span data-ttu-id="c092f-149">Selezionare una connessione dati dall'elenco di connessioni disponibili nella pagina **Seleziona connessione dati**.</span><span class="sxs-lookup"><span data-stu-id="c092f-149">Select a data connection from the list of available connections on the **Choose Your Data Connection** page.</span></span> <span data-ttu-id="c092f-150">Se la connessione dati voluta non è disponibile, selezionare **Nuova connessione** per creare una nuova connessione dati.</span><span class="sxs-lookup"><span data-stu-id="c092f-150">If your desired data connection is not available, select **New Connection** to create a new data connection.</span></span>  
  
    5. <span data-ttu-id="c092f-151">Fare clic su **Sì, salva la connessione con nome** per salvare la stringa di connessione nel file di configurazione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c092f-151">Click **Yes, save the connection** to save the connection string in the application configuration file.</span></span>  
  
    6. <span data-ttu-id="c092f-152">Selezionare gli oggetti database da inserire nell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c092f-152">Select the database objects to bring into your application.</span></span> <span data-ttu-id="c092f-153">In questo caso, selezionare la tabella padre e la tabella figlio (ad esempio, Customers e Orders) con una relazione di chiave esterna.</span><span class="sxs-lookup"><span data-stu-id="c092f-153">In this case, select a parent table and child table (for example, Customers and Orders) with a foreign key relationship.</span></span>  
  
    7. <span data-ttu-id="c092f-154">Se si vuole, sostituire il nome predefinito del set di dati.</span><span class="sxs-lookup"><span data-stu-id="c092f-154">Replace the default dataset name if you want.</span></span>  
  
    8. <span data-ttu-id="c092f-155">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="c092f-155">Click **Finish**.</span></span>  
  
4. <span data-ttu-id="c092f-156">Nella casella di riepilogo a discesa **Visualizza membro** selezionare il nome di colonna (ad esempio, ContactName) da visualizzare nella casella combinata.</span><span class="sxs-lookup"><span data-stu-id="c092f-156">In the **Display Member** drop-down box, select the column name (for example, ContactName) to be displayed in the combo box.</span></span>  
  
5. <span data-ttu-id="c092f-157">Nella casella di riepilogo a discesa **Membro valore** selezionare la colonna (ad esempio, CustomerID) per eseguire la ricerca nella tabella figlio.</span><span class="sxs-lookup"><span data-stu-id="c092f-157">In the **Value Member** drop-down box, select the column (for example, CustomerID) to perform the lookup operation in the child table.</span></span>  
  
6. <span data-ttu-id="c092f-158">Nella casella di riepilogo a discesa **Valore selezionato** passare a **Origini dati del progetto** e al set di dati appena creato che include le tabelle padre e figlio.</span><span class="sxs-lookup"><span data-stu-id="c092f-158">In the **Selected Value** drop-down box, navigate to **Project Data Sources** and the dataset you just created that contains the parent and child tables.</span></span> <span data-ttu-id="c092f-159">Selezionare la stessa proprietà della tabella figlio che corrisponde al Membro valore della tabella padre (ad esempio, Orders.CustomerID).</span><span class="sxs-lookup"><span data-stu-id="c092f-159">Select the same property of the child table that is the Value Member of the parent table (for example, Orders.CustomerID).</span></span> <span data-ttu-id="c092f-160">I componenti appropriati per <xref:System.Windows.Forms.BindingSource>, set di dati e adattatori di tabelle saranno creati e aggiunti al form.</span><span class="sxs-lookup"><span data-stu-id="c092f-160">The appropriate <xref:System.Windows.Forms.BindingSource> , data set, and table adapter components will be created and added to the form.</span></span>  
  
7. <span data-ttu-id="c092f-161">Associare il controllo <xref:System.Windows.Forms.BindingNavigator> a <xref:System.Windows.Forms.BindingSource> della tabella figlio (ad esempio, `OrdersBindingSource`).</span><span class="sxs-lookup"><span data-stu-id="c092f-161">Bind the <xref:System.Windows.Forms.BindingNavigator> control to the <xref:System.Windows.Forms.BindingSource> of the child table (for example, `OrdersBindingSource`).</span></span>  
  
8. <span data-ttu-id="c092f-162">Associare i controlli diversi dal controllo <xref:System.Windows.Forms.ComboBox> e <xref:System.Windows.Forms.BindingNavigator> ai campi di dettagli da <xref:System.Windows.Forms.BindingSource> della tabella figlio (ad esempio, `OrdersBindingSource`) da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="c092f-162">Bind the controls other than the <xref:System.Windows.Forms.ComboBox> and <xref:System.Windows.Forms.BindingNavigator> control to the details fields from the child table's <xref:System.Windows.Forms.BindingSource> (for example, `OrdersBindingSource`) that you want to display.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c092f-163">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c092f-163">See also</span></span>

- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="c092f-164">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="c092f-164">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="c092f-165">Controllo ComboBox</span><span class="sxs-lookup"><span data-stu-id="c092f-165">ComboBox Control</span></span>](combobox-control-windows-forms.md)
- [<span data-ttu-id="c092f-166">Associare controlli ai dati in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c092f-166">Bind controls to data in Visual Studio</span></span>](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio)
