---
title: 'Procedura: migliorare le prestazioni di un controllo TreeView'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], improving the performance
ms.assetid: b792c740-cf2b-4da8-8ba8-3d2e5a821874
ms.openlocfilehash: 75f17c770af89f08fedfd3c8193a916901fe6f79
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33552753"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>Procedura: migliorare le prestazioni di un controllo TreeView
Se un <xref:System.Windows.Controls.TreeView> contiene molti elementi, la quantità di tempo impiegato per caricare potrebbe comportare un notevole ritardo nell'interfaccia utente. È possibile migliorare il tempo di caricamento tramite l'impostazione di `VirtualizingStackPanel.IsVirtualizing` proprietà associata `true`.  L'interfaccia utente potrebbe inoltre essere lento a rispondere quando un utente scorre il <xref:System.Windows.Controls.TreeView> usando la rotellina del mouse o trascinando il cursore di una barra di scorrimento. È possibile migliorare le prestazioni del <xref:System.Windows.Controls.TreeView> quando l'utente scorre impostando il `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
Nell'esempio seguente viene creato un <xref:System.Windows.Controls.TreeView> che imposta il `VirtualizingStackPanel.IsVirtualizing` proprietà associata su true e `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> per ottimizzare le prestazioni.  
  
## <a name="code"></a>Codice  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 Nell'esempio seguente mostra i dati che utilizza l'esempio precedente.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>Vedere anche  
 [Controlli](../../../../docs/framework/wpf/advanced/optimizing-performance-controls.md)
