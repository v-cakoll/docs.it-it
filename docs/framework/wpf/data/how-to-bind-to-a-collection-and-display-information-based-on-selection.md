---
title: "Procedura: eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata"
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
ms.openlocfilehash: 032a1d98e1aa80ea755f5922f79d43a796e9697e
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459152"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="d6749-102">Procedura: eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata</span><span class="sxs-lookup"><span data-stu-id="d6749-102">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="d6749-103">In un semplice scenario Master-Details è presente una <xref:System.Windows.Controls.ItemsControl> associata a dati, ad esempio una <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="d6749-103">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="d6749-104">In base alla selezione dell'utente, vengono visualizzate altre informazioni sull'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="d6749-104">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="d6749-105">In questo esempio viene illustrato come implementare questo scenario.</span><span class="sxs-lookup"><span data-stu-id="d6749-105">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d6749-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="d6749-106">Example</span></span>  
 <span data-ttu-id="d6749-107">In questo esempio `People` è un <xref:System.Collections.ObjectModel.ObservableCollection%601> di classi di `Person`.</span><span class="sxs-lookup"><span data-stu-id="d6749-107">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="d6749-108">Questa classe `Person` contiene tre proprietà: `FirstName`, `LastName`e `HomeTown`, tutti di tipo `string`.</span><span class="sxs-lookup"><span data-stu-id="d6749-108">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="d6749-109">Il <xref:System.Windows.Controls.ContentControl> usa il <xref:System.Windows.DataTemplate> seguente che definisce la modalità di presentazione delle informazioni di un `Person`:</span><span class="sxs-lookup"><span data-stu-id="d6749-109">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="d6749-110">Di seguito è riportata una schermata dell'esempio prodotto dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="d6749-110">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="d6749-111">Il <xref:System.Windows.Controls.ContentControl> Mostra le altre proprietà della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="d6749-111">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="d6749-112">![Associazione a una raccolta](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="d6749-112">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="d6749-113">I due aspetti da notare in questo esempio sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d6749-113">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="d6749-114">Il <xref:System.Windows.Controls.ListBox> e il <xref:System.Windows.Controls.ContentControl> vengono associati alla stessa origine.</span><span class="sxs-lookup"><span data-stu-id="d6749-114">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="d6749-115">Le proprietà <xref:System.Windows.Data.Binding.Path%2A> di entrambe le associazioni non sono specificate perché entrambi i controlli sono associati all'intero oggetto Collection.</span><span class="sxs-lookup"><span data-stu-id="d6749-115">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="d6749-116">Per il corretto funzionamento di questo, è necessario impostare la proprietà <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> su `true`.</span><span class="sxs-lookup"><span data-stu-id="d6749-116">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="d6749-117">L'impostazione di questa proprietà garantisce che l'elemento selezionato sia sempre impostato come <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span><span class="sxs-lookup"><span data-stu-id="d6749-117">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="d6749-118">In alternativa, se il <xref:System.Windows.Controls.ListBox> ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource>, sincronizza automaticamente la selezione e la valuta.</span><span class="sxs-lookup"><span data-stu-id="d6749-118">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="d6749-119">Si noti che la classe `Person` esegue l'override del metodo `ToString` nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="d6749-119">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="d6749-120">Per impostazione predefinita, il <xref:System.Windows.Controls.ListBox> chiama `ToString` e visualizza una rappresentazione di stringa di ogni oggetto nella raccolta associata.</span><span class="sxs-lookup"><span data-stu-id="d6749-120">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="d6749-121">Per questo motivo ogni `Person` viene visualizzato come nome nel <xref:System.Windows.Controls.ListBox>.</span><span class="sxs-lookup"><span data-stu-id="d6749-121">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="d6749-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6749-122">See also</span></span>

- [<span data-ttu-id="d6749-123">Usare il modello Master-Details con dati gerarchici</span><span class="sxs-lookup"><span data-stu-id="d6749-123">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="d6749-124">Usare il modello Master-Details con dati XML gerarchici</span><span class="sxs-lookup"><span data-stu-id="d6749-124">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="d6749-125">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="d6749-125">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="d6749-126">Panoramica sui modelli di dati</span><span class="sxs-lookup"><span data-stu-id="d6749-126">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="d6749-127">Procedure relative alle proprietà</span><span class="sxs-lookup"><span data-stu-id="d6749-127">How-to Topics</span></span>](data-binding-how-to-topics.md)
