---
title: 'Procedura: Impostare la modalità di ordinamento delle colonne nel controllo DataGridView Windows Form'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 43ee1f43dfed0a9612ef0b460e5633262c9b6a5c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54674885"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="e16d3-102">Procedura: Impostare la modalità di ordinamento delle colonne nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="e16d3-102">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="e16d3-103">Nel <xref:System.Windows.Forms.DataGridView> le colonne di caselle di testo di controllo, utilizzano l'ordinamento automatico per impostazione predefinita, mentre altri tipi di colonna non sono ordinati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e16d3-103">In the <xref:System.Windows.Forms.DataGridView> control, text box columns use automatic sorting by default, while other column types are not sorted automatically.</span></span> <span data-ttu-id="e16d3-104">In alcuni casi si dovranno eseguire l'override di questi valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e16d3-104">Sometimes you will want to override these defaults.</span></span> <span data-ttu-id="e16d3-105">Ad esempio, è possibile visualizzare le immagini al posto di testo, numeri o valori di cella di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="e16d3-105">For example, you can display images in place of text, numbers, or enumeration cell values.</span></span> <span data-ttu-id="e16d3-106">Mentre le immagini non possono essere ordinate, possono essere ordinati i valori sottostanti che rappresentano.</span><span class="sxs-lookup"><span data-stu-id="e16d3-106">While the images cannot be sorted, the underlying values that they represent can be sorted.</span></span>  
  
 <span data-ttu-id="e16d3-107">Nel <xref:System.Windows.Forms.DataGridView> (controllo), il <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> valore della proprietà di una colonna determina il comportamento di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="e16d3-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property value of a column determines its sorting behavior.</span></span>  
  
 <span data-ttu-id="e16d3-108">La procedura seguente viene illustrato il `Priority` colonna da [come: Personalizzare la formattazione dei dati nel controllo DataGridView Windows Form](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="e16d3-108">The following procedure shows the `Priority` column from [How to: Customize Data Formatting in the Windows Forms DataGridView Control](../../../../docs/framework/winforms/controls/how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="e16d3-109">Questa colonna è una colonna di immagine e non è ordinabile per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="e16d3-109">This column is an image column and is not sortable by default.</span></span> <span data-ttu-id="e16d3-110">Contiene valori di cella effettivo sono stringhe, tuttavia, in modo che possono essere ordinato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="e16d3-110">It contains actual cell values that are strings, however, so it can be sorted automatically.</span></span>  
  
### <a name="to-set-the-sort-mode-for-a-column"></a><span data-ttu-id="e16d3-111">Per impostare la modalità di ordinamento per una colonna</span><span class="sxs-lookup"><span data-stu-id="e16d3-111">To set the sort mode for a column</span></span>  
  
-   <span data-ttu-id="e16d3-112">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e16d3-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="e16d3-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="e16d3-113">Compiling the Code</span></span>  
 <span data-ttu-id="e16d3-114">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e16d3-114">This example requires:</span></span>  
  
-   <span data-ttu-id="e16d3-115">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` contenente una colonna denominata `Priority`.</span><span class="sxs-lookup"><span data-stu-id="e16d3-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Priority`.</span></span>  
  
-   <span data-ttu-id="e16d3-116">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e16d3-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e16d3-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e16d3-117">See also</span></span>
- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="e16d3-118">Ordinamento di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e16d3-118">Sorting Data in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e16d3-119">Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="e16d3-119">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="e16d3-120">Procedura: Personalizzare l'ordinamento nel controllo DataGridView Windows Form</span><span class="sxs-lookup"><span data-stu-id="e16d3-120">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
