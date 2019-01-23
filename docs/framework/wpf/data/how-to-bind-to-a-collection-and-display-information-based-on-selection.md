---
title: "Procedura: Eseguire l'associazione a una raccolta e visualizzare informazioni in base alla selezione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data collections [WPF], selecting data for views
- data binding [WPF], creating views of data collections
- data binding [WPF], selecting data for views
- data binding [WPF], binding to collections
ms.assetid: 952a7d76-dd29-49e5-86f5-32c4530e70eb
ms.openlocfilehash: 549f4e7af1a9aa623c7f8ff12b528f771a8ff806
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504776"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="8e5b3-102">Procedura: Eseguire l'associazione a una raccolta e visualizzare informazioni in base alla selezione</span><span class="sxs-lookup"><span data-stu-id="8e5b3-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="8e5b3-103">In uno scenario master-dettagli semplice, è necessario con associazione a dati <xref:System.Windows.Controls.ItemsControl> , ad esempio un <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="8e5b3-104">È basato sulla selezione dell'utente, visualizzare altre informazioni sull'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="8e5b3-105">In questo esempio viene illustrato come implementare questo scenario.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8e5b3-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="8e5b3-106">Example</span></span>  
 <span data-ttu-id="8e5b3-107">In questo esempio `People` è un <xref:System.Collections.ObjectModel.ObservableCollection%601> di `Person` classi.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="8e5b3-108">Ciò `Person` classe contiene tre proprietà: `FirstName`, `LastName`, e `HomeTown`, tutti di tipo `string`.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="8e5b3-109">Il <xref:System.Windows.Controls.ContentControl> utilizza il seguente <xref:System.Windows.DataTemplate> che definisce come le informazioni di un `Person` viene presentato:</span><span class="sxs-lookup"><span data-stu-id="8e5b3-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="8e5b3-110">Di seguito è riportato uno screenshot del risultato dell'esempio.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="8e5b3-111">Il <xref:System.Windows.Controls.ContentControl> Mostra le altre proprietà della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="8e5b3-112">![Associazione a una raccolta](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="8e5b3-112">![Binding to a collection](../../../../docs/framework/wpf/data/media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="8e5b3-113">I due aspetti da notare in questo esempio sono:</span><span class="sxs-lookup"><span data-stu-id="8e5b3-113">The two things to notice in this example are:</span></span>  
  
1.  <span data-ttu-id="8e5b3-114">Il <xref:System.Windows.Controls.ListBox> e il <xref:System.Windows.Controls.ContentControl> associare alla stessa origine.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="8e5b3-115">Il <xref:System.Windows.Data.Binding.Path%2A> le proprietà di entrambe le associazioni non vengono specificate perché entrambi i controlli vengono associati all'intero oggetto collection.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2.  <span data-ttu-id="8e5b3-116">È necessario impostare il <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> proprietà `true` per il corretto funzionamento.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="8e5b3-117">Impostazione di questa proprietà garantisce che l'elemento selezionato è sempre impostato come il <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="8e5b3-118">In alternativa, se il <xref:System.Windows.Controls.ListBox> Ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource>, selezione e la valuta viene sincronizzato automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="8e5b3-119">Si noti che il `Person` classe esegue l'override di `ToString` metodo modo seguente.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="8e5b3-120">Per impostazione predefinita, il <xref:System.Windows.Controls.ListBox> chiamate `ToString` e visualizza una rappresentazione di stringa di ogni oggetto nella raccolta associata.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="8e5b3-121">Ecco perché ogni `Person` appare come un nome nel <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="8e5b3-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](../../../../samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="8e5b3-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8e5b3-122">See also</span></span>
- [<span data-ttu-id="8e5b3-123">Usare il modello Master-Details con dati gerarchici</span><span class="sxs-lookup"><span data-stu-id="8e5b3-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="8e5b3-124">Usare il modello Master-Details con dati XML gerarchici</span><span class="sxs-lookup"><span data-stu-id="8e5b3-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](../../../../docs/framework/wpf/data/how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="8e5b3-125">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="8e5b3-125">Data Binding Overview</span></span>](../../../../docs/framework/wpf/data/data-binding-overview.md)
- [<span data-ttu-id="8e5b3-126">Panoramica sui modelli di dati</span><span class="sxs-lookup"><span data-stu-id="8e5b3-126">Data Templating Overview</span></span>](../../../../docs/framework/wpf/data/data-templating-overview.md)
- [<span data-ttu-id="8e5b3-127">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="8e5b3-127">How-to Topics</span></span>](../../../../docs/framework/wpf/data/data-binding-how-to-topics.md)
