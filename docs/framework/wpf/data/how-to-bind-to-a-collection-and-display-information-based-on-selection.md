---
title: "Procedura: eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata"
description: Seguire questo esempio per scoprire come eseguire l'associazione a una raccolta e visualizzare le informazioni in base alla selezione nel Windows Presentation Foundation (WPF).
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
ms.openlocfilehash: fb8757ee6818a2812308a0a132fa9d06951ad52e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619611"
---
# <a name="how-to-bind-to-a-collection-and-display-information-based-on-selection"></a><span data-ttu-id="9ef64-103">Procedura: eseguire l'associazione di una raccolta e visualizzare informazioni in base alla selezione effettuata</span><span class="sxs-lookup"><span data-stu-id="9ef64-103">How to: Bind to a Collection and Display Information Based on Selection</span></span>
<span data-ttu-id="9ef64-104">In un semplice scenario Master-Details è presente un oggetto con associazione a dati, <xref:System.Windows.Controls.ItemsControl> ad esempio <xref:System.Windows.Controls.ListBox> .</span><span class="sxs-lookup"><span data-stu-id="9ef64-104">In a simple master-detail scenario, you have a data-bound <xref:System.Windows.Controls.ItemsControl> such as a <xref:System.Windows.Controls.ListBox>.</span></span> <span data-ttu-id="9ef64-105">In base alla selezione dell'utente, vengono visualizzate altre informazioni sull'elemento selezionato.</span><span class="sxs-lookup"><span data-stu-id="9ef64-105">Based on user selection, you display more information about the selected item.</span></span> <span data-ttu-id="9ef64-106">In questo esempio viene illustrato come implementare questo scenario.</span><span class="sxs-lookup"><span data-stu-id="9ef64-106">This example shows how to implement this scenario.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9ef64-107">Esempio</span><span class="sxs-lookup"><span data-stu-id="9ef64-107">Example</span></span>  
 <span data-ttu-id="9ef64-108">In questo esempio, `People` è un oggetto <xref:System.Collections.ObjectModel.ObservableCollection%601> di `Person` classi.</span><span class="sxs-lookup"><span data-stu-id="9ef64-108">In this example, `People` is an <xref:System.Collections.ObjectModel.ObservableCollection%601> of `Person` classes.</span></span> <span data-ttu-id="9ef64-109">Questa `Person` classe contiene tre proprietà: `FirstName` , `LastName` e `HomeTown` , tutti di tipo `string` .</span><span class="sxs-lookup"><span data-stu-id="9ef64-109">This `Person` class contains three properties: `FirstName`, `LastName`, and `HomeTown`, all of type `string`.</span></span>  
  
 [!code-xaml[CollectionBinding#Source](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#source)]  
[!code-xaml[CollectionBinding#UI](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#ui)]  
  
 <span data-ttu-id="9ef64-110">In <xref:System.Windows.Controls.ContentControl> viene utilizzato il codice seguente <xref:System.Windows.DataTemplate> che definisce la modalità di presentazione delle informazioni di un oggetto `Person` :</span><span class="sxs-lookup"><span data-stu-id="9ef64-110">The <xref:System.Windows.Controls.ContentControl> uses the following <xref:System.Windows.DataTemplate> that defines how the information of a `Person` is presented:</span></span>  
  
 [!code-xaml[CollectionBinding#DetailTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Window1.xaml#detailtemplate)]  
  
 <span data-ttu-id="9ef64-111">Di seguito è riportata una schermata dell'esempio prodotto dall'esempio.</span><span class="sxs-lookup"><span data-stu-id="9ef64-111">The following is a screenshot of what the example produces.</span></span> <span data-ttu-id="9ef64-112"><xref:System.Windows.Controls.ContentControl>Mostra le altre proprietà della persona selezionata.</span><span class="sxs-lookup"><span data-stu-id="9ef64-112">The <xref:System.Windows.Controls.ContentControl> shows the other properties of the person selected.</span></span>  
  
 <span data-ttu-id="9ef64-113">![Binding to a Collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span><span class="sxs-lookup"><span data-stu-id="9ef64-113">![Binding to a collection](./media/databinding-collectionbindingsample.png "DataBinding_CollectionBindingSample")</span></span>  
  
 <span data-ttu-id="9ef64-114">I due aspetti da notare in questo esempio sono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="9ef64-114">The two things to notice in this example are:</span></span>  
  
1. <span data-ttu-id="9ef64-115"><xref:System.Windows.Controls.ListBox>E <xref:System.Windows.Controls.ContentControl> si associano alla stessa origine.</span><span class="sxs-lookup"><span data-stu-id="9ef64-115">The <xref:System.Windows.Controls.ListBox> and the <xref:System.Windows.Controls.ContentControl> bind to the same source.</span></span> <span data-ttu-id="9ef64-116">Le <xref:System.Windows.Data.Binding.Path%2A> proprietà di entrambe le associazioni non sono specificate perché entrambi i controlli sono associati all'intero oggetto della raccolta.</span><span class="sxs-lookup"><span data-stu-id="9ef64-116">The <xref:System.Windows.Data.Binding.Path%2A> properties of both bindings are not specified because both controls are binding to the entire collection object.</span></span>  
  
2. <span data-ttu-id="9ef64-117">È necessario impostare la <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> proprietà su `true` affinché funzioni.</span><span class="sxs-lookup"><span data-stu-id="9ef64-117">You must set the <xref:System.Windows.Controls.Primitives.Selector.IsSynchronizedWithCurrentItem%2A> property to `true` for this to work.</span></span> <span data-ttu-id="9ef64-118">L'impostazione di questa proprietà garantisce che l'elemento selezionato sia sempre impostato come <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A> .</span><span class="sxs-lookup"><span data-stu-id="9ef64-118">Setting this property ensures that the selected item is always set as the <xref:System.Windows.Controls.ItemCollection.CurrentItem%2A>.</span></span> <span data-ttu-id="9ef64-119">In alternativa, se <xref:System.Windows.Controls.ListBox> ottiene i dati da un <xref:System.Windows.Data.CollectionViewSource> , sincronizza automaticamente la selezione e la valuta.</span><span class="sxs-lookup"><span data-stu-id="9ef64-119">Alternatively, if the <xref:System.Windows.Controls.ListBox> gets it data from a <xref:System.Windows.Data.CollectionViewSource>, it synchronizes selection and currency automatically.</span></span>  
  
 <span data-ttu-id="9ef64-120">Si noti che la `Person` classe esegue `ToString` l'override del metodo nel modo seguente.</span><span class="sxs-lookup"><span data-stu-id="9ef64-120">Note that the `Person` class overrides the `ToString` method the following way.</span></span> <span data-ttu-id="9ef64-121">Per impostazione predefinita, <xref:System.Windows.Controls.ListBox> chiama `ToString` e visualizza una rappresentazione di stringa di ogni oggetto nella raccolta associata.</span><span class="sxs-lookup"><span data-stu-id="9ef64-121">By default, the <xref:System.Windows.Controls.ListBox> calls `ToString` and displays a string representation of each object in the bound collection.</span></span> <span data-ttu-id="9ef64-122">Per questo motivo ogni `Person` viene visualizzato come nome in <xref:System.Windows.Controls.ListBox> .</span><span class="sxs-lookup"><span data-stu-id="9ef64-122">That is why each `Person` appears as a first name in the <xref:System.Windows.Controls.ListBox>.</span></span>  
  
 [!code-csharp[CollectionBinding#ToString](~/samples/snippets/csharp/VS_Snippets_Wpf/CollectionBinding/CSharp/Data.cs#tostring)]
 [!code-vb[CollectionBinding#ToString](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CollectionBinding/VisualBasic/Person.vb#tostring)]  
  
## <a name="see-also"></a><span data-ttu-id="9ef64-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ef64-123">See also</span></span>

- [<span data-ttu-id="9ef64-124">Usare il modello Master-Details con dati gerarchici</span><span class="sxs-lookup"><span data-stu-id="9ef64-124">Use the Master-Detail Pattern with Hierarchical Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-data.md)
- [<span data-ttu-id="9ef64-125">Usare il modello Master-Details con dati XML gerarchici</span><span class="sxs-lookup"><span data-stu-id="9ef64-125">Use the Master-Detail Pattern with Hierarchical XML Data</span></span>](how-to-use-the-master-detail-pattern-with-hierarchical-xml-data.md)
- [<span data-ttu-id="9ef64-126">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="9ef64-126">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="9ef64-127">Cenni preliminari sui modelli di dati</span><span class="sxs-lookup"><span data-stu-id="9ef64-127">Data Templating Overview</span></span>](data-templating-overview.md)
- [<span data-ttu-id="9ef64-128">Procedure</span><span class="sxs-lookup"><span data-stu-id="9ef64-128">How-to Topics</span></span>](data-binding-how-to-topics.md)
