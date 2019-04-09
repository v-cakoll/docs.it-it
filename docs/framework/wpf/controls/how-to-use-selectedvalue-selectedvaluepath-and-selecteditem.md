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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59169704"
---
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="63c7e-102">Procedura: Usare gli oggetti SelectedValue, SelectedValuePath e SelectedItem</span><span class="sxs-lookup"><span data-stu-id="63c7e-102">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="63c7e-103">Questo esempio illustra come usare il <xref:System.Windows.Controls.TreeView.SelectedValue%2A> e <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> delle proprietà per specificare un valore per il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> di un <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="63c7e-103">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63c7e-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="63c7e-104">Example</span></span>  
 <span data-ttu-id="63c7e-105">Il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà fornisce un modo per specificare un <xref:System.Windows.Controls.TreeView.SelectedValue%2A> per il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in un <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="63c7e-105">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="63c7e-106">Il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> rappresenta un oggetto nel <xref:System.Windows.Controls.ItemsControl.Items%2A> raccolta e il <xref:System.Windows.Controls.TreeView> viene visualizzato il valore di una singola proprietà dell'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="63c7e-106">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="63c7e-107">Il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà specifica il percorso della proprietà che consente di determinare il valore di <xref:System.Windows.Controls.TreeView.SelectedValue%2A> proprietà.</span><span class="sxs-lookup"><span data-stu-id="63c7e-107">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="63c7e-108">Gli esempi in questo argomento illustrano questo concetto.</span><span class="sxs-lookup"><span data-stu-id="63c7e-108">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="63c7e-109">L'esempio seguente mostra un <xref:System.Windows.Data.XmlDataProvider> che contiene informazioni sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="63c7e-109">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="63c7e-110">L'esempio seguente definisce una <xref:System.Windows.HierarchicalDataTemplate> che consente di visualizzare il `EmployeeName` e `EmployeeWorkDay` del `Employee`.</span><span class="sxs-lookup"><span data-stu-id="63c7e-110">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="63c7e-111">Si noti che il <xref:System.Windows.HierarchicalDataTemplate> non specifica il `EmployeeNumber` come parte del modello.</span><span class="sxs-lookup"><span data-stu-id="63c7e-111">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="63c7e-112">L'esempio seguente mostra una <xref:System.Windows.Controls.TreeView> che usa definita in precedenza <xref:System.Windows.HierarchicalDataTemplate> e che consente di scegliere il <xref:System.Windows.Controls.TreeView.SelectedValue%2A> proprietà per il `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="63c7e-112">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="63c7e-113">Quando si seleziona un' `EmployeeName` nella <xref:System.Windows.Controls.TreeView>, il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> restituisce proprietà il `EmployeeInfo` elemento dati che corrisponde all'oggetto selezionato `EmployeeName`.</span><span class="sxs-lookup"><span data-stu-id="63c7e-113">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="63c7e-114">Tuttavia, perché il <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> di questo <xref:System.Windows.Controls.TreeView> è impostata su `EmployeeNumber`, il <xref:System.Windows.Controls.TreeView.SelectedValue%2A> è impostato sul `EmployeeNumber`.</span><span class="sxs-lookup"><span data-stu-id="63c7e-114">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="63c7e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="63c7e-115">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="63c7e-116">Cenni preliminari sul controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="63c7e-116">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="63c7e-117">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="63c7e-117">How-to Topics</span></span>](treeview-how-to-topics.md)
