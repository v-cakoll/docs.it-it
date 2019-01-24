---
title: 'Procedura: Associazione di una visualizzazione struttura ad albero a dati di profondità non determinabile'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: 702a86f049635423a31e554d205dcc3cf4aa799d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54605367"
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Procedura: Associazione di una visualizzazione struttura ad albero a dati di profondità non determinabile
Quando si desidera associare a volte può essere un <xref:System.Windows.Controls.TreeView> a un'origine dati di profondità non è noto.  Ciò può verificarsi quando i dati ricorsivi, ad esempio un file system, in cui le cartelle possono contenere le cartelle, o struttura organizzativa dell'azienda, in cui i dipendenti hanno altri dipendenti come dipendenti diretti.  
  
 L'origine dati deve avere un modello gerarchico di oggetti. Ad esempio, un `Employee` classe potrebbe contenere una raccolta di oggetti dipendenti che sono i dipendenti diretti di un dipendente. Se i dati vengono rappresentati in modo che non è di tipo gerarchico, è necessario compilare una rappresentazione gerarchica dei dati.  
  
 Quando si imposta la <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> proprietà e, se il <xref:System.Windows.Controls.ItemsControl> genera un' <xref:System.Windows.Controls.ItemsControl> per ogni elemento figlio, quindi l'elemento figlio <xref:System.Windows.Controls.ItemsControl> Usa lo stesso <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> come elemento padre. Ad esempio, se si imposta il <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà con associazione a dati <xref:System.Windows.Controls.TreeView>, ognuna <xref:System.Windows.Controls.TreeViewItem> generato utilizza il <xref:System.Windows.DataTemplate> assegnato al <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> proprietà del <xref:System.Windows.Controls.TreeView>.  
  
 Il <xref:System.Windows.HierarchicalDataTemplate> consente di specificare il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per una <xref:System.Windows.Controls.TreeViewItem>, o qualsiasi <xref:System.Windows.Controls.HeaderedItemsControl>, sul modello di dati. Quando si imposta la <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType> proprietà, questo valore è utilizzato quando il <xref:System.Windows.HierarchicalDataTemplate> viene applicato. Usando un <xref:System.Windows.HierarchicalDataTemplate>, è possibile impostare in modo ricorsivo il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per ogni <xref:System.Windows.Controls.TreeViewItem> nel <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come associare un <xref:System.Windows.Controls.TreeView> ai dati gerarchici e usare una <xref:System.Windows.HierarchicalDataTemplate> per specificare le <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per ogni <xref:System.Windows.Controls.TreeViewItem>.  Il <xref:System.Windows.Controls.TreeView> viene associato a dati XML che rappresenta i dipendenti in un'azienda.  Ciascuna `Employee` elemento può contenere altri `Employee` elementi per indicare la struttura gerarchica. Poiché i dati sono ricorsivo, il <xref:System.Windows.HierarchicalDataTemplate> può essere applicato a ogni livello.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche
- [Panoramica sul data binding](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [Panoramica sui modelli di dati](../../../../docs/framework/wpf/data/data-templating-overview.md)
