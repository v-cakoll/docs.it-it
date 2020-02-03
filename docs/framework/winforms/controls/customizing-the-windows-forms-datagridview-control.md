---
title: Personalizzare il controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 348c78d091679418f2452326555d49229bd2a8ea
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744030"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="e99cd-102">Personalizzazione del controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="e99cd-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e99cd-103">Il controllo `DataGridView` fornisce diverse proprietà che è possibile utilizzare per modificare l'aspetto e il comportamento di base (aspetto) delle relative celle, righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="e99cd-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="e99cd-104">Se si hanno esigenze particolari che vanno oltre le funzionalità della classe <xref:System.Windows.Forms.DataGridViewCellStyle>, tuttavia, è anche possibile implementare il disegno del proprietario per il controllo o estenderne le funzionalità creando celle, colonne e righe personalizzate.</span><span class="sxs-lookup"><span data-stu-id="e99cd-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="e99cd-105">Per disegnare le celle e le righe manualmente, è possibile gestire vari eventi di disegno `DataGridView`.</span><span class="sxs-lookup"><span data-stu-id="e99cd-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="e99cd-106">Per modificare la funzionalità esistente o fornire nuove funzionalità, è possibile creare tipi personalizzati derivati dai tipi di `DataGridViewCell`, `DataGridViewColumn`e `DataGridViewRow` esistenti.</span><span class="sxs-lookup"><span data-stu-id="e99cd-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="e99cd-107">È anche possibile fornire nuove funzionalità di modifica creando tipi derivati che visualizzano un controllo a scelta quando una cella è in modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="e99cd-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e99cd-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e99cd-108">In This Section</span></span>  
 [<span data-ttu-id="e99cd-109">Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e99cd-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="e99cd-110">Viene descritto come gestire l'evento <xref:System.Windows.Forms.DataGridView.CellPainting> per disegnare manualmente le celle.</span><span class="sxs-lookup"><span data-stu-id="e99cd-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="e99cd-111">Procedura: Personalizzare l'aspetto delle righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e99cd-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="e99cd-112">Viene descritto come gestire gli eventi <xref:System.Windows.Forms.DataGridView.RowPrePaint> e <xref:System.Windows.Forms.DataGridView.RowPostPaint> per disegnare le righe con uno sfondo sfumato e un contenuto personalizzati che si estende su più colonne.</span><span class="sxs-lookup"><span data-stu-id="e99cd-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="e99cd-113">Procedura: Personalizzare celle e colonne nel controllo DataGridView di Windows Form estendendone il comportamento e l'aspetto</span><span class="sxs-lookup"><span data-stu-id="e99cd-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="e99cd-114">Viene descritto come creare tipi personalizzati derivati da `DataGridViewCell` e `DataGridViewColumn` per evidenziare le celle quando il puntatore del mouse viene posizionato su di essi.</span><span class="sxs-lookup"><span data-stu-id="e99cd-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="e99cd-115">Procedura: Disabilitare i pulsanti in una colonna del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e99cd-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="e99cd-116">Viene descritto come creare tipi personalizzati derivati da <xref:System.Windows.Forms.DataGridViewButtonCell> e <xref:System.Windows.Forms.DataGridViewButtonColumn> per visualizzare i pulsanti disabilitati in una colonna di un pulsante.</span><span class="sxs-lookup"><span data-stu-id="e99cd-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="e99cd-117">Procedura: Inserire controlli in celle del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e99cd-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="e99cd-118">Viene descritto come implementare l'interfaccia `IDataGridViewEditingControl` e creare tipi personalizzati derivati da `DataGridViewCell` e `DataGridViewColumn` per visualizzare un controllo <xref:System.Windows.Forms.DateTimePicker> quando una cella è in modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="e99cd-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="e99cd-119">Riferimento</span><span class="sxs-lookup"><span data-stu-id="e99cd-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="e99cd-120">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="e99cd-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="e99cd-121">Fornisce la documentazione di riferimento per la classe <xref:System.Windows.Forms.DataGridViewCell>.</span><span class="sxs-lookup"><span data-stu-id="e99cd-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="e99cd-122">Fornisce la documentazione di riferimento per la classe <xref:System.Windows.Forms.DataGridViewRow>.</span><span class="sxs-lookup"><span data-stu-id="e99cd-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="e99cd-123">Fornisce la documentazione di riferimento per la classe <xref:System.Windows.Forms.DataGridViewColumn>.</span><span class="sxs-lookup"><span data-stu-id="e99cd-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="e99cd-124">Fornisce la documentazione di riferimento per l'interfaccia <xref:System.Windows.Forms.IDataGridViewEditingControl>.</span><span class="sxs-lookup"><span data-stu-id="e99cd-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e99cd-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="e99cd-125">Related Sections</span></span>  
 [<span data-ttu-id="e99cd-126">Formattazione e stile di base nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e99cd-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="e99cd-127">Fornisce argomenti che descrivono come modificare l'aspetto del controllo e la formattazione di base dei dati delle celle.</span><span class="sxs-lookup"><span data-stu-id="e99cd-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e99cd-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e99cd-128">See also</span></span>

- [<span data-ttu-id="e99cd-129">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="e99cd-129">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
- [<span data-ttu-id="e99cd-130">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e99cd-130">Column Types in the Windows Forms DataGridView Control</span></span>](column-types-in-the-windows-forms-datagridview-control.md)
