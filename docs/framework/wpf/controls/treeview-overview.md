---
title: Cenni preliminari sul controllo TreeView
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: 267e870e13d26439e4fbcbba3c5741ff84cabe3c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187375"
---
# <a name="treeview-overview"></a>Cenni preliminari sul controllo TreeView
Il <xref:System.Windows.Controls.TreeView> controllo consente di visualizzare informazioni in una struttura gerarchica utilizzando nodi comprimibili. In questo argomento <xref:System.Windows.Controls.TreeView> <xref:System.Windows.Controls.TreeViewItem> vengono presentati i controlli e vengono forniti semplici esempi del relativo utilizzo.  

<a name="Simple_TreeView_Control"></a>
## <a name="what-is-a-treeview"></a>Che cos'è un controllo TreeView?  
 <xref:System.Windows.Controls.TreeView>è <xref:System.Windows.Controls.ItemsControl> un oggetto che nidifica <xref:System.Windows.Controls.TreeViewItem> gli elementi utilizzando i controlli. Nell'esempio riportato di seguito viene creato un <xref:System.Windows.Controls.TreeView>oggetto .  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>
## <a name="creating-a-treeview"></a>Creazione di un controllo TreeView  
 Il <xref:System.Windows.Controls.TreeView> controllo contiene <xref:System.Windows.Controls.TreeViewItem> una gerarchia di controlli. Un <xref:System.Windows.Controls.TreeViewItem> controllo <xref:System.Windows.Controls.HeaderedItemsControl> è un <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> che <xref:System.Windows.Controls.ItemsControl.Items%2A> dispone di un e una raccolta.  
  
 Se si <xref:System.Windows.Controls.TreeView> definisce [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)]un oggetto utilizzando <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> , è <xref:System.Windows.Controls.TreeViewItem> possibile definire in modo esplicito il contenuto di un controllo e gli elementi che ne costituiscono l'insieme. La figura precedente illustra questo metodo.  
  
 È inoltre possibile <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> specificare un come <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> origine <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> dati <xref:System.Windows.Controls.TreeViewItem> e quindi specificare un e per definire il contenuto.  
  
 Per definire il <xref:System.Windows.Controls.TreeViewItem> layout di un <xref:System.Windows.HierarchicalDataTemplate> controllo, è anche possibile utilizzare gli oggetti. Per altre informazioni e un esempio, vedere [Uso di SelectedValue, SelectedValuePath e SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Se un elemento <xref:System.Windows.Controls.TreeViewItem> non è un controllo, <xref:System.Windows.Controls.TreeViewItem> viene racchiuso automaticamente da un controllo quando il <xref:System.Windows.Controls.TreeView> controllo viene visualizzato.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>
## <a name="expanding-and-collapsing-a-treeviewitem"></a>Espansione e compressione di un oggetto TreeViewItem  
 Se l'utente <xref:System.Windows.Controls.TreeViewItem>espande <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> un oggetto `true`, la proprietà è impostata su . È inoltre possibile espandere <xref:System.Windows.Controls.TreeViewItem> o comprimere un senza <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> alcuna azione diretta dell'utente impostando la proprietà su `true` (espandere) o `false` (comprimere). Quando questa proprietà <xref:System.Windows.Controls.TreeViewItem.Expanded> viene <xref:System.Windows.Controls.TreeViewItem.Collapsed> modificata, si verifica un evento o .  
  
 Quando <xref:System.Windows.FrameworkElement.BringIntoView%2A> il metodo viene <xref:System.Windows.Controls.TreeViewItem> chiamato <xref:System.Windows.Controls.TreeViewItem> su un <xref:System.Windows.Controls.TreeViewItem> controllo, i controlli padre e e più controlli espandere. Se <xref:System.Windows.Controls.TreeViewItem> un oggetto non è <xref:System.Windows.Controls.TreeView> visibile o parzialmente visibile, scorre per renderlo visibile.  
  
<a name="TreeViewItem_Selection"></a>
## <a name="treeviewitem-selection"></a>Selezione di TreeViewItem  
 Quando un utente <xref:System.Windows.Controls.TreeViewItem> fa clic su <xref:System.Windows.Controls.TreeViewItem.Selected> un controllo per <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> selezionarlo, `true`si verifica l'evento e la relativa proprietà viene impostata su . Il <xref:System.Windows.Controls.TreeViewItem> diventa <xref:System.Windows.Controls.TreeView.SelectedItem%2A> anche <xref:System.Windows.Controls.TreeView> il del controllo. Al contrario, quando la <xref:System.Windows.Controls.TreeViewItem> selezione cambia <xref:System.Windows.Controls.TreeViewItem.Unselected> da un <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> controllo, `false`si verifica un evento e la relativa proprietà è impostata su .  
  
 La <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà <xref:System.Windows.Controls.TreeView> nel controllo è di sola lettura. pertanto, non è possibile impostarlo in modo esplicito. La <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà viene impostata se <xref:System.Windows.Controls.TreeViewItem> l'utente <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> fa clic `true` su <xref:System.Windows.Controls.TreeViewItem> un controllo o quando la proprietà è impostata su del controllo.  
  
 Utilizzare <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> la proprietà <xref:System.Windows.Controls.TreeView.SelectedValue%2A> per <xref:System.Windows.Controls.TreeView.SelectedItem%2A>specificare un oggetto . Per altre informazioni, vedere [Uso di SelectedValue, SelectedValuePath e SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 È possibile registrare un <xref:System.Windows.Controls.TreeView.SelectedItemChanged> gestore eventi nell'evento per determinare quando un oggetto selezionato <xref:System.Windows.Controls.TreeViewItem> viene modificato. Che <xref:System.Windows.RoutedPropertyChangedEventArgs%601> viene fornito al gestore <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>eventi specifica il , che <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>è la selezione precedente, e il , che è la selezione corrente. Il valore può essere `null` se l'applicazione o l'utente non ha effettuato una selezione precedente o attuale.  
  
<a name="TreeView_Style"></a>
## <a name="treeview-style"></a>Stile del controllo TreeView  
 Lo stile predefinito <xref:System.Windows.Controls.TreeView> per un <xref:System.Windows.Controls.StackPanel> controllo lo <xref:System.Windows.Controls.ScrollViewer> inserisce all'interno di un oggetto che contiene un controllo. Quando si <xref:System.Windows.FrameworkElement.Width%2A> impostano le proprietà <xref:System.Windows.FrameworkElement.Height%2A> e per <xref:System.Windows.Controls.TreeView>un <xref:System.Windows.Controls.StackPanel> oggetto , <xref:System.Windows.Controls.TreeView>questi valori vengono utilizzati per ridimensionare l'oggetto che visualizza il file . Se il contenuto da visualizzare è più <xref:System.Windows.Controls.ScrollViewer> grande dell'area di visualizzazione, viene visualizzato automaticamente un elemento in modo che l'utente possa scorrere il <xref:System.Windows.Controls.TreeView> contenuto.  
  
 Per personalizzare l'aspetto di <xref:System.Windows.Controls.TreeViewItem> <xref:System.Windows.FrameworkElement.Style%2A> un controllo, <xref:System.Windows.Style>impostare la proprietà su un oggetto .  
  
 Nell'esempio riportato di <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.FontSize%2A> seguito viene <xref:System.Windows.Controls.TreeViewItem> illustrato come <xref:System.Windows.FrameworkElement.Style%2A>impostare i valori delle proprietà e per un controllo utilizzando un oggetto .  
  
 [!code-xaml[TreeViewSimple#8](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>
## <a name="adding-images-and-other-content-to-treeview-items"></a>Aggiunta di immagini e altro contenuto a elementi di TreeView  
 È possibile includere più di <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> un <xref:System.Windows.Controls.TreeViewItem>oggetto nel contenuto di un oggetto . Per includere più <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> oggetti nel contenuto, racchiudere gli <xref:System.Windows.Controls.Panel> oggetti <xref:System.Windows.Controls.StackPanel>all'interno di un controllo layout, ad esempio a o .  
  
 Nell'esempio seguente viene <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> illustrato <xref:System.Windows.Controls.TreeViewItem> come <xref:System.Windows.Controls.CheckBox> definire <xref:System.Windows.Controls.TextBlock> il di un <xref:System.Windows.Controls.DockPanel> come un e che sono entrambi racchiusi in un controllo.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 Nell'esempio seguente viene <xref:System.Windows.DataTemplate> illustrato come <xref:System.Windows.Controls.Image> definire <xref:System.Windows.Controls.TextBlock> un che contiene <xref:System.Windows.Controls.DockPanel> un e un che sono racchiusi in un controllo. È possibile <xref:System.Windows.DataTemplate> utilizzare un <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> per <xref:System.Windows.Controls.TreeViewItem>impostare il o per un file .  
  
 [!code-xaml[TreeViewDataBinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Argomenti relativi alle procedure](treeview-how-to-topics.md)
- [Modello di contenuto WPF](wpf-content-model.md)
