---
title: 'Procedura: associare una visualizzazione struttura ad albero a dati di profondità non determinabile'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], binding to data of indeterminate depth
ms.assetid: daddcd74-1b0f-4ffd-baeb-ec934c5e0f53
ms.openlocfilehash: cd9a1ee015ebb707a7a06d1c062a1bb3003c96e8
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73458609"
---
# <a name="how-to-bind-a-treeview-to-data-that-has-an-indeterminable-depth"></a>Procedura: associare una visualizzazione struttura ad albero a dati di profondità non determinabile
In alcuni casi potrebbe essere necessario associare un <xref:System.Windows.Controls.TreeView> a un'origine dati la cui profondità non è nota.  Questo problema può verificarsi quando i dati sono di natura ricorsiva, ad esempio un file system, in cui le cartelle possono contenere cartelle o la struttura organizzativa di una società, in cui i dipendenti hanno altri dipendenti come report diretti.  
  
 L'origine dati deve disporre di un modello a oggetti gerarchico. Ad esempio, una classe `Employee` potrebbe contenere una raccolta di oggetti Employee che sono i rapporti diretti di un dipendente. Se i dati sono rappresentati in modo non gerarchico, è necessario compilare una rappresentazione gerarchica dei dati.  
  
 Quando si imposta la proprietà <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A?displayProperty=nameWithType> e se il <xref:System.Windows.Controls.ItemsControl> genera un <xref:System.Windows.Controls.ItemsControl> per ogni elemento figlio, il <xref:System.Windows.Controls.ItemsControl> figlio usa lo stesso <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> del padre. Se, ad esempio, si imposta la proprietà <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> in un <xref:System.Windows.Controls.TreeView>associato a dati, ogni <xref:System.Windows.Controls.TreeViewItem> generato utilizza il <xref:System.Windows.DataTemplate> assegnato alla proprietà <xref:System.Windows.Controls.ItemsControl.ItemTemplate%2A> del <xref:System.Windows.Controls.TreeView>.  
  
 Il <xref:System.Windows.HierarchicalDataTemplate> consente di specificare il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per un <xref:System.Windows.Controls.TreeViewItem>o qualsiasi <xref:System.Windows.Controls.HeaderedItemsControl>sul modello di dati. Quando si imposta la proprietà <xref:System.Windows.HierarchicalDataTemplate.ItemsSource%2A?displayProperty=nameWithType>, tale valore viene utilizzato quando viene applicato il <xref:System.Windows.HierarchicalDataTemplate>. Utilizzando una <xref:System.Windows.HierarchicalDataTemplate>, è possibile impostare in modo ricorsivo il <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per ogni <xref:System.Windows.Controls.TreeViewItem> nel <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come associare un <xref:System.Windows.Controls.TreeView> ai dati gerarchici e utilizzare un <xref:System.Windows.HierarchicalDataTemplate> per specificare la <xref:System.Windows.Controls.ItemsControl.ItemsSource%2A> per ogni <xref:System.Windows.Controls.TreeViewItem>.  Il <xref:System.Windows.Controls.TreeView> viene associato ai dati XML che rappresentano i dipendenti di una società.  Ogni elemento `Employee` può contenere altri elementi `Employee` per indicare chi segnala a chi. Poiché i dati sono ricorsivi, il <xref:System.Windows.HierarchicalDataTemplate> può essere applicato a ogni livello.  
  
 [!code-xaml[TreeViewWithUnknownDepth#1](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewWithUnknownDepth/CS/Window1.xaml#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sul data binding](../../../desktop-wpf/data/data-binding-overview.md)
- [Panoramica sui modelli di dati](../data/data-templating-overview.md)
