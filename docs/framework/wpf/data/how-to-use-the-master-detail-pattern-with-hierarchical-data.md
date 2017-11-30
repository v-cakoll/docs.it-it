---
title: 'Procedura: utilizzare il modello Master-Details con dati gerarchici'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bb546a3429012a49ee7652a3470460935fc76d70
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="313d6-102">Procedura: utilizzare il modello Master-Details con dati gerarchici</span><span class="sxs-lookup"><span data-stu-id="313d6-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="313d6-103">In questo esempio viene illustrato come implementare uno scenario master-details.</span><span class="sxs-lookup"><span data-stu-id="313d6-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="313d6-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="313d6-104">Example</span></span>  
 <span data-ttu-id="313d6-105">In questo esempio, `LeagueList` è una raccolta di `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="313d6-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="313d6-106">Ogni `League` ha un `Name` e una raccolta di `Divisions`e ogni `Division` ha un nome e una raccolta di `Teams`.</span><span class="sxs-lookup"><span data-stu-id="313d6-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="313d6-107">Ogni `Team` ha un nome.</span><span class="sxs-lookup"><span data-stu-id="313d6-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="313d6-108">Lo screenshot seguente mostra l'esempio.</span><span class="sxs-lookup"><span data-stu-id="313d6-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="313d6-109">Il `Divisions` <xref:System.Windows.Controls.ListBox> automaticamente tiene traccia delle selezioni nel `Leagues` <xref:System.Windows.Controls.ListBox> e visualizzare i dati corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="313d6-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="313d6-110">Il `Teams` <xref:System.Windows.Controls.ListBox> tiene traccia delle selezioni negli altri due <xref:System.Windows.Controls.ListBox> controlli.</span><span class="sxs-lookup"><span data-stu-id="313d6-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 <span data-ttu-id="313d6-111">![Master &#45; ad esempio di dettaglio](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")</span><span class="sxs-lookup"><span data-stu-id="313d6-111">![Master&#45;detail example](../../../../docs/framework/wpf/data/media/databindingmasterdetailsample.png "DataBindingMasterDetailSample")</span></span>  
  
 <span data-ttu-id="313d6-112">I due elementi per rilevare in questo esempio sono:</span><span class="sxs-lookup"><span data-stu-id="313d6-112">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="313d6-113">I tre <xref:System.Windows.Controls.ListBox> associare i controlli alla stessa origine.</span><span class="sxs-lookup"><span data-stu-id="313d6-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="313d6-114">Impostare il <xref:System.Windows.Data.Binding.Path%2A> proprietà dell'associazione per specificare il livello di dati di cui si desidera il <xref:System.Windows.Controls.ListBox> da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="313d6-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2.  <span data-ttu-id="313d6-115">È necessario impostare il <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> proprietà `true` sul <xref:System.Windows.Controls.ListBox> controlli dei quali la selezione si tiene traccia.</span><span class="sxs-lookup"><span data-stu-id="313d6-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="313d6-116">L'impostazione di questa proprietà garantisce che l'elemento selezionato è sempre impostato come il <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="313d6-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="313d6-117">In alternativa, se il <xref:System.Windows.Controls.ListBox> Ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource>, la selezione e valuta sincronizzate automaticamente.</span><span class="sxs-lookup"><span data-stu-id="313d6-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="313d6-118">La tecnica è leggermente diversa quando si utilizza [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dati.</span><span class="sxs-lookup"><span data-stu-id="313d6-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="313d6-119">Per un esempio, vedere [utilizzare il modello Master-Details con dati XML gerarchici](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="313d6-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="313d6-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="313d6-120">See Also</span></span>  
 <xref:System.Windows.HierarchicalDataTemplate>  
 [<span data-ttu-id="313d6-121">Eseguire l'associazione a una raccolta e visualizzare informazioni in base alla selezione</span><span class="sxs-lookup"><span data-stu-id="313d6-121">Bind to a Collection and Display Information Based on Selection</span></span>](../../../../docs/framework/wpf/data/how-to-bind-to-a-collection-and-display-information-based-on-selection.md)  
 [<span data-ttu-id="313d6-122">Cenni preliminari sull'associazione dati</span><span class="sxs-lookup"><span data-stu-id="313d6-122">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)  
 [<span data-ttu-id="313d6-123">Panoramica sui modelli di dati</span><span class="sxs-lookup"><span data-stu-id="313d6-123">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)  
 [<span data-ttu-id="313d6-124">Procedure relative</span><span class="sxs-lookup"><span data-stu-id="313d6-124">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
