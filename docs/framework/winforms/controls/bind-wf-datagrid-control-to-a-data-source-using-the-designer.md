---
title: 'Procedura: associare il controllo DataGrid Windows Form a un''origine dati mediante la finestra di progettazione'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9e0bde96442e09ee33a63cecd56a4cd6e2cf19a9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-bind-the-windows-forms-datagrid-control-to-a-data-source-using-the-designer"></a><span data-ttu-id="4a09b-102">Procedura: associare il controllo DataGrid Windows Form a un'origine dati mediante la finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="4a09b-102">How to: Bind the Windows Forms DataGrid Control to a Data Source Using the Designer</span></span>
> [!NOTE]
>  <span data-ttu-id="4a09b-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="4a09b-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="4a09b-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="4a09b-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="4a09b-105">Windows Form <xref:System.Windows.Forms.DataGrid> controllo è progettato specificamente per visualizzare le informazioni da un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="4a09b-105">The Windows Forms <xref:System.Windows.Forms.DataGrid> control is specifically designed to display information from a data source.</span></span> <span data-ttu-id="4a09b-106">Per associare il controllo in fase di progettazione impostando il <xref:System.Windows.Forms.DataGrid.DataSource%2A> e <xref:System.Windows.Forms.DataGrid.DataMember%2A> , proprietà o in fase di esecuzione chiamando il <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> metodo.</span><span class="sxs-lookup"><span data-stu-id="4a09b-106">You bind the control at design time by setting the <xref:System.Windows.Forms.DataGrid.DataSource%2A> and <xref:System.Windows.Forms.DataGrid.DataMember%2A> properties, or at run time by calling the <xref:System.Windows.Forms.DataGrid.SetDataBinding%2A> method.</span></span> <span data-ttu-id="4a09b-107">Sebbene sia possibile visualizzare i dati da un'ampia gamma di origini dati, le cause più comuni sono i set di dati e le visualizzazioni dati.</span><span class="sxs-lookup"><span data-stu-id="4a09b-107">Although you can display data from a variety of data sources, the most typical sources are datasets and data views.</span></span>  
  
 <span data-ttu-id="4a09b-108">Se l'origine dati è disponibile in fase di progettazione, ad esempio, se il form contiene un'istanza di un set di dati o una vista dati, è possibile associare la griglia per l'origine dati in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4a09b-108">If the data source is available at design time—for example, if the form contains an instance of a dataset or a data view—you can bind the grid to the data source at design time.</span></span> <span data-ttu-id="4a09b-109">È quindi possibile visualizzare in anteprima l'aspetto dei dati nella griglia.</span><span class="sxs-lookup"><span data-stu-id="4a09b-109">You can then preview what the data will look like in the grid.</span></span>  
  
 <span data-ttu-id="4a09b-110">È anche possibile associare la griglia a livello di codice in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4a09b-110">You can also bind the grid programmatically, at run time.</span></span> <span data-ttu-id="4a09b-111">Ciò è utile quando si desidera impostare un'origine dati in base alle informazioni ottenute in fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="4a09b-111">This is useful when you want to set a data source based on information you get at run time.</span></span> <span data-ttu-id="4a09b-112">Ad esempio, l'applicazione potrebbe consentire all'utente di specificare il nome di una tabella da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="4a09b-112">For example, the application might let the user specify the name of a table to view.</span></span> <span data-ttu-id="4a09b-113">È inoltre necessaria nelle situazioni in cui l'origine dati non esiste in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4a09b-113">It is also necessary in situations where the data source does not exist at design time.</span></span> <span data-ttu-id="4a09b-114">Sono incluse origini dati, ad esempio matrici, raccolte, dataset non tipizzati e lettori di dati.</span><span class="sxs-lookup"><span data-stu-id="4a09b-114">This includes data sources such as arrays, collections, untyped datasets, and data readers.</span></span>  
  
 <span data-ttu-id="4a09b-115">La procedura seguente richiede un **applicazione Windows** progetto con un form contenente un <xref:System.Windows.Forms.DataGrid> controllo.</span><span class="sxs-lookup"><span data-stu-id="4a09b-115">The following procedure requires a **Windows Application** project with a form containing a <xref:System.Windows.Forms.DataGrid> control.</span></span> <span data-ttu-id="4a09b-116">Per informazioni sull'impostazione di un progetto, vedere [procedura: creare un progetto di applicazione Windows](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) e [procedura: aggiungere controlli a un Windows Form](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span><span class="sxs-lookup"><span data-stu-id="4a09b-116">For information about setting up such a project, see [How to: Create a Windows Application Project](http://msdn.microsoft.com/en-us/b2f93fed-c635-4705-8d0e-cf079a264efa) and [How to: Add Controls to Windows Forms](../../../../docs/framework/winforms/controls/how-to-add-controls-to-windows-forms.md).</span></span> <span data-ttu-id="4a09b-117">In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], <xref:System.Windows.Forms.DataGrid> controllo non sarà il **della casella degli strumenti** per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4a09b-117">In [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], the <xref:System.Windows.Forms.DataGrid> control is not in the **Toolbox** by default.</span></span> <span data-ttu-id="4a09b-118">Per informazioni su come aggiungerlo, vedere [procedura: aggiungere elementi alla casella degli strumenti](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0).</span><span class="sxs-lookup"><span data-stu-id="4a09b-118">For information about adding it, see [How to: Add Items to the Toolbox](http://msdn.microsoft.com/en-us/458e119e-17fe-450b-b889-e31c128bd7e0).</span></span> <span data-ttu-id="4a09b-119">Inoltre in [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], è possibile utilizzare il **origini dati** finestra per l'associazione dati in fase di progettazione.</span><span class="sxs-lookup"><span data-stu-id="4a09b-119">Additionally in [!INCLUDE[vsprvslong](../../../../includes/vsprvslong-md.md)], you can use the **Data Sources** window for design-time data binding.</span></span> <span data-ttu-id="4a09b-120">Per ulteriori informazioni vedere [associare i controlli ai dati in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="4a09b-120">For more information see [Bind controls to data in Visual Studio](/visualstudio/data-tools/bind-controls-to-data-in-visual-studio).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a09b-121">Le finestre di dialogo e i comandi di menu visualizzati potrebbero essere diversi da quelli descritti nella Guida a seconda delle impostazioni attive o dell'edizione del programma.</span><span class="sxs-lookup"><span data-stu-id="4a09b-121">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="4a09b-122">Per modificare le impostazioni, scegliere **Importa/Esporta impostazioni** dal menu **Strumenti** .</span><span class="sxs-lookup"><span data-stu-id="4a09b-122">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="4a09b-123">Per altre informazioni, vedere [Personalizzazione delle impostazioni di sviluppo in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span><span class="sxs-lookup"><span data-stu-id="4a09b-123">For more information, see [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-a-single-table-in-the-designer"></a><span data-ttu-id="4a09b-124">Per associare il controllo DataGrid a una singola tabella nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="4a09b-124">To data-bind the DataGrid control to a single table in the designer</span></span>  
  
1.  <span data-ttu-id="4a09b-125">Impostare il controllo <xref:System.Windows.Forms.DataGrid.DataSource%2A> proprietà all'oggetto contenente gli elementi di dati a cui si desidera associare.</span><span class="sxs-lookup"><span data-stu-id="4a09b-125">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="4a09b-126">Se l'origine dati è un set di dati, impostare il <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà sul nome della tabella da associare.</span><span class="sxs-lookup"><span data-stu-id="4a09b-126">If the data source is a dataset, set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the table to bind to.</span></span>  
  
3.  <span data-ttu-id="4a09b-127">Se l'origine dati è un set di dati o una vista di dati basato su una tabella di set di dati, aggiungere codice al form per riempire il set di dati.</span><span class="sxs-lookup"><span data-stu-id="4a09b-127">If the data source is a dataset or a data view based on a dataset table, add code to the form to fill the dataset.</span></span>  
  
     <span data-ttu-id="4a09b-128">Il codice esatto che è utilizzare dipende in cui il set di dati Ottiene i dati.</span><span class="sxs-lookup"><span data-stu-id="4a09b-128">The exact code you use depends on where the dataset is getting data.</span></span> <span data-ttu-id="4a09b-129">Se il set di dati viene popolato direttamente da un database, si chiama in genere il `Fill` metodo di un adattatore di dati, come nell'esempio di codice seguente, che popola un set di dati denominato `DsCategories1`:</span><span class="sxs-lookup"><span data-stu-id="4a09b-129">If the dataset is being populated directly from a database, you typically call the `Fill` method of a data adapter, as in the following code example, which populates a dataset called `DsCategories1`:</span></span>  
  
    ```vb  
    sqlDataAdapter1.Fill(DsCategories1)  
    ```  
  
    ```csharp  
    sqlDataAdapter1.Fill(DsCategories1);  
    ```  
  
    ```cpp  
    sqlDataAdapter1->Fill(dsCategories1);  
    ```  
  
4.  <span data-ttu-id="4a09b-130">(Facoltativo) Aggiungere gli stili tabella appropriata e gli stili di colonna nella griglia.</span><span class="sxs-lookup"><span data-stu-id="4a09b-130">(Optional) Add the appropriate table styles and column styles to the grid.</span></span>  
  
     <span data-ttu-id="4a09b-131">Se sono presenti nessuno stile di tabella, verrà visualizzato nella tabella, ma con una formattazione minima e con tutte le colonne visibili.</span><span class="sxs-lookup"><span data-stu-id="4a09b-131">If there are no table styles, you will see the table, but with minimal formatting and with all columns visible.</span></span>  
  
### <a name="to-data-bind-the-datagrid-control-to-multiple-tables-in-a-dataset-in-the-designer"></a><span data-ttu-id="4a09b-132">Per associare il controllo DataGrid a più tabelle in un set di dati nella finestra di progettazione</span><span class="sxs-lookup"><span data-stu-id="4a09b-132">To data-bind the DataGrid control to multiple tables in a dataset in the designer</span></span>  
  
1.  <span data-ttu-id="4a09b-133">Impostare il controllo <xref:System.Windows.Forms.DataGrid.DataSource%2A> proprietà all'oggetto contenente gli elementi di dati a cui si desidera associare.</span><span class="sxs-lookup"><span data-stu-id="4a09b-133">Set the control's <xref:System.Windows.Forms.DataGrid.DataSource%2A> property to the object containing the data items you want to bind to.</span></span>  
  
2.  <span data-ttu-id="4a09b-134">Se il set di dati contiene tabelle correlate (ovvero, se contiene un oggetto relation), impostare il <xref:System.Windows.Forms.DataGrid.DataMember%2A> proprietà sul nome della tabella padre.</span><span class="sxs-lookup"><span data-stu-id="4a09b-134">If the dataset contains related tables (that is, if it contains a relation object), set the <xref:System.Windows.Forms.DataGrid.DataMember%2A> property to the name of the parent table.</span></span>  
  
3.  <span data-ttu-id="4a09b-135">Scrivere codice per riempire il set di dati.</span><span class="sxs-lookup"><span data-stu-id="4a09b-135">Write code to fill the dataset.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a09b-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a09b-136">See Also</span></span>  
 [<span data-ttu-id="4a09b-137">Cenni preliminari sul controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="4a09b-137">DataGrid Control Overview</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-overview-windows-forms.md)  
 [<span data-ttu-id="4a09b-138">Procedura: Aggiungere tabelle e colonne al controllo DataGrid Windows Form</span><span class="sxs-lookup"><span data-stu-id="4a09b-138">How to: Add Tables and Columns to the Windows Forms DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/how-to-add-tables-and-columns-to-the-windows-forms-datagrid-control.md)  
 [<span data-ttu-id="4a09b-139">Controllo DataGrid</span><span class="sxs-lookup"><span data-stu-id="4a09b-139">DataGrid Control</span></span>](../../../../docs/framework/winforms/controls/datagrid-control-windows-forms.md)  
 [<span data-ttu-id="4a09b-140">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="4a09b-140">Windows Forms Data Binding</span></span>](../../../../docs/framework/winforms/windows-forms-data-binding.md)  
 [<span data-ttu-id="4a09b-141">Accesso ai dati in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="4a09b-141">Accessing data in Visual Studio</span></span>](/visualstudio/data-tools/accessing-data-in-visual-studio)
