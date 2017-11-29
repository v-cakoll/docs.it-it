---
title: 'Procedura: trovare un oggetto TreeViewItem in un oggetto TreeView'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- TreeView control [WPF], finding a TreeViewItem
- TreeViewItem [WPF], finding
ms.assetid: 72ecd40c-3939-4e01-b617-5e9daa6074d9
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a231f5eae92bff8e3d525579dae865aaa0d7e496
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-find-a-treeviewitem-in-a-treeview"></a><span data-ttu-id="6e009-102">Procedura: trovare un oggetto TreeViewItem in un oggetto TreeView</span><span class="sxs-lookup"><span data-stu-id="6e009-102">How to: Find a TreeViewItem in a TreeView</span></span>
<span data-ttu-id="6e009-103">Il <xref:System.Windows.Controls.TreeView> controllo fornisce un modo pratico per visualizzare i dati gerarchici.</span><span class="sxs-lookup"><span data-stu-id="6e009-103">The <xref:System.Windows.Controls.TreeView> control provides a convenient way to display hierarchical data.</span></span> <span data-ttu-id="6e009-104">Se il <xref:System.Windows.Controls.TreeView> è associato a un'origine dati, il <xref:System.Windows.Controls.TreeView.SelectedItem%2A> proprietà fornisce un modo pratico per recuperare rapidamente l'oggetto dati selezionato.</span><span class="sxs-lookup"><span data-stu-id="6e009-104">If your <xref:System.Windows.Controls.TreeView> is bound to a data source, the <xref:System.Windows.Controls.TreeView.SelectedItem%2A> property provides a convenient way for you to quickly retrieve the selected data object.</span></span> <span data-ttu-id="6e009-105">È in genere preferibile utilizzare l'oggetto dati sottostante, ma talvolta potrebbe essere necessario modificare a livello di codice che contiene i dati <xref:System.Windows.Controls.TreeViewItem>.</span><span class="sxs-lookup"><span data-stu-id="6e009-105">It is typically best to work with the underlying data object, but sometimes you may need to programmatically manipulate the data's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="6e009-106">Ad esempio, potrebbe essere necessario espandere a livello di codice il <xref:System.Windows.Controls.TreeViewItem>, oppure selezionare un elemento diverso nella <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="6e009-106">For example, you may need to programmatically expand the <xref:System.Windows.Controls.TreeViewItem>, or select a different item in the <xref:System.Windows.Controls.TreeView>.</span></span>  
  
 <span data-ttu-id="6e009-107">Per trovare un <xref:System.Windows.Controls.TreeViewItem> che contiene un oggetto dati specifico, è necessario scorrere ogni livello del <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="6e009-107">To find a <xref:System.Windows.Controls.TreeViewItem> that contains a specific data object, you must traverse each level of the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="6e009-108">Gli elementi in un <xref:System.Windows.Controls.TreeView> può anche essere virtualizzato per migliorare le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="6e009-108">The items in a <xref:System.Windows.Controls.TreeView> can also be virtualized to improve performance.</span></span> <span data-ttu-id="6e009-109">Nel caso in cui gli elementi potrebbero essere virtualizzati, è inoltre necessario eseguire un <xref:System.Windows.Controls.TreeViewItem> per verificare se contiene l'oggetto dati.</span><span class="sxs-lookup"><span data-stu-id="6e009-109">In the case where items might be virtualized, you also must realize a <xref:System.Windows.Controls.TreeViewItem> to check whether it contains the data object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6e009-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="6e009-110">Example</span></span>  
  
## <a name="description"></a><span data-ttu-id="6e009-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6e009-111">Description</span></span>  
 <span data-ttu-id="6e009-112">Le ricerche di esempio seguente un <xref:System.Windows.Controls.TreeView> per un oggetto specifico e restituisce l'oggetto contenente <xref:System.Windows.Controls.TreeViewItem>.</span><span class="sxs-lookup"><span data-stu-id="6e009-112">The following example searches a <xref:System.Windows.Controls.TreeView> for a specific object and returns the object's containing <xref:System.Windows.Controls.TreeViewItem>.</span></span> <span data-ttu-id="6e009-113">Nell'esempio garantisce che ogni <xref:System.Windows.Controls.TreeViewItem> viene creata un'istanza in modo che i relativi elementi figlio è possibile eseguire ricerche.</span><span class="sxs-lookup"><span data-stu-id="6e009-113">The example ensures that each <xref:System.Windows.Controls.TreeViewItem> is instantiated so that its child items can be searched.</span></span> <span data-ttu-id="6e009-114">Questo esempio funziona anche se il <xref:System.Windows.Controls.TreeView> non utilizza gli elementi virtualizzati.</span><span class="sxs-lookup"><span data-stu-id="6e009-114">This example also works if the <xref:System.Windows.Controls.TreeView> does not use virtualized items.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6e009-115">Nell'esempio seguente è applicabile a qualsiasi <xref:System.Windows.Controls.TreeView>, indipendentemente dal modello di dati sottostante e ricerche ogni <xref:System.Windows.Controls.TreeViewItem> fino a quando non viene trovato l'oggetto.</span><span class="sxs-lookup"><span data-stu-id="6e009-115">The following example works for any <xref:System.Windows.Controls.TreeView>, regardless of the underlying data model, and searches every <xref:System.Windows.Controls.TreeViewItem> until the object is found.</span></span> <span data-ttu-id="6e009-116">Un'altra tecnica che offre prestazioni migliori è eseguire ricerche nel modello di dati per l'oggetto specificato, tenere traccia della relativa posizione all'interno della gerarchia di dati e quindi individuare la corrispondente <xref:System.Windows.Controls.TreeViewItem> nel <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="6e009-116">Another technique that has better performance is to search the data model for the specified object, keep track of its location within the data hierarchy, and then find the corresponding <xref:System.Windows.Controls.TreeViewItem> in the <xref:System.Windows.Controls.TreeView>.</span></span> <span data-ttu-id="6e009-117">Tuttavia, la tecnica che offre prestazioni migliori richiede una conoscenza del modello di dati e non può essere generalizzata per un dato <xref:System.Windows.Controls.TreeView>.</span><span class="sxs-lookup"><span data-stu-id="6e009-117">However, the technique that has better performance requires knowledge of the data model and cannot be generalized for any given <xref:System.Windows.Controls.TreeView>.</span></span>  
  
## <a name="code"></a><span data-ttu-id="6e009-118">Codice</span><span class="sxs-lookup"><span data-stu-id="6e009-118">Code</span></span>  
 [!code-csharp[TreeViewFindTVI#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[TreeViewFindTVI#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#1)]  
  
 <span data-ttu-id="6e009-119">Il codice precedente si basa su un oggetto personalizzato <xref:System.Windows.Controls.VirtualizingStackPanel> che espone un metodo denominato `BringIntoView`.</span><span class="sxs-lookup"><span data-stu-id="6e009-119">The previous code relies on a custom <xref:System.Windows.Controls.VirtualizingStackPanel> that exposes a method named `BringIntoView`.</span></span> <span data-ttu-id="6e009-120">Il codice seguente definisce l'oggetto personalizzato <xref:System.Windows.Controls.VirtualizingStackPanel>.</span><span class="sxs-lookup"><span data-stu-id="6e009-120">The following code defines the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-csharp[TreeViewFindTVI#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml.cs#2)]
 [!code-vb[TreeViewFindTVI#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/TreeViewFindTVI/VisualBasic/MainWindow.xaml.vb#2)]  
  
 <span data-ttu-id="6e009-121">Il codice XAML seguente viene illustrato come creare un <xref:System.Windows.Controls.TreeView> che utilizza l'oggetto personalizzato <xref:System.Windows.Controls.VirtualizingStackPanel>.</span><span class="sxs-lookup"><span data-stu-id="6e009-121">The following XAML shows how to create a <xref:System.Windows.Controls.TreeView> that uses the custom <xref:System.Windows.Controls.VirtualizingStackPanel>.</span></span>  
  
 [!code-xaml[TreeViewFindTVI#3](../../../../samples/snippets/csharp/VS_Snippets_Wpf/TreeViewFindTVI/CSharp/MainWindow.xaml#3)]  
  
## <a name="see-also"></a><span data-ttu-id="6e009-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6e009-122">See Also</span></span>  
 [<span data-ttu-id="6e009-123">Migliorare le prestazioni di un controllo TreeView</span><span class="sxs-lookup"><span data-stu-id="6e009-123">Improve the Performance of a TreeView</span></span>](../../../../docs/framework/wpf/controls/how-to-improve-the-performance-of-a-treeview.md)
