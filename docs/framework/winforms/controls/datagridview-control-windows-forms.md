---
title: Controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- tables [Windows Forms]
- data grids [Windows Forms
- data [Windows Forms], displaying in tabular format
- grid controls [Windows Forms]
- datasets [Windows Forms], user interface
- Windows Forms, displaying data
- data presentation
- tabular data [Windows Forms], displaying on Windows Forms
- datasets [Windows Forms], displaying in DataGridView control
- DataGridView control [Windows Forms]
ms.assetid: dbee73f2-bba6-4874-9389-cd21d44309be
ms.openlocfilehash: fc40c0f08c0c11fa9acc94ce12caab8766658f1e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746945"
---
# <a name="datagridview-control-windows-forms"></a><span data-ttu-id="e319d-102">Controllo DataGridView (Windows Form)</span><span class="sxs-lookup"><span data-stu-id="e319d-102">DataGridView Control (Windows Forms)</span></span>
<span data-ttu-id="e319d-103">Il controllo `DataGridView` fornisce un sistema efficiente e flessibile per visualizzare i dati in formato tabulare.</span><span class="sxs-lookup"><span data-stu-id="e319d-103">The `DataGridView` control provides a powerful and flexible way to display data in a tabular format.</span></span> <span data-ttu-id="e319d-104">È possibile usare il controllo `DataGridView` per mostrare le visualizzazioni di sola lettura di una piccola quantità di dati oppure ridimensionarlo per mostrare le visualizzazioni modificabili di set di dati di dimensioni molto estese.</span><span class="sxs-lookup"><span data-stu-id="e319d-104">You can use the `DataGridView` control to show read-only views of a small amount of data, or you can scale it to show editable views of very large sets of data.</span></span>  
  
 <span data-ttu-id="e319d-105">È possibile estendere il controllo `DataGridView` in diversi modi per sviluppare comportamenti personalizzati nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e319d-105">You can extend the `DataGridView` control in a number of ways to build custom behaviors into your applications.</span></span> <span data-ttu-id="e319d-106">Ad esempio, è possibile specificare a livello di codice i propri algoritmi di ordinamento e creare i propri tipi di celle.</span><span class="sxs-lookup"><span data-stu-id="e319d-106">For example, you can programmatically specify your own sorting algorithms, and you can create your own types of cells.</span></span> <span data-ttu-id="e319d-107">È possibile personalizzare facilmente l'aspetto del controllo `DataGridView` scegliendo tra diverse proprietà.</span><span class="sxs-lookup"><span data-stu-id="e319d-107">You can easily customize the appearance of the `DataGridView` control by choosing among several properties.</span></span> <span data-ttu-id="e319d-108">Si possono usare molti tipi di archivi dati come origine dati, ma il controllo `DataGridView` può operare anche senza alcuna origine dati associata.</span><span class="sxs-lookup"><span data-stu-id="e319d-108">Many types of data stores can be used as a data source, or the `DataGridView` control can operate with no data source bound to it.</span></span>  
  
 <span data-ttu-id="e319d-109">Gli argomenti di questa sezione descrivono i concetti e le tecniche che è possibile usare per compilare funzionalità `DataGridView` nelle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="e319d-109">The topics in this section describe the concepts and techniques that you can use to build `DataGridView` features into your applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e319d-110">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e319d-110">In This Section</span></span>  
 [<span data-ttu-id="e319d-111">Panoramica sul controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="e319d-111">DataGridView Control Overview</span></span>](datagridview-control-overview-windows-forms.md)  
 <span data-ttu-id="e319d-112">Fornisce argomenti che descrivono l'architettura e i concetti principali del controllo `DataGridView` Windows Form.</span><span class="sxs-lookup"><span data-stu-id="e319d-112">Provides topics that describe the architecture and core concepts of the Windows Forms `DataGridView` control.</span></span>  
  
 [<span data-ttu-id="e319d-113">Funzionalità predefinite nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-113">Default Functionality in the Windows Forms DataGridView Control</span></span>](default-functionality-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e319d-114">Descrive l'aspetto e il comportamento predefiniti del controllo `DataGridView` Windows Form quando è associato a un'origine dati.</span><span class="sxs-lookup"><span data-stu-id="e319d-114">Describes the default appearance and behavior of the Windows Forms `DataGridView` control when it is bound to a data source.</span></span>  
  
 [<span data-ttu-id="e319d-115">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-115">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e319d-116">Descrive i tipi di colonna nel controllo `DataGridView` Windows Form, usati per visualizzare i dati e consentire agli utenti di modificare o aggiungere dati.</span><span class="sxs-lookup"><span data-stu-id="e319d-116">Describes the column types in the Windows Forms `DataGridView` control used to display data and allow users to modify or add data.</span></span>  
  
 [<span data-ttu-id="e319d-117">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-117">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="e319d-118">Fornisce argomenti che descrivono le proprietà di uso comune di celle, righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="e319d-118">Provides topics that describe commonly-used cell, row, and column properties.</span></span>  
  
 [<span data-ttu-id="e319d-119">Formattazione e stile di base nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-119">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e319d-120">Fornisce argomenti che descrivono come modificare l'aspetto del controllo e la formattazione di base dei dati delle celle.</span><span class="sxs-lookup"><span data-stu-id="e319d-120">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
 [<span data-ttu-id="e319d-121">Visualizzazione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-121">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e319d-122">Fornisce argomenti che descrivono come popolare il controllo con i dati manualmente o da un'origine dati esterna.</span><span class="sxs-lookup"><span data-stu-id="e319d-122">Provides topics that describe how to populate the control with data either manually, or from an external data source.</span></span>  
  
 [<span data-ttu-id="e319d-123">Ridimensionamento di colonne e righe nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-123">Resizing Columns and Rows in the Windows Forms DataGridView Control</span></span>](resizing-columns-and-rows-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e319d-124">Fornisce argomenti che spiegano come le dimensioni di righe e colonne possano essere adattate automaticamente al contenuto delle celle o alla larghezza disponibile del controllo.</span><span class="sxs-lookup"><span data-stu-id="e319d-124">Provides topics that describe how the size of rows and columns can be adjusted automatically to fit cell content or to fit the available width of the control.</span></span>  
  
 [<span data-ttu-id="e319d-125">Ordinamento di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-125">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e319d-126">Fornisce argomenti che descrivono le funzionalità di ordinamento nel controllo.</span><span class="sxs-lookup"><span data-stu-id="e319d-126">Provides topics that describe the sorting features in the control.</span></span>  
  
 [<span data-ttu-id="e319d-127">Immissione di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-127">Data Entry in the Windows Forms DataGridView Control</span></span>](data-entry-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e319d-128">Fornisce argomenti che spiegano come cambiare la modalità di aggiunta e modifica dei dati nel controllo da parte degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e319d-128">Provides topics that describe how to change the way users add and modify data in the control.</span></span>  
  
 [<span data-ttu-id="e319d-129">Uso della selezione e degli Appunti con il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-129">Selection and Clipboard Use with the Windows Forms DataGridView Control</span></span>](selection-and-clipboard-use-with-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e319d-130">Fornisce argomenti che descrivono le funzionalità di selezione di celle, righe e colonne del controllo.</span><span class="sxs-lookup"><span data-stu-id="e319d-130">Provides topics that describe the cell, row, and column selection features in the control.</span></span>  
  
 [<span data-ttu-id="e319d-131">Programmazione con celle, righe e colonne nel controllo DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="e319d-131">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)  
 <span data-ttu-id="e319d-132">Fornisce argomenti che descrivono come eseguire la programmazione con oggetti cella, riga e colonna.</span><span class="sxs-lookup"><span data-stu-id="e319d-132">Provides topics that describe how to program with cell, row, and column objects.</span></span>  
  
 [<span data-ttu-id="e319d-133">Personalizzazione del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-133">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e319d-134">Fornisce argomenti che descrivono come disegnare celle e righe personalizzate di `DataGridView` e come creare tipi di cella, colonna e riga derivati.</span><span class="sxs-lookup"><span data-stu-id="e319d-134">Provides topics that describe custom painting `DataGridView` cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="e319d-135">Ottimizzazione delle prestazioni nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-135">Performance Tuning in the Windows Forms DataGridView Control</span></span>](performance-tuning-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e319d-136">Fornisce argomenti che descrivono come usare il controllo in modo efficiente per evitare problemi di prestazioni quando si lavora con grandi quantità di dati.</span><span class="sxs-lookup"><span data-stu-id="e319d-136">Provides topics that describe how to use the control efficiently to avoid performance problems when working with large amounts of data.</span></span>  
  
 [<span data-ttu-id="e319d-137">Gestione predefinita di tastiera e mouse nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-137">Default Keyboard and Mouse Handling in the Windows Forms DataGridView Control</span></span>](default-keyboard-and-mouse-handling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e319d-138">Descrive come gli utenti possono interagire con il controllo `DataGridView` tramite tastiera e mouse.</span><span class="sxs-lookup"><span data-stu-id="e319d-138">Describes how users can interact with the `DataGridView` control through a keyboard and a mouse.</span></span>  
  
 [<span data-ttu-id="e319d-139">Differenze tra i controlli DataGridView e DataGrid di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-139">Differences Between the Windows Forms DataGridView and DataGrid Controls</span></span>](differences-between-the-windows-forms-datagridview-and-datagrid-controls.md)  
 <span data-ttu-id="e319d-140">Descrive come il controllo `DataGridView` migliori e sostituisca il controllo <xref:System.Windows.Forms.DataGrid>.</span><span class="sxs-lookup"><span data-stu-id="e319d-140">Describes how the `DataGridView` control improves upon and replaces the <xref:System.Windows.Forms.DataGrid> control.</span></span>  
  
 <span data-ttu-id="e319d-141">Vedere anche [uso della finestra di progettazione con il controllo DataGridView Windows Forms](using-the-designer-with-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="e319d-141">Also see [Using the Designer with the Windows Forms DataGridView Control](using-the-designer-with-the-windows-forms-datagridview-control.md).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e319d-142">Riferimento</span><span class="sxs-lookup"><span data-stu-id="e319d-142">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="e319d-143">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e319d-143">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.BindingSource>  
 <span data-ttu-id="e319d-144">Fornisce la documentazione di riferimento per il componente <xref:System.Windows.Forms.BindingSource>.</span><span class="sxs-lookup"><span data-stu-id="e319d-144">Provides reference documentation for the <xref:System.Windows.Forms.BindingSource> component.</span></span> <span data-ttu-id="e319d-145">Il controllo <xref:System.Windows.Forms.DataGridView> e il componente <xref:System.Windows.Forms.BindingSource> sono progettati per interagire tra loro.</span><span class="sxs-lookup"><span data-stu-id="e319d-145">The <xref:System.Windows.Forms.DataGridView> control and the <xref:System.Windows.Forms.BindingSource> component are designed to work closely together.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e319d-146">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e319d-146">See also</span></span>

- [<span data-ttu-id="e319d-147">Controlli da usare in Windows Form</span><span class="sxs-lookup"><span data-stu-id="e319d-147">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
