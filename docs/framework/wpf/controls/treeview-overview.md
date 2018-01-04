---
title: Cenni preliminari sul controllo TreeView
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- expanding node [WPF]
- TreeView control [WPF], about TreeView control
- Control class [WPF], TreeView
ms.assetid: 62212512-5a5c-4864-949e-b6a6a3a52c02
caps.latest.revision: "33"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6e5f6b3d0a185754bc0d8d8ee726ca13443ccdc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="treeview-overview"></a>Cenni preliminari sul controllo TreeView
Il <xref:System.Windows.Controls.TreeView> controllo consente di visualizzare le informazioni in una struttura gerarchica tramite nodi comprimibili. Questo argomento vengono presentate le <xref:System.Windows.Controls.TreeView> e <xref:System.Windows.Controls.TreeViewItem> controlla e alcuni semplici esempi del loro utilizzo.  
  
  
<a name="Simple_TreeView_Control"></a>   
## <a name="what-is-a-treeview"></a>Che cos'è un controllo TreeView?  
 <xref:System.Windows.Controls.TreeView>è un <xref:System.Windows.Controls.ItemsControl> che consente di annidare gli elementi utilizzando <xref:System.Windows.Controls.TreeViewItem> controlli. Nell'esempio seguente viene creato un <xref:System.Windows.Controls.TreeView>.  
  
 [!code-xaml[TreeViewSnips#EmbeddedTVIs](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#embeddedtvis)]  
  
<a name="Creating_a_TreeView"></a>   
## <a name="creating-a-treeview"></a>Creazione di un controllo TreeView  
 Il <xref:System.Windows.Controls.TreeView> controllo contiene una gerarchia di <xref:System.Windows.Controls.TreeViewItem> controlli. A <xref:System.Windows.Controls.TreeViewItem> controllo è un <xref:System.Windows.Controls.HeaderedItemsControl> che ha un <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> e <xref:System.Windows.Controls.ItemsControl.Items%2A> insieme.  
  
 Se si sta definendo un <xref:System.Windows.Controls.TreeView> utilizzando [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)], è possibile definire in modo esplicito il <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> contenuto di un <xref:System.Windows.Controls.TreeViewItem> controllo e gli elementi che costituiscono la raccolta. La figura precedente illustra questo metodo.  
  
 È inoltre possibile specificare un <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> come dati di origine e quindi specificare un <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> e <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> per definire il <xref:System.Windows.Controls.TreeViewItem> contenuto.  
  
 Per definire il layout di un <xref:System.Windows.Controls.TreeViewItem> (controllo), è inoltre possibile utilizzare <xref:System.Windows.HierarchicalDataTemplate> oggetti. Per altre informazioni e un esempio, vedere [Uso di SelectedValue, SelectedValuePath e SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 Se un elemento non è un <xref:System.Windows.Controls.TreeViewItem> controllo, viene automaticamente racchiuso da un <xref:System.Windows.Controls.TreeViewItem> controllare quando il <xref:System.Windows.Controls.TreeView> controllo viene visualizzato.  
  
<a name="Expanding_and_Collapsing_a_TreeViewItem"></a>   
## <a name="expanding-and-collapsing-a-treeviewitem"></a>Espansione e compressione di un oggetto TreeViewItem  
 Se l'utente espande una <xref:System.Windows.Controls.TreeViewItem>, <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> è impostata su `true`. È anche possibile espandere o comprimere un <xref:System.Windows.Controls.TreeViewItem> senza alcun intervento diretto dell'utente impostando il <xref:System.Windows.Controls.TreeViewItem.IsExpanded%2A> proprietà `true` (expand) o `false` (compresso). Quando questa proprietà viene modificata una <xref:System.Windows.Controls.TreeViewItem.Expanded> o <xref:System.Windows.Controls.TreeViewItem.Collapsed> si verifica l'evento.  
  
 Quando il <xref:System.Windows.FrameworkElement.BringIntoView%2A> metodo viene chiamato su un <xref:System.Windows.Controls.TreeViewItem> (controllo), il <xref:System.Windows.Controls.TreeViewItem> e il relativo elemento padre <xref:System.Windows.Controls.TreeViewItem> espandere i controlli. Se un <xref:System.Windows.Controls.TreeViewItem> non è visibile o parzialmente visibile il <xref:System.Windows.Controls.TreeView> scorre per renderlo visibile.  
  
<a name="TreeViewItem_Selection"></a>   
## <a name="treeviewitem-selection"></a>Selezione di TreeViewItem  
 Quando un utente sceglie un <xref:System.Windows.Controls.TreeViewItem> controllo per selezionarlo, il <xref:System.Windows.Controls.TreeViewItem.Selected> evento si verifica e il relativo <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> è impostata su `true`. Il <xref:System.Windows.Controls.TreeViewItem> diventa anche il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> del <xref:System.Windows.Controls.TreeView> controllo. Al contrario, quando si modifica la selezione da un <xref:System.Windows.Controls.TreeViewItem> (controllo), il relativo <xref:System.Windows.Controls.TreeViewItem.Unselected> evento si verifica e la relativa <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> è impostata su `false`.  
  
 Il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà il <xref:System.Windows.Controls.TreeView> controllo è una proprietà di sola lettura; pertanto, è possibile impostarlo in modo esplicito. Il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà viene impostata se l'utente fa clic su un <xref:System.Windows.Controls.TreeViewItem> controllo o quando il <xref:System.Windows.Controls.TreeViewItem.IsSelected%2A> è impostata su `true` sul <xref:System.Windows.Controls.TreeViewItem> controllo.  
  
 Utilizzare il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà per specificare un <xref:System.Windows.Controls.TreeView.SelectedValue%2A> di un <xref:System.Windows.Controls.TreeView.SelectedItem%2A>. Per altre informazioni, vedere [Uso di SelectedValue, SelectedValuePath e SelectedItem](../../../../docs/framework/wpf/controls/how-to-use-selectedvalue-selectedvaluepath-and-selecteditem.md).  
  
 È possibile registrare un gestore eventi nel <xref:System.Windows.Controls.TreeView.SelectedItemChanged> evento per determinare quando un selezionato <xref:System.Windows.Controls.TreeViewItem> le modifiche. Il <xref:System.Windows.RoutedPropertyChangedEventArgs%601> che viene fornito per l'evento gestore specifica il <xref:System.Windows.RoutedPropertyChangedEventArgs%601.OldValue%2A>, ovvero la selezione precedente e <xref:System.Windows.RoutedPropertyChangedEventArgs%601.NewValue%2A>, che è la selezione corrente. Il valore può essere `null` se l'applicazione o l'utente non ha effettuato una selezione precedente o attuale.  
  
<a name="TreeView_Style"></a>   
## <a name="treeview-style"></a>Stile del controllo TreeView  
 Lo stile predefinito per un <xref:System.Windows.Controls.TreeView> controllo viene inserito in un <xref:System.Windows.Controls.StackPanel> oggetto che contiene un <xref:System.Windows.Controls.ScrollViewer> controllo. Quando si imposta la <xref:System.Windows.FrameworkElement.Width%2A> e <xref:System.Windows.FrameworkElement.Height%2A> le proprietà per un <xref:System.Windows.Controls.TreeView>, questi valori vengono utilizzati per ridimensionare il <xref:System.Windows.Controls.StackPanel> oggetto che consente di visualizzare il <xref:System.Windows.Controls.TreeView>. Se il contenuto da visualizzare è maggiore dell'area di visualizzazione, un <xref:System.Windows.Controls.ScrollViewer> vengono visualizzati automaticamente in modo che l'utente può scorrere il <xref:System.Windows.Controls.TreeView> contenuto.  
  
 Per personalizzare l'aspetto di un <xref:System.Windows.Controls.TreeViewItem> di controllo, impostare il <xref:System.Windows.FrameworkElement.Style%2A> proprietà su un oggetto personalizzato <xref:System.Windows.Style>.  
  
 Nell'esempio seguente viene illustrato come impostare il <xref:System.Windows.Controls.Control.Foreground%2A> e <xref:System.Windows.Controls.Control.FontSize%2A> i valori delle proprietà per un <xref:System.Windows.Controls.TreeViewItem> controllo utilizzando un <xref:System.Windows.FrameworkElement.Style%2A>.  
  
 [!code-xaml[TreeViewSimple#8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSimple/CS/Window1.xaml#8)]  
  
<a name="Adding_Images_and_oOther_Content_to_TreeView_Items"></a>   
## <a name="adding-images-and-other-content-to-treeview-items"></a>Aggiunta di immagini e altro contenuto a elementi di TreeView  
 È possibile includere più di un oggetto nel <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> contenuto di un <xref:System.Windows.Controls.TreeViewItem>. Per includere più oggetti in <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> contenuto, racchiudere gli oggetti in un controllo di layout, ad esempio un <xref:System.Windows.Controls.Panel> o <xref:System.Windows.Controls.StackPanel>.  
  
 Nell'esempio seguente viene illustrato come definire il <xref:System.Windows.Controls.HeaderedItemsControl.Header%2A> di un <xref:System.Windows.Controls.TreeViewItem> come un <xref:System.Windows.Controls.CheckBox> e <xref:System.Windows.Controls.TextBlock> che siano racchiusi tra un <xref:System.Windows.Controls.DockPanel> controllo.  
  
 [!code-xaml[TreeViewSnips#TVIHeader](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSnips/CSharp/Window1.xaml#tviheader)]  
  
 Nell'esempio seguente viene illustrato come definire un <xref:System.Windows.DataTemplate> che contiene un <xref:System.Windows.Controls.Image> e <xref:System.Windows.Controls.TextBlock> racchiusi in un <xref:System.Windows.Controls.DockPanel> controllo. È possibile utilizzare un <xref:System.Windows.DataTemplate> per impostare il <xref:System.Windows.Controls.HeaderedItemsControl.HeaderTemplate%2A> o <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> per un <xref:System.Windows.Controls.TreeViewItem>.  
  
 [!code-xaml[TreeViewDataBinding#6](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewDataBinding/CSharp/Window1.xaml#6)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)  
 [Modello di contenuto WPF](../../../../docs/framework/wpf/controls/wpf-content-model.md)
