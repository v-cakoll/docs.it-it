---
title: 'Procedura: Usare il modello Master-Details con dati gerarchici'
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [WPF], Master-Detail data paradigm
- Master-Detail data paradigm
ms.assetid: 11429b9e-058d-4084-bfb6-2cf209c8ddf7
ms.openlocfilehash: e0bbb24b07fdc1c362e2be43d69d189defbc27a4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61931892"
---
# <a name="how-to-use-the-master-detail-pattern-with-hierarchical-data"></a><span data-ttu-id="6ec06-102">Procedura: Usare il modello Master-Details con dati gerarchici</span><span class="sxs-lookup"><span data-stu-id="6ec06-102">How to: Use the Master-Detail Pattern with Hierarchical Data</span></span>
<span data-ttu-id="6ec06-103">In questo esempio viene illustrato come implementare lo scenario master-dettagli.</span><span class="sxs-lookup"><span data-stu-id="6ec06-103">This example shows how to implement the master-detail scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ec06-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="6ec06-104">Example</span></span>  
 <span data-ttu-id="6ec06-105">In questo esempio `LeagueList` è una raccolta di `Leagues`.</span><span class="sxs-lookup"><span data-stu-id="6ec06-105">In this example, `LeagueList` is a collection of `Leagues`.</span></span> <span data-ttu-id="6ec06-106">Ciascuna `League` ha un `Name` e una raccolta di `Divisions`e ogni `Division` ha un nome e una raccolta di `Teams`.</span><span class="sxs-lookup"><span data-stu-id="6ec06-106">Each `League` has a `Name` and a collection of `Divisions`, and each `Division` has a name and a collection of `Teams`.</span></span> <span data-ttu-id="6ec06-107">Ogni `Team` ha un nome.</span><span class="sxs-lookup"><span data-stu-id="6ec06-107">Each `Team` has a team name.</span></span>  
  
 [!code-xaml[MasterDetail#HowTo1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto1)]  
[!code-xaml[MasterDetail#HowTo2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/MasterDetail/VisualBasic/Page1.xaml#howto2)]  
  
 <span data-ttu-id="6ec06-108">Lo screenshot seguente mostra l'esempio.</span><span class="sxs-lookup"><span data-stu-id="6ec06-108">The following is a screenshot of the example.</span></span> <span data-ttu-id="6ec06-109">Il `Divisions` <xref:System.Windows.Controls.ListBox> tiene automaticamente traccia delle selezioni nel `Leagues` <xref:System.Windows.Controls.ListBox> e visualizzare i dati corrispondenti.</span><span class="sxs-lookup"><span data-stu-id="6ec06-109">The `Divisions` <xref:System.Windows.Controls.ListBox> automatically tracks selections in the `Leagues` <xref:System.Windows.Controls.ListBox> and display the corresponding data.</span></span> <span data-ttu-id="6ec06-110">Il `Teams` <xref:System.Windows.Controls.ListBox> tiene traccia delle selezioni negli altri due <xref:System.Windows.Controls.ListBox> controlli.</span><span class="sxs-lookup"><span data-stu-id="6ec06-110">The `Teams` <xref:System.Windows.Controls.ListBox> tracks selections in the other two <xref:System.Windows.Controls.ListBox> controls.</span></span>  
  
 ![Screenshot che mostra un Master&#45;esempio di scenario di dettaglio.](./media/how-to-use-the-master-detail-pattern-with-hierarchical-data/databinding-master-detail-scenario.png)  
  
 <span data-ttu-id="6ec06-112">I due aspetti da notare in questo esempio sono:</span><span class="sxs-lookup"><span data-stu-id="6ec06-112">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="6ec06-113">I tre <xref:System.Windows.Controls.ListBox> associare i controlli alla stessa origine.</span><span class="sxs-lookup"><span data-stu-id="6ec06-113">The three <xref:System.Windows.Controls.ListBox> controls bind to the same source.</span></span> <span data-ttu-id="6ec06-114">Impostare il <xref:System.Windows.Data.Binding.Path%2A> proprietà dell'associazione per specificare il livello di dati di cui si vuole il <xref:System.Windows.Controls.ListBox> da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="6ec06-114">You set the <xref:System.Windows.Data.Binding.Path%2A> property of the binding to specify which level of data you want the <xref:System.Windows.Controls.ListBox> to display.</span></span>  
  
2. <span data-ttu-id="6ec06-115">È necessario impostare il <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> proprietà `true` nel <xref:System.Windows.Controls.ListBox> controlli di cui la selezione si esegue il monitoraggio.</span><span class="sxs-lookup"><span data-stu-id="6ec06-115">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` on the <xref:System.Windows.Controls.ListBox> controls of which the selection you are tracking.</span></span> <span data-ttu-id="6ec06-116">Impostazione di questa proprietà garantisce che l'elemento selezionato è sempre impostato come il <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="6ec06-116">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="6ec06-117">In alternativa, se il <xref:System.Windows.Controls.ListBox> Ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource>, selezione e la valuta viene sincronizzato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6ec06-117">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="6ec06-118">La tecnica è leggermente diversa quando si usa [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] dei dati.</span><span class="sxs-lookup"><span data-stu-id="6ec06-118">The technique is slightly different when you are using [!INCLUDE[TLA2#tla_xml](../../../../includes/tla2sharptla-xml-md.md)] data.</span></span> <span data-ttu-id="6ec06-119">Per un esempio, vedere [usare il modello Master-Details con dati XML gerarchici](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="6ec06-119">For an example, see [Use the Master-Detail Pattern with Hierarchical XML Data](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6ec06-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6ec06-120">See also</span></span>

- <xref:System.Windows.HierarchicalDataTemplate>
- [<span data-ttu-id="6ec06-121">Eseguire l'associazione a una raccolta e visualizzare informazioni in base alla selezione</span><span class="sxs-lookup"><span data-stu-id="6ec06-121">Bind to a Collection and Display Information Based on Selection</span></span>](how-to-bind-to-a-collection-and-display-information-based-on-selection.md)
- [<span data-ttu-id="6ec06-122">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="6ec06-122">Data Binding Overview</span></span>](data-binding-overview.md)
- [<span data-ttu-id="6ec06-123">Panoramica sui modelli di dati</span><span class="sxs-lookup"><span data-stu-id="6ec06-123">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="6ec06-124">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="6ec06-124">How-to Topics</span></span>](data-binding-how-to-topics.md)
