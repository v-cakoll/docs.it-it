---
title: Cenni preliminari sul controllo TreeView
description: Informazioni sul modo in cui il controllo TreeView Windows Presentation Foundation Visualizza le informazioni in una struttura gerarchica usando i nodi, inclusi esempi semplici.
ms.date: 03/30/2017
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
ms.openlocfilehash: 6ef77febdd3facb7c7e1af566841c2a1aeaff810
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164530"
---
# <a name="treeview-overview"></a>Cenni preliminari sul controllo TreeView
Il <xref:System.Windows.Controls.TreeView> controllo fornisce un modo per visualizzare le informazioni in una struttura gerarchica usando nodi comprimibili. In questo argomento vengono introdotti i <xref:System.Windows.Controls.TreeView> <xref:System.Windows.Controls.TreeViewItem> controlli e e vengono forniti esempi semplici del relativo utilizzo.  

<a name="Simple_TreeView_Control"></a>
## <a name="what-is-a-treeview"></a>Che cos'è un controllo TreeView?  
 <xref:System.Windows.Controls.TreeView>è un oggetto <xref:System.Windows.Controls.ItemsControl> che nidifica gli elementi utilizzando i <xref:System.Windows.Controls.TreeViewItem> controlli. Nell'esempio seguente viene creato un oggetto <xref:System.Windows.Controls.TreeView> .  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>
## <a name="creating-a-treeview"></a>Creazione di un controllo TreeView  
 Il <xref:System.Windows.Controls.TreeView> controllo contiene una gerarchia di <xref:System.Windows.Controls.TreeViewItem> controlli. Un <xref:System.Windows.Controls.TreeViewItem> controllo è un oggetto <xref:System.Windows.Controls.HeaderedItemsControl> che dispone di un oggetto <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> e di una <xref:System.Windows.Controls.ItemsControl.Items%2A> raccolta.  
  
 Se si definisce un oggetto utilizzando <xref:System.Windows.Controls.TreeView> [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] , è possibile definire in modo esplicito il <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> contenuto di un <xref:System.Windows.Controls.TreeViewItem> controllo e gli elementi che costituiscono la relativa raccolta. La figura precedente illustra questo metodo.  
  
 È anche possibile specificare un <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> come origine dati e quindi specificare un oggetto <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> e <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> per definire il <xref:System.Windows.Controls.TreeViewItem> contenuto.  
  
 Per definire il layout di un <xref:System.Windows.Controls.TreeViewItem> controllo, è anche possibile usare <xref:System.Windows.HierarchicalDataTemplate> gli oggetti. Per altre informazioni e un esempio, vedere [Uso di SelectedValue, SelectedValuePath e SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Se un elemento non è un <xref:System.Windows.Controls.TreeViewItem> controllo, viene automaticamente racchiuso da un <xref:System.Windows.Controls.TreeViewItem> controllo quando <xref:System.Windows.Controls.TreeView> viene visualizzato il controllo.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>
## <a name="expanding-and-collapsing-a-treeviewitem"></a>Espansione e compressione di un oggetto TreeViewItem  
 Se l'utente espande un oggetto <xref:System.Windows.Controls.TreeViewItem> , la <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> proprietà viene impostata su `true` . È anche possibile espandere o comprimere un <xref:System.Windows.Controls.TreeViewItem> senza azione diretta dell'utente impostando la <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> proprietà su `true` (Espandi) o `false` (Comprimi). Quando questa proprietà viene modificata, <xref:System.Windows.Controls.TreeViewItem.Expanded> <xref:System.Windows.Controls.TreeViewItem.Collapsed> si verifica un evento o.  
  
 Quando il <xref:System.Windows.FrameworkElement.BringIntoView%2A> metodo viene chiamato su un <xref:System.Windows.Controls.TreeViewItem> controllo, l'oggetto <xref:System.Windows.Controls.TreeViewItem> e i relativi controlli padre si <xref:System.Windows.Controls.TreeViewItem> espandono. Se un oggetto <xref:System.Windows.Controls.TreeViewItem> non è visibile o parzialmente visibile, <xref:System.Windows.Controls.TreeView> scorre per renderlo visibile.  
  
<a name="TreeViewItem_Selection"></a>
## <a name="treeviewitem-selection"></a>Selezione di TreeViewItem  
 Quando un utente fa clic <xref:System.Windows.Controls.TreeViewItem> su un controllo per selezionarlo, <xref:System.Windows.Controls.TreeViewItem.Selected> si verifica l'evento e la relativa <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> proprietà è impostata su `true` . L'oggetto <xref:System.Windows.Controls.TreeViewItem> diventa anche l'oggetto <xref:System.Windows.Controls.TreeView.SelectedItem%2A> del <xref:System.Windows.Controls.TreeView> controllo. Viceversa, quando la selezione viene modificata da un <xref:System.Windows.Controls.TreeViewItem> controllo, <xref:System.Windows.Controls.TreeViewItem.Unselected> viene generato l'evento e la relativa <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> proprietà viene impostata su `false` .  
  
 La <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà del <xref:System.Windows.Controls.TreeView> controllo è una proprietà di sola lettura, pertanto non è possibile impostarla in modo esplicito. La <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà viene impostata se l'utente fa clic su un <xref:System.Windows.Controls.TreeViewItem> controllo o quando la <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> proprietà è impostata `true` su nel <xref:System.Windows.Controls.TreeViewItem> controllo.  
  
 Utilizzare la <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà per specificare un oggetto <xref:System.Windows.Controls.TreeView.SelectedValue%2A> di un oggetto <xref:System.Windows.Controls.TreeView.SelectedItem%2A> . Per altre informazioni, vedere [Uso di SelectedValue, SelectedValuePath e SelectedItem](how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 È possibile registrare un gestore eventi per l' <xref:System.Windows.Controls.TreeView.SelectedItemChanged> evento per determinare quando un oggetto selezionato <xref:System.Windows.Controls.TreeViewItem> viene modificato. L'oggetto <xref:System.Windows.RoutedPropertyChangedEventArgs%601> fornito al gestore eventi specifica <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A> , che corrisponde alla selezione precedente, e <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A> , che rappresenta la selezione corrente. Il valore può essere `null` se l'applicazione o l'utente non ha effettuato una selezione precedente o attuale.  
  
<a name="TreeView_Style"></a>
## <a name="treeview-style"></a>Stile del controllo TreeView  
 Lo stile predefinito per un <xref:System.Windows.Controls.TreeView> controllo lo inserisce all'interno di un <xref:System.Windows.Controls.StackPanel> oggetto che contiene un <xref:System.Windows.Controls.ScrollViewer> controllo. Quando si impostano le <xref:System.Windows.FrameworkElement.Width%2A> <xref:System.Windows.FrameworkElement.Height%2A> proprietà e per un <xref:System.Windows.Controls.TreeView> , questi valori vengono utilizzati per ridimensionare l' <xref:System.Windows.Controls.StackPanel> oggetto che visualizza <xref:System.Windows.Controls.TreeView> . Se il contenuto da visualizzare è più grande dell'area di visualizzazione, viene visualizzato automaticamente un oggetto in <xref:System.Windows.Controls.ScrollViewer> modo che l'utente possa scorrere il <xref:System.Windows.Controls.TreeView> contenuto.  
  
 Per personalizzare l'aspetto di un <xref:System.Windows.Controls.TreeViewItem> controllo, impostare la <xref:System.Windows.FrameworkElement.Style%2A> proprietà su un oggetto personalizzato <xref:System.Windows.Style> .  
  
 Nell'esempio seguente viene illustrato come impostare i <xref:System.Windows.Controls.Control.Foreground%2A> <xref:System.Windows.Controls.Control.FontSize%2A> valori delle proprietà e per un <xref:System.Windows.Controls.TreeViewItem> controllo utilizzando un oggetto <xref:System.Windows.FrameworkElement.Style%2A> .  
  
 [!code-xaml[TreeViewSimple#8](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>
## <a name="adding-images-and-other-content-to-treeview-items"></a>Aggiunta di immagini e altro contenuto a elementi di TreeView  
 È possibile includere più di un oggetto nel <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> contenuto di un oggetto <xref:System.Windows.Controls.TreeViewItem> . Per includere più oggetti nel <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> contenuto, racchiudere gli oggetti all'interno di un controllo di layout, ad esempio <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.StackPanel> .  
  
 Nell'esempio seguente viene illustrato come definire l'oggetto <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> di un oggetto <xref:System.Windows.Controls.TreeViewItem> come <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.TextBlock> che sono entrambi racchiusi in un <xref:System.Windows.Controls.DockPanel> controllo.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 Nell'esempio seguente viene illustrato come definire un oggetto <xref:System.Windows.DataTemplate> che contiene un oggetto <xref:System.Windows.Controls.Image> e un oggetto <xref:System.Windows.Controls.TextBlock> racchiuso in un <xref:System.Windows.Controls.DockPanel> controllo. È possibile usare un oggetto <xref:System.Windows.DataTemplate> per impostare <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> o <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> per un oggetto <xref:System.Windows.Controls.TreeViewItem> .  
  
 [!code-xaml[TreeViewDataBinding#6](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Procedure relative](treeview-how-to-topics.md)
- [Modello di contenuto WPF](wpf-content-model.md)
