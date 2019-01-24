---
title: 'Procedura: Utilizzare i trigger per applicare uno stile agli elementi selezionati in un controllo ListView'
ms.date: 03/30/2017
helpviewer_keywords:
- ListView controls [WPF], styling
ms.assetid: 1e2bdce0-afe8-4507-9b18-f33de43de25a
ms.openlocfilehash: 5229c8db70d7d1200c75c7cbefd497e62cf72bdd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54682053"
---
# <a name="how-to-use-triggers-to-style-selected-items-in-a-listview"></a>Procedura: Utilizzare i trigger per applicare uno stile agli elementi selezionati in un controllo ListView
In questo esempio viene illustrato come definire <xref:System.Windows.Style.Triggers%2A> per un <xref:System.Windows.Controls.ListViewItem> controllo in modo che quando un valore della proprietà di un <xref:System.Windows.Controls.ListViewItem> modifiche, il <xref:System.Windows.Style> del <xref:System.Windows.Controls.ListViewItem> modifiche in risposta.  
  
## <a name="example"></a>Esempio  
 Se si desidera che il <xref:System.Windows.Style> di un <xref:System.Windows.Controls.ListViewItem> per modificare in risposta alle modifiche delle proprietà, definire <xref:System.Windows.Style.Triggers%2A> per il <xref:System.Windows.Style> modificare.  
  
 L'esempio seguente definisce un <xref:System.Windows.Trigger> che consente di scegliere il <xref:System.Windows.Controls.Control.Foreground%2A> proprietà <xref:System.Windows.Media.Brushes.Blue%2A> e cambia il <xref:System.Windows.FrameworkElement.Cursor%2A> per visualizzare un <xref:System.Windows.Input.CursorType.Hand> quando la <xref:System.Windows.UIElement.IsMouseOver%2A> le modifiche alle proprietà `true`.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#Trigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#trigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
 L'esempio seguente definisce una <xref:System.Windows.MultiTrigger> che consente di scegliere il <xref:System.Windows.Controls.Control.Foreground%2A> proprietà di un <xref:System.Windows.Controls.ListViewItem> al <xref:System.Windows.Media.Brushes.Yellow%2A> quando il <xref:System.Windows.Controls.ListViewItem> è l'elemento selezionato e lo stato attivo.  
  
 [!code-xaml[ListViewChkBox#ListViewItemTriggersStart](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersstart)]  
[!code-xaml[ListViewChkBox#MultiTrigger](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#multitrigger)]  
[!code-xaml[ListViewChkBox#ListViewItemTriggersEnd](../../../../samples/snippets/csharp/VS_Snippets_Wpf/ListViewChkBox/CS/window1.xaml#listviewitemtriggersend)]  
  
## <a name="see-also"></a>Vedere anche
- <xref:System.Windows.Controls.Control>
- <xref:System.Windows.Controls.ListView>
- <xref:System.Windows.Controls.GridView>
- [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/listview-how-to-topics.md)
- [Panoramica sul controllo ListView](../../../../docs/framework/wpf/controls/listview-overview.md)
- [Cenni preliminari su GridView](../../../../docs/framework/wpf/controls/gridview-overview.md)
