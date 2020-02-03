---
title: Aggiungere descrizioni comandi a singole celle nel controllo DataGridView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
ms.openlocfilehash: ac86db5fa27a95adb20888cd59b5e236941d9177
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2020
ms.locfileid: "76732185"
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="2d719-102">Procedura: aggiungere descrizioni comandi a singole celle in un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="2d719-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="2d719-103">Per impostazione predefinita, le descrizioni comandi vengono utilizzate per visualizzare i valori delle celle <xref:System.Windows.Forms.DataGridView> troppo piccole per visualizzare l'intero contenuto.</span><span class="sxs-lookup"><span data-stu-id="2d719-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="2d719-104">È tuttavia possibile eseguire l'override di questo comportamento per impostare i valori di testo della descrizione comando per le singole celle.</span><span class="sxs-lookup"><span data-stu-id="2d719-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="2d719-105">Questa operazione è utile per visualizzare agli utenti informazioni aggiuntive su una cella o per fornire agli utenti una descrizione alternativa del contenuto della cella.</span><span class="sxs-lookup"><span data-stu-id="2d719-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="2d719-106">Se, ad esempio, è presente una riga in cui sono visualizzate le icone di stato, è possibile fornire spiegazioni del testo utilizzando le descrizioni comandi.</span><span class="sxs-lookup"><span data-stu-id="2d719-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="2d719-107">È anche possibile disabilitare la visualizzazione delle descrizioni comando a livello di cella impostando la proprietà <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> su `false`.</span><span class="sxs-lookup"><span data-stu-id="2d719-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="2d719-108">Per aggiungere una descrizione comando a una cella</span><span class="sxs-lookup"><span data-stu-id="2d719-108">To add a ToolTip to a cell</span></span>  
  
- <span data-ttu-id="2d719-109">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2d719-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="2d719-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="2d719-110">Compiling the Code</span></span>  
  
- <span data-ttu-id="2d719-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2d719-111">This example requires:</span></span>  
  
- <span data-ttu-id="2d719-112">Un controllo <xref:System.Windows.Forms.DataGridView> denominato `dataGridView1` che contiene una colonna denominata `Rating` per la visualizzazione dei valori stringa di uno e quattro simboli asterisco ("\*").</span><span class="sxs-lookup"><span data-stu-id="2d719-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("\*") symbols.</span></span> <span data-ttu-id="2d719-113">L'evento <xref:System.Windows.Forms.DataGridView.CellFormatting> del controllo deve essere associato al metodo del gestore eventi illustrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="2d719-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
- <span data-ttu-id="2d719-114">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="2d719-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="2d719-115">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="2d719-115">Robust Programming</span></span>  
 <span data-ttu-id="2d719-116">Quando si associa il controllo <xref:System.Windows.Forms.DataGridView> a un'origine dati esterna o si fornisce un'origine dati personalizzata implementando la modalità virtuale, è possibile che si verifichino problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="2d719-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="2d719-117">Per evitare una riduzione delle prestazioni quando si lavora con grandi quantità di dati, gestire l'evento <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> anziché impostare la proprietà <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> di più celle.</span><span class="sxs-lookup"><span data-stu-id="2d719-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="2d719-118">Quando si gestisce questo evento, se si recupera il valore di una cella <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> proprietà, viene generato l'evento e viene restituito il valore della proprietà <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType>, come specificato nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="2d719-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d719-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2d719-119">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>
- <xref:System.Windows.Forms.DataGridViewCell>
- <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>
- [<span data-ttu-id="2d719-120">Programmazione con celle, righe e colonne nel controllo DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="2d719-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](programming-with-cells-rows-and-columns-in-the-datagrid.md)
