---
title: 'Procedura: utilizzare le proprietà SelectedValue, SelectedValuePath e SelectedItem'
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
ms.openlocfilehash: 93720c0e1ac96a55fafa36479968cc3492cb0d84
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>Procedura: utilizzare le proprietà SelectedValue, SelectedValuePath e SelectedItem
In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Controls.TreeView.SelectedValue%2A> e <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> le proprietà per specificare un valore per il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> di un <xref:System.Windows.Controls.TreeView>.  
  
## <a name="example"></a>Esempio  
 Il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà fornisce un modo per specificare un <xref:System.Windows.Controls.TreeView.SelectedValue%2A> per il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in un <xref:System.Windows.Controls.TreeView>. Il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> rappresenta un oggetto nel <xref:System.Windows.Controls.ItemsControl.Items%2A> insieme e <xref:System.Windows.Controls.TreeView> viene visualizzato il valore di una singola proprietà dell'elemento selezionato. Il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà specifica il percorso della proprietà utilizzato per determinare il valore di <xref:System.Windows.Controls.TreeView.SelectedValue%2A> proprietà. Negli esempi in questo argomento viene illustrato questo concetto.  
  
 Nell'esempio seguente un <xref:System.Windows.Data.XmlDataProvider> che contiene informazioni sui dipendenti.  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 L'esempio seguente definisce un <xref:System.Windows.HierarchicalDataTemplate> che consente di visualizzare il `EmployeeName` e `EmployeeWorkDay` del `Employee`. Si noti che il <xref:System.Windows.HierarchicalDataTemplate> non specifica il `EmployeeNumber` come parte del modello.  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 Nell'esempio seguente un <xref:System.Windows.Controls.TreeView> che utilizza definita in precedenza <xref:System.Windows.HierarchicalDataTemplate> e che imposta il <xref:System.Windows.Controls.TreeView.SelectedValue%2A> proprietà per il `EmployeeNumber`. Quando si seleziona un `EmployeeName` nel <xref:System.Windows.Controls.TreeView>, <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà restituisce il `EmployeeInfo` elemento di dati corrispondente al `EmployeeName`. Tuttavia, poiché il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> di questo <xref:System.Windows.Controls.TreeView> è impostato su `EmployeeNumber`, il <xref:System.Windows.Controls.TreeView.SelectedValue%2A> è impostata sul `EmployeeNumber`.  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [Panoramica sul controllo TreeView](../../../../docs/framework/wpf/controls/treeview-overview.md)  
 [Procedure relative alle proprietà](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
