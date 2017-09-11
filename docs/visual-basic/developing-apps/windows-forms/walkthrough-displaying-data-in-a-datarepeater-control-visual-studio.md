---
title: 'Procedura dettagliata: Visualizzazione dei dati in un controllo DataRepeater (Visual Studio) | Documenti di Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- DataRepeater, walkthrough
ms.assetid: 65dcdb95-6c3e-47cc-987d-190000f71653
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: b795b8f3bb42aecdbdfade62f4943239fec6eac4
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-displaying-data-in-a-datarepeater-control-visual-studio"></a><span data-ttu-id="b0818-102">Procedura dettagliata: visualizzazione di dati in un controllo DataRepeater (Visual Studio)</span><span class="sxs-lookup"><span data-stu-id="b0818-102">Walkthrough: Displaying Data in a DataRepeater Control (Visual Studio)</span></span>
<span data-ttu-id="b0818-103">Questa procedura dettagliata fornisce uno scenario di inizio alla fine di base per visualizzare i dati associati in un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-103">This walkthrough provides a basic start-to-finish scenario for displaying bound data in a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="b0818-104">Prerequisito</span><span class="sxs-lookup"><span data-stu-id="b0818-104">Prerequisite</span></span>  
 <span data-ttu-id="b0818-105">Per questa procedura dettagliata è richiesto il database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="b0818-105">This walkthrough requires the Northwind sample database.</span></span>  
  
 <span data-ttu-id="b0818-106">Se questo database non è presente nel computer di sviluppo, è possibile scaricarlo dall' [Area download Microsoft](http://go.microsoft.com/fwlink/?LinkID=98088).</span><span class="sxs-lookup"><span data-stu-id="b0818-106">If you do not have this database on your development computer, you can download it from the [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088).</span></span> <span data-ttu-id="b0818-107">Per istruzioni, vedere [download dei database di esempio](https://msdn.microsoft.com/library/bb399411).</span><span class="sxs-lookup"><span data-stu-id="b0818-107">For instructions, see [Downloading Sample Databases](https://msdn.microsoft.com/library/bb399411).</span></span>  
  
## <a name="overview"></a><span data-ttu-id="b0818-108">Panoramica</span><span class="sxs-lookup"><span data-stu-id="b0818-108">Overview</span></span>  
 <span data-ttu-id="b0818-109">La prima parte di questa procedura dettagliata è costituita da quattro attività principali:</span><span class="sxs-lookup"><span data-stu-id="b0818-109">The first part of this walkthrough consists of four main tasks:</span></span>  
  
-   <span data-ttu-id="b0818-110">Creazione di una soluzione.</span><span class="sxs-lookup"><span data-stu-id="b0818-110">Creating a solution.</span></span>  
  
-   <span data-ttu-id="b0818-111">Aggiunta di un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-111">Adding a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="b0818-112">Aggiunta di un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="b0818-112">Adding a data source.</span></span>  
  
-   <span data-ttu-id="b0818-113">Aggiunta di controlli con associazione a dati.</span><span class="sxs-lookup"><span data-stu-id="b0818-113">Adding data-bound controls.</span></span>  
  
[!INCLUDE[note_settings_general](../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-a-datarepeater-solution"></a><span data-ttu-id="b0818-114">Creazione di una soluzione DataRepeater</span><span class="sxs-lookup"><span data-stu-id="b0818-114">Creating a DataRepeater Solution</span></span>  
 <span data-ttu-id="b0818-115">Il primo passaggio consiste nel creare un progetto e una soluzione.</span><span class="sxs-lookup"><span data-stu-id="b0818-115">In the first step, you create a project and solution.</span></span>  
  
#### <a name="to-create-a-datarepeater-solution"></a><span data-ttu-id="b0818-116">Per creare una soluzione DataRepeater</span><span class="sxs-lookup"><span data-stu-id="b0818-116">To create a DataRepeater solution</span></span>  
  
1.  <span data-ttu-id="b0818-117">Scegliere **Nuovo progetto** dal menu **File**di Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0818-117">On the Visual Studio **File** menu, click **New Project**.</span></span>  
  
2.  <span data-ttu-id="b0818-118">Nel riquadro **Tipi progetto** della finestra di dialogo **Nuovo progetto** espandere **Visual Basic**, quindi fare clic su **Windows**</span><span class="sxs-lookup"><span data-stu-id="b0818-118">In the **Project types** pane in the **New Project** dialog box, expand **Visual Basic**, and then click **Windows**.</span></span>  
  
3.  <span data-ttu-id="b0818-119">Nel riquadro **Modelli** scegliere **Applicazione Windows Form**.</span><span class="sxs-lookup"><span data-stu-id="b0818-119">In the **Templates** pane, click **Windows Forms Application**.</span></span>  
  
4.  <span data-ttu-id="b0818-120">Nella casella **Nome** digitare `DataRepeaterApp`.</span><span class="sxs-lookup"><span data-stu-id="b0818-120">In the **Name** box, type `DataRepeaterApp`.</span></span>  
  
5.  <span data-ttu-id="b0818-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b0818-121">Click **OK**.</span></span>  
  
     <span data-ttu-id="b0818-122">Verrà aperto Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b0818-122">The Windows Forms Designer opens.</span></span>  
  
6.  <span data-ttu-id="b0818-123">Selezionare il form in Progettazione Windows Form.</span><span class="sxs-lookup"><span data-stu-id="b0818-123">Select the form in the Windows Forms Designer.</span></span> <span data-ttu-id="b0818-124">Nella finestra **Proprietà** impostare la proprietà **Size** su `800, 700`.</span><span class="sxs-lookup"><span data-stu-id="b0818-124">In the **Properties** window, set the **Size** property to `800, 700`.</span></span>  
  
## <a name="adding-a-datarepeater-control"></a><span data-ttu-id="b0818-125">Aggiunta di un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="b0818-125">Adding a DataRepeater Control</span></span>  
 <span data-ttu-id="b0818-126">In questo passaggio, aggiungere un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>al form.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-126">In this step, you add a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to the form.</span></span>  
  
#### <a name="to-add-a-datarepeater-control"></a><span data-ttu-id="b0818-127">Per aggiungere un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="b0818-127">To add a DataRepeater control</span></span>  
  
1.  <span data-ttu-id="b0818-128">Scegliere **Casella degli strumenti** dal menu **Visualizza**.</span><span class="sxs-lookup"><span data-stu-id="b0818-128">On the **View** menu, click **Toolbox**.</span></span>  
  
     <span data-ttu-id="b0818-129">Verrà aperta la **Casella degli strumenti** .</span><span class="sxs-lookup"><span data-stu-id="b0818-129">The **Toolbox** opens.</span></span>  
  
2.  <span data-ttu-id="b0818-130">Selezionare la scheda **Visual Basic PowerPacks** .</span><span class="sxs-lookup"><span data-stu-id="b0818-130">Select the **Visual Basic PowerPacks** tab.</span></span>  
  
3.  <span data-ttu-id="b0818-131">Trascinare un <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo **Form1**.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-131">Drag a <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control onto **Form1**.</span></span>  
  
4.  <span data-ttu-id="b0818-132">Nella finestra Proprietà impostare la proprietà **Location** su `0, 25`.</span><span class="sxs-lookup"><span data-stu-id="b0818-132">In the Properties window, set the **Location** property to `0, 25`.</span></span>  
  
5.  <span data-ttu-id="b0818-133">Impostare la proprietà **Size** su `460, 600`.</span><span class="sxs-lookup"><span data-stu-id="b0818-133">Set the **Size** property to `460, 600`.</span></span>  
  
## <a name="adding-a-data-source"></a><span data-ttu-id="b0818-134">Aggiunta di un'origine dati</span><span class="sxs-lookup"><span data-stu-id="b0818-134">Adding a Data Source</span></span>  
 <span data-ttu-id="b0818-135">In questo passaggio si aggiunge un'origine dati per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-135">In this step, you add a data source for the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-add-a-data-source"></a><span data-ttu-id="b0818-136">Per aggiungere un'origine dati</span><span class="sxs-lookup"><span data-stu-id="b0818-136">To add a data source</span></span>  
  
1.  <span data-ttu-id="b0818-137">Scegliere **Mostra origini dati** dal menu **Dati**.</span><span class="sxs-lookup"><span data-stu-id="b0818-137">On the **Data** menu, click **Show Data Sources**.</span></span>  
  
2.  <span data-ttu-id="b0818-138">Nella finestra **Origini dati** fare clic su **Aggiungi nuova origine dati**.</span><span class="sxs-lookup"><span data-stu-id="b0818-138">In the **Data Sources** window, click **Add New Data Source**.</span></span>  
  
3.  <span data-ttu-id="b0818-139">Selezionare **Database** nella pagina **Scegliere un tipo di origine dati** e scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b0818-139">Select **Database** on the **Choose a Data Source Type** page, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="b0818-140">Nella pagina **Seleziona connessione dati** , eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b0818-140">On the **Choose Your Data Connection** page, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="b0818-141">Se disponibile nell'elenco a discesa, scegliere la connessione dati al database di esempio Northwind.</span><span class="sxs-lookup"><span data-stu-id="b0818-141">If a data connection to the Northwind sample database is available in the drop-down list, click it.</span></span>  
  
         <span data-ttu-id="b0818-142">-oppure-</span><span class="sxs-lookup"><span data-stu-id="b0818-142">-or-</span></span>  
  
    -   <span data-ttu-id="b0818-143">Scegliere **Nuova connessione** per configurare una nuova connessione dati.</span><span class="sxs-lookup"><span data-stu-id="b0818-143">Click **New Connection** to configure a new data connection.</span></span> <span data-ttu-id="b0818-144">Per ulteriori informazioni, vedere [procedura: creare connessioni a database di SQL Server](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).</span><span class="sxs-lookup"><span data-stu-id="b0818-144">For more information, see [How to: Create Connections to SQL Server Databases](http://msdn.microsoft.com/en-us/360c340d-e5a6-4a7e-a569-e95d500be43d).</span></span>  
  
5.  <span data-ttu-id="b0818-145">Se il database richiede una password, selezionare l'opzione che consente di includere dati riservati, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="b0818-145">If the database requires a password, select the option to include sensitive data, and then click **Next**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0818-146">Se viene visualizzata una finestra di dialogo, scegliere **Sì** per salvare il file nel progetto.</span><span class="sxs-lookup"><span data-stu-id="b0818-146">If a dialog box appears, click **Yes** to save the file to your project.</span></span>  
  
6.  <span data-ttu-id="b0818-147">Nella pagina **Salva stringa di connessione nel file di configurazione dell'applicazione** fare clic su **Avanti** .</span><span class="sxs-lookup"><span data-stu-id="b0818-147">Click **Next** on the **Save Connection String to the Application Configuration file** page.</span></span>  
  
7.  <span data-ttu-id="b0818-148">Espandere il nodo **Tabelle** nella pagina **Seleziona oggetti di database** .</span><span class="sxs-lookup"><span data-stu-id="b0818-148">Expand the **Tables** node on the **Choose Your Database Objects** page.</span></span>  
  
8.  <span data-ttu-id="b0818-149">Selezionare le caselle di controllo accanto alle tabelle **Customers** e **Orders** , quindi fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="b0818-149">Select the check boxes next to the **Customers** and **Orders** tables, and then click **Finish**.</span></span>  
  
     <span data-ttu-id="b0818-150">L'oggetto**NorthwindDataSet** viene aggiunto al progetto e le tabelle **Customers** e **Orders** vengono visualizzate nella finestra **Origini dati** .</span><span class="sxs-lookup"><span data-stu-id="b0818-150">**NorthwindDataSet** is added to your project and the **Customers** and **Orders** tables appear in the **Data Sources** window.</span></span>  
  
## <a name="adding-data-bound-controls"></a><span data-ttu-id="b0818-151">Aggiunta di controlli con associazione a dati</span><span class="sxs-lookup"><span data-stu-id="b0818-151">Adding Data-Bound Controls</span></span>  
 <span data-ttu-id="b0818-152">In questo passaggio, aggiungere controlli associati a dati <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-152">In this step, you add data-bound controls to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>.</span></span>  
  
#### <a name="to-add-data-bound-controls"></a><span data-ttu-id="b0818-153">Per aggiungere controlli con associazione a dati</span><span class="sxs-lookup"><span data-stu-id="b0818-153">To add data-bound controls</span></span>  
  
1.  <span data-ttu-id="b0818-154">Nella finestra **Origini dati** selezionare il nodo di livello principale della tabella **Customers** .</span><span class="sxs-lookup"><span data-stu-id="b0818-154">In the **Data Sources** window, select the top-level node for the **Customers** table.</span></span>  
  
2.  <span data-ttu-id="b0818-155">Modificare il tipo di rilascio della tabella in **Dettagli** selezionando **Dettagli** dall'elenco a discesa nel nodo della tabella.</span><span class="sxs-lookup"><span data-stu-id="b0818-155">Change the drop type of the table to **Details** by clicking **Details** in the drop-down list on the table node.</span></span>  
  
3.  <span data-ttu-id="b0818-156">Selezionare il **clienti** tabella nodo e trascinarlo nell'area del modello di elemento (l'area superiore) del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-156">Select the **Customers** table node and drag it onto the item template region (the upper region) of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="b0818-157">Oggetto <xref:System.Windows.Forms.BindingNavigator>controllo viene aggiunto al form e **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, e **CustomersBindingNavigator** componenti vengono aggiunti alla barra dei componenti.</xref:System.Windows.Forms.BindingNavigator></span><span class="sxs-lookup"><span data-stu-id="b0818-157">A <xref:System.Windows.Forms.BindingNavigator> control is added to the form, and the **NorthwindDataSet**, **CustomersBindingSource**, **CustomersTableAdapter**, **TableAdapterManager**, and **CustomersBindingNavigator** components are added to the Component Tray.</span></span>  
  
4.  <span data-ttu-id="b0818-158">Selezionare tutti i campi e le etichette corrispondenti e posizionarli vicino al bordo sinistro dell'area modello dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="b0818-158">Select all of the fields and their associated labels and position them near the left edge of the item template region.</span></span>  
  
5.  <span data-ttu-id="b0818-159">Selezionare gli ultimi cinque campi (**Region**, **Postal Code**, **Country**, **Phone**e **Fax**) e le etichette corrispondenti e spostarli in alto e a destra dei primi sei campi.</span><span class="sxs-lookup"><span data-stu-id="b0818-159">Select the last five fields (**Region**, **Postal Code**, **Country**, **Phone**, and **Fax**) and their associated labels and move them up and to the right of the first six fields.</span></span>  
  
6.  <span data-ttu-id="b0818-160">Selezionare il modello di elemento (l'area superiore del controllo).</span><span class="sxs-lookup"><span data-stu-id="b0818-160">Select the item template (the upper region of the control).</span></span>  
  
7.  <span data-ttu-id="b0818-161">Nella finestra Proprietà impostare la proprietà **Size** su `427, 170`.</span><span class="sxs-lookup"><span data-stu-id="b0818-161">In the Properties window, set the **Size** property to `427, 170`.</span></span>  
  
 <span data-ttu-id="b0818-162">A questo punto si dispone di un'applicazione funzionante che visualizzerà un elenco ripetuto di clienti.</span><span class="sxs-lookup"><span data-stu-id="b0818-162">At this point, you have a working application that will display a repeating list of customers.</span></span> <span data-ttu-id="b0818-163">Premere F5 per eseguire l'applicazione, modificare i dati e aggiungere o eliminare i record cliente.</span><span class="sxs-lookup"><span data-stu-id="b0818-163">You can press F5 to run the application, change the data, and add or delete customer records.</span></span>  
  
 <span data-ttu-id="b0818-164">Nei passaggi facoltativi, si apprenderà come personalizzare il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-164">In the next optional steps, you will learn how to customize the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="next-steps-optional"></a><span data-ttu-id="b0818-165">Passaggi successivi (facoltativi)</span><span class="sxs-lookup"><span data-stu-id="b0818-165">Next Steps (Optional)</span></span>  
 <span data-ttu-id="b0818-166">Questa parte della procedura dettagliata è costituita da quattro attività facoltative:</span><span class="sxs-lookup"><span data-stu-id="b0818-166">This part of the walkthrough consists of four optional tasks:</span></span>  
  
-   <span data-ttu-id="b0818-167">Modifica dell'aspetto di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-167">Changing the appearance of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="b0818-168">Impedire agli utenti di aggiungere o eliminare record.</span><span class="sxs-lookup"><span data-stu-id="b0818-168">Preventing users from adding or deleting records.</span></span>  
  
-   <span data-ttu-id="b0818-169">Aggiunta di funzionalità di ricerca per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-169">Adding search capability to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
-   <span data-ttu-id="b0818-170">Aggiunta di una tabella master e di dettaglio per il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-170">Adding a master and detail table to the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="changing-the-appearance-of-the-datarepeater-control"></a><span data-ttu-id="b0818-171">Modifica dell'aspetto di un controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="b0818-171">Changing the Appearance of the DataRepeater Control</span></span>  
 <span data-ttu-id="b0818-172">In questo passaggio facoltativo, si modifica il `BackColor` del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo in fase di progettazione.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-172">In this optional step, you change the `BackColor` of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control at design time.</span></span> <span data-ttu-id="b0818-173">È anche possibile aggiungere codice per visualizzare le righe in colori alternati e modificare il `ForeColor` di un'etichetta in modo condizionale.</span><span class="sxs-lookup"><span data-stu-id="b0818-173">You also add code to display rows in alternating colors and to change a label's `ForeColor` conditionally.</span></span>  
  
#### <a name="to-change-the-appearance-of-the-control"></a><span data-ttu-id="b0818-174">Per modificare l'aspetto del controllo</span><span class="sxs-lookup"><span data-stu-id="b0818-174">To change the appearance of the control</span></span>  
  
1.  <span data-ttu-id="b0818-175">In Progettazione Windows Form, selezionare l'area principale (inferiore) del <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-175">In the Windows Forms Designer, select the main (lower) region of the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="b0818-176">Nella finestra Proprietà impostare la proprietà `BackColor` su bianco.</span><span class="sxs-lookup"><span data-stu-id="b0818-176">In the Properties window, set the `BackColor` property to white.</span></span>  
  
3.  <span data-ttu-id="b0818-177">Fare doppio clic su di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>per aprire l'Editor di codice.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-177">Double-click the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> to open the Code Editor.</span></span>  
  
4.  <span data-ttu-id="b0818-178">Nell'elenco a discesa Event dell'editor di codice, selezionare **DrawItem**.</span><span class="sxs-lookup"><span data-stu-id="b0818-178">In the Code Editor, in the Event drop-down list, click **DrawItem**.</span></span>  
  
5.  <span data-ttu-id="b0818-179">Nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>gestore dell'evento, aggiungere il codice seguente per alternare il `BackColor`:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem></span><span class="sxs-lookup"><span data-stu-id="b0818-179">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to alternate the `BackColor`:</span></span>  
  
     <span data-ttu-id="b0818-180">[!code-cs[N.&1; VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough n.&1;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="b0818-180">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_1.vb)]</span></span>  
  
6.  <span data-ttu-id="b0818-181">Nel <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem>gestore dell'evento, aggiungere il codice seguente per modificare il `ForeColor` di un'etichetta in base a una condizione:</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem></span><span class="sxs-lookup"><span data-stu-id="b0818-181">In the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater.DrawItem> event handler, add the following code to change the `ForeColor` of a label depending on a condition:</span></span>  
  
     <span data-ttu-id="b0818-182">[!code-cs[N.&2; VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough n.&2;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="b0818-182">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_2.vb)]</span></span>  
  
7.  <span data-ttu-id="b0818-183">Premere F5 per eseguire l'applicazione e visualizzare la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="b0818-183">Press F5 to run the application and see the customizations.</span></span>  
  
## <a name="preventing-users-from-adding-or-deleting-records"></a><span data-ttu-id="b0818-184">Impedire agli utenti di aggiungere o eliminare record</span><span class="sxs-lookup"><span data-stu-id="b0818-184">Preventing Users from Adding or Deleting Records</span></span>  
 <span data-ttu-id="b0818-185">In questo passaggio facoltativo, aggiungere il codice che impedisce agli utenti di aggiungere o eliminare i record di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-185">In this optional step, you add code that prevents users from adding or deleting records in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
#### <a name="to-prevent-users-from-adding-and-deleting-records"></a><span data-ttu-id="b0818-186">Per impedire agli utenti di aggiungere o eliminare record</span><span class="sxs-lookup"><span data-stu-id="b0818-186">To prevent users from adding and deleting records</span></span>  
  
1.  <span data-ttu-id="b0818-187">In Progettazione Windows Form, fare doppio clic sul form per aprire l'editor di codice.</span><span class="sxs-lookup"><span data-stu-id="b0818-187">In the Windows Forms Designer, double-click the form to open the Code Editor.</span></span>  
  
2.  <span data-ttu-id="b0818-188">Aggiungere il codice seguente all'evento `Form_Load` :</span><span class="sxs-lookup"><span data-stu-id="b0818-188">Add the following code to the `Form_Load` event:</span></span>  
  
     <span data-ttu-id="b0818-189">[!code-cs[N.&3; VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough n.&3;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="b0818-189">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#3](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_3.vb)]</span></span>  
  
3.  <span data-ttu-id="b0818-190">Nell'elenco a discesa Class Name, fare clic su **BindingNavigatorDeleteItem**.</span><span class="sxs-lookup"><span data-stu-id="b0818-190">In the Class Name drop-down list, click **BindingNavigatorDeleteItem**.</span></span> <span data-ttu-id="b0818-191">Nell'elenco a discesa Method Name, fare clic su **EnabledChanged**.</span><span class="sxs-lookup"><span data-stu-id="b0818-191">In the Method Name drop-down list, click **EnabledChanged**.</span></span>  
  
4.  <span data-ttu-id="b0818-192">Aggiungere il codice seguente al gestore eventi `BindingNavigatorDeleteItem_EnabledChanged` :</span><span class="sxs-lookup"><span data-stu-id="b0818-192">Add the following code to the `BindingNavigatorDeleteItem_EnabledChanged` event handler:</span></span>  
  
     <span data-ttu-id="b0818-193">[!code-cs[N.&4; VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough n.&4;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="b0818-193">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#4](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_4.vb)]</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b0818-194">Questa operazione è necessaria perché il <xref:System.Windows.Forms.BindingSource>consentirà di **DeleteItem** pulsante ogni volta che viene modificato il record corrente.</xref:System.Windows.Forms.BindingSource></span><span class="sxs-lookup"><span data-stu-id="b0818-194">This step is necessary because the <xref:System.Windows.Forms.BindingSource> will enable the **DeleteItem** button every time that the current record changes.</span></span>  
  
5.  <span data-ttu-id="b0818-195">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0818-195">Press F5 to run the application.</span></span> <span data-ttu-id="b0818-196">Notare che il pulsante **DeleteItem** pulsante è disabilitato e non è possibile eliminare elementi premendo il tasto CANC.</span><span class="sxs-lookup"><span data-stu-id="b0818-196">Notice that the **DeleteItem** button is disabled and that you cannot delete items by pressing the DELETE key.</span></span>  
  
## <a name="adding-search-capability-to-the-datarepeater-control"></a><span data-ttu-id="b0818-197">Aggiunta di funzionalità di ricerca al controllo DataRepeater</span><span class="sxs-lookup"><span data-stu-id="b0818-197">Adding Search Capability to the DataRepeater Control</span></span>  
 <span data-ttu-id="b0818-198">In questo passaggio facoltativo, si implementa la funzionalità di ricerca per un valore di <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-198">In this optional step, you implement the capability to search for a value in the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="b0818-199">Se viene individuata la stringa di ricerca, il controllo seleziona l'elemento che contiene il valore e scorre l'elemento nella visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="b0818-199">If the search string is found, the control selects the item that contains the value and scrolls the item into view.</span></span>  
  
#### <a name="to-add-search-capability"></a><span data-ttu-id="b0818-200">Per aggiungere funzionalità di ricerca</span><span class="sxs-lookup"><span data-stu-id="b0818-200">To add search capability</span></span>  
  
1.  <span data-ttu-id="b0818-201">Trascinare un <xref:System.Windows.Forms.TextBox>da controllare il **della casella degli strumenti** nel form che contiene il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.TextBox></span><span class="sxs-lookup"><span data-stu-id="b0818-201">Drag a <xref:System.Windows.Forms.TextBox> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="b0818-202">Posizionarlo sotto il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-202">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
2.  <span data-ttu-id="b0818-203">Nella finestra Proprietà modificare la proprietà **Name** in **SearchTextBox**.</span><span class="sxs-lookup"><span data-stu-id="b0818-203">In the Properties window, change the **Name** property to **SearchTextBox**.</span></span>  
  
3.  <span data-ttu-id="b0818-204">Trascinare un <xref:System.Windows.Forms.Button>da controllare il **della casella degli strumenti** nel form che contiene il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="b0818-204">Drag a <xref:System.Windows.Forms.Button> control from the **Toolbox** onto the form that contains the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span> <span data-ttu-id="b0818-205">Posizionarlo sotto il <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-205">Position it under the <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
4.  <span data-ttu-id="b0818-206">Nella finestra Proprietà modificare la proprietà **Name** in **SearchButton**.</span><span class="sxs-lookup"><span data-stu-id="b0818-206">In the Properties window, change the **Name** property to **SearchButton**.</span></span> <span data-ttu-id="b0818-207">Impostare la proprietà **Text** su **Search**.</span><span class="sxs-lookup"><span data-stu-id="b0818-207">Change the **Text** property to **Search**.</span></span>  
  
5.  <span data-ttu-id="b0818-208">Fare doppio clic su di <xref:System.Windows.Forms.Button>di controllo per aprire l'Editor di codice e aggiungere il codice seguente per il `SearchButton_Click` gestore dell'evento.</xref:System.Windows.Forms.Button></span><span class="sxs-lookup"><span data-stu-id="b0818-208">Double-click the <xref:System.Windows.Forms.Button> control to open the Code Editor, and add the following code to the `SearchButton_Click` event handler.</span></span>  
  
     <span data-ttu-id="b0818-209">[!code-cs[N.&5; VbPowerPacksDataRepeaterWalkthrough](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs) ] 
     [!code-vb [VbPowerPacksDataRepeaterWalkthrough n.&5;](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="b0818-209">[!code-cs[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.cs)]
 [!code-vb[VbPowerPacksDataRepeaterWalkthrough#5](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/walkthrough-displaying-data-in-a-datarepeater-control-visual-studio_5.vb)]</span></span>  
  
6.  <span data-ttu-id="b0818-210">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0818-210">Press F5 to run the application.</span></span> <span data-ttu-id="b0818-211">Digitare un ID cliente in **SearchTextBox** e fare clic sul pulsante **Search** .</span><span class="sxs-lookup"><span data-stu-id="b0818-211">Type a customer ID in **SearchTextBox** and click the **Search** button.</span></span>  
  
## <a name="adding-a-master-and-detail-table-to-the-datarepeater"></a><span data-ttu-id="b0818-212">Aggiunta di una tabella master e di dettaglio per il controllo</span><span class="sxs-lookup"><span data-stu-id="b0818-212">Adding a Master and Detail Table to the DataRepeater</span></span>  
 <span data-ttu-id="b0818-213">In questo passaggio facoltativo, verrà aggiunta una seconda <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo per visualizzare gli ordini correlati per ogni cliente.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-213">In this optional step, you add a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control to display related orders for each customer.</span></span>  
  
#### <a name="to-add-a-master-and-detail-table"></a><span data-ttu-id="b0818-214">Per aggiungere una tabella master e di dettaglio</span><span class="sxs-lookup"><span data-stu-id="b0818-214">To add a master and detail table</span></span>  
  
1.  <span data-ttu-id="b0818-215">Trascinare una seconda <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo il **Visual Basic Power Packs** nella scheda il **della casella degli strumenti** nel form.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-215">Drag a second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control from the **Visual Basic PowerPacks** tab in the **Toolbox** onto the form.</span></span>  
  
2.  <span data-ttu-id="b0818-216">Nella finestra Proprietà impostare la proprietà **Location** su `465, 25`.</span><span class="sxs-lookup"><span data-stu-id="b0818-216">In the Properties window, set the **Location** property to `465, 25`.</span></span>  
  
3.  <span data-ttu-id="b0818-217">Impostare la proprietà **Size** su `315, 600`.</span><span class="sxs-lookup"><span data-stu-id="b0818-217">Set the **Size** property to `315, 600`.</span></span>  
  
4.  <span data-ttu-id="b0818-218">Nella finestra **Origini dati** espandere il nodo della tabella **Customers** e selezionare il nodo dettaglio della tabella **Orders** .</span><span class="sxs-lookup"><span data-stu-id="b0818-218">In the **Data Sources** window, expand the **Customers** table node and select the detail node for the **Orders** table.</span></span>  
  
5.  <span data-ttu-id="b0818-219">Modificare il tipo di rilascio della tabella **Orders** selezionando **Details** dall'elenco a discesa nel nodo della tabella.</span><span class="sxs-lookup"><span data-stu-id="b0818-219">Change the drop type of this **Orders** table to Details by clicking **Details** in the drop-down list on the table node.</span></span>  
  
6.  <span data-ttu-id="b0818-220">Trascinare questo **ordini** area del modello di elemento (l'area superiore) del secondo nodo della tabella <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-220">Drag this **Orders** table node onto the item template region (the upper region) of the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
     <span data-ttu-id="b0818-221">Alla barra dei componenti vengono aggiunti il componente **OrdersBindingSource** e il componente **OrdersTableAdapter** .</span><span class="sxs-lookup"><span data-stu-id="b0818-221">An **OrdersBindingSource** component and an **OrdersTableAdapter** component are added to the Component Tray.</span></span>  
  
7.  <span data-ttu-id="b0818-222">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="b0818-222">Press F5 to run the application.</span></span> <span data-ttu-id="b0818-223">Quando si seleziona ogni cliente nel primo <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllare, gli ordini per quel cliente vengono visualizzati nella seconda <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater>controllo.</xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> </xref:Microsoft.VisualBasic.PowerPacks.DataRepeater></span><span class="sxs-lookup"><span data-stu-id="b0818-223">When you select each customer in the first <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control, the orders for that customer are displayed in the second <xref:Microsoft.VisualBasic.PowerPacks.DataRepeater> control.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0818-224">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b0818-224">See Also</span></span>  
 <span data-ttu-id="b0818-225">[Introduzione al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b0818-225">[Introduction to the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="b0818-226"> [Procedura: visualizzare i dati associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b0818-226"> [How to: Display Bound Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-bound-data-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="b0818-227"> [Procedura: visualizzazione controlli non associati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b0818-227"> [How to: Display Unbound Controls in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-unbound-controls-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="b0818-228"> [Procedura: modificare il Layout di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b0818-228"> [How to: Change the Layout of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-layout-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="b0818-229"> [Procedura: visualizzare le intestazioni degli elementi in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b0818-229"> [How to: Display Item Headers in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-display-item-headers-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="b0818-230"> [Procedura: cercare dati in un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b0818-230"> [How to: Search Data in a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-search-data-in-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="b0818-231"> [Procedura: creare un Form Master-Details mediante due controlli DataRepeater (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span><span class="sxs-lookup"><span data-stu-id="b0818-231"> [How to: Create a Master/Detail Form by Using Two DataRepeater Controls (Visual Studio)](../../../visual-basic/developing-apps/windows-forms/how-to-create-a-master-detail-form-by-using-two-datarepeater-controls.md) </span></span>  
<span data-ttu-id="b0818-232"> [Procedura: modificare l'aspetto di un controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b0818-232"> [How to: Change the Appearance of a DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/how-to-change-the-appearance-of-a-datarepeater-control-visual-studio.md) </span></span>  
<span data-ttu-id="b0818-233"> [Procedura: disabilitare l'aggiunta e l'eliminazione di elementi DataRepeater](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md) </span><span class="sxs-lookup"><span data-stu-id="b0818-233"> [How to: Disable Adding and Deleting DataRepeater Items](../../../visual-basic/developing-apps/windows-forms/how-to-disable-adding-and-deleting-datarepeater-items-visual-studio.md) </span></span>  
<span data-ttu-id="b0818-234"> [Risoluzione dei problemi relativi al controllo DataRepeater](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="b0818-234"> [Troubleshooting the DataRepeater Control](../../../visual-basic/developing-apps/windows-forms/troubleshooting-the-datarepeater-control-visual-studio.md)</span></span>
