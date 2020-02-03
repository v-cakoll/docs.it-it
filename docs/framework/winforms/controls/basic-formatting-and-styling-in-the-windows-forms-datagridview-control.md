---
title: Formattazione e stile di base nel controllo DataGridView
ms.date: 03/30/2017
helpviewer_keywords:
- DataGridView control [Windows Forms], formatting and styling
- data grids [Windows Forms], formatting
ms.assetid: b9b90836-1f56-4aa9-8db8-edc78fe830e8
ms.openlocfilehash: d295718b7bd4f3bc4c5f63b6e6cb911f733525fe
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732006"
---
# <a name="basic-formatting-and-styling-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="06df9-102">Formattazione e stile di base nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="06df9-102">Basic Formatting and Styling in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="06df9-103">Il controllo `DataGridView` semplifica la definizione dell'aspetto di base delle celle e la formattazione di visualizzazione dei valori delle celle.</span><span class="sxs-lookup"><span data-stu-id="06df9-103">The `DataGridView` control makes it easy to define the basic appearance of cells and the display formatting of cell values.</span></span> <span data-ttu-id="06df9-104">È possibile definire gli stili di aspetto e formattazione per le singole celle, per le celle in colonne e righe specifiche o per tutte le celle nel controllo impostando le proprietà degli oggetti `DataGridViewCellStyle` a cui si accede tramite varie proprietà del controllo `DataGridView`.</span><span class="sxs-lookup"><span data-stu-id="06df9-104">You can define appearance and formatting styles for individual cells, for cells in specific columns and rows, or for all cells in the control by setting the properties of the `DataGridViewCellStyle` objects accessed through various `DataGridView` control properties.</span></span> <span data-ttu-id="06df9-105">Inoltre, è possibile modificare questi stili in modo dinamico in base a fattori quali il valore della cella gestendo l'evento `CellFormatting`.</span><span class="sxs-lookup"><span data-stu-id="06df9-105">Additionally, you can modify these styles dynamically based on factors such as the cell value by handling the `CellFormatting` event.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="06df9-106">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="06df9-106">In This Section</span></span>  
 [<span data-ttu-id="06df9-107">Procedura: Modificare gli stili dei bordi e delle linee della griglia nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="06df9-107">How to: Change the Border and Gridline Styles in the Windows Forms DataGridView Control</span></span>](change-the-border-and-gridline-styles-in-the-datagrid.md)  
 <span data-ttu-id="06df9-108">Viene descritto come impostare `DataGridView` proprietà che definiscono l'aspetto del bordo del controllo e le linee di limite tra le celle.</span><span class="sxs-lookup"><span data-stu-id="06df9-108">Describes how to set `DataGridView` properties that define the appearance of the control border and the boundary lines between cells.</span></span>  
  
 [<span data-ttu-id="06df9-109">Stili delle celle nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="06df9-109">Cell Styles in the Windows Forms DataGridView Control</span></span>](cell-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="06df9-110">Viene descritta la classe `DataGridViewCellStyle` e il modo in cui le proprietà di tale tipo interagiscono per definire la modalità di visualizzazione delle celle nel controllo.</span><span class="sxs-lookup"><span data-stu-id="06df9-110">Describes the `DataGridViewCellStyle` class and how properties of that type interact to define how cells are displayed in the control.</span></span>  
  
 [<span data-ttu-id="06df9-111">Procedura: Impostare stili di cella predefiniti per il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="06df9-111">How to: Set Default Cell Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-default-cell-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="06df9-112">Viene descritto come utilizzare `DataGridViewCellStyle` proprietà per definire l'aspetto predefinito delle celle in righe e colonne specifiche e nell'intero controllo.</span><span class="sxs-lookup"><span data-stu-id="06df9-112">Describes how to use `DataGridViewCellStyle` properties to define the default appearance of cells in specific rows and columns and in the entire control.</span></span>  
  
 [<span data-ttu-id="06df9-113">Procedura: Formattare i dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="06df9-113">How to: Format Data in the Windows Forms DataGridView Control</span></span>](how-to-format-data-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="06df9-114">Viene descritto come formattare i valori di visualizzazione delle celle utilizzando `DataGridViewCellStyle` proprietà.</span><span class="sxs-lookup"><span data-stu-id="06df9-114">Describes how to format cell display values using `DataGridViewCellStyle` properties.</span></span>  
  
 [<span data-ttu-id="06df9-115">Procedura: Impostare gli stili di carattere e colore nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="06df9-115">How to: Set Font and Color Styles in the Windows Forms DataGridView Control</span></span>](how-to-set-font-and-color-styles-in-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="06df9-116">Viene descritto come utilizzare la proprietà `DefaultCellStyle` per impostare le caratteristiche di visualizzazione di base per tutte le celle nel controllo.</span><span class="sxs-lookup"><span data-stu-id="06df9-116">Describes how to use the `DefaultCellStyle` property to set basic display characteristics for all cells in the control.</span></span>  
  
 [<span data-ttu-id="06df9-117">Procedura: Impostare stili di righe alterne per il controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="06df9-117">How to: Set Alternating Row Styles for the Windows Forms DataGridView Control</span></span>](how-to-set-alternating-row-styles-for-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="06df9-118">Viene descritto come creare un effetto di tipo Ledger nel controllo utilizzando righe alternate visualizzate in modo diverso.</span><span class="sxs-lookup"><span data-stu-id="06df9-118">Describes how to create a ledger-like effect in the control using alternating rows that are displayed differently.</span></span>  
  
 [<span data-ttu-id="06df9-119">Procedura: Usare il modello di riga per personalizzare le righe nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="06df9-119">How to: Use the Row Template to Customize Rows in the Windows Forms DataGridView Control</span></span>](use-the-row-template-to-customize-rows-in-the-datagrid.md)  
 <span data-ttu-id="06df9-120">Viene descritto come utilizzare la proprietà `RowTemplate` per impostare le proprietà delle righe che verranno utilizzate per tutte le righe nel controllo.</span><span class="sxs-lookup"><span data-stu-id="06df9-120">Describes how to use the `RowTemplate` property to set row properties that will be used for all rows in the control.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="06df9-121">Riferimento</span><span class="sxs-lookup"><span data-stu-id="06df9-121">Reference</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <span data-ttu-id="06df9-122">Fornisce la documentazione di riferimento per il controllo <xref:System.Windows.Forms.DataGridView>.</span><span class="sxs-lookup"><span data-stu-id="06df9-122">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <xref:System.Windows.Forms.DataGridViewCellStyle>  
 <span data-ttu-id="06df9-123">Fornisce la documentazione di riferimento per la classe <xref:System.Windows.Forms.DataGridViewCellStyle>.</span><span class="sxs-lookup"><span data-stu-id="06df9-123">Provides reference documentation for the <xref:System.Windows.Forms.DataGridViewCellStyle> class.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.CellFormatting>  
 <span data-ttu-id="06df9-124">Fornisce la documentazione di riferimento per l'evento <xref:System.Windows.Forms.DataGridView.CellFormatting>.</span><span class="sxs-lookup"><span data-stu-id="06df9-124">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.CellFormatting> event.</span></span>  
  
 <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>  
 <span data-ttu-id="06df9-125">Fornisce la documentazione di riferimento per la proprietà <xref:System.Windows.Forms.DataGridView.RowTemplate%2A>.</span><span class="sxs-lookup"><span data-stu-id="06df9-125">Provides reference documentation for the <xref:System.Windows.Forms.DataGridView.RowTemplate%2A> property.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="06df9-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="06df9-126">Related Sections</span></span>  
 [<span data-ttu-id="06df9-127">Personalizzazione del controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="06df9-127">Customizing the Windows Forms DataGridView Control</span></span>](customizing-the-windows-forms-datagridview-control.md)  
 <span data-ttu-id="06df9-128">Fornisce argomenti che descrivono come disegnare celle e righe personalizzate di <xref:System.Windows.Forms.DataGridView> e come creare tipi di cella, colonna e riga derivati.</span><span class="sxs-lookup"><span data-stu-id="06df9-128">Provides topics that describe custom painting <xref:System.Windows.Forms.DataGridView> cells and rows, and creating derived cell, column, and row types.</span></span>  
  
 [<span data-ttu-id="06df9-129">Funzionalità di base per colonna, riga e cella nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="06df9-129">Basic Column, Row, and Cell Features in the Windows Forms DataGridView Control</span></span>](basic-column-row-and-cell-features-wf-datagridview-control.md)  
 <span data-ttu-id="06df9-130">Fornisce argomenti che descrivono le proprietà di celle, righe e colonne comunemente utilizzate.</span><span class="sxs-lookup"><span data-stu-id="06df9-130">Provides topics that describe commonly used cell, row, and column properties.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06df9-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="06df9-131">See also</span></span>

- [<span data-ttu-id="06df9-132">Controllo DataGridView</span><span class="sxs-lookup"><span data-stu-id="06df9-132">DataGridView Control</span></span>](datagridview-control-windows-forms.md)
