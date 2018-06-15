---
title: 'Procedura dettagliata: visualizzazione di dati in un controllo DataRepeater (Visual Studio)'
ms.date: 07/20/2015
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
ms.openlocfilehash: 8e64a819e9670a29e97140a32c81f5ff9006f83e
ms.sourcegitcommit: 2ad7d06f4f469b5d8a5280ac0e0289a81867fc8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2018
ms.locfileid: "35231509"
---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="18980-102">Procedura dettagliata: visualizzazione di dati in un controllo DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="18980-102">Walkthrough: Displaying Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="18980-103">Questa procedura dettagliata illustra uno scenario di base completo per visualizzare i dati associati in un controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-103">This walkthrough provides a basic start-to-finish scenario for displaying bound data in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="18980-104">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="18980-104">Prerequisite</span></span>  
 <span data-ttu-id="18980-105">Per questa procedura dettagliata è richiesto il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="18980-105">This walkthrough requires the Northwind sample database.</span></span>  
  
 <span data-ttu-id="18980-106">Se non è il database nel computer di sviluppo, è possibile scaricare da Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="18980-106">If you do not have this database on your development computer, you can download it from the Microsoft Download Center.</span></span> <span data-ttu-id="18980-107">Per istruzioni, vedere [download dei database di esempio](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span><span class="sxs-lookup"><span data-stu-id="18980-107">For instructions, see [Downloading Sample Databases](../../../framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="18980-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="18980-108">Overview</span></span>  
 <span data-ttu-id="18980-109">La prima parte di questa procedura dettagliata è costituita da quattro attività principali:</span><span class="sxs-lookup"><span data-stu-id="18980-109">The first part of this walkthrough consists of four main tasks:</span></span>  
  
-   <span data-ttu-id="18980-110">Creazione di una soluzione.</span><span class="sxs-lookup"><span data-stu-id="18980-110">Creating a solution.</span></span>  
  
-   <span data-ttu-id="18980-111">Aggiunta di un controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-111">Adding a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="18980-112">Aggiunta di un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="18980-112">Adding a data source.</span></span>  
  
-   <span data-ttu-id="18980-113">Aggiunta di controlli con associazione a dati.</span><span class="sxs-lookup"><span data-stu-id="18980-113">Adding data-bound controls.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a><span data-ttu-id="18980-114">Creazione di una soluzione DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-114">Creating a DataRepeater Solution</span></span>  
 <span data-ttu-id="18980-115">Il primo passaggio consiste nel creare un progetto e una soluzione.</span><span class="sxs-lookup"><span data-stu-id="18980-115">In the first step, you create a project and solution.</span></span>  
  
#### <a name="to-create-a-datarepeater-solution"></a><span data-ttu-id="18980-116">Per creare una soluzione DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-116">To create a DataRepeater solution</span></span>  
  
1.  <span data-ttu-id="18980-117">Scegliere **Nuovo progetto** dal menu **File**di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="18980-117">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="18980-118">Nel riquadro **Tipi progetto** della finestra di dialogo **Nuovo progetto** espandere **Visual Basic**, quindi fare clic su **Windows**</span><span class="sxs-lookup"><span data-stu-id="18980-118">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3.  <span data-ttu-id="18980-119">Nel riquadro **Modelli** scegliere **Applicazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="18980-119">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="18980-120">Nella casella **Nome** digitare `DataRepeaterApp`.</span><span class="sxs-lookup"><span data-stu-id="18980-120">In the **Name** box, type `DataRepeaterApp`.</span></span>  
  
5.  <span data-ttu-id="18980-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="18980-121">Click **OK**.</span></span>  
  
     <span data-ttu-id="18980-122">Verrà aperto Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="18980-122">The Windows Forms Designer opens.</span></span>  
  
6.  <span data-ttu-id="18980-123">Selezionare il form in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="18980-123">Select the form in the Windows Forms Designer.</span></span> <span data-ttu-id="18980-124">Nella finestra **Proprietà** impostare la proprietà **Size** su `800, 700`.</span><span class="sxs-lookup"><span data-stu-id="18980-124">In the **Properties** window, set the **Size** property to `800, 700`.</span></span>  
  
## <a name="adding-a-datarepeater-control"></a><span data-ttu-id="18980-125">Aggiunta di un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-125">Adding a DataRepeater Control</span></span>  
 <span data-ttu-id="18980-126">In questo passaggio si aggiunge un controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> al form.</span><span class="sxs-lookup"><span data-stu-id="18980-126">In this step, you add a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to the form.</span></span>  
  
#### <a name="to-add-a-datarepeater-control"></a><span data-ttu-id="18980-127">Per aggiungere un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-127">To add a DataRepeater control</span></span>  
  
1.  <span data-ttu-id="18980-128">Scegliere **Casella degli strumenti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="18980-128">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="18980-129">Verrà aperta la **Casella degli strumenti** .</span><span class="sxs-lookup"><span data-stu-id="18980-129">The **Toolbox** opens.</span></span>  
  
2.  <span data-ttu-id="18980-130">Selezionare la scheda **Visual Basic PowerPacks** .</span><span class="sxs-lookup"><span data-stu-id="18980-130">Select the **Visual Basic PowerPacks** tab.</span></span>  
  
3.  <span data-ttu-id="18980-131">Trascinare un controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> in **Form1**.</span><span class="sxs-lookup"><span data-stu-id="18980-131">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control onto **Form1**.</span></span>  
  
4.  <span data-ttu-id="18980-132">Nella finestra Proprietà impostare la proprietà **Location** su `0, 25`.</span><span class="sxs-lookup"><span data-stu-id="18980-132">In the Properties window, set the **Location** property to `0, 25`.</span></span>  
  
5.  <span data-ttu-id="18980-133">Impostare la proprietà **Size** su `460, 600`.</span><span class="sxs-lookup"><span data-stu-id="18980-133">Set the **Size** property to `460, 600`.</span></span>  
  
## <a name="adding-a-data-source"></a><span data-ttu-id="18980-134">Aggiunta di un'origine dati</span><span class="sxs-lookup"><span data-stu-id="18980-134">Adding a Data Source</span></span>  
 <span data-ttu-id="18980-135">In questo passaggio si aggiunge un'origine dati per il controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-135">In this step, you add a data source for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-add-a-data-source"></a><span data-ttu-id="18980-136">Per aggiungere un'origine dati</span><span class="sxs-lookup"><span data-stu-id="18980-136">To add a data source</span></span>  
  
1.  <span data-ttu-id="18980-137">Scegliere **Mostra origini dati** dal menu **Dati**.</span><span class="sxs-lookup"><span data-stu-id="18980-137">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
2.  <span data-ttu-id="18980-138">Nella finestra **Origini dati** fare clic su **Aggiungi nuova origine dati**.</span><span class="sxs-lookup"><span data-stu-id="18980-138">In the **Data Sources** window, click **Add New Data Source**.</span></span>  
  
3.  <span data-ttu-id="18980-139">Selezionare **Database** nella pagina **Scegliere un tipo di origine dati** e scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="18980-139">Select **Database** on the **Choose a Data Source Type** page, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="18980-140">Nella pagina **Seleziona connessione dati** , eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="18980-140">On the **Choose Your Data Connection** page, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="18980-141">Se disponibile nell'elenco a discesa, scegliere la connessione dati al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="18980-141">If a data connection to the Northwind sample database is available in the drop-down list, click it.</span></span>  
  
         <span data-ttu-id="18980-142">oppure</span><span class="sxs-lookup"><span data-stu-id="18980-142">-or-</span></span>  
  
    -   <span data-ttu-id="18980-143">Scegliere **Nuova connessione** per configurare una nuova connessione dati.</span><span class="sxs-lookup"><span data-stu-id="18980-143">Click **New Connection** to configure a new data connection.</span></span> <span data-ttu-id="18980-144">Per ulteriori informazioni, vedere [aggiungere nuove connessioni](/visualstudio/data-tools/add-new-connections).</span><span class="sxs-lookup"><span data-stu-id="18980-144">For more information, see [Add new connections](/visualstudio/data-tools/add-new-connections).</span></span>  
  
5.  <span data-ttu-id="18980-145">Se il database richiede una password, selezionare l'opzione che consente di includere dati riservati, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="18980-145">If the database requires a password, select the option to include sensitive data, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="18980-146">Se viene visualizzata una finestra di dialogo, scegliere **Sì** per salvare il file nel progetto.</span><span class="sxs-lookup"><span data-stu-id="18980-146">If a dialog box appears, click **Yes** to save the file to your project.</span></span>  
  
6.  <span data-ttu-id="18980-147">Nella pagina **Salva stringa di connessione nel file di configurazione dell'applicazione** fare clic su **Avanti** .</span><span class="sxs-lookup"><span data-stu-id="18980-147">Click **Next** on the **Save Connection String to the Application Configuration file** page.</span></span>  
  
7.  <span data-ttu-id="18980-148">Espandere il nodo **Tabelle** nella pagina **Seleziona oggetti di database** .</span><span class="sxs-lookup"><span data-stu-id="18980-148">Expand the **Tables** node on the **Choose Your Database Objects** page.</span></span>  
  
8.  <span data-ttu-id="18980-149">Selezionare le caselle di controllo accanto alle tabelle **Customers** e **Orders** , quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="18980-149">Select the check boxes next to the **Customers** and **Orders** tables, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="18980-150">L'oggetto**NorthwindDataSet** viene aggiunto al progetto e le tabelle **Customers** e **Orders** vengono visualizzate nella finestra **Origini dati** .</span><span class="sxs-lookup"><span data-stu-id="18980-150">**NorthwindDataSet** is added to your project and the **Customers** and **Orders** tables appear in the **Data Sources** window.</span></span>  
  
## <a name="adding-data-bound-controls"></a><span data-ttu-id="18980-151">Aggiunta di controlli con associazione a dati</span><span class="sxs-lookup"><span data-stu-id="18980-151">Adding Data-Bound Controls</span></span>  
 <span data-ttu-id="18980-152">In questo passaggio si aggiungono controlli con associazione a dati a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span><span class="sxs-lookup"><span data-stu-id="18980-152">In this step, you add data-bound controls to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
#### <a name="to-add-data-bound-controls"></a><span data-ttu-id="18980-153">Per aggiungere controlli con associazione a dati</span><span class="sxs-lookup"><span data-stu-id="18980-153">To add data-bound controls</span></span>  
  
1.  <span data-ttu-id="18980-154">Nella finestra **Origini dati** selezionare il nodo di livello principale della tabella **Customers** .</span><span class="sxs-lookup"><span data-stu-id="18980-154">In the **Data Sources** window, select the top-level node for the **Customers** table.</span></span>  
  
2.  <span data-ttu-id="18980-155">Modificare il tipo di rilascio della tabella in **Dettagli** selezionando **Dettagli** dall'elenco a discesa nel nodo della tabella.</span><span class="sxs-lookup"><span data-stu-id="18980-155">Change the drop type of the table to **Details** by clicking **Details** in the drop-down list on the table node.</span></span>  
  
3.  <span data-ttu-id="18980-156">Selezionare il nodo della tabella **Customers** e trascinarlo nell'area modello dell'elemento (l'area superiore) del controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-156">Select the **Customers** table node and drag it onto the item template region (the upper region) of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="18980-157">Il controllo <xref:System.Windows.Forms.BindingNavigator> viene aggiunto al form e i componenti **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**e **CustomersBindingNavigator** vengono aggiunti alla barra dei componenti.</span><span class="sxs-lookup"><span data-stu-id="18980-157">A <xref:System.Windows.Forms.BindingNavigator> control is added to the form, and the **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, and **CustomersBindingNavigator** components are added to the Component Tray.</span></span>  
  
4.  <span data-ttu-id="18980-158">Selezionare tutti i campi e le etichette corrispondenti e posizionarli vicino al bordo sinistro dell'area modello dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="18980-158">Select all of the fields and their associated labels and position them near the left edge of the item template region.</span></span>  
  
5.  <span data-ttu-id="18980-159">Selezionare gli ultimi cinque campi (**Region**, **Postal Code**, **Country**, **Phone**e **Fax**) e le etichette corrispondenti e spostarli in alto e a destra dei primi sei campi.</span><span class="sxs-lookup"><span data-stu-id="18980-159">Select the last five fields (**Region**, **Postal Code**, **Country**, **Phone**, and **Fax**) and their associated labels and move them up and to the right of the first six fields.</span></span>  
  
6.  <span data-ttu-id="18980-160">Selezionare il modello di elemento (l'area superiore del controllo).</span><span class="sxs-lookup"><span data-stu-id="18980-160">Select the item template (the upper region of the control).</span></span>  
  
7.  <span data-ttu-id="18980-161">Nella finestra Proprietà impostare la proprietà **Size** su `427, 170`.</span><span class="sxs-lookup"><span data-stu-id="18980-161">In the Properties window, set the **Size** property to `427, 170`.</span></span>  
  
 <span data-ttu-id="18980-162">A questo punto si dispone di un'applicazione funzionante che visualizzerà un elenco ripetuto di clienti.</span><span class="sxs-lookup"><span data-stu-id="18980-162">At this point, you have a working application that will display a repeating list of customers.</span></span> <span data-ttu-id="18980-163">Premere F5 per eseguire l'applicazione, modificare i dati e aggiungere o eliminare i record cliente.</span><span class="sxs-lookup"><span data-stu-id="18980-163">You can press F5 to run the application, change the data, and add or delete customer records.</span></span>  
  
 <span data-ttu-id="18980-164">Nei successivi passaggi facoltativi verrà illustrato come personalizzare il controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-164">In the next optional steps, you will learn how to customize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="next-steps-optional"></a><span data-ttu-id="18980-165">Passaggi successivi (facoltativi)</span><span class="sxs-lookup"><span data-stu-id="18980-165">Next Steps (Optional)</span></span>  
 <span data-ttu-id="18980-166">Questa parte della procedura dettagliata è costituita da quattro attività facoltative:</span><span class="sxs-lookup"><span data-stu-id="18980-166">This part of the walkthrough consists of four optional tasks:</span></span>  
  
-   <span data-ttu-id="18980-167">Modifica dell'aspetto del controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="18980-167">Changing the appearance of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="18980-168">Impedire agli utenti di aggiungere o eliminare record.</span><span class="sxs-lookup"><span data-stu-id="18980-168">Preventing users from adding or deleting records.</span></span>  
  
-   <span data-ttu-id="18980-169">Aggiunta di funzionalità di ricerca al controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-169">Adding search capability to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="18980-170">Aggiunta di una tabella master e di dettaglio per il controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-170">Adding a master and detail table to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a><span data-ttu-id="18980-171">Modifica dell'aspetto di un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-171">Changing the Appearance of the DataRepeater Control</span></span>  
 <span data-ttu-id="18980-172">In questo passaggio facoltativo, si modifica l' `BackColor` del controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="18980-172">In this optional step, you change the `BackColor` of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time.</span></span> <span data-ttu-id="18980-173">È anche possibile aggiungere codice per visualizzare le righe in colori alternati e modificare il `ForeColor` di un'etichetta in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="18980-173">You also add code to display rows in alternating colors and to change a label's `ForeColor` conditionally.</span></span>  
  
#### <a name="to-change-the-appearance-of-the-control"></a><span data-ttu-id="18980-174">Per modificare l'aspetto del controllo</span><span class="sxs-lookup"><span data-stu-id="18980-174">To change the appearance of the control</span></span>  
  
1.  <span data-ttu-id="18980-175">In Progettazione Windows Form, selezionare l'area principale (inferiore) del controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-175">In the Windows Forms Designer, select the main (lower) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="18980-176">Nella finestra Proprietà impostare la proprietà `BackColor` su bianco.</span><span class="sxs-lookup"><span data-stu-id="18980-176">In the Properties window, set the `BackColor` property to white.</span></span>  
  
3.  <span data-ttu-id="18980-177">Fare doppio clic su <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> per aprire l'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="18980-177">Double-click the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> to open the Code Editor.</span></span>  
  
4.  <span data-ttu-id="18980-178">Nell'elenco a discesa Event dell'editor di codice, selezionare **DrawItem**.</span><span class="sxs-lookup"><span data-stu-id="18980-178">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
5.  <span data-ttu-id="18980-179">Nel gestore eventi <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> aggiungere il codice che segue per alternare il colore `BackColor`.</span><span class="sxs-lookup"><span data-stu-id="18980-179">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to alternate the `BackColor`:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]  
  
6.  <span data-ttu-id="18980-180">Nel gestore eventi <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> aggiungere il codice seguente per modificare il `ForeColor` di un'etichetta in base a una condizione:</span><span class="sxs-lookup"><span data-stu-id="18980-180">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to change the `ForeColor` of a label depending on a condition:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]  
  
7.  <span data-ttu-id="18980-181">Premere F5 per eseguire l'applicazione e visualizzare la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="18980-181">Press F5 to run the application and see the customizations.</span></span>  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a><span data-ttu-id="18980-182">Impedire agli utenti di aggiungere o eliminare record</span><span class="sxs-lookup"><span data-stu-id="18980-182">Preventing Users from Adding or Deleting Records</span></span>  
 <span data-ttu-id="18980-183">In questo passaggio facoltativo, si aggiunge il codice che impedisce agli utenti di aggiungere o eliminare i record del controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-183">In this optional step, you add code that prevents users from adding or deleting records in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a><span data-ttu-id="18980-184">Per impedire agli utenti di aggiungere o eliminare record</span><span class="sxs-lookup"><span data-stu-id="18980-184">To prevent users from adding and deleting records</span></span>  
  
1.  <span data-ttu-id="18980-185">In Progettazione Windows Form, fare doppio clic sul form per aprire l'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="18980-185">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="18980-186">Aggiungere il codice seguente all'evento `Form_Load` :</span><span class="sxs-lookup"><span data-stu-id="18980-186">Add the following code to the `Form_Load` event:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]  
  
3.  <span data-ttu-id="18980-187">Nell'elenco a discesa Class Name, fare clic su **BindingNavigatorDeleteItem**.</span><span class="sxs-lookup"><span data-stu-id="18980-187">In the Class Name drop-down list, click **BindingNavigatorDeleteItem**.</span></span> <span data-ttu-id="18980-188">Nell'elenco a discesa Method Name, fare clic su **EnabledChanged**.</span><span class="sxs-lookup"><span data-stu-id="18980-188">In the Method Name drop-down list, click **EnabledChanged**.</span></span>  
  
4.  <span data-ttu-id="18980-189">Aggiungere il codice seguente al gestore eventi `BindingNavigatorDeleteItem_EnabledChanged` :</span><span class="sxs-lookup"><span data-stu-id="18980-189">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]  
  
    > [!NOTE]
    >  <span data-ttu-id="18980-190">Questo passaggio è necessario affinché <xref:System.Windows.Forms.BindingSource> abiliti il pulsante **DeleteItem** pulsante a ogni modifica del record corrente.</span><span class="sxs-lookup"><span data-stu-id="18980-190">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
5.  <span data-ttu-id="18980-191">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18980-191">Press F5 to run the application.</span></span> <span data-ttu-id="18980-192">Notare che il pulsante **DeleteItem** pulsante è disabilitato e non è possibile eliminare elementi premendo il tasto CANC.</span><span class="sxs-lookup"><span data-stu-id="18980-192">Notice that the **DeleteItem** button is disabled and that you cannot delete items by pressing the DELETE key.</span></span>  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a><span data-ttu-id="18980-193">Aggiunta di funzionalità di ricerca al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-193">Adding Search Capability to the DataRepeater Control</span></span>  
 <span data-ttu-id="18980-194">In questo passaggio facoltativo si implementa la funzionalità di ricerca per un valore nel controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-194">In this optional step, you implement the capability to search for a value in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="18980-195">Se viene individuata la stringa di ricerca, il controllo seleziona l'elemento che contiene il valore e scorre l'elemento nella visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="18980-195">If the search string is found, the control selects the item that contains the value and scrolls the item into view.</span></span>  
  
#### <a name="to-add-search-capability"></a><span data-ttu-id="18980-196">Per aggiungere funzionalità di ricerca</span><span class="sxs-lookup"><span data-stu-id="18980-196">To add search capability</span></span>  
  
1.  <span data-ttu-id="18980-197">Trascinare il controllo <xref:System.Windows.Forms.TextBox> dalla **casella degli strumenti** al form che contiene il controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-197">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="18980-198">Collocarlo sotto al controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-198">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="18980-199">Nella finestra Proprietà modificare la proprietà **Name** in **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="18980-199">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="18980-200">Trascinare il controllo <xref:System.Windows.Forms.Button> dalla **casella degli strumenti** al form che contiene il controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-200">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="18980-201">Collocarlo sotto al controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-201">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="18980-202">Nella finestra Proprietà modificare la proprietà **Name** in **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="18980-202">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="18980-203">Impostare la proprietà **Text** su **Search**.</span><span class="sxs-lookup"><span data-stu-id="18980-203">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="18980-204">Fare doppio clic sul controllo <xref:System.Windows.Forms.Button> per aprire l'editor di codice e aggiungere il codice seguente al gestore dell'evento `SearchButton_Click` .</span><span class="sxs-lookup"><span data-stu-id="18980-204">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     [!code-csharp[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
     [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]  
  
6.  <span data-ttu-id="18980-205">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18980-205">Press F5 to run the application.</span></span> <span data-ttu-id="18980-206">Digitare un ID cliente in **SearchTextBox** e fare clic sul pulsante **Search** .</span><span class="sxs-lookup"><span data-stu-id="18980-206">Type a customer ID in **SearchTextBox** and click the **Search** button.</span></span>  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a><span data-ttu-id="18980-207">Aggiunta di una tabella master e di dettaglio per il controllo</span><span class="sxs-lookup"><span data-stu-id="18980-207">Adding a Master and Detail Table to the DataRepeater</span></span>  
 <span data-ttu-id="18980-208">In questo passaggio facoltativo si aggiunge un secondo controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> per visualizzare gli ordini correlati a ciascun cliente.</span><span class="sxs-lookup"><span data-stu-id="18980-208">In this optional step, you add a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to display related orders for each customer.</span></span>  
  
#### <a name="to-add-a-master-and-detail-table"></a><span data-ttu-id="18980-209">Per aggiungere una tabella master e di dettaglio</span><span class="sxs-lookup"><span data-stu-id="18980-209">To add a master and detail table</span></span>  
  
1.  <span data-ttu-id="18980-210">Trascinare un secondo controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> dalla scheda **Visual Basic Power Packs** della **Casella degli strumenti** al form.</span><span class="sxs-lookup"><span data-stu-id="18980-210">Drag a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="18980-211">Nella finestra Proprietà impostare la proprietà **Location** su `465, 25`.</span><span class="sxs-lookup"><span data-stu-id="18980-211">In the Properties window, set the **Location** property to `465, 25`.</span></span>  
  
3.  <span data-ttu-id="18980-212">Impostare la proprietà **Size** su `315, 600`.</span><span class="sxs-lookup"><span data-stu-id="18980-212">Set the **Size** property to `315, 600`.</span></span>  
  
4.  <span data-ttu-id="18980-213">Nella finestra **Origini dati** espandere il nodo della tabella **Customers** e selezionare il nodo dettaglio della tabella **Orders** .</span><span class="sxs-lookup"><span data-stu-id="18980-213">In the **Data Sources** window, expand the **Customers** table node and select the detail node for the **Orders** table.</span></span>  
  
5.  <span data-ttu-id="18980-214">Modificare il tipo di rilascio della tabella **Orders** selezionando **Details** dall'elenco a discesa nel nodo della tabella.</span><span class="sxs-lookup"><span data-stu-id="18980-214">Change the drop type of this **Orders** table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="18980-215">Trascinare il nodo della tabella **Orders** nell'area modello dell'elemento (l'area superiore) del secondo controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-215">Drag this **Orders** table node onto the item template region (the upper region) of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="18980-216">Alla barra dei componenti vengono aggiunti il componente **OrdersBindingSource** e il componente **OrdersTableAdapter** .</span><span class="sxs-lookup"><span data-stu-id="18980-216">An **OrdersBindingSource** component and an **OrdersTableAdapter** component are added to the Component Tray.</span></span>  
  
7.  <span data-ttu-id="18980-217">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="18980-217">Press F5 to run the application.</span></span> <span data-ttu-id="18980-218">Selezionando ciascun cliente nel primo controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> , gli ordini relativi a quel cliente vengono visualizzati nel secondo controllo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> .</span><span class="sxs-lookup"><span data-stu-id="18980-218">When you select each customer in the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, the orders for that customer are displayed in the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18980-219">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="18980-219">See Also</span></span>  
 [<span data-ttu-id="18980-220">Introduzione al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-220">Introduction to the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="18980-221">Procedura: Visualizzare i dati associati in un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-221">How to: Display Bound Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="18980-222">Procedura: Visualizzare i controlli non associati in un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-222">How to: Display Unbound Controls in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="18980-223">Procedura: Modificare il layout di un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-223">How to: Change the Layout of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="18980-224">Procedura: Visualizzare le intestazioni degli elementi in un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-224">How to: Display Item Headers in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="18980-225">Procedura: Cercare dati in un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-225">How to: Search Data in a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="18980-226">Procedura: creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="18980-226">How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md)  
 [<span data-ttu-id="18980-227">Procedura: Modificare l'aspetto di un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-227">How to: Change the Appearance of a DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md)  
 [<span data-ttu-id="18980-228">Procedura: Disabilitare l'aggiunta e l'eliminazione di elementi DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-228">How to: Disable Adding and Deleting DataRepeater Items</span></span>](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md)  
 [<span data-ttu-id="18980-229">Risoluzione dei problemi relativi al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="18980-229">Troubleshooting the DataRepeater Control</span></span>](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)
