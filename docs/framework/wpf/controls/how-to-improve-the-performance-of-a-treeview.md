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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61771007"
---
# <a name="how-to-improve-the-performance-of-a-treeview"></a>Procedura: Migliorare le prestazioni di un controllo TreeView
Se un <xref:System.Windows.Controls.TreeView> contiene molti elementi, la quantità di tempo impiegato per caricare potrebbe provocare un ritardo significativo nell'interfaccia utente. È possibile migliorare il tempo di caricamento, impostando il `VirtualizingStackPanel.IsVirtualizing` proprietà associata `true`.  L'interfaccia utente potrebbe anche risultare lento reagisce quando l'utente scorre il <xref:System.Windows.Controls.TreeView> usando la rotellina del mouse o trascinando il cursore di una barra di scorrimento. È possibile migliorare le prestazioni dei <xref:System.Windows.Controls.TreeView> quando l'utente scorre, impostare il `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType>.  
  
## <a name="example"></a>Esempio  
  
## <a name="description"></a>Descrizione  
L'esempio seguente crea una <xref:System.Windows.Controls.TreeView> che consente di scegliere il `VirtualizingStackPanel.IsVirtualizing` collegato proprietà su true e il `VirtualizingStackPanel.VirtualizationMode` proprietà associata <xref:System.Windows.Controls.VirtualizationMode.Recycling?displayProperty=nameWithType> per ottimizzarne le prestazioni.  
  
## <a name="code"></a>Codice  
 [!code-xaml[RecycleItemContainerShippets#VirtualizingTreeView](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml#virtualizingtreeview)]  
  
 Nell'esempio seguente mostra i dati che usa l'esempio precedente.  
  
 [!code-csharp[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/csharp/VS_Snippets_Wpf/RecycleItemContainerShippets/CSharp/Window1.xaml.cs#treeviewdata)]
 [!code-vb[RecycleItemContainerShippets#TreeViewData](~/samples/snippets/visualbasic/VS_Snippets_Wpf/RecycleItemContainerShippets/visualbasic/window1.xaml.vb#treeviewdata)]  
  
## <a name="see-also"></a>Vedere anche

- [Controlli](../advanced/optimizing-performance-controls.md)
