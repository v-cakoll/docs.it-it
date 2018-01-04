---
title: 'Procedura: aggiungere descrizioni comandi a singole celle in un controllo DataGridView di Windows Form'
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
- tooltips [Windows Forms], adding to data grids
- DataGridView control [Windows Forms], adding tooltips
- data grids [Windows Forms], adding tooltips
ms.assetid: 2a81f9de-d58b-4ea8-bc0b-8d93c2f4cf78
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a533f4cbf5000489e774ba8661c3ab03cea4948a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-add-tooltips-to-individual-cells-in-a-windows-forms-datagridview-control"></a><span data-ttu-id="ac009-102">Procedura: aggiungere descrizioni comandi a singole celle in un controllo DataGridView di Windows Form</span><span class="sxs-lookup"><span data-stu-id="ac009-102">How to: Add ToolTips to Individual Cells in a Windows Forms DataGridView Control</span></span>
<span data-ttu-id="ac009-103">Per impostazione predefinita, le descrizioni comandi consentono di visualizzare i valori di <xref:System.Windows.Forms.DataGridView> celle che sono troppo piccole per visualizzare il contenuto intero.</span><span class="sxs-lookup"><span data-stu-id="ac009-103">By default, ToolTips are used to display the values of <xref:System.Windows.Forms.DataGridView> cells that are too small to show their entire contents.</span></span> <span data-ttu-id="ac009-104">È possibile ignorare questo comportamento, tuttavia, per impostare i valori di testo della descrizione comando per le singole celle.</span><span class="sxs-lookup"><span data-stu-id="ac009-104">You can override this behavior, however, to set ToolTip-text values for individual cells.</span></span> <span data-ttu-id="ac009-105">Ciò è utile per visualizzare ulteriori informazioni su una cella o di fornire agli utenti una descrizione alternativa del contenuto della cella.</span><span class="sxs-lookup"><span data-stu-id="ac009-105">This is useful to display to users additional information about a cell or to provide to users an alternate description of the cell contents.</span></span> <span data-ttu-id="ac009-106">Ad esempio, se si dispone di una riga che consente di visualizzare le icone di stato, è opportuno fornire descrizioni testuali tramite le descrizioni comandi.</span><span class="sxs-lookup"><span data-stu-id="ac009-106">For example, if you have a row that displays status icons, you may want to provide text explanations using ToolTips.</span></span>  
  
 <span data-ttu-id="ac009-107">È anche possibile disabilitare la visualizzazione delle descrizioni comandi a livello di cella impostando il <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> proprietà `false`.</span><span class="sxs-lookup"><span data-stu-id="ac009-107">You can also disable the display of cell-level ToolTips by setting the <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType> property to `false`.</span></span>  
  
### <a name="to-add-a-tooltip-to-a-cell"></a><span data-ttu-id="ac009-108">Per aggiungere una descrizione comandi a una cella</span><span class="sxs-lookup"><span data-stu-id="ac009-108">To add a ToolTip to a cell</span></span>  
  
-   <span data-ttu-id="ac009-109">Impostare la proprietà <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ac009-109">Set the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType> property.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/cpp/datagridviewcell.tooltiptext.cpp#1)]
     [!code-csharp[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/CS/datagridviewcell.tooltiptext.cs#1)]
     [!code-vb[System.Windows.Forms.DataGridViewCell.ToolTipText#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewCell.ToolTipText/VB/datagridviewcell.tooltiptext.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="ac009-110">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="ac009-110">Compiling the Code</span></span>  
  
-   <span data-ttu-id="ac009-111">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac009-111">This example requires:</span></span>  
  
-   <span data-ttu-id="ac009-112">Oggetto <xref:System.Windows.Forms.DataGridView> controllo denominato `dataGridView1` che contiene una colonna denominata `Rating` per la visualizzazione dei valori di stringa di uno a quattro asterisco ("*") i simboli.</span><span class="sxs-lookup"><span data-stu-id="ac009-112">A <xref:System.Windows.Forms.DataGridView> control named `dataGridView1` that contains a column named `Rating` for displaying string values of one through four asterisk ("*") symbols.</span></span> <span data-ttu-id="ac009-113">Il <xref:System.Windows.Forms.DataGridView.CellFormatting> evento del controllo deve essere associata al metodo del gestore eventi illustrato nell'esempio.</span><span class="sxs-lookup"><span data-stu-id="ac009-113">The <xref:System.Windows.Forms.DataGridView.CellFormatting> event of the control must be associated with the event handler method shown in the example.</span></span>  
  
-   <span data-ttu-id="ac009-114">Riferimenti agli assembly <xref:System?displayProperty=nameWithType> e <xref:System.Windows.Forms?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ac009-114">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="ac009-115">Programmazione efficiente</span><span class="sxs-lookup"><span data-stu-id="ac009-115">Robust Programming</span></span>  
 <span data-ttu-id="ac009-116">Quando si associa il <xref:System.Windows.Forms.DataGridView> il controllo a un'origine dati esterna o fornire la propria origine dati mediante l'implementazione della modalità virtuale, possono verificarsi problemi di prestazioni.</span><span class="sxs-lookup"><span data-stu-id="ac009-116">When you bind the <xref:System.Windows.Forms.DataGridView> control to an external data source or provide your own data source by implementing virtual mode, you might encounter performance issues.</span></span> <span data-ttu-id="ac009-117">Per evitare una riduzione delle prestazioni quando si lavora con grandi quantità di dati, gestire il <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> evento invece di impostare il <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> proprietà di più celle.</span><span class="sxs-lookup"><span data-stu-id="ac009-117">To avoid a performance penalty when working with large amounts of data, handle the <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded> event rather than setting the <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property of multiple cells.</span></span> <span data-ttu-id="ac009-118">Quando si gestisce questo evento, ottenere il valore di una cella <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> proprietà genera l'evento e restituisce il valore di <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> proprietà come specificato nel gestore eventi.</span><span class="sxs-lookup"><span data-stu-id="ac009-118">When you handle this event, getting the value of a cell <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A> property raises the event and returns the value of the <xref:System.Windows.Forms.DataGridViewCellToolTipTextNeededEventArgs.ToolTipText%2A?displayProperty=nameWithType> property as specified in the event handler.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac009-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac009-119">See Also</span></span>  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.ShowCellToolTips%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridView.CellToolTipTextNeeded?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewCell>  
 <xref:System.Windows.Forms.DataGridViewCell.ToolTipText%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="ac009-120">Programmazione con celle, righe e colonne nel controllo DataGridView Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ac009-120">Programming with Cells, Rows, and Columns in the Windows Forms DataGridView Control</span></span>](../../../../docs/framework/winforms/controls/programming-with-cells-rows-and-columns-in-the-datagrid.md)
