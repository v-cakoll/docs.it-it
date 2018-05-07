---
title: 'Procedura: raggruppare gli elementi di un controllo ListView che implementa una GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: 76074449d4ea1454689c51ecad54d7c495f00872
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a>Procedura: raggruppare gli elementi di un controllo ListView che implementa una GridView
In questo esempio viene illustrato come visualizzare i gruppi di elementi nel <xref:System.Windows.Controls.GridView> modalità di visualizzazione di un <xref:System.Windows.Controls.ListView> controllo.  
  
## <a name="example"></a>Esempio  
 Per visualizzare i gruppi di elementi in un <xref:System.Windows.Controls.ListView>, definire un <xref:System.Windows.Data.CollectionViewSource>. Nell'esempio seguente un <xref:System.Windows.Data.CollectionViewSource> che raggruppa gli elementi di dati in base al valore del `Catalog` campo dati.  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 L'esempio seguente imposta il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per il <xref:System.Windows.Controls.ListView> per il <xref:System.Windows.Data.CollectionViewSource> definito nell'esempio precedente. Viene inoltre definito un <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> che implementa un <xref:System.Windows.Controls.Expander> controllo.  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.ListView>  
 <xref:System.Windows.Controls.GridView>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)  
 [Panoramica sul controllo ListView](../../../../docs/framework/wpf/controls/listview-overview.md)  
 [Cenni preliminari su GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
