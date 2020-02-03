---
title: Associare il controllo DataGrid a un'origine dati tramite la finestra di progettazione
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- datasets [Windows Forms], binding to DataGrid control
- data binding [Windows Forms], DataGrid control
- DataGrid control [Windows Forms], data binding
- Windows Forms controls, data binding
- bound controls [Windows Forms]
ms.assetid: 4e96e3d0-b1cc-4de1-8774-bc9970ec4554
ms.openlocfilehash: cc0a74eca40e34f06b065980d25d922b919b0c3c
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744095"
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="e5493-102">Procedura: associare il controllo DataGrid Windows Form a un'origine dati mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="e5493-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>

> [!NOTE]
> <span data-ttu-id="e5493-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="e5493-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="e5493-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="e5493-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>

 <span data-ttu-id="e5493-105">Il controllo Windows Forms <xref:System.Windows.Forms.DataGrid> è progettato in modo specifico per visualizzare le informazioni provenienti da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e5493-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="e5493-106">Per associare il controllo in fase di progettazione, è necessario impostare le proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> oppure in fase di esecuzione chiamando il metodo <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A>.</span><span class="sxs-lookup"><span data-stu-id="e5493-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="e5493-107">Sebbene sia possibile visualizzare i dati da un'ampia gamma di origini dati, le origini più tipiche sono i set di dati e le visualizzazioni dati.</span><span class="sxs-lookup"><span data-stu-id="e5493-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>

 <span data-ttu-id="e5493-108">Se l'origine dati è disponibile in fase di progettazione, ad esempio se il form contiene un'istanza di un set di dati o una vista dati, è possibile associare la griglia all'origine dati in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e5493-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="e5493-109">Sarà quindi possibile visualizzare l'anteprima dei dati nella griglia.</span><span class="sxs-lookup"><span data-stu-id="e5493-109">You can then preview what the data will look like in the grid.</span></span>

 <span data-ttu-id="e5493-110">È anche possibile associare la griglia a livello di codice, in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e5493-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="e5493-111">Questa operazione è utile quando si vuole impostare un'origine dati in base alle informazioni che si ottengono in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="e5493-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="e5493-112">Ad esempio, l'applicazione potrebbe consentire all'utente di specificare il nome di una tabella da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="e5493-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="e5493-113">È anche necessario nelle situazioni in cui l'origine dati non esiste in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e5493-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="e5493-114">Sono incluse origini dati quali matrici, raccolte, set di dati non tipizzati e lettori di dati.</span><span class="sxs-lookup"><span data-stu-id="e5493-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>

 <span data-ttu-id="e5493-115">Per la procedura seguente è necessario un progetto di **applicazione Windows** con un modulo contenente un controllo <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="e5493-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="e5493-116">Per informazioni sulla configurazione di un progetto di questo tipo, vedere [procedura: creare un progetto Windows Forms Application](/visualstudio/ide/step-1-create-a-windows-forms-application-project) e [procedura: aggiungere controlli a Windows Forms](how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="e5493-116">For information about setting up such a project, see [How to: Create a Windows Forms application project](/visualstudio/ide/step-1-create-a-windows-forms-application-project) and [How to: Add Controls to Windows Forms](how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="e5493-117">In Visual Studio 2005, per impostazione predefinita, il controllo <xref:System.Windows.Forms.DataGrid> non è presente nella **casella degli strumenti** .</span><span class="sxs-lookup"><span data-stu-id="e5493-117">In Visual Studio 2005, the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="e5493-118">Per informazioni sull'aggiunta, vedere [procedura: aggiungere elementi alla casella degli strumenti](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e5493-118">For information about adding it, see [How to: Add Items to the Toolbox](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165355(v=vs.100)).</span></span> <span data-ttu-id="e5493-119">Inoltre, in Visual Studio 2005 è possibile utilizzare la finestra **origini dati** per la data binding in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="e5493-119">Additionally in Visual Studio 2005, you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="e5493-120">Per altre informazioni, vedere [associare i controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="e5493-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>

## <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="e5493-121">Per associare il controllo DataGrid a una singola tabella nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="e5493-121">To data-bind the DataGrid control to a single table in the designer</span></span>

1. <span data-ttu-id="e5493-122">Impostare la proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> del controllo sull'oggetto contenente gli elementi di dati a cui si desidera eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="e5493-122">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>

2. <span data-ttu-id="e5493-123">Se l'origine dati è un set di dati, impostare la proprietà <xref:System.Windows.Forms.DataGrid.DataMember%2A> sul nome della tabella a cui eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="e5493-123">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>

3. <span data-ttu-id="e5493-124">Se l'origine dati è un set di dati o una vista dati basata su una tabella del set di dati, aggiungere il codice al form per riempire il set di dati.</span><span class="sxs-lookup"><span data-stu-id="e5493-124">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>

     <span data-ttu-id="e5493-125">Il codice esatto utilizzato dipende dalla posizione in cui il set di dati recupera i dati.</span><span class="sxs-lookup"><span data-stu-id="e5493-125">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="e5493-126">Se il set di dati viene popolato direttamente da un database, in genere si chiama il metodo `Fill` di un adattatore dati, come nell'esempio di codice seguente, che popola un set di dati denominato `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="e5493-126">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>

    ```vb
    sqlDataAdapter1.Fill(DsCategories1)
    ```

    ```csharp
    sqlDataAdapter1.Fill(DsCategories1);
    ```

    ```cpp
    sqlDataAdapter1->Fill(dsCategories1);
    ```

4. <span data-ttu-id="e5493-127">Opzionale Aggiungere gli stili di tabella e gli stili di colonna appropriati alla griglia.</span><span class="sxs-lookup"><span data-stu-id="e5493-127">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>

     <span data-ttu-id="e5493-128">Se non sono presenti stili di tabella, verrà visualizzata la tabella, ma con la formattazione minima e con tutte le colonne visibili.</span><span class="sxs-lookup"><span data-stu-id="e5493-128">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>

## <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="e5493-129">Per associare il controllo DataGrid a più tabelle in un set di dati nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="e5493-129">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>

1. <span data-ttu-id="e5493-130">Impostare la proprietà <xref:System.Windows.Forms.DataGrid.DataSource%2A> del controllo sull'oggetto contenente gli elementi di dati a cui si desidera eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="e5493-130">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>

2. <span data-ttu-id="e5493-131">Se il set di dati contiene tabelle correlate (ovvero se contiene un oggetto Relation), impostare la proprietà <xref:System.Windows.Forms.DataGrid.DataMember%2A> sul nome della tabella padre.</span><span class="sxs-lookup"><span data-stu-id="e5493-131">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>

3. <span data-ttu-id="e5493-132">Scrivere il codice per riempire il set di dati.</span><span class="sxs-lookup"><span data-stu-id="e5493-132">Write code to fill the dataset.</span></span>

## <a name="see-also"></a><span data-ttu-id="e5493-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e5493-133">See also</span></span>

- [<span data-ttu-id="e5493-134">Cenni preliminari sul controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="e5493-134">DataGrid Control Overview</span></span>](datagrid-control-overview-windows-forms.md)
- [<span data-ttu-id="e5493-135">Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="e5493-135">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)
- [<span data-ttu-id="e5493-136">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="e5493-136">DataGrid Control</span></span>](datagrid-control-windows-forms.md)
- [<span data-ttu-id="e5493-137">Associazione ai dati di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e5493-137">Windows Forms Data Binding</span></span>](../windows-forms-data-binding.md)
- [<span data-ttu-id="e5493-138">Accesso ai dati in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e5493-138">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
