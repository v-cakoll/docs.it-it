---
title: 'Procedura: migliorare le prestazioni di un controllo TreeView'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2c13a9c89bdcb149df61f26177ea8705e502402f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="b4d26-102">Procedura: migliorare le prestazioni di un controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="b4d26-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="b4d26-103">Se un <xref:System.Windows.Controls.TreeView> contiene molti elementi, la quantità di tempo impiegato per caricare potrebbe comportare un notevole ritardo nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="b4d26-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="b4d26-104">È possibile migliorare il tempo di caricamento tramite l'impostazione di `VirtualizingStackPanel.IsVirtualizing` proprietà associata `true`.</span><span class="sxs-lookup"><span data-stu-id="b4d26-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="b4d26-105">L'interfaccia utente potrebbe inoltre essere lento a rispondere quando un utente scorre il <xref:System.Windows.Controls.TreeView> usando la rotellina del mouse o trascinando il cursore di una barra di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="b4d26-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="b4d26-106">È possibile migliorare le prestazioni del <xref:System.Windows.Controls.TreeView> quando l'utente scorre impostando il `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b4d26-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4d26-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="b4d26-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="b4d26-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4d26-108">Description</span></span>  
<span data-ttu-id="b4d26-109">Nell'esempio seguente viene creato un <xref:System.Windows.Controls.TreeView> che imposta il `VirtualizingStackPanel.IsVirtualizing` proprietà associata su true e `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> per ottimizzare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="b4d26-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="b4d26-110">Codice</span><span class="sxs-lookup"><span data-stu-id="b4d26-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="b4d26-111">Nell'esempio seguente mostra i dati che utilizza l'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="b4d26-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="b4d26-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4d26-112">See Also</span></span>  
 [<span data-ttu-id="b4d26-113">Controlli</span><span class="sxs-lookup"><span data-stu-id="b4d26-113">Controls</span></span>](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
