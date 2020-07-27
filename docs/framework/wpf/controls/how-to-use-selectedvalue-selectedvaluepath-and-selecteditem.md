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
# <a name="how-to-use-selectedvalue-selectedvaluepath-and-selecteditem"></a><span data-ttu-id="f9f01-103">Procedura: utilizzare le proprietà SelectedValue, SelectedValuePath e SelectedItem</span><span class="sxs-lookup"><span data-stu-id="f9f01-103">How to: Use SelectedValue, SelectedValuePath, and SelectedItem</span></span>
<span data-ttu-id="f9f01-104">Questo esempio illustra come usare le <xref:System.Windows.Controls.TreeView.SelectedValue%2A> proprietà e <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> per specificare un valore per l'oggetto <xref:System.Windows.Controls.TreeView.SelectedItem%2A> di un oggetto <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="f9f01-104">This example shows how to use the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> and <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> properties to specify a value for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> of a <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f9f01-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f9f01-105">Example</span></span>  
 <span data-ttu-id="f9f01-106">La <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà fornisce un modo per specificare un oggetto <xref:System.Windows.Controls.TreeView.SelectedValue%2A> per l'oggetto <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in un oggetto <xref:System.Windows.Controls.TreeView> .</span><span class="sxs-lookup"><span data-stu-id="f9f01-106">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property provides a way to specify a <xref:System.Windows.Controls.TreeView.SelectedValue%2A> for the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> in a <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="f9f01-107">L' <xref:System.Windows.Controls.TreeView.SelectedItem%2A> oggetto rappresenta un oggetto nella <xref:System.Windows.Controls.ItemsControl.Items%2A> raccolta e <xref:System.Windows.Controls.TreeView> Visualizza il valore di una singola proprietà dell'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="f9f01-107">The <xref:System.Windows.Controls.TreeView.SelectedItem%2A> represents an object in the <xref:System.Windows.Controls.ItemsControl.Items%2A> collection and the <xref:System.Windows.Controls.TreeView> displays the value of a single property of the selected item.</span></span> <span data-ttu-id="f9f01-108">La <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> proprietà specifica il percorso della proprietà utilizzata per determinare il valore della <xref:System.Windows.Controls.TreeView.SelectedValue%2A> Proprietà.</span><span class="sxs-lookup"><span data-stu-id="f9f01-108">The <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> property specifies the path to the property that is used to determine the value of the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property.</span></span> <span data-ttu-id="f9f01-109">Negli esempi di questo argomento viene illustrato questo concetto.</span><span class="sxs-lookup"><span data-stu-id="f9f01-109">The examples in this topic illustrate this concept.</span></span>  
  
 <span data-ttu-id="f9f01-110">Nell'esempio seguente viene illustrato un oggetto <xref:System.Windows.Data.XmlDataProvider> che contiene informazioni sui dipendenti.</span><span class="sxs-lookup"><span data-stu-id="f9f01-110">The following example shows an <xref:System.Windows.Data.XmlDataProvider> that contains employee information.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#XMLDataProvider](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#xmldataprovider)]  
  
 <span data-ttu-id="f9f01-111">Nell'esempio seguente viene definito un oggetto <xref:System.Windows.HierarchicalDataTemplate> che consente `EmployeeName` di visualizzare e `EmployeeWorkDay` di `Employee` .</span><span class="sxs-lookup"><span data-stu-id="f9f01-111">The following example defines a <xref:System.Windows.HierarchicalDataTemplate> that displays the `EmployeeName` and `EmployeeWorkDay` of the `Employee`.</span></span> <span data-ttu-id="f9f01-112">Si noti che non <xref:System.Windows.HierarchicalDataTemplate> specifica `EmployeeNumber` come parte del modello.</span><span class="sxs-lookup"><span data-stu-id="f9f01-112">Note that the <xref:System.Windows.HierarchicalDataTemplate> does not specify the `EmployeeNumber` as part of the template.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#HierarchicalDataTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#hierarchicaldatatemplate)]  
  
 <span data-ttu-id="f9f01-113">Nell'esempio seguente viene illustrato un oggetto <xref:System.Windows.Controls.TreeView> che utilizza l'oggetto definito in precedenza <xref:System.Windows.HierarchicalDataTemplate> e che imposta la <xref:System.Windows.Controls.TreeView.SelectedValue%2A> proprietà su `EmployeeNumber` .</span><span class="sxs-lookup"><span data-stu-id="f9f01-113">The following example shows a <xref:System.Windows.Controls.TreeView> that uses the previously defined <xref:System.Windows.HierarchicalDataTemplate> and that sets the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> property to the `EmployeeNumber`.</span></span> <span data-ttu-id="f9f01-114">Quando si seleziona un oggetto `EmployeeName` in <xref:System.Windows.Controls.TreeView> , la <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà restituisce l' `EmployeeInfo` elemento dati corrispondente all'oggetto selezionato `EmployeeName` .</span><span class="sxs-lookup"><span data-stu-id="f9f01-114">When you select an `EmployeeName` in the <xref:System.Windows.Controls.TreeView>, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property returns the `EmployeeInfo` data item that corresponds to the selected `EmployeeName`.</span></span> <span data-ttu-id="f9f01-115">Tuttavia, poiché l'oggetto <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> di <xref:System.Windows.Controls.TreeView> è impostato su `EmployeeNumber` , <xref:System.Windows.Controls.TreeView.SelectedValue%2A> è impostato su `EmployeeNumber` .</span><span class="sxs-lookup"><span data-stu-id="f9f01-115">However, because the <xref:System.Windows.Controls.TreeView.SelectedValuePath%2A> of this <xref:System.Windows.Controls.TreeView> is set to `EmployeeNumber`, the <xref:System.Windows.Controls.TreeView.SelectedValue%2A> is set to the `EmployeeNumber`.</span></span>  
  
 [!code-xaml[TreeViewSelectedValue#SelectedValuePath](~/samples/snippets/csharp/VS_Snippets_Wpf/TreeViewSelectedValue/CS/Window1.xaml#selectedvaluepath)]  
  
## <a name="see-also"></a><span data-ttu-id="f9f01-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f9f01-116">See also</span></span>

- <xref:System.Windows.Controls.TreeView>
- <xref:System.Windows.Controls.TreeViewItem>
- [<span data-ttu-id="f9f01-117">Cenni preliminari sul controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="f9f01-117">TreeView Overview</span></span>](treeview-overview.md)
- [<span data-ttu-id="f9f01-118">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="f9f01-118">How-to Topics</span></span>](treeview-how-to-topics.md)
