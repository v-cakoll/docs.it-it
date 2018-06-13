---
title: Personalizzazione del controllo DataGridView Windows Form
ms.date: 03/30/2017
helpviewer_keywords:
- data grids [Windows Forms], customization
- DataGridView control [Windows Forms], customization
ms.assetid: 01ea5d4c-a736-4596-b0e9-a67a1b86e15f
ms.openlocfilehash: 92bbace4d0869aca67025f1e4ac8c451fe073219
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33529844"
---
# <a name="customizing-the-windows-forms-datagridview-control"></a><span data-ttu-id="76f5f-102">Personalizzazione del controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="76f5f-102">Customizing the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="76f5f-103">Il `DataGridView` controllo fornisce diverse proprietà che è possibile utilizzare per modificare l'aspetto e il comportamento di base (aspetto) delle relative celle, righe e colonne.</span><span class="sxs-lookup"><span data-stu-id="76f5f-103">The `DataGridView` control provides several properties that you can use to adjust the appearance and basic behavior (look and feel) of its cells, rows, and columns.</span></span> <span data-ttu-id="76f5f-104">Se si dispone di particolari esigenze che vanno oltre le capacità del <xref:System.Windows.Forms.DataGridViewCellStyle> classe, tuttavia, è possibile inoltre implementare il disegno personalizzato per il controllo o estenderne le funzionalità tramite la creazione di celle, colonne e righe.</span><span class="sxs-lookup"><span data-stu-id="76f5f-104">If you have special needs that go beyond the capabilities of the <xref:System.Windows.Forms.DataGridViewCellStyle> class, however, you can also implement owner drawing for the control or extend its capabilities by creating custom cells, columns, and rows.</span></span>  
  
 <span data-ttu-id="76f5f-105">Per disegnare celle e righe personalizzate, è possibile gestire vari `DataGridView` gli eventi di disegno.</span><span class="sxs-lookup"><span data-stu-id="76f5f-105">To paint cells and rows yourself, you can handle various `DataGridView` painting events.</span></span> <span data-ttu-id="76f5f-106">Per modificare le funzionalità esistenti o fornire nuove funzionalità, è possibile creare i propri tipi derivati da esistenti `DataGridViewCell`, `DataGridViewColumn`, e `DataGridViewRow` tipi.</span><span class="sxs-lookup"><span data-stu-id="76f5f-106">To modify existing functionality or provide new functionality, you can create your own types derived from the existing `DataGridViewCell`, `DataGridViewColumn`, and `DataGridViewRow` types.</span></span> <span data-ttu-id="76f5f-107">È anche possibile fornire nuove funzionalità di modifica mediante la creazione di tipi derivati che visualizzano un controllo di propria scelta quando una cella si trova in modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="76f5f-107">You can also provide new editing capabilities by creating derived types that display a control of your choosing when a cell is in edit mode.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="76f5f-108">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="76f5f-108">In This Section</span></span>  
 [<span data-ttu-id="76f5f-109">Procedura: Personalizzare l'aspetto delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="76f5f-109">How to: Customize the Appearance of Cells in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-cells-in-the-datagrid.md)  
 <span data-ttu-id="76f5f-110">Viene descritto come gestire il <xref:System.Windows.Forms.DataGridView.CellPainting> evento per disegnare le celle manualmente.</span><span class="sxs-lookup"><span data-stu-id="76f5f-110">Describes how to handle the <xref:System.Windows.Forms.DataGridView.CellPainting> event in order to paint cells manually.</span></span>  
  
 [<span data-ttu-id="76f5f-111">Procedura: Personalizzare l'aspetto delle righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="76f5f-111">How to: Customize the Appearance of Rows in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/customize-the-appearance-of-rows-in-the-datagrid.md)  
 <span data-ttu-id="76f5f-112">Viene descritto come gestire il <xref:System.Windows.Forms.DataGridView.RowPrePaint> e <xref:System.Windows.Forms.DataGridView.RowPostPaint> gli eventi per disegnare righe con uno sfondo sfumato personalizzato e un contenuto che si estende su più colonne.</span><span class="sxs-lookup"><span data-stu-id="76f5f-112">Describes how to handle the <xref:System.Windows.Forms.DataGridView.RowPrePaint> and <xref:System.Windows.Forms.DataGridView.RowPostPaint> events in order to paint rows with a custom, gradient background and content that spans multiple columns.</span></span>  
  
 [<span data-ttu-id="76f5f-113">Procedura: Personalizzare celle e colonne nel controllo DataGridView di Windows Form estendendone il comportamento e l'aspetto</span><span class="sxs-lookup"><span data-stu-id="76f5f-113">How to: Customize Cells and Columns in the Windows Forms DataGridView Control by Extending Their Behavior and Appearance</span></span>](../../../../docs/framework/winforms/controls/customize-cells-and-columns-in-the-datagrid-by-extending-behavior.md)  
 <span data-ttu-id="76f5f-114">Viene descritto come creare tipi personalizzati derivati da `DataGridViewCell` e `DataGridViewColumn` per evidenziare le celle quando il puntatore del mouse si sofferma su di essi.</span><span class="sxs-lookup"><span data-stu-id="76f5f-114">Describes how to create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to highlight cells when the mouse pointer rests on them.</span></span>  
  
 [<span data-ttu-id="76f5f-115">Procedura: Disabilitare i pulsanti in una colonna del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="76f5f-115">How to: Disable Buttons in a Button Column in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/disable-buttons-in-a-button-column-in-the-datagrid.md)  
 <span data-ttu-id="76f5f-116">Viene descritto come creare tipi personalizzati derivati da <xref:System.Windows.Forms.DataGridViewButtonCell> e <xref:System.Windows.Forms.DataGridViewButtonColumn> per visualizzare i pulsanti disabilitati in una colonna.</span><span class="sxs-lookup"><span data-stu-id="76f5f-116">Describes how to create custom types derived from <xref:System.Windows.Forms.DataGridViewButtonCell> and <xref:System.Windows.Forms.DataGridViewButtonColumn> in order to display disabled buttons in a button column.</span></span>  
  
 [<span data-ttu-id="76f5f-117">Procedura: Inserire controlli in celle del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="76f5f-117">How to: Host Controls in Windows Forms DataGridView Cells</span></span>](../../../../docs/framework/winforms/controls/how-to-host-controls-in-windows-forms-datagridview-cells.md)  
 <span data-ttu-id="76f5f-118">Viene descritto come implementare il `IDataGridViewEditingControl` l'interfaccia e creare tipi personalizzati derivati da `DataGridViewCell` e `DataGridViewColumn` per visualizzare un <xref:System.Windows.Forms.DateTimePicker> controllare quando una cella si trova in modalità di modifica.</span><span class="sxs-lookup"><span data-stu-id="76f5f-118">Describes how to implement the `IDataGridViewEditingControl` interface and create custom types derived from `DataGridViewCell` and `DataGridViewColumn` in order to display a <xref:System.Windows.Forms.DateTimePicker> control when a cell is in edit mode.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="76f5f-119">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="76f5f-119">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="76f5f-120">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="76f5f-120">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <span data-ttu-id="76f5f-121">Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewCell> classe.</span><span class="sxs-lookup"><span data-stu-id="76f5f-121">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCell> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewRow>  
 <span data-ttu-id="76f5f-122">Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewRow> classe.</span><span class="sxs-lookup"><span data-stu-id="76f5f-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewRow> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewColumn>  
 <span data-ttu-id="76f5f-123">Fornisce la documentazione di riferimento per la <xref:System.Windows.Forms.DataGridViewColumn> classe.</span><span class="sxs-lookup"><span data-stu-id="76f5f-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewColumn> class.</span></span>  
  
 <xref:System.Windows.Forms.IDataGridViewEditingControl>  
 <span data-ttu-id="76f5f-124">Fornisce la documentazione di riferimento per il <xref:System.Windows.Forms.IDataGridViewEditingControl> interfaccia.</span><span class="sxs-lookup"><span data-stu-id="76f5f-124">Provides reference documentation for the <xref:System.Windows.Forms.IDataGridViewEditingControl> interface.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="76f5f-125">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="76f5f-125">Related Sections</span></span>  
 [<span data-ttu-id="76f5f-126">Formattazione e stile di base nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="76f5f-126">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/basic-formatting-and-styling-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="76f5f-127">Fornisce argomenti che descrivono come modificare l'aspetto del controllo e la formattazione di base dei dati delle celle.</span><span class="sxs-lookup"><span data-stu-id="76f5f-127">Provides topics that describe how to modify the basic appearance of the control and the display formatting of cell data.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76f5f-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="76f5f-128">See Also</span></span>  
 [<span data-ttu-id="76f5f-129">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="76f5f-129">DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/datagridview-control-windows-forms.md)  
 [<span data-ttu-id="76f5f-130">Tipi di colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="76f5f-130">Column Types in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-types-in-the-windows-forms-datagridview-control.md)
