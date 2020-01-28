---
title: Impostare le modalità di ordinamento per le colonne nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- sorting [Windows Forms], data grids
- DataGridView control [Windows Forms], sort mode
- data grids [Windows Forms], sorting data
ms.assetid: 57dfed60-a608-40d5-86f9-d65686ffb325
ms.openlocfilehash: 45ee1e7d82f826cddbd3492fed0f63e7a9c2cf1d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743002"
---
# <a name="how-to-set-the-sort-modes-for-columns-in-the-windows-forms-datagridview-control"></a><span data-ttu-id="10718-102">Procedura: impostare le modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="10718-102">How to: Set the Sort Modes for Columns in the Windows Forms DataGridView Control</span></span>
<span data-ttu-id="10718-103">Nel controllo <xref:System.Windows.Forms.DataGridView>, le colonne casella di testo utilizzano l'ordinamento automatico per impostazione predefinita, mentre altri tipi di colonna non vengono ordinati automaticamente.</span><span class="sxs-lookup"><span data-stu-id="10718-103">In the <xref:System.Windows.Forms.DataGridView> control, text box columns use automatic sorting by default, while other column types are not sorted automatically.</span></span> <span data-ttu-id="10718-104">A volte è necessario eseguire l'override di queste impostazioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="10718-104">Sometimes you will want to override these defaults.</span></span> <span data-ttu-id="10718-105">Ad esempio, è possibile visualizzare le immagini al posto di testo, numeri o valori delle celle di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="10718-105">For example, you can display images in place of text, numbers, or enumeration cell values.</span></span> <span data-ttu-id="10718-106">Mentre le immagini non possono essere ordinate, i valori sottostanti che rappresentano possono essere ordinati.</span><span class="sxs-lookup"><span data-stu-id="10718-106">While the images cannot be sorted, the underlying values that they represent can be sorted.</span></span>  
  
 <span data-ttu-id="10718-107">Nel controllo <xref:System.Windows.Forms.DataGridView> il valore della proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> di una colonna ne determina il comportamento di ordinamento.</span><span class="sxs-lookup"><span data-stu-id="10718-107">In the <xref:System.Windows.Forms.DataGridView> control, the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A> property value of a column determines its sorting behavior.</span></span>  
  
 <span data-ttu-id="10718-108">La procedura seguente illustra la `Priority` colonna di procedura [: personalizzare la formattazione dei dati nel controllo Windows Forms DataGridView](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span><span class="sxs-lookup"><span data-stu-id="10718-108">The following procedure shows the `Priority` column from [How to: Customize Data Formatting in the Windows Forms DataGridView Control](how-to-customize-data-formatting-in-the-windows-forms-datagridview-control.md).</span></span> <span data-ttu-id="10718-109">Questa colonna è una colonna dell'immagine e non è ordinabile per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="10718-109">This column is an image column and is not sortable by default.</span></span> <span data-ttu-id="10718-110">Contiene tuttavia i valori di cella effettivi che sono stringhe, pertanto è possibile ordinarli automaticamente.</span><span class="sxs-lookup"><span data-stu-id="10718-110">It contains actual cell values that are strings, however, so it can be sorted automatically.</span></span>  
  
### <a name="to-set-the-sort-mode-for-a-column"></a><span data-ttu-id="10718-111">Per impostare la modalità di ordinamento per una colonna</span><span class="sxs-lookup"><span data-stu-id="10718-111">To set the sort mode for a column</span></span>  
  
- <span data-ttu-id="10718-112">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="10718-112">Set the <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#066)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#066](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#066)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="10718-113">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="10718-113">Compiling the Code</span></span>  
 <span data-ttu-id="10718-114">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="10718-114">This example requires:</span></span>  
  
- <span data-ttu-id="10718-115">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` contenente una colonna denominata `Priority`.</span><span class="sxs-lookup"><span data-stu-id="10718-115">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Priority`.</span></span>  
  
- <span data-ttu-id="10718-116">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="10718-116">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10718-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10718-117">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridViewColumn.SortMode%2A?displayProperty=nameWithType>
- [<span data-ttu-id="10718-118">Ordinamento di dati nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="10718-118">Sorting Data in the Windows Forms DataGridView Control</span></span>](sorting-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="10718-119">Modalità di ordinamento delle colonne nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="10718-119">Column Sort Modes in the Windows Forms DataGridView Control</span></span>](column-sort-modes-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="10718-120">Procedura: Personalizzare l'ordinamento nel controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="10718-120">How to: Customize Sorting in the Windows Forms DataGridView Control</span></span>](how-to-customize-sorting-in-the-windows-forms-datagridview-control.md)
