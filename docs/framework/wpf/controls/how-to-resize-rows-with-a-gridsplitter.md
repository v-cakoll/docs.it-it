---
title: 'Procedura: ridimensionare le righe con un GridSplitter'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- resizing grid rows [WPF]
- grid rows [WPF], resizing
- GridSplitter control [WPF], resizing grid rows
ms.assetid: 2413a9f2-1d81-46ed-95cb-95ec8233eea2
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6621cc0048270b97c42ff4c4e646b0ddd9ca3477
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-resize-rows-with-a-gridsplitter"></a><span data-ttu-id="638b6-102">Procedura: ridimensionare le righe con un GridSplitter</span><span class="sxs-lookup"><span data-stu-id="638b6-102">How to: Resize Rows with a GridSplitter</span></span>
<span data-ttu-id="638b6-103">In questo esempio viene illustrato come utilizzare un oggetto orizzontale <xref:System.Windows.Controls.GridSplitter> per ridistribuire lo spazio tra le due righe in un <xref:System.Windows.Controls.Grid> senza modificare le dimensioni del <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="638b6-103">This example shows how to use a horizontal <xref:System.Windows.Controls.GridSplitter> to redistribute the space between two rows in a <xref:System.Windows.Controls.Grid> without changing the dimensions of the <xref:System.Windows.Controls.Grid>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="638b6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="638b6-104">Example</span></span>  
 <span data-ttu-id="638b6-105">**Come creare un oggetto GridSplitter si sovrapponga al bordo di una riga**</span><span class="sxs-lookup"><span data-stu-id="638b6-105">**How to create a GridSplitter that overlays the edge of a row**</span></span>  
  
 <span data-ttu-id="638b6-106">Per specificare un <xref:System.Windows.Controls.GridSplitter> che ridimensiona le righe adiacenti in un <xref:System.Windows.Controls.Grid>, impostare il <xref:System.Windows.Controls.Grid.Row%2A> proprietà associata a una delle righe da ridimensionare.</span><span class="sxs-lookup"><span data-stu-id="638b6-106">To specify a <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="638b6-107">Se il <xref:System.Windows.Controls.Grid> ha più di una colonna, impostare il <xref:System.Windows.Controls.Grid.ColumnSpan%2A> proprietà associata per specificare il numero di colonne.</span><span class="sxs-lookup"><span data-stu-id="638b6-107">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to specify the number of columns.</span></span> <span data-ttu-id="638b6-108">Impostare quindi la <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> a <xref:System.Windows.VerticalAlignment.Top> o <xref:System.Windows.VerticalAlignment.Bottom> (l'allineamento impostato dipende dalle due righe da ridimensionare).</span><span class="sxs-lookup"><span data-stu-id="638b6-108">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Top> or <xref:System.Windows.VerticalAlignment.Bottom> (which alignment you set depends on which two rows you want to resize).</span></span> <span data-ttu-id="638b6-109">Infine, impostare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà <xref:System.Windows.HorizontalAlignment.Stretch>.</span><span class="sxs-lookup"><span data-stu-id="638b6-109">Finally, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>.</span></span>  
  
 <span data-ttu-id="638b6-110">Nell'esempio seguente viene illustrato come definire un oggetto orizzontale <xref:System.Windows.Controls.GridSplitter> che ridimensiona le righe adiacenti.</span><span class="sxs-lookup"><span data-stu-id="638b6-110">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that resizes adjacent rows.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterRowOverlay](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterrowoverlay)]  
  
 <span data-ttu-id="638b6-111">A <xref:System.Windows.Controls.GridSplitter> che non occupino una riga può essere nascosto da altri controlli di <xref:System.Windows.Controls.Grid>.</span><span class="sxs-lookup"><span data-stu-id="638b6-111">A <xref:System.Windows.Controls.GridSplitter> that does not occupy its own row may be obscured by other controls in the <xref:System.Windows.Controls.Grid>.</span></span> <span data-ttu-id="638b6-112">Per altre informazioni su come evitare questo problema, vedere [Assicurarsi che GridSplitter sia visibile](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span><span class="sxs-lookup"><span data-stu-id="638b6-112">For more information about how to prevent this issue, see [Make Sure That a GridSplitter Is Visible](../../../../docs/framework/wpf/controls/how-to-make-sure-that-a-gridsplitter-is-visible.md).</span></span>  
  
 <span data-ttu-id="638b6-113">**Come creare un oggetto GridSplitter che occupa una riga**</span><span class="sxs-lookup"><span data-stu-id="638b6-113">**How to create a GridSplitter that occupies a row**</span></span>  
  
 <span data-ttu-id="638b6-114">Per specificare un <xref:System.Windows.Controls.GridSplitter> che occupa una riga in un <xref:System.Windows.Controls.Grid>, impostare il <xref:System.Windows.Controls.Grid.Row%2A> proprietà associata a una delle righe da ridimensionare.</span><span class="sxs-lookup"><span data-stu-id="638b6-114">To specify a <xref:System.Windows.Controls.GridSplitter> that occupies a row in a <xref:System.Windows.Controls.Grid>, set the <xref:System.Windows.Controls.Grid.Row%2A> attached property to one of the rows that you want to resize.</span></span> <span data-ttu-id="638b6-115">Se il <xref:System.Windows.Controls.Grid> ha più di una colonna, impostare il <xref:System.Windows.Controls.Grid.ColumnSpan%2A> proprietà associata al numero di colonne.</span><span class="sxs-lookup"><span data-stu-id="638b6-115">If your <xref:System.Windows.Controls.Grid> has more than one column, set the <xref:System.Windows.Controls.Grid.ColumnSpan%2A> attached property to the number of columns.</span></span> <span data-ttu-id="638b6-116">Quindi impostare il <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> a <xref:System.Windows.VerticalAlignment.Center>, impostare il <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> proprietà <xref:System.Windows.HorizontalAlignment.Stretch>e impostare il <xref:System.Windows.Controls.RowDefinition.Height%2A> della riga che contiene il <xref:System.Windows.Controls.GridSplitter> a <xref:System.Windows.GridLength.Auto%2A>.</span><span class="sxs-lookup"><span data-stu-id="638b6-116">Then set the <xref:System.Windows.FrameworkElement.VerticalAlignment%2A> to <xref:System.Windows.VerticalAlignment.Center>, set the <xref:System.Windows.FrameworkElement.HorizontalAlignment%2A> property to <xref:System.Windows.HorizontalAlignment.Stretch>, and set the <xref:System.Windows.Controls.RowDefinition.Height%2A> of the row that contains the <xref:System.Windows.Controls.GridSplitter> to <xref:System.Windows.GridLength.Auto%2A>.</span></span>  
  
 <span data-ttu-id="638b6-117">Nell'esempio seguente viene illustrato come definire un oggetto orizzontale <xref:System.Windows.Controls.GridSplitter> che occupa una riga e ridimensiona le righe su entrambi i lati di esso.</span><span class="sxs-lookup"><span data-stu-id="638b6-117">The following example shows how to define a horizontal <xref:System.Windows.Controls.GridSplitter> that occupies a row and resizes the rows on either side of it.</span></span>  
  
 [!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart1)]  
[!code-xaml[GridSplitterRowColumn#GridSplitterEntireRowPart2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridSplitterRowColumn/CS/Window1.xaml#gridsplitterentirerowpart2)]  
  
## <a name="see-also"></a><span data-ttu-id="638b6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="638b6-118">See Also</span></span>  
 <xref:System.Windows.Controls.GridSplitter>  
 [<span data-ttu-id="638b6-119">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="638b6-119">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/gridsplitter-how-to-topics.md)
