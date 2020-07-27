---
title: 'Procedura: utilizzare le proprietà SelectedValue, SelectedValuePath e SelectedItem'
description: Informazioni su come usare le proprietà SelectedValue e SelectedValuePath per specificare un valore per l'oggetto SelectedItem di un Windows Presentation Foundation TreeView.
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
ms.openlocfilehash: ddac2455dee0bf69d25307340eddd5364e43e823
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87166283"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a>Procedura: utilizzare le proprietà SelectedValue, SelectedValuePath e SelectedItem
Questo esempio illustra come usare le <xref:System.Windows.Controls.TreeView.SelectedValue%2A> proprietà e <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> per specificare un valore per l'oggetto <xref:System.Windows.Controls.TreeView.SelectedItem%2A> di un oggetto <xref:System.Windows.Controls.TreeView> .  
  
## <a name="example"></a>Esempio  
 La <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà fornisce un modo per specificare un oggetto <xref:System.Windows.Controls.TreeView.SelectedValue%2A> per l'oggetto <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in un oggetto <xref:System.Windows.Controls.TreeView> . L' <xref:System.Windows.Controls.TreeView.SelectedItem%2A> oggetto rappresenta un oggetto nella <xref:System.Windows.Controls.ItemsControl.Items%2A> raccolta e <xref:System.Windows.Controls.TreeView> Visualizza il valore di una singola proprietà dell'elemento selezionato. La <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà specifica il percorso della proprietà utilizzata per determinare il valore della <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Proprietà. Negli esempi di questo argomento viene illustrato questo concetto.  
  
 Nell'esempio seguente viene illustrato un oggetto <xref:System.Windows.Data.XmlDataProvider> che contiene informazioni sui dipendenti.  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 Nell'esempio seguente viene definito un oggetto <xref:System.Windows.HierarchicalDataTemplate> che consente `EmployeeName` di visualizzare e `EmployeeWorkDay` di `Employee` . Si noti che non <xref:System.Windows.HierarchicalDataTemplate> specifica `EmployeeNumber` come parte del modello.  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 Nell'esempio seguente viene illustrato un oggetto <xref:System.Windows.Controls.TreeView> che utilizza l'oggetto definito in precedenza <xref:System.Windows.HierarchicalDataTemplate> e che imposta la <xref:System.Windows.Controls.TreeView.SelectedValue%2A> proprietà su `EmployeeNumber` . Quando si seleziona un oggetto `EmployeeName` in <xref:System.Windows.Controls.TreeView> , la <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà restituisce l' `EmployeeInfo` elemento dati corrispondente all'oggetto selezionato `EmployeeName` . Tuttavia, poiché l'oggetto <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> di <xref:System.Windows.Controls.TreeView> è impostato su `EmployeeNumber` , <xref:System.Windows.Controls.TreeView.SelectedValue%2A> è impostato su `EmployeeNumber` .  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [Cenni preliminari sul controllo TreeView](treeview-overview.md)
- [Procedure relative](treeview-how-to-topics.md)
