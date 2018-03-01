---
title: Cenni preliminari sul controllo DataGridView (Windows Form)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DataGridView
helpviewer_keywords:
- DataGridView control [Windows Forms], about DataGridView control
- grid controls [Windows Forms]
- tables [Windows Forms], displaying in DataGridView control
- tables [Windows Forms], binding to DataGridView control
- columns [Windows Forms], DataGridView control
- bound controls [Windows Forms], dataGridView control
- datasets [Windows Forms], binding to DataGridView control
- data grids [Windows Forms], about data grids
- data [Windows Forms], resorting
- data [Windows Forms], navigating
- grids [Windows Forms]
- data binding [Windows Forms], DataGridView control
- data sources [Windows Forms], binding to DataGridView control
- DataGridView control [Windows Forms], data binding
ms.assetid: 0a45c661-89dc-4390-9cc6-c47eee501488
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6d9cc6568813af866acaf20696b870bedc3099be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="datagridview-control-overview-windows-forms"></a><span data-ttu-id="ba5a5-102">Cenni preliminari sul controllo DataGridView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="ba5a5-102">DataGridView Control Overview (Windows Forms)</span></span>
> [!NOTE]
>  <span data-ttu-id="ba5a5-103">Benché il controllo <xref:System.Windows.Forms.DataGridView> sostituisca il controllo <xref:System.Windows.Forms.DataGrid> aggiungendovi funzionalità, il controllo <xref:System.Windows.Forms.DataGrid> viene mantenuto per compatibilità con le versioni precedenti e per un eventuale uso futuro.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-103">The <xref:System.Windows.Forms.DataGridView> control replaces and adds functionality to the <xref:System.Windows.Forms.DataGrid> control; however, the <xref:System.Windows.Forms.DataGrid> control is retained for both backward compatibility and future use, if you choose.</span></span> <span data-ttu-id="ba5a5-104">Per altre informazioni, vedere [Differenze tra i controlli DataGridView e DataGrid Windows Form](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span><span class="sxs-lookup"><span data-stu-id="ba5a5-104">For more information, see [Differences Between the Windows Forms DataGridView and DataGrid Controls](../../../../docs/framework/winforms/controls/differences-between-the-windows-forms-datagridview-and-datagrid-controls.md).</span></span>  
  
 <span data-ttu-id="ba5a5-105">Con il <xref:System.Windows.Forms.DataGridView> (controllo), è possibile visualizzare e modificare i dati tabulari da molti tipi diversi di origini dati.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-105">With the <xref:System.Windows.Forms.DataGridView> control, you can display and edit tabular data from many different kinds of data sources.</span></span>  
  
 <span data-ttu-id="ba5a5-106">Associazione di dati per il <xref:System.Windows.Forms.DataGridView> controllo è semplice e intuitivo e in molti casi è semplice come l'impostazione di <xref:System.Windows.Forms.DataGridView.DataSource%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-106">Binding data to the <xref:System.Windows.Forms.DataGridView> control is straightforward and intuitive, and in many cases it is as simple as setting the <xref:System.Windows.Forms.DataGridView.DataSource%2A> property.</span></span> <span data-ttu-id="ba5a5-107">Quando si associa a un'origine dati contenente più elenchi o tabelle, impostare il <xref:System.Windows.Forms.DataGridView.DataMember%2A> proprietà in una stringa che specifica l'elenco o una tabella da associare.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-107">When you bind to a data source that contains multiple lists or tables, set the <xref:System.Windows.Forms.DataGridView.DataMember%2A> property to a string that specifies the list or table to bind to.</span></span>  
  
 <span data-ttu-id="ba5a5-108">Il <xref:System.Windows.Forms.DataGridView> controllo supporta il modello di associazione dati standard di Windows Form, quindi eseguirà l'associazione a istanze delle classi descritte nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="ba5a5-108">The <xref:System.Windows.Forms.DataGridView> control supports the standard Windows Forms data binding model, so it will bind to instances of classes described in the following list:</span></span>  
  
-   <span data-ttu-id="ba5a5-109">Qualsiasi classe che implementa il <xref:System.Collections.IList> interfaccia, incluse le matrici unidimensionali.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-109">Any class that implements the <xref:System.Collections.IList> interface, including one-dimensional arrays.</span></span>  
  
-   <span data-ttu-id="ba5a5-110">Qualsiasi classe che implementa il <xref:System.ComponentModel.IListSource> interfaccia, ad esempio il <xref:System.Data.DataTable> e <xref:System.Data.DataSet> classi.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-110">Any class that implements the <xref:System.ComponentModel.IListSource> interface, such as the <xref:System.Data.DataTable> and <xref:System.Data.DataSet> classes.</span></span>  
  
-   <span data-ttu-id="ba5a5-111">Qualsiasi classe che implementa il <xref:System.ComponentModel.IBindingList> interfaccia, ad esempio la <xref:System.ComponentModel.BindingList%601> classe.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-111">Any class that implements the <xref:System.ComponentModel.IBindingList> interface, such as the <xref:System.ComponentModel.BindingList%601> class.</span></span>  
  
-   <span data-ttu-id="ba5a5-112">Qualsiasi classe che implementa il <xref:System.ComponentModel.IBindingListView> interfaccia, ad esempio la <xref:System.Windows.Forms.BindingSource> classe.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-112">Any class that implements the <xref:System.ComponentModel.IBindingListView> interface, such as the <xref:System.Windows.Forms.BindingSource> class.</span></span>  
  
 <span data-ttu-id="ba5a5-113">Il <xref:System.Windows.Forms.DataGridView> controllo supporta il data binding per le proprietà pubbliche degli oggetti restituiti da queste interfacce o per la raccolta di proprietà restituito da un <xref:System.ComponentModel.ICustomTypeDescriptor> interfaccia, se implementata in oggetti restituiti.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-113">The <xref:System.Windows.Forms.DataGridView> control supports data binding to the public properties of the objects returned by these interfaces or to the properties collection returned by an <xref:System.ComponentModel.ICustomTypeDescriptor> interface, if implemented on the returned objects.</span></span>  
  
 <span data-ttu-id="ba5a5-114">In genere, verrà associato a un <xref:System.Windows.Forms.BindingSource> componente e associare il <xref:System.Windows.Forms.BindingSource> componente a un'altra origine dati o viene popolato con gli oggetti business.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-114">Typically, you will bind to a <xref:System.Windows.Forms.BindingSource> component and bind the <xref:System.Windows.Forms.BindingSource> component to another data source or populate it with business objects.</span></span> <span data-ttu-id="ba5a5-115">Il <xref:System.Windows.Forms.BindingSource> componente è l'origine dati preferita in quanto è possibile associare a una vasta gamma di origini dati e di risolvere molti problemi relativi all'associazione dati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-115">The <xref:System.Windows.Forms.BindingSource> component is the preferred data source because it can bind to a wide variety of data sources and can resolve many data binding issues automatically.</span></span> <span data-ttu-id="ba5a5-116">Per ulteriori informazioni, vedere [BindingSource (componente)](../../../../docs/framework/winforms/controls/bindingsource-component.md).</span><span class="sxs-lookup"><span data-stu-id="ba5a5-116">For more information, see [BindingSource Component](../../../../docs/framework/winforms/controls/bindingsource-component.md).</span></span>  
  
 <span data-ttu-id="ba5a5-117">Il <xref:System.Windows.Forms.DataGridView> controllo può essere utilizzato anche *non associato* modalità con alcun archivio dati sottostante.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-117">The <xref:System.Windows.Forms.DataGridView> control can also be used in *unbound* mode, with no underlying data store.</span></span> <span data-ttu-id="ba5a5-118">Per un esempio di codice che utilizza un oggetto non associato <xref:System.Windows.Forms.DataGridView> di controllo, vedere [procedura dettagliata: creazione di un controllo DataGridView di Windows Form non associato](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="ba5a5-118">For a code example that uses an unbound <xref:System.Windows.Forms.DataGridView> control, see [Walkthrough: Creating an Unbound Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/walkthrough-creating-an-unbound-windows-forms-datagridview-control.md).</span></span>  
  
 <span data-ttu-id="ba5a5-119">Il <xref:System.Windows.Forms.DataGridView> controllo è particolarmente configurabile ed estendibile e fornisce molte proprietà, metodi ed eventi per personalizzare l'aspetto e comportamento.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-119">The <xref:System.Windows.Forms.DataGridView> control is highly configurable and extensible, and it provides many properties, methods, and events to customize its appearance and behavior.</span></span> <span data-ttu-id="ba5a5-120">Quando si desidera che l'applicazione Windows Form per visualizzare i dati tabulari, è consigliabile utilizzare il <xref:System.Windows.Forms.DataGridView> controllo prima di altre (ad esempio, <xref:System.Windows.Forms.DataGrid>).</span><span class="sxs-lookup"><span data-stu-id="ba5a5-120">When you want your Windows Forms application to display tabular data, consider using the <xref:System.Windows.Forms.DataGridView> control before others (for example, <xref:System.Windows.Forms.DataGrid>).</span></span> <span data-ttu-id="ba5a5-121">Se si intende visualizzare una griglia di piccole dimensioni dei valori di sola lettura o se si sta abilitando un utente di modificare una tabella con milioni di record, il <xref:System.Windows.Forms.DataGridView> controllo offre una soluzione facilmente programmabile e utilizzo efficiente della memoria.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-121">If you are displaying a small grid of read-only values, or if you are enabling a user to edit a table with millions of records, the <xref:System.Windows.Forms.DataGridView> control will provide you with a readily programmable, memory-efficient solution.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ba5a5-122">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="ba5a5-122">In This Section</span></span>  
 [<span data-ttu-id="ba5a5-123">Riepilogo della tecnologia del controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="ba5a5-123">DataGridView Control Technology Summary</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-technology-summary-windows-forms.md)  
 <span data-ttu-id="ba5a5-124">Riepiloga <xref:System.Windows.Forms.DataGridView> controllare i concetti e l'utilizzo di classi correlate.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-124">Summarizes <xref:System.Windows.Forms.DataGridView> control concepts and the use of related classes.</span></span>  
  
 [<span data-ttu-id="ba5a5-125">Architettura del controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="ba5a5-125">DataGridView Control Architecture</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-architecture-windows-forms.md)  
 <span data-ttu-id="ba5a5-126">Viene descritta l'architettura del <xref:System.Windows.Forms.DataGridView> controllo, ne viene illustrata la struttura di gerarchia e l'ereditarietà di tipo.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-126">Describes the architecture of the <xref:System.Windows.Forms.DataGridView> control, explaining its type hierarchy and inheritance structure.</span></span>  
  
 [<span data-ttu-id="ba5a5-127">Scenari del controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="ba5a5-127">DataGridView Control Scenarios</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-scenarios-windows-forms.md)  
 <span data-ttu-id="ba5a5-128">Vengono descritti gli scenari più comuni in cui <xref:System.Windows.Forms.DataGridView> i controlli vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-128">Describes the most common scenarios in which <xref:System.Windows.Forms.DataGridView> controls are used.</span></span>  
  
 [<span data-ttu-id="ba5a5-129">Directory del codice del controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="ba5a5-129">DataGridView Control Code Directory</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-code-directory-windows-forms.md)  
 <span data-ttu-id="ba5a5-130">Vengono forniti collegamenti a esempi di codice nella documentazione per i diversi <xref:System.Windows.Forms.DataGridView> attività.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-130">Provides links to code examples in the documentation for various <xref:System.Windows.Forms.DataGridView> tasks.</span></span> <span data-ttu-id="ba5a5-131">Questi esempi sono suddivisi in categorie in base al tipo di attività.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-131">These examples are categorized by task type.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="ba5a5-132">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="ba5a5-132">Related Sections</span></span>  
 [<span data-ttu-id="ba5a5-133">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ba5a5-133">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="ba5a5-134">Vengono descritti i tipi di colonna in Windows Form <xref:System.Windows.Forms.DataGridView> controllo utilizzato per visualizzare informazioni e consentire agli utenti di modificare o aggiungere informazioni.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-134">Discusses the column types in the Windows Forms <xref:System.Windows.Forms.DataGridView> control used to display information and allow users to modify or add information.</span></span>  
  
 [<span data-ttu-id="ba5a5-135">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ba5a5-135">Displaying Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="ba5a5-136">Fornisce argomenti che descrivono come popolare il controllo con i dati manualmente o da un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-136">Provides topics that describe how to populate the control with data either manually, or from an external data source.</span></span>  
  
 [<span data-ttu-id="ba5a5-137">Personalizzazione del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ba5a5-137">Customizing the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="ba5a5-138">Fornisce argomenti che descrivono come disegnare celle e righe personalizzate di <xref:System.Windows.Forms.DataGridView> e come creare tipi di cella, colonna e riga derivati.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-138">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="ba5a5-139">Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ba5a5-139">Performance Tuning in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/performance-tuning-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="ba5a5-140">Fornisce argomenti che descrivono come usare il controllo in modo efficiente per evitare problemi di prestazioni quando si lavora con grandi quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="ba5a5-140">Provides topics that describe how to use the control efficiently to avoid performance problems when working with large amounts of data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba5a5-141">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ba5a5-141">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.BindingSource>  
 [<span data-ttu-id="ba5a5-142">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="ba5a5-142">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="ba5a5-143">Funzionalità predefinite nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ba5a5-143">Default Functionality in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-functionality-in-the-windows-forms-datagridview-control.md)  
 [<span data-ttu-id="ba5a5-144">Gestione predefinita di tastiera e mouse nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ba5a5-144">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)
