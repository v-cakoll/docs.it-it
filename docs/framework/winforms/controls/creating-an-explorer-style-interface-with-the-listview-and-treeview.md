---
title: "Procedura dettagliata: Creazione di un'interfaccia di tipo Esplora risorse con i controlli ListView e TreeView utilizzando la finestra di progettazione"
description: Informazioni su come creare un'interfaccia di tipo Esplora risorse con i controlli ListView e TreeView Windows Forms usando la finestra di progettazione.
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
ms.openlocfilehash: 44d4db1ef3da85dbf411498f486882b86a05c140
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174627"
---
# <a name="walkthrough-creating-an-explorer-style-interface-with-the-listview-and-treeview-controls-using-the-designer"></a><span data-ttu-id="2c777-103">Procedura dettagliata: Creazione di un'interfaccia di tipo Esplora risorse con i controlli ListView e TreeView utilizzando la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="2c777-103">Walkthrough: Creating an Explorer Style Interface with the ListView and TreeView Controls Using the Designer</span></span>

<span data-ttu-id="2c777-104">Uno dei vantaggi di Visual Studio è la possibilità di creare applicazioni Windows Forms professionali in un breve periodo di tempo.</span><span class="sxs-lookup"><span data-stu-id="2c777-104">One of the benefits of Visual Studio is the ability to create professional-looking Windows Forms applications in a short of amount of time.</span></span> <span data-ttu-id="2c777-105">Uno scenario comune consiste nel creare un'interfaccia utente con <xref:System.Windows.Forms.ListView> <xref:System.Windows.Forms.TreeView> i controlli e che è simile alla funzionalità Esplora risorse dei sistemi operativi Windows.</span><span class="sxs-lookup"><span data-stu-id="2c777-105">A common scenario is creating a user interface (UI) with <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls that resembles the Windows Explorer feature of Windows operating systems.</span></span> <span data-ttu-id="2c777-106">Esplora risorse Visualizza una struttura gerarchica dei file e delle cartelle nel computer di un utente.</span><span class="sxs-lookup"><span data-stu-id="2c777-106">Windows Explorer displays a hierarchical structure of the files and folders on a user's computer.</span></span>

### <a name="to-create-the-form-containing-a-listview-and-treeview-control"></a><span data-ttu-id="2c777-107">Per creare il form contenente un controllo ListView e TreeView</span><span class="sxs-lookup"><span data-stu-id="2c777-107">To create the form containing a ListView and TreeView control</span></span>

1. <span data-ttu-id="2c777-108">Scegliere **Nuovo** dal menu **File**e quindi fare clic su **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="2c777-108">On the **File** menu, point to **New**, and then click **Project**.</span></span>

2. <span data-ttu-id="2c777-109">Nella finestra di dialogo **New Project** (Nuovo progetto) seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="2c777-109">In the **New Project** dialog box, do the following:</span></span>

    1. <span data-ttu-id="2c777-110">Nelle categorie scegliere **Visual Basic** o **Visual C#**.</span><span class="sxs-lookup"><span data-stu-id="2c777-110">In the categories, choose either **Visual Basic** or **Visual C#**.</span></span>

    2. <span data-ttu-id="2c777-111">Nell'elenco dei modelli scegliere **Windows Forms applicazione**.</span><span class="sxs-lookup"><span data-stu-id="2c777-111">In the list of templates, choose **Windows Forms Application**.</span></span>

3. <span data-ttu-id="2c777-112">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="2c777-112">Click **OK**.</span></span> <span data-ttu-id="2c777-113">Viene creato un nuovo progetto Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="2c777-113">A new Windows Forms project is created.</span></span>

4. <span data-ttu-id="2c777-114">Aggiungere un <xref:System.Windows.Forms.SplitContainer> controllo al form e impostare la relativa <xref:System.Windows.Forms.SplitContainer.Dock%2A> proprietà su <xref:System.Windows.Forms.DockStyle.Fill> .</span><span class="sxs-lookup"><span data-stu-id="2c777-114">Add a <xref:System.Windows.Forms.SplitContainer> control to the form and set its <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

5. <span data-ttu-id="2c777-115">Aggiungere un oggetto <xref:System.Windows.Forms.ImageList> denominato `imageList1` al modulo e usare il finestra proprietà per aggiungere due immagini: un'immagine di cartella e un'immagine del documento, in questo ordine.</span><span class="sxs-lookup"><span data-stu-id="2c777-115">Add an <xref:System.Windows.Forms.ImageList> named `imageList1` to the form and use the Properties window to add two images: a folder image and a document image, in that order.</span></span>

6. <span data-ttu-id="2c777-116">Aggiungere un <xref:System.Windows.Forms.TreeView> controllo denominato `treeview1` al form e posizionarlo sul lato sinistro del <xref:System.Windows.Forms.SplitContainer> controllo.</span><span class="sxs-lookup"><span data-stu-id="2c777-116">Add a <xref:System.Windows.Forms.TreeView> control named `treeview1` to the form, and position it on the left side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="2c777-117">Nella Finestra Proprietà per `treeView1` eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c777-117">In the Properties window for `treeView1` do the following:</span></span>

    1. <span data-ttu-id="2c777-118">Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="2c777-118">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="2c777-119">Impostare la proprietà <xref:System.Windows.Forms.TreeView.ImageList%2A> su `imagelist1.`</span><span class="sxs-lookup"><span data-stu-id="2c777-119">Set the <xref:System.Windows.Forms.TreeView.ImageList%2A> property to `imagelist1.`</span></span>

7. <span data-ttu-id="2c777-120">Aggiungere un <xref:System.Windows.Forms.ListView> controllo denominato `listView1` al form e posizionarlo sul lato destro del <xref:System.Windows.Forms.SplitContainer> controllo.</span><span class="sxs-lookup"><span data-stu-id="2c777-120">Add a <xref:System.Windows.Forms.ListView> control named `listView1` to the form, and position it on the right side of the <xref:System.Windows.Forms.SplitContainer> control.</span></span> <span data-ttu-id="2c777-121">Nella Finestra Proprietà per `listview1` eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c777-121">In the Properties window for `listview1` do the following:</span></span>

    1. <span data-ttu-id="2c777-122">Impostare la proprietà <xref:System.Windows.Forms.Control.Dock%2A> su <xref:System.Windows.Forms.DockStyle.Fill>.</span><span class="sxs-lookup"><span data-stu-id="2c777-122">Set the <xref:System.Windows.Forms.Control.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Fill>.</span></span>

    2. <span data-ttu-id="2c777-123">Impostare la proprietà <xref:System.Windows.Forms.ListView.View%2A> su <xref:System.Windows.Forms.View.Details>.</span><span class="sxs-lookup"><span data-stu-id="2c777-123">Set the <xref:System.Windows.Forms.ListView.View%2A> property to <xref:System.Windows.Forms.View.Details>.</span></span>

    3. <span data-ttu-id="2c777-124">Aprire l'editor della raccolta ColumnHeader facendo clic sui puntini di sospensione ( ![ il pulsante con i puntini di sospensione (...) nella finestra proprietà di Visual Studio. ](./media/visual-studio-ellipsis-button.png) ) nella <xref:System.Windows.Forms.ListView.Columns%2A> proprietà **.**</span><span class="sxs-lookup"><span data-stu-id="2c777-124">Open the ColumnHeader Collection Editor by clicking the ellipses (![The Ellipsis button (...) in the Properties window of Visual Studio.](./media/visual-studio-ellipsis-button.png)) in the <xref:System.Windows.Forms.ListView.Columns%2A> property **.**</span></span> <span data-ttu-id="2c777-125">Aggiungere tre colonne e impostare la relativa <xref:System.Windows.Forms.ColumnHeader.Text%2A> proprietà `Name` rispettivamente su, `Type` e `Last Modified` .</span><span class="sxs-lookup"><span data-stu-id="2c777-125">Add three columns and set their <xref:System.Windows.Forms.ColumnHeader.Text%2A> property to `Name`, `Type`, and `Last Modified`, respectively.</span></span> <span data-ttu-id="2c777-126">Fare clic su **OK** per chiudere la finestra di dialogo.</span><span class="sxs-lookup"><span data-stu-id="2c777-126">Click **OK** to close the dialog box.</span></span>

    4. <span data-ttu-id="2c777-127">Impostare la proprietà <xref:System.Windows.Forms.ListView.SmallImageList%2A> su `imageList1.`</span><span class="sxs-lookup"><span data-stu-id="2c777-127">Set the <xref:System.Windows.Forms.ListView.SmallImageList%2A> property to `imageList1.`</span></span>

8. <span data-ttu-id="2c777-128">Implementare il codice per popolare l'oggetto <xref:System.Windows.Forms.TreeView> con nodi e sottonodi.</span><span class="sxs-lookup"><span data-stu-id="2c777-128">Implement the code to populate the <xref:System.Windows.Forms.TreeView> with nodes and subnodes.</span></span> <span data-ttu-id="2c777-129">Aggiungere questo codice alla `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="2c777-129">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#1)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#1)]

9. <span data-ttu-id="2c777-130">Poiché il codice precedente usa lo spazio dei nomi System.IO, aggiungere l'istruzione using o Import appropriata nella parte superiore del form.</span><span class="sxs-lookup"><span data-stu-id="2c777-130">Since the previous code uses the System.IO namespace, add the appropriate using or import statement at the top of the form.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#4)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#4)]

10. <span data-ttu-id="2c777-131">Chiamare il metodo di impostazione del passaggio precedente nel costruttore del form o nel metodo di <xref:System.Windows.Forms.Form.Load> gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="2c777-131">Call the set-up method from the previous step in the form's constructor or <xref:System.Windows.Forms.Form.Load> event-handling method.</span></span> <span data-ttu-id="2c777-132">Aggiungere questo codice al costruttore del form.</span><span class="sxs-lookup"><span data-stu-id="2c777-132">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#2)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#2](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#2)]

11. <span data-ttu-id="2c777-133">Gestire l' <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento per `treeview1` **,** e implementare il codice per popolare `listview1` con il contenuto di un nodo quando si fa clic su un nodo.</span><span class="sxs-lookup"><span data-stu-id="2c777-133">Handle the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event for `treeview1`**,** and implement the code to populate `listview1` with a node's contents when a node is clicked.</span></span> <span data-ttu-id="2c777-134">Aggiungere questo codice alla `Form1` classe.</span><span class="sxs-lookup"><span data-stu-id="2c777-134">Add this code to the `Form1` class.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#3)]
     [!code-vb[System.Windows.Forms.ExplorerStyleInterface#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/VB/Form1.vb#3)]

     <span data-ttu-id="2c777-135">Se si usa C#, assicurarsi che l' <xref:System.Windows.Forms.TreeView.NodeMouseClick> evento sia associato al relativo metodo di gestione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="2c777-135">If you are using C#, make sure you have the <xref:System.Windows.Forms.TreeView.NodeMouseClick> event associated with its event-handling method.</span></span> <span data-ttu-id="2c777-136">Aggiungere questo codice al costruttore del form.</span><span class="sxs-lookup"><span data-stu-id="2c777-136">Add this code to the form constructor.</span></span>

     [!code-csharp[System.Windows.Forms.ExplorerStyleInterface#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ExplorerStyleInterface/CS/Form1.cs#5)]

## <a name="testing-the-application"></a><span data-ttu-id="2c777-137">Test dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="2c777-137">Testing the Application</span></span>

<span data-ttu-id="2c777-138">È ora possibile testare il form per assicurarsi che si comportano come previsto.</span><span class="sxs-lookup"><span data-stu-id="2c777-138">You can now test the form to make sure it behaves as expected.</span></span>

#### <a name="to-test-the-form"></a><span data-ttu-id="2c777-139">Per testare il modulo</span><span class="sxs-lookup"><span data-stu-id="2c777-139">To test the form</span></span>

- <span data-ttu-id="2c777-140">Premere F5 per eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="2c777-140">Press F5 to run the application.</span></span>

     <span data-ttu-id="2c777-141">Verrà visualizzato un form suddiviso contenente un <xref:System.Windows.Forms.TreeView> controllo che visualizza la directory del progetto sul lato sinistro e un <xref:System.Windows.Forms.ListView> controllo sul lato destro con tre colonne.</span><span class="sxs-lookup"><span data-stu-id="2c777-141">You will see a split form containing a <xref:System.Windows.Forms.TreeView> control that displays your project directory on the left side, and a <xref:System.Windows.Forms.ListView> control on the right side with three columns.</span></span> <span data-ttu-id="2c777-142">È possibile attraversare il <xref:System.Windows.Forms.TreeView> selezionando i nodi della directory e il <xref:System.Windows.Forms.ListView> viene popolato con il contenuto della directory selezionata.</span><span class="sxs-lookup"><span data-stu-id="2c777-142">You can traverse the <xref:System.Windows.Forms.TreeView> by selecting directory nodes, and the <xref:System.Windows.Forms.ListView> is populated with the contents of the selected directory.</span></span>

## <a name="next-steps"></a><span data-ttu-id="2c777-143">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="2c777-143">Next Steps</span></span>

<span data-ttu-id="2c777-144">Questa applicazione fornisce un esempio di come è possibile usare insieme i <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.ListView> controlli e.</span><span class="sxs-lookup"><span data-stu-id="2c777-144">This application gives you an example of a way you can use <xref:System.Windows.Forms.TreeView> and <xref:System.Windows.Forms.ListView> controls together.</span></span> <span data-ttu-id="2c777-145">Per ulteriori informazioni su questi controlli, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c777-145">For more information on these controls, see the following topics:</span></span>

- [<span data-ttu-id="2c777-146">Procedura: Aggiungere informazioni personalizzate a un controllo TreeView o ListView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="2c777-146">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>](add-custom-information-to-a-treeview-or-listview-control-wf.md)

- [<span data-ttu-id="2c777-147">Procedura: aggiungere funzionalità di ricerca a un controllo ListView</span><span class="sxs-lookup"><span data-stu-id="2c777-147">How to: Add Search Capabilities to a ListView Control</span></span>](how-to-add-search-capabilities-to-a-listview-control.md)

- [<span data-ttu-id="2c777-148">Procedura: associare un menu di scelta rapida a un nodo di TreeView</span><span class="sxs-lookup"><span data-stu-id="2c777-148">How to: Attach a ShortCut Menu to a TreeView Node</span></span>](how-to-attach-a-shortcut-menu-to-a-treeview-node.md)

## <a name="see-also"></a><span data-ttu-id="2c777-149">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2c777-149">See also</span></span>

- <xref:System.Windows.Forms.ListView>
- <xref:System.Windows.Forms.TreeView>
- [<span data-ttu-id="2c777-150">Controllo ListView</span><span class="sxs-lookup"><span data-stu-id="2c777-150">ListView Control</span></span>](listview-control-windows-forms.md)
- [<span data-ttu-id="2c777-151">Procedura: aggiungere e rimuovere nodi tramite il controllo TreeView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2c777-151">How to: Add and Remove Nodes with the Windows Forms TreeView Control</span></span>](how-to-add-and-remove-nodes-with-the-windows-forms-treeview-control.md)
- [<span data-ttu-id="2c777-152">Procedura: aggiungere e rimuovere elementi tramite il controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2c777-152">How to: Add and Remove Items with the Windows Forms ListView Control</span></span>](how-to-add-and-remove-items-with-the-windows-forms-listview-control.md)
- [<span data-ttu-id="2c777-153">Procedura: aggiungere colonne al controllo ListView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2c777-153">How to: Add Columns to the Windows Forms ListView Control</span></span>](how-to-add-columns-to-the-windows-forms-listview-control.md)
