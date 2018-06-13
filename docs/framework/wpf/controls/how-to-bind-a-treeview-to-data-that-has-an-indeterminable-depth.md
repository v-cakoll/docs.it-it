---
title: 'Procedura: associare una visualizzazione struttura ad albero a dati di profondità non determinabile'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: 30e328c94e1e1da4641e93dd5f5730eab2d8af1f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33554377"
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Procedura: associare una visualizzazione struttura ad albero a dati di profondità non determinabile
Talvolta potrebbe essere quando si desidera associare un <xref:System.Windows.Controls.TreeView> a un'origine dati di profondità non è noto.  Ciò può verificarsi quando i dati sono ricorsivi, ad esempio un file system, in cui le cartelle possono contenere cartelle, o struttura organizzativa di una società, in cui i dipendenti hanno altri dipendenti diretti.  
  
 L'origine dati deve disporre di un modello gerarchico di oggetti. Ad esempio, un `Employee` classe potrebbe contenere una raccolta di oggetti dipendenti che sono i report diretti di un dipendente. Se i dati vengono rappresentati in modo che non è di tipo gerarchico, è necessario generare una rappresentazione gerarchica dei dati.  
  
 Quando si imposta la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> proprietà e, se il <xref:System.Windows.Controls.ItemsControl> genera un <xref:System.Windows.Controls.ItemsControl> per ogni elemento figlio, quindi l'elemento figlio <xref:System.Windows.Controls.ItemsControl> utilizza lo stesso <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> come elemento padre. Ad esempio, se si imposta la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà in un controllo con associazione a dati <xref:System.Windows.Controls.TreeView>, ogni <xref:System.Windows.Controls.TreeViewItem> generato utilizza il <xref:System.Windows.DataTemplate> assegnato al <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà del <xref:System.Windows.Controls.TreeView>.  
  
 Il <xref:System.Windows.HierarchicalDataTemplate> consente di specificare il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per un <xref:System.Windows.Controls.TreeViewItem>, o qualsiasi <xref:System.Windows.Controls.HeaderedItemsControl>, sul modello di dati. Quando si imposta la <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> proprietà, questo valore è utilizzato quando il <xref:System.Windows.HierarchicalDataTemplate> viene applicato. Utilizzando un <xref:System.Windows.HierarchicalDataTemplate>, è possibile impostare in modo ricorsivo il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per ogni <xref:System.Windows.Controls.TreeViewItem> nel <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come associare un <xref:System.Windows.Controls.TreeView> per i dati gerarchici e utilizzare un <xref:System.Windows.HierarchicalDataTemplate> per specificare il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per ogni <xref:System.Windows.Controls.TreeViewItem>.  Il <xref:System.Windows.Controls.TreeView> associato ai dati XML che rappresentano i dipendenti di una società.  Ogni `Employee` elemento può contenere altre `Employee` degli elementi per indicare la struttura gerarchica. Poiché i dati sono ricorsivi, il <xref:System.Windows.HierarchicalDataTemplate> può essere applicato a ogni livello.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche  
 [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Panoramica sui modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md)
