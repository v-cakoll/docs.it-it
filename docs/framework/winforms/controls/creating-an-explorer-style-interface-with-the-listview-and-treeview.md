---
title: "Procedura dettagliata: Creazione di un'interfaccia di tipo Esplora risorse con i controlli ListView e TreeView usando la finestra di progettazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Explorer-style applications [Windows Forms], walkthroughs
- TreeView control [Windows Forms], ListView controls used with
- ListView control [Windows Forms], TreeView controls used with
- Explorer-style applications
- TreeView control [Windows Forms], using for explorer-style interface
- ListView control [Windows Forms], explorer style interface
- ListView control [Windows Forms], explorer-style interface
ms.assetid: 9e5e7721-19e2-4890-b273-a43589fe99ff
ms.openlocfilehash: c8f6e51b5ab8242ba8253a04160c40e59fce0088
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648193"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="7849b-102">Procedura dettagliata: Creazione di un'interfaccia di tipo Esplora risorse con i controlli ListView e TreeView usando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="7849b-102">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>
<span data-ttu-id="7849b-103">Uno dei vantaggi di Visual Studio è la possibilità di creare rapidamente applicazioni di Windows Forms dall'aspetto professionale della quantità di tempo.</span><span class="sxs-lookup"><span data-stu-id="7849b-103">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="7849b-104">Uno scenario comune consiste nel creare un'interfaccia utente (UI) con <xref:System.Windows.Forms.ListView> e <xref:System.Windows.Forms.TreeView> controlli simile alla funzionalità di Windows Explorer dei sistemi operativi Windows.</span><span class="sxs-lookup"><span data-stu-id="7849b-104">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="7849b-105">Windows Explorer visualizza una struttura gerarchica di file e cartelle nel computer dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7849b-105">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="7849b-106">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="7849b-106">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="7849b-107">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="7849b-107">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="7849b-108">Per altre informazioni, vedere [Personalizzare l'IDE di Visual Studio](/visualstudio/ide/personalizing-the-visual-studio-ide).</span><span class="sxs-lookup"><span data-stu-id="7849b-108">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="7849b-109">Per creare il modulo che contiene un controllo ListView e TreeView</span><span class="sxs-lookup"><span data-stu-id="7849b-109">To create the form containing a ListView and TreeView control</span></span>  
  
1. <span data-ttu-id="7849b-110">Scegliere **Nuovo** dal menu **File**, quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="7849b-110">On the **File** menu, point to **New**, and then click **Project**.</span></span>  
  
2. <span data-ttu-id="7849b-111">Nel **nuovo progetto** dialogo casella, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7849b-111">In the **New Project** dialog box, do the following:</span></span>  
  
    1. <span data-ttu-id="7849b-112">Nelle categorie, scegliere **Visual Basic** oppure **Visual c#**.</span><span class="sxs-lookup"><span data-stu-id="7849b-112">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>  
  
    2. <span data-ttu-id="7849b-113">Nell'elenco dei modelli, scegliere **Windows Forms Application**.</span><span class="sxs-lookup"><span data-stu-id="7849b-113">In the list of templates, choose **Windows Forms Application**.</span></span>  
  
3. <span data-ttu-id="7849b-114">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="7849b-114">Click **OK**.</span></span> <span data-ttu-id="7849b-115">Viene creato un nuovo progetto Windows Form.</span><span class="sxs-lookup"><span data-stu-id="7849b-115">A new Windows Forms project is created.</span></span>  
  
4. <span data-ttu-id="7849b-116">Aggiungere un <xref:System.Windows.Forms.SplitContainer> controllo al form e impostarne relativi <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="7849b-116">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
5. <span data-ttu-id="7849b-117">Aggiungere un <xref:System.Windows.Forms.ImageList> denominato `imageList1` al form e utilizzare la finestra delle proprietà per aggiungere due immagini: un'immagine di una cartella e un'immagine di documento, in quest'ordine.</span><span class="sxs-lookup"><span data-stu-id="7849b-117">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>  
  
6. <span data-ttu-id="7849b-118">Aggiungere un <xref:System.Windows.Forms.TreeView> controllo denominato `treeview1` al form e posizionarla a sinistra del <xref:System.Windows.Forms.SplitContainer> controllo.</span><span class="sxs-lookup"><span data-stu-id="7849b-118">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="7849b-119">Nella finestra proprietà per `treeView1` eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7849b-119">In the Properties window for `treeView1` do the following:</span></span>  
  
    1. <span data-ttu-id="7849b-120">Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="7849b-120">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    2. <span data-ttu-id="7849b-121">Impostare la proprietà <xref:System.Windows.Forms.TreeView.ImageList%2A> su `imagelist1.`</span><span class="sxs-lookup"><span data-stu-id="7849b-121">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>  
  
7. <span data-ttu-id="7849b-122">Aggiungere un <xref:System.Windows.Forms.ListView> controllo denominato `listView1` al form e posizionarlo a destra del <xref:System.Windows.Forms.SplitContainer> controllo.</span><span class="sxs-lookup"><span data-stu-id="7849b-122">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="7849b-123">Nella finestra proprietà per `listview1` eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="7849b-123">In the Properties window for `listview1` do the following:</span></span>  
  
    1. <span data-ttu-id="7849b-124">Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="7849b-124">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>  
  
    2. <span data-ttu-id="7849b-125">Impostare la proprietà <xref:System.Windows.Forms.ListView.View%2A> su <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="7849b-125">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>  
  
    3. <span data-ttu-id="7849b-126">Aprire l'Editor della raccolta ColumnHeader facendo clic sui puntini di sospensione (![schermata di VisualStudioEllipsesButton](../media/vbellipsesbutton.png "vbEllipsesButton")) nella <xref:System.Windows.Forms.ListView.Columns%2A> proprietà **.**</span><span class="sxs-lookup"><span data-stu-id="7849b-126">Open the ColumnHeader Collection Editor by clicking the ellipses (![VisualStudioEllipsesButton screenshot](../media/vbellipsesbutton.png "vbEllipsesButton")) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="7849b-127">Aggiungere tre colonne e impostare loro <xref:System.Windows.Forms.ColumnHeader.Text%2A> proprietà `Name`, `Type`, e `Last Modified`, rispettivamente.</span><span class="sxs-lookup"><span data-stu-id="7849b-127">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="7849b-128">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="7849b-128">Click **OK** to close the dialog box.</span></span>  
  
    4. <span data-ttu-id="7849b-129">Impostare la proprietà <xref:System.Windows.Forms.ListView.SmallImageList%2A> su `imageList1.`</span><span class="sxs-lookup"><span data-stu-id="7849b-129">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>  
  
8. <span data-ttu-id="7849b-130">Implementare il codice per popolare il <xref:System.Windows.Forms.TreeView> con nodi principali e secondari.</span><span class="sxs-lookup"><span data-stu-id="7849b-130">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="7849b-131">Aggiungere questo codice per il `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="7849b-131">Add this code to the `Form1` class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]  
  
9. <span data-ttu-id="7849b-132">Poiché il codice precedente Usa lo spazio dei nomi System.IO, aggiungere l'utilizzo appropriato o Importa istruzione nella parte superiore del form.</span><span class="sxs-lookup"><span data-stu-id="7849b-132">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]  
  
10. <span data-ttu-id="7849b-133">Chiamare il metodo di configurazione nel passaggio precedente nel costruttore del form o <xref:System.Windows.Forms.Form.Load> metodo di gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="7849b-133">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="7849b-134">Aggiungere questo codice al costruttore del form.</span><span class="sxs-lookup"><span data-stu-id="7849b-134">Add this code to the form constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]  
  
11. <span data-ttu-id="7849b-135">Gestire il <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento `treeview1` **,** e implementare il codice per popolare `listview1` con contenuto di un nodo quando si fa clic su un nodo.</span><span class="sxs-lookup"><span data-stu-id="7849b-135">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="7849b-136">Aggiungere questo codice per il `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="7849b-136">Add this code to the `Form1` class.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]  
  
     <span data-ttu-id="7849b-137">Se si usa c#, assicurarsi di avere il <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento associato al relativo metodo di gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="7849b-137">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="7849b-138">Aggiungere questo codice al costruttore del form.</span><span class="sxs-lookup"><span data-stu-id="7849b-138">Add this code to the form constructor.</span></span>  
  
     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]  
  
## <a name="testing-the-application"></a><span data-ttu-id="7849b-139">Verifica dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="7849b-139">Testing the Application</span></span>  
 <span data-ttu-id="7849b-140">È ora possibile testare il form per assicurarsi che tutto funzioni come previsto.</span><span class="sxs-lookup"><span data-stu-id="7849b-140">You can now test the form to make sure it behaves as expected.</span></span>  
  
#### <a name="to-test-the-form"></a><span data-ttu-id="7849b-141">Per testare il form</span><span class="sxs-lookup"><span data-stu-id="7849b-141">To test the form</span></span>  
  
- <span data-ttu-id="7849b-142">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="7849b-142">Press F5 to run the application.</span></span>  
  
     <span data-ttu-id="7849b-143">Verrà visualizzato un form di split contenente un <xref:System.Windows.Forms.TreeView> controllo che visualizza la directory del progetto sul lato sinistro, e un <xref:System.Windows.Forms.ListView> controllo sul lato destro con tre colonne.</span><span class="sxs-lookup"><span data-stu-id="7849b-143">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="7849b-144">È possibile attraversare il <xref:System.Windows.Forms.TreeView> selezionando i nodi di directory e il <xref:System.Windows.Forms.ListView> viene popolato con il contenuto della directory selezionata.</span><span class="sxs-lookup"><span data-stu-id="7849b-144">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="7849b-145">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="7849b-145">Next Steps</span></span>  
 <span data-ttu-id="7849b-146">Questa applicazione fornisce un esempio di come è possibile usare <xref:System.Windows.Forms.TreeView> e <xref:System.Windows.Forms.ListView> insieme i controlli.</span><span class="sxs-lookup"><span data-stu-id="7849b-146">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="7849b-147">Per altre informazioni su questi controlli, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7849b-147">For more information on these controls, see the following topics:</span></span>  
  
- [<span data-ttu-id="7849b-148">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="7849b-148">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)  
  
- [<span data-ttu-id="7849b-149">Procedura: Aggiungere le funzionalità di ricerca a un controllo ListView</span><span class="sxs-lookup"><span data-stu-id="7849b-149">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)  
  
- [<span data-ttu-id="7849b-150">Procedura: Associare un Menu di scelta rapida a un nodo di TreeView</span><span class="sxs-lookup"><span data-stu-id="7849b-150">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)  
  
## <a name="see-also"></a><span data-ttu-id="7849b-151">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7849b-151">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="7849b-152">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="7849b-152">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="7849b-153">Procedura: Aggiungere e rimuovere nodi con il controllo TreeView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7849b-153">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="7849b-154">Procedura: Aggiungere e rimuovere elementi con il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="7849b-154">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="7849b-155">Procedura: Aggiungere colonne al controllo ListView Windows Form</span><span class="sxs-lookup"><span data-stu-id="7849b-155">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
