---
title: 'Procedura: Usare gli oggetti SelectedValue, SelectedValuePath e SelectedItem'
ms.date: 03/30/2017
helpviewer_keywords:
- TreeView control [WPF], SelectedValue properties
- Control class [WPF], SelectedItem properties
- Control class [WPF], TreeView properties
- Control class [WPF], SelectedValue properties
- TreeView control [WPF], SelectedItem properties
- SelectedValue [WPF], SelectedValuePath properties
- TreeView control [WPF], SelectedValuePath properties
- Control class [WPF], SelectedValuePath properties
- SelectedValue [WPF], SelectedItem properties
ms.assetid: 2fc92ad4-f02c-4f89-bbe9-d4978a7af0db
ms.openlocfilehash: d9f7a8f04f53b7d38a49dfef2c947dfa1c2d263d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59169704"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>Procedura: Usare gli oggetti SelectedValue, SelectedValuePath e SelectedItem
Questo esempio illustra come usare il <xref:System.Windows.Controls.TreeView.SelectedValue%2A> e <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> delle proprietà per specificare un valore per il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> di un <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà fornisce un modo per specificare un <xref:System.Windows.Controls.TreeView.SelectedValue%2A> per il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in un <xref:System.Windows.Controls.TreeView>. Il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> rappresenta un oggetto nel <xref:System.Windows.Controls.ItemsControl.Items%2A> raccolta e il <xref:System.Windows.Controls.TreeView> viene visualizzato il valore di una singola proprietà dell'elemento selezionato. Il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà specifica il percorso della proprietà che consente di determinare il valore di <xref:System.Windows.Controls.TreeView.SelectedValue%2A> proprietà. Gli esempi in questo argomento illustrano questo concetto.  
  
 L'esempio seguente mostra un <xref:System.Windows.Data.XmlDataProvider> che contiene informazioni sui dipendenti.  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 L'esempio seguente definisce una <xref:System.Windows.HierarchicalDataTemplate> che consente di visualizzare il `EmployeeName` e `EmployeeWorkDay` del `Employee`. Si noti che il <xref:System.Windows.HierarchicalDataTemplate> non specifica il `EmployeeNumber` come parte del modello.  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 L'esempio seguente mostra una <xref:System.Windows.Controls.TreeView> che usa definita in precedenza <xref:System.Windows.HierarchicalDataTemplate> e che consente di scegliere il <xref:System.Windows.Controls.TreeView.SelectedValue%2A> proprietà per il `EmployeeNumber`. Quando si seleziona un' `EmployeeName` nella <xref:System.Windows.Controls.TreeView>, il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> restituisce proprietà il `EmployeeInfo` elemento dati che corrisponde all'oggetto selezionato `EmployeeName`. Tuttavia, perché il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> di questo <xref:System.Windows.Controls.TreeView> è impostata su `EmployeeNumber`, il <xref:System.Windows.Controls.TreeView.SelectedValue%2A> è impostato sul `EmployeeNumber`.  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Panoramica sul controllo TreeView](treeview-overview.md)
- [Procedure relative alle proprietà](treeview-how-to-topics.md)
