---
title: 'Procedura: Migliorare le prestazioni di un controllo TreeView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: de1b46da2a7c6c3db0c0c19cdbb654fcf2fbbd6c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153439"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a><span data-ttu-id="1baed-102">Procedura: Migliorare le prestazioni di un controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="1baed-102">How to: Improve the Performance of a TreeView</span></span>
<span data-ttu-id="1baed-103">Se un <xref:System.Windows.Controls.TreeView> contiene molti elementi, la quantità di tempo impiegato per caricare potrebbe provocare un ritardo significativo nell'interfaccia utente.</span><span class="sxs-lookup"><span data-stu-id="1baed-103">If a <xref:System.Windows.Controls.TreeView> contains many items, the amount of time it takes to load may cause a significant delay in the user interface.</span></span> <span data-ttu-id="1baed-104">È possibile migliorare il tempo di caricamento, impostando il `VirtualizingStackPanel.IsVirtualizing` proprietà associata `true`.</span><span class="sxs-lookup"><span data-stu-id="1baed-104">You can improve the load time by setting the `VirtualizingStackPanel.IsVirtualizing` attached property to `true`.</span></span>  <span data-ttu-id="1baed-105">L'interfaccia utente potrebbe anche risultare lento reagisce quando l'utente scorre il <xref:System.Windows.Controls.TreeView> usando la rotellina del mouse o trascinando il cursore di una barra di scorrimento.</span><span class="sxs-lookup"><span data-stu-id="1baed-105">The UI might also be slow to react when a user scrolls the <xref:System.Windows.Controls.TreeView> by using the mouse wheel or dragging the thumb of a scrollbar.</span></span> <span data-ttu-id="1baed-106">È possibile migliorare le prestazioni dei <xref:System.Windows.Controls.TreeView> quando l'utente scorre, impostare il `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="1baed-106">You can improve the performance of the <xref:System.Windows.Controls.TreeView> when the user scrolls by setting the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1baed-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="1baed-107">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="1baed-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="1baed-108">Description</span></span>  
<span data-ttu-id="1baed-109">L'esempio seguente crea una <xref:System.Windows.Controls.TreeView> che consente di scegliere il `VirtualizingStackPanel.IsVirtualizing` collegato proprietà su true e il `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> per ottimizzarne le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="1baed-109">The following example creates a <xref:System.Windows.Controls.TreeView> that sets the `VirtualizingStackPanel.IsVirtualizing` attached property to true and the `VirtualizingStackPanel.VirtualizationMode` attached property to <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> to optimize its performance.</span></span>  
  
## <a name="code"></a><span data-ttu-id="1baed-110">Codice</span><span class="sxs-lookup"><span data-stu-id="1baed-110">Code</span></span>  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 <span data-ttu-id="1baed-111">Nell'esempio seguente mostra i dati che usa l'esempio precedente.</span><span class="sxs-lookup"><span data-stu-id="1baed-111">The following example shows the data that the previous example uses.</span></span>  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a><span data-ttu-id="1baed-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1baed-112">See also</span></span>

- [<span data-ttu-id="1baed-113">Controlli</span><span class="sxs-lookup"><span data-stu-id="1baed-113">Controls</span></span>](../advanced/optimizing-performance-controls.md)
