---
title: 'Procedura: Raggruppare gli elementi di un controllo ListView che implementa una GridView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], grouping items with GridViews
- grouping items in ListViews implementing GridViews [WPF]
- GridView controls [WPF], grouping items
ms.assetid: eebef25b-ddc6-424e-a66d-ea228d1bf33d
ms.openlocfilehash: 1570eab70dae690f508975162b7553de92be6f12
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54664356"
---
# <a name="how-to-group-items-in-a-listview-that-implements-a-gridview"></a>Procedura: Raggruppare gli elementi di un controllo ListView che implementa una GridView
In questo esempio viene illustrato come visualizzare i gruppi di voci di <xref:System.Windows.Controls.GridView> modalità di visualizzazione di un <xref:System.Windows.Controls.ListView> controllo.  
  
## <a name="example"></a>Esempio  
 Per visualizzare i gruppi di elementi in un <xref:System.Windows.Controls.ListView>, definire un <xref:System.Windows.Data.CollectionViewSource>. L'esempio seguente mostra una <xref:System.Windows.Data.CollectionViewSource> che raggruppa gli elementi di dati secondo il valore della `Catalog` campo dati.  
  
 [!code-xaml[GridViewWithGroups#GroupingCollectionViewSource](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#groupingcollectionviewsource)]  
  
 L'esempio seguente imposta la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per il <xref:System.Windows.Controls.ListView> per il <xref:System.Windows.Data.CollectionViewSource> definito nell'esempio precedente. L'esempio definisce anche un <xref:System.Windows.Controls.ItemsControl.GroupStyle%2A> che implementa un <xref:System.Windows.Controls.Expander> controllo.  
  
 [!code-xaml[GridViewWithGroups#ListViewGroups](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewgroups)]  
[!code-xaml[GridViewWithGroups#ListViewEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GridViewWithGroups/CS/Window1.xaml#listviewend)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
- [Panoramica sul controllo ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
- [Cenni preliminari su GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
