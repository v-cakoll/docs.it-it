---
title: "Procedura: utilizzare le proprietà SelectedValue, SelectedValuePath e SelectedItem"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f6355ed45d7422735d1dac1e1419990e1c5bd120
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="2895e-102">Procedura: utilizzare le proprietà SelectedValue, SelectedValuePath e SelectedItem</span><span class="sxs-lookup"><span data-stu-id="2895e-102">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="2895e-103">In questo esempio viene illustrato come utilizzare il <xref:System.Windows.Controls.TreeView.SelectedValue%2A> e <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> le proprietà per specificare un valore per il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> di un <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="2895e-103">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2895e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="2895e-104">Example</span></span>  
 <span data-ttu-id="2895e-105">Il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà fornisce un modo per specificare un <xref:System.Windows.Controls.TreeView.SelectedValue%2A> per il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in un <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="2895e-105">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="2895e-106">Il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> rappresenta un oggetto nel <xref:System.Windows.Controls.ItemsControl.Items%2A> insieme e <xref:System.Windows.Controls.TreeView> viene visualizzato il valore di una singola proprietà dell'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="2895e-106">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="2895e-107">Il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà specifica il percorso della proprietà utilizzato per determinare il valore di <xref:System.Windows.Controls.TreeView.SelectedValue%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="2895e-107">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="2895e-108">Negli esempi in questo argomento viene illustrato questo concetto.</span><span class="sxs-lookup"><span data-stu-id="2895e-108">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="2895e-109">Nell'esempio seguente un <xref:System.Windows.Data.XmlDataProvider> che contiene informazioni sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="2895e-109">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="2895e-110">L'esempio seguente definisce un <xref:System.Windows.HierarchicalDataTemplate> che consente di visualizzare il `EmployeeName` e `EmployeeWorkDay` del `Employee`.</span><span class="sxs-lookup"><span data-stu-id="2895e-110">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="2895e-111">Si noti che il <xref:System.Windows.HierarchicalDataTemplate> non specifica il `EmployeeNumber` come parte del modello.</span><span class="sxs-lookup"><span data-stu-id="2895e-111">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="2895e-112">Nell'esempio seguente un <xref:System.Windows.Controls.TreeView> che utilizza definita in precedenza <xref:System.Windows.HierarchicalDataTemplate> e che imposta il <xref:System.Windows.Controls.TreeView.SelectedValue%2A> proprietà per il `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="2895e-112">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="2895e-113">Quando si seleziona un `EmployeeName` nel <xref:System.Windows.Controls.TreeView>, <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà restituisce il `EmployeeInfo` elemento di dati corrispondente al `EmployeeName`.</span><span class="sxs-lookup"><span data-stu-id="2895e-113">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="2895e-114">Tuttavia, poiché il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> di questo <xref:System.Windows.Controls.TreeView> è impostato su `EmployeeNumber`, il <xref:System.Windows.Controls.TreeView.SelectedValue%2A> è impostata sul `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="2895e-114">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="2895e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2895e-115">See Also</span></span>  
 <xref:System.Windows.Controls.TreeView>  
 <xref:System.Windows.Controls.TreeViewItem>  
 [<span data-ttu-id="2895e-116">Panoramica sul controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="2895e-116">TreeView Overview</span></span>](../../../../docs/framework/wpf/controls/treeview-overview.md)  
 [<span data-ttu-id="2895e-117">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="2895e-117">How-to Topics</span></span>](../../../../docs/framework/wpf/controls/treeview-how-to-topics.md)
