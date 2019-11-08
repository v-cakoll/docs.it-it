---
title: 'Procedura: utilizzare il modello Master-Details con dati gerarchici'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e4183ddc3868a1568662853b46e05348df129092
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "73733476"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="6aa1d-102">Procedura: utilizzare il modello Master-Details con dati gerarchici</span><span class="sxs-lookup"><span data-stu-id="6aa1d-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="6aa1d-103">Questo esempio illustra come implementare lo scenario Master-Details.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aa1d-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6aa1d-104">Example</span></span>  
 <span data-ttu-id="6aa1d-105">In questo esempio `LeagueList` è una raccolta di `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="6aa1d-106">Ogni `League` dispone di un `Name` e una raccolta di `Divisions`e ogni `Division` ha un nome e una raccolta di `Teams`.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="6aa1d-107">Ogni `Team` ha un nome del team.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="6aa1d-108">Lo screenshot seguente mostra l'esempio.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="6aa1d-109">Il `Divisions` <xref:System.Windows.Controls.ListBox> rileva automaticamente le selezioni nel `Leagues` <xref:System.Windows.Controls.ListBox> e Visualizza i dati corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="6aa1d-110">Il `Teams` <xref:System.Windows.Controls.ListBox> tiene traccia delle selezioni negli altri due controlli di <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![Screenshot che mostra un esempio&#45;di scenario di dettaglio master.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="6aa1d-112">I due aspetti da notare in questo esempio sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="6aa1d-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="6aa1d-113">I tre controlli <xref:System.Windows.Controls.ListBox> si associano alla stessa origine.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="6aa1d-114">È possibile impostare la proprietà <xref:System.Windows.Data.Binding.Path%2A> dell'associazione per specificare il livello di dati che si desidera visualizzare nel <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="6aa1d-115">È necessario impostare la proprietà <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> su `true` sui controlli <xref:System.Windows.Controls.ListBox> di cui si sta verificando la selezione.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="6aa1d-116">L'impostazione di questa proprietà garantisce che l'elemento selezionato sia sempre impostato come <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="6aa1d-117">In alternativa, se il <xref:System.Windows.Controls.ListBox> ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource>, sincronizza automaticamente la selezione e la valuta.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="6aa1d-118">La tecnica è leggermente diversa quando si utilizzano dati XML.</span><span class="sxs-lookup"><span data-stu-id="6aa1d-118">The technique is slightly different when you are using XML data.</span></span> <span data-ttu-id="6aa1d-119">Per un esempio, vedere [usare il modello Master-Details con dati XML gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="6aa1d-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6aa1d-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6aa1d-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="6aa1d-121">Eseguire l'associazione a una raccolta e visualizzare informazioni in base alla selezione</span><span class="sxs-lookup"><span data-stu-id="6aa1d-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="6aa1d-122">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="6aa1d-122">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="6aa1d-123">Panoramica sui modelli di dati</span><span class="sxs-lookup"><span data-stu-id="6aa1d-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="6aa1d-124">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="6aa1d-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
