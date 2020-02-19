---
title: 'Procedura: filtrare i dati in una visualizzazione'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- views [WPF], filtering data
- filtering data in views [WPF]
- data binding [WPF], filtering data in views
ms.assetid: c76e8606-4cc4-45a8-9110-e2ec66dc6afd
ms.openlocfilehash: f15bcfd1e3c4175f8b4b97244f120d5edbdec9b8
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77453078"
---
# <a name="how-to-filter-data-in-a-view"></a><span data-ttu-id="49ff7-102">Procedura: filtrare i dati in una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="49ff7-102">How to: Filter Data in a View</span></span>
<span data-ttu-id="49ff7-103">Questo esempio Mostra come filtrare i dati in una visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="49ff7-103">This example shows how to filter data in a view.</span></span>  
  
## <a name="example"></a><span data-ttu-id="49ff7-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="49ff7-104">Example</span></span>  
 <span data-ttu-id="49ff7-105">Per creare un filtro, definire un metodo che fornisca la logica di filtro.</span><span class="sxs-lookup"><span data-stu-id="49ff7-105">To create a filter, define a method that provides the filtering logic.</span></span> <span data-ttu-id="49ff7-106">Il metodo viene utilizzato come callback e accetta un parametro di tipo `object`.</span><span class="sxs-lookup"><span data-stu-id="49ff7-106">The method is used as a callback and accepts a parameter of type `object`.</span></span> <span data-ttu-id="49ff7-107">Il metodo seguente restituisce tutti gli oggetti `Order` con la proprietà `filled` impostata su "No", filtrando il resto degli oggetti.</span><span class="sxs-lookup"><span data-stu-id="49ff7-107">The following method returns all the `Order` objects with the `filled` property set to "No", filtering out the rest of the objects.</span></span>  
  
 [!code-csharp[SortFilter#2](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#2)]
 [!code-vb[SortFilter#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#2)]  
  
 <span data-ttu-id="49ff7-108">È quindi possibile applicare il filtro, come illustrato nell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="49ff7-108">You can then apply the filter, as shown in the following example.</span></span> <span data-ttu-id="49ff7-109">In questo esempio `myCollectionView` è un oggetto <xref:System.Windows.Data.ListCollectionView>.</span><span class="sxs-lookup"><span data-stu-id="49ff7-109">In this example, `myCollectionView` is a <xref:System.Windows.Data.ListCollectionView> object.</span></span>  
  
 [!code-csharp[SortFilter#Filter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#filter)]
 [!code-vb[SortFilter#Filter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#filter)]  
  
 <span data-ttu-id="49ff7-110">Per annullare l'applicazione di filtri, è possibile impostare la proprietà <xref:System.Windows.Data.CollectionView.Filter%2A> su `null`:</span><span class="sxs-lookup"><span data-stu-id="49ff7-110">To undo filtering, you can set the <xref:System.Windows.Data.CollectionView.Filter%2A> property to `null`:</span></span>  
  
 [!code-csharp[SortFilter#Unfilter](~/samples/snippets/csharp/VS_Snippets_Wpf/SortFilter/CSharp/Page1.xaml.cs#unfilter)]
 [!code-vb[SortFilter#Unfilter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SortFilter/VisualBasic/Page1.xaml.vb#unfilter)]  
  
 <span data-ttu-id="49ff7-111">Per informazioni su come creare o ottenere una vista, vedere [ottenere la visualizzazione predefinita di una raccolta di dati](how-to-get-the-default-view-of-a-data-collection.md).</span><span class="sxs-lookup"><span data-stu-id="49ff7-111">For information about how to create or obtain a view, see [Get the Default View of a Data Collection](how-to-get-the-default-view-of-a-data-collection.md).</span></span> <span data-ttu-id="49ff7-112">Per l'esempio completo, vedere [ordinamento e filtro degli elementi in un esempio di visualizzazione](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter).</span><span class="sxs-lookup"><span data-stu-id="49ff7-112">For the complete example, see [Sorting and Filtering Items in a View Sample](https://github.com/Microsoft/WPF-Samples/tree/master/Data%20Binding/SortFilter).</span></span>  
  
 <span data-ttu-id="49ff7-113">Se l'oggetto visualizzazione deriva da un oggetto <xref:System.Windows.Data.CollectionViewSource>, applicare la logica di filtro impostando un gestore eventi per l'evento <xref:System.Windows.Data.CollectionViewSource.Filter>.</span><span class="sxs-lookup"><span data-stu-id="49ff7-113">If your view object comes from a <xref:System.Windows.Data.CollectionViewSource> object, you apply filtering logic by setting an event handler for the <xref:System.Windows.Data.CollectionViewSource.Filter> event.</span></span> <span data-ttu-id="49ff7-114">Nell'esempio seguente `listingDataView` è un'istanza di <xref:System.Windows.Data.CollectionViewSource>.</span><span class="sxs-lookup"><span data-stu-id="49ff7-114">In the following example, `listingDataView` is an instance of <xref:System.Windows.Data.CollectionViewSource>.</span></span>  
  
 [!code-csharp[DataBindingLab#10](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#10)]
 [!code-vb[DataBindingLab#10](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#10)]  
  
 <span data-ttu-id="49ff7-115">Di seguito viene illustrata l'implementazione dell'esempio `ShowOnlyBargainsFilter` gestore dell'evento Filter.</span><span class="sxs-lookup"><span data-stu-id="49ff7-115">The following shows the implementation of the example `ShowOnlyBargainsFilter` filter event handler.</span></span> <span data-ttu-id="49ff7-116">Questo gestore eventi usa la proprietà <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> per filtrare gli oggetti `AuctionItem` con un `CurrentPrice` di $25 o superiore.</span><span class="sxs-lookup"><span data-stu-id="49ff7-116">This event handler uses the <xref:System.Windows.Data.FilterEventArgs.Accepted%2A> property to filter out `AuctionItem` objects that have a `CurrentPrice` of $25 or greater.</span></span>  
  
 [!code-csharp[DataBindingLab#5](~/samples/snippets/csharp/VS_Snippets_Wpf/DataBindingLab/CSharp/MainWindow.xaml.cs#5)]
 [!code-vb[DataBindingLab#5](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DataBindingLab/VisualBasic/MainWindow.xaml.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="49ff7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49ff7-117">See also</span></span>

- <xref:System.Windows.Data.CollectionView.CanFilter%2A>
- <xref:System.Windows.Data.BindingListCollectionView.CustomFilter%2A>
- [<span data-ttu-id="49ff7-118">Panoramica sul data binding</span><span class="sxs-lookup"><span data-stu-id="49ff7-118">Data Binding Overview</span></span>](../../../desktop-wpf/data/data-binding-overview.md)
- [<span data-ttu-id="49ff7-119">Ordinare i dati in una visualizzazione</span><span class="sxs-lookup"><span data-stu-id="49ff7-119">Sort Data in a View</span></span>](how-to-sort-data-in-a-view.md)
- [<span data-ttu-id="49ff7-120">Procedure relative alla struttura ad albero e alla serializzazione degli elementi</span><span class="sxs-lookup"><span data-stu-id="49ff7-120">How-to Topics</span></span>](data-binding-how-to-topics.md)
